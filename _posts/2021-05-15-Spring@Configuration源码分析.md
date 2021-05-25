---
layout: post
title: spring @Configuration源码分析
tags: java spring
categories: java
---

### 前言：@Configuration类和其他类不同的关键判断

- ```java
  /**
   * Check the given metadata for a configuration class candidate
   * (or nested component class declared within a configuration/component class).
   * @param metadata the metadata of the annotated class
   * @return {@code true} if the given class is to be registered as a
   * reflection-detected bean definition; {@code false} otherwise
   */
  public static boolean isConfigurationCandidate(AnnotationMetadata metadata) {
     return (isFullConfigurationCandidate(metadata) || isLiteConfigurationCandidate(metadata));
  }
  ```

- full Configutaion class 指带有@code @configuration的类

  ```java
  /** 
   * Check the given metadata for a full configuration class candidate
   * (i.e. a class annotated with {@code @Configuration}).
   * @param metadata the metadata of the annotated class
   * @return {@code true} if the given class is to be processed as a full
   * configuration class, including cross-method call interception
   */
  public static boolean isFullConfigurationCandidate(AnnotationMetadata metadata) {
     return metadata.isAnnotated(Configuration.class.getName());
  }
  ```
  
- lite Configuration 指带有@Component,@ComponentScan, @Import, @ImportResource的类

```java
	/**
	 * Determine whether the given bean definition indicates a lite {@code @Configuration}
	 * class, through checking {@link #checkConfigurationClassCandidate}'s metadata marker.
	 */
	public static boolean isLiteConfigurationClass(BeanDefinition beanDef) {
		return CONFIGURATION_CLASS_LITE.equals(beanDef.getAttribute(CONFIGURATION_CLASS_ATTRIBUTE));
	}
	
    static {
		candidateIndicators.add(Component.class.getName());
		candidateIndicators.add(ComponentScan.class.getName());
		candidateIndicators.add(Import.class.getName());
		candidateIndicators.add(ImportResource.class.getName());
	}
```

- 如果类上有candidateIndicators这个Set中定义的注解的话（@Component，@ComponentScan，@Import，@ImportResource）那么就是一个简化配置类，如果不是上面两种情况，那么有@Bean注解修饰的方法也是简化配置类。

## 相关概念

### beanDefinition

bean的定义，它存储着一个bean对象需要的各种信息，如class信息、beanName、作用范围scope等信息，那么为什么要有这个定义呢？spring是扫描class字节码文件加载类的，在启动时扫描一次，之后我们要通过getBean获取一个bean，要判断这个bean是否懒加载，是否单例等等，那么这时候就不能再去解析了，因为在启动时就扫描解析过一次了，所以在第一次扫描解析会把bean的各种信息保存用来创建bean，这就是beanDefinition的作用。

### beanDefinitionReader

beanDefinition的读取器，用于注册beanDefinition， 提供了注册、获取资源加载器、获取类加载器、beanname生成、加载beanDefinition等接口。

### **BanDefinitionRegistry**

是定义一个BeanDefinition注册器的接口,具体的BeanDefinition就是通过这个接口注册进spring容器中的

### BeanPostProcessor

bean的后置处理器，可以在**创建每个Bean的过程中进行干涉**，如在bean的实例化前或后，修改bean，或者做一些处理，如aop

### BeanFactoryPostProcessor

bean工厂的后置处理器，可以对beanFactory继续设置，比如修改beanFactory的属性，增加xml方式注入的忽略接口等。BeanFactoryPostProcessor的作用。允许修改spring容器中Bean的定义，也就是修改BeanDefinition。

### FactoryBean

它和beanFactory不一样，首先factoryBean可以注册成为一个bean，而它的子类更是添加了获取bean工厂的接口，如`AbstractFactoryBean`，继承子类你就有了bean工厂的功能。

理解的话，有点像工厂模式，用于生产某个bean的，它的getObject方法只调用一次。

### beanFactory

beanFactory有**存放bean，生成bean**的功能，但它只是一个接口，spring中最核心的是`DefaultListableBeanFactory`，它是beanFactory最底层的类，获取beanDefinition、注册beanDefinition、别名功能、bean注册、获取bean、自动装配功能等等。

因为**启动spring就是创建beanFactory，然后扫描bean的定义，拿到beanFactory，创建bean，再通过beanFactory拿到bean**。

![](../img/20210515-Spring@Bean%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90.asserts/image-20210515151624917.png)

### 模板模式

一个抽象类公开定义了执行它的方法的方式/模板。它的子类可以按需要重写方法实现,但调用将以抽象类中定义的方式进行。

### spring源码之 @Configuration 配置类处理 与 CGLIB代理

结论：**Spring将被@Configuration注解的配置类定义为full configuration, 而将没有被@Configuration注解的配置类定义为lite configuration。full configuration能重定向从跨方法的引用，从而保证@Configuration代码中的bean是一个单例.**

1. 当一个类上面加了注解 @Configuration 时候，初始化ApplicationContext 的时候， invokeBeanDefinitionRegistryPostProcessors 方法解析此类

   ```
   refresh()     模板方法，创建一个spring的上下文，产生Bean definitions
   invokeBeanFactoryPostProcessors()     实例化所有注册为BeanFactoryPostProcessor的Bean
   invokeBeanDefinitionRegistryPostProcessors(postProcess,registry)  首先调用bfr的后置处理器 
   invokeBeanFactoryPostProcessors(postProcessors,beanFactory), 这里调用所有bf的后置处理器，此时会调用BeanDefinitionRegistryPostProcessor接口，该接口只有ConfigurationClassPostProcessor一个默认实现类，使用这个postProcessor类的postProcessBeanFactory方法会调用enhanceConfigurationClass()方法
   ```
   
   ![image-20210515175739813](https://github.com/yukia-yuqin/blog/blob/master/img/20210515-Spring@Bean%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90.asserts/image-20210515175739813.png)
   
   ![image-20210515175528043](../img/20210515-Spring@Bean%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90.asserts/image-20210515175528043.png)
   
2. 调用到enhanceConfigurationClass() ，此方法获取registry里面的所有类，遍历判断实例化的bean是否是有@configuration注解，如果有则存到一个map中，为lite则不存，若map为null ，则返回之后直接new 对象；若map 不为null，则去完成cglib代理的实现。

   ```
   static void invokeBeanFactoryPostProcessors(postProcessors, beanfactory)
   postProcessBeanFactory(beanFactory)  load所有的bean，但是不实例化它们。通过用CGLIB-enhance的子类准备好配置类，从而提供bean。
   enhanceConfigurationClasses(beanFactory);  遍历full configuration的BD,
   configBeanDefs.put(beanName, (AbstractBeanDefinition) beanDef);  存到一个map中。
   ```

   ![image-20210515180237571](https://github.com/yukia-yuqin/blog/blob/master/img/20210515-Spring@Bean%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90.asserts/image-20210515180237571.png)

3. `cglib`代理的实现：调用`enhance()` ，判断该类是否实现`EnhancedConfiguration` ，完成代理则会让该类去实现此接口；若没有被代理则去实现代理 `enhancer.create()`创建代码对象。**BeanMethodInterceptor会根据方法名去IOC找到Bean并返回。**

   ```
   enhancer.enhance(configClass, this.beanClassLoader);
   newEnhancer()中有BeanMethodInterceptor()方法来增强@Configuration类，BeanMethodInterceptor会根据方法名去IOC找到Bean并返回。
   ```
   
   ![image-20210515181633163](../img/20210515-Spring@Bean%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90.asserts/image-20210515181633163.png)

![image-20210515190029647](../img/20210515-Spring@Bean%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90.asserts/image-20210515190029647.png)

- 调用bf的后置处理器的流程

```java
public static void invokeBeanFactoryPostProcessors(
        ConfigurableListableBeanFactory beanFactory, List<BeanFactoryPostProcessor> beanFactoryPostProcessors) {
 
    // Invoke BeanDefinitionRegistryPostProcessors first, if any.
    Set<String> processedBeans = new HashSet<String>();
 
    // 1.判断beanFactory是否为BeanDefinitionRegistry，beanFactory为DefaultListableBeanFactory,
    // 而DefaultListableBeanFactory实现了BeanDefinitionRegistry接口，因此这边为true
    if (beanFactory instanceof BeanDefinitionRegistry) {
        BeanDefinitionRegistry registry = (BeanDefinitionRegistry) beanFactory;
        // 用于存放普通的BeanFactoryPostProcessor
        List<BeanFactoryPostProcessor> regularPostProcessors = new LinkedList<BeanFactoryPostProcessor>();
        // 用于存放BeanDefinitionRegistryPostProcessor
        List<BeanDefinitionRegistryPostProcessor> registryProcessors = new LinkedList<BeanDefinitionRegistryPostProcessor>();
 
        // 2.首先处理入参中的beanFactoryPostProcessors
        // 遍历所有的beanFactoryPostProcessors, 将BeanDefinitionRegistryPostProcessor和普通BeanFactoryPostProcessor区分开
        for (BeanFactoryPostProcessor postProcessor : beanFactoryPostProcessors) {
            if (postProcessor instanceof BeanDefinitionRegistryPostProcessor) {
                // 2.1 如果是BeanDefinitionRegistryPostProcessor
                BeanDefinitionRegistryPostProcessor registryProcessor =
                        (BeanDefinitionRegistryPostProcessor) postProcessor;
                // 2.1.1 直接执行BeanDefinitionRegistryPostProcessor接口的postProcessBeanDefinitionRegistry方法 [这个方法可以加入更多的bean definition]
                registryProcessor.postProcessBeanDefinitionRegistry(registry);
                // 2.1.2 添加到registryProcessors(用于最后执行postProcessBeanFactory方法)
                registryProcessors.add(registryProcessor);
            } else {
                // 2.2 否则，只是普通的BeanFactoryPostProcessor
                // 2.2.1 添加到regularPostProcessors(用于最后执行postProcessBeanFactory方法)
                regularPostProcessors.add(postProcessor);
            }
        }
 
        // Do not initialize FactoryBeans here: We need to leave all regular beans
        // uninitialized to let the bean factory post-processors apply to them!
        // Separate between BeanDefinitionRegistryPostProcessors that implement
        // PriorityOrdered, Ordered, and the rest.
        // 用于保存本次要执行的BeanDefinitionRegistryPostProcessor
        List<BeanDefinitionRegistryPostProcessor> currentRegistryProcessors = new ArrayList<BeanDefinitionRegistryPostProcessor>();
 
        // First, invoke the BeanDefinitionRegistryPostProcessors that implement PriorityOrdered.
        // 3.调用所有实现PriorityOrdered接口的BeanDefinitionRegistryPostProcessor实现类
        // 3.1 找出所有实现BeanDefinitionRegistryPostProcessor接口的Bean的beanName
        String[] postProcessorNames =
                beanFactory.getBeanNamesForType(BeanDefinitionRegistryPostProcessor.class, true, false);
        // 3.2 遍历postProcessorNames
        for (String ppName : postProcessorNames) {
            // 3.3 校验是否实现了PriorityOrdered接口
            if (beanFactory.isTypeMatch(ppName, PriorityOrdered.class)) {
                // 3.4 获取ppName对应的bean实例, 添加到currentRegistryProcessors中,
                // beanFactory.getBean: 这边getBean方法会触发创建ppName对应的bean对象, 目前暂不深入解析
                currentRegistryProcessors.add(beanFactory.getBean(ppName, BeanDefinitionRegistryPostProcessor.class));
                // 3.5 将要被执行的加入processedBeans，避免后续重复执行
                processedBeans.add(ppName);
            }
        }
        // 3.6 进行排序(根据是否实现PriorityOrdered、Ordered接口和order值来排序)
        sortPostProcessors(currentRegistryProcessors, beanFactory);
        // 3.7 添加到registryProcessors(用于最后执行postProcessBeanFactory方法)
        registryProcessors.addAll(currentRegistryProcessors);
        // 3.8 遍历currentRegistryProcessors, 执行postProcessBeanDefinitionRegistry方法
        invokeBeanDefinitionRegistryPostProcessors(currentRegistryProcessors, registry);
        // 3.9 执行完毕后, 清空currentRegistryProcessors
        currentRegistryProcessors.clear();
 
        // Next, invoke the BeanDefinitionRegistryPostProcessors that implement Ordered.
        // 4.调用所有实现了Ordered接口的BeanDefinitionRegistryPostProcessor实现类（过程跟上面的步骤3基本一样）
        // 4.1 找出所有实现BeanDefinitionRegistryPostProcessor接口的类, 这边重复查找是因为执行完上面的BeanDefinitionRegistryPostProcessor,
        // 可能会新增了其他的BeanDefinitionRegistryPostProcessor, 因此需要重新查找
        postProcessorNames = beanFactory.getBeanNamesForType(BeanDefinitionRegistryPostProcessor.class, true, false);
        for (String ppName : postProcessorNames) {
            // 校验是否实现了Ordered接口，并且还未执行过
            if (!processedBeans.contains(ppName) && beanFactory.isTypeMatch(ppName, Ordered.class)) {
                currentRegistryProcessors.add(beanFactory.getBean(ppName, BeanDefinitionRegistryPostProcessor.class));
                processedBeans.add(ppName);
            }
        }
        sortPostProcessors(currentRegistryProcessors, beanFactory);
        registryProcessors.addAll(currentRegistryProcessors);
        // 4.2 遍历currentRegistryProcessors, 执行postProcessBeanDefinitionRegistry方法
        invokeBeanDefinitionRegistryPostProcessors(currentRegistryProcessors, registry);
        currentRegistryProcessors.clear();
 
        // Finally, invoke all other BeanDefinitionRegistryPostProcessors until no further ones appear.
        // 5.最后, 调用所有剩下的BeanDefinitionRegistryPostProcessors
        boolean reiterate = true;
        while (reiterate) {
            reiterate = false;
            // 5.1 找出所有实现BeanDefinitionRegistryPostProcessor接口的类
            postProcessorNames = beanFactory.getBeanNamesForType(BeanDefinitionRegistryPostProcessor.class, true, false);
            for (String ppName : postProcessorNames) {
                // 5.2 跳过已经执行过的
                if (!processedBeans.contains(ppName)) {
                    currentRegistryProcessors.add(beanFactory.getBean(ppName, BeanDefinitionRegistryPostProcessor.class));
                    processedBeans.add(ppName);
                    // 5.3 如果有BeanDefinitionRegistryPostProcessor被执行, 则有可能会产生新的BeanDefinitionRegistryPostProcessor,
                    // 因此这边将reiterate赋值为true, 代表需要再循环查找一次
                    reiterate = true;
                }
            }
            sortPostProcessors(currentRegistryProcessors, beanFactory);
            registryProcessors.addAll(currentRegistryProcessors);
            // 5.4 遍历currentRegistryProcessors, 执行postProcessBeanDefinitionRegistry方法
            invokeBeanDefinitionRegistryPostProcessors(currentRegistryProcessors, registry);
            currentRegistryProcessors.clear();
        }
 
        // Now, invoke the postProcessBeanFactory callback of all processors handled so far.
        // 6.调用所有BeanDefinitionRegistryPostProcessor的postProcessBeanFactory方法(BeanDefinitionRegistryPostProcessor继承自BeanFactoryPostProcessor)
        invokeBeanFactoryPostProcessors(registryProcessors, beanFactory);
        // 7.最后, 调用入参beanFactoryPostProcessors中的普通BeanFactoryPostProcessor的postProcessBeanFactory方法
        invokeBeanFactoryPostProcessors(regularPostProcessors, beanFactory);
    } else {
        // Invoke factory processors registered with the context instance.
        invokeBeanFactoryPostProcessors(beanFactoryPostProcessors, beanFactory);
    }
 
    // 到这里 , 入参beanFactoryPostProcessors和容器中的所有BeanDefinitionRegistryPostProcessor已经全部处理完毕,
    // 下面开始处理容器中的所有BeanFactoryPostProcessor
 
    // Do not initialize FactoryBeans here: We need to leave all regular beans
    // uninitialized to let the bean factory post-processors apply to them!
    // 8.找出所有实现BeanFactoryPostProcessor接口的类
    String[] postProcessorNames =
            beanFactory.getBeanNamesForType(BeanFactoryPostProcessor.class, true, false);
 
    // Separate between BeanFactoryPostProcessors that implement PriorityOrdered,
    // Ordered, and the rest.
    // 用于存放实现了PriorityOrdered接口的BeanFactoryPostProcessor
    List<BeanFactoryPostProcessor> priorityOrderedPostProcessors = new ArrayList<BeanFactoryPostProcessor>();
    // 用于存放实现了Ordered接口的BeanFactoryPostProcessor的beanName
    List<String> orderedPostProcessorNames = new ArrayList<String>();
    // 用于存放普通BeanFactoryPostProcessor的beanName
    List<String> nonOrderedPostProcessorNames = new ArrayList<String>();
    // 8.1 遍历postProcessorNames, 将BeanFactoryPostProcessor按实现PriorityOrdered、实现Ordered接口、普通三种区分开
    for (String ppName : postProcessorNames) {
        // 8.2 跳过已经执行过的
        if (processedBeans.contains(ppName)) {
            // skip - already processed in first phase above
        } else if (beanFactory.isTypeMatch(ppName, PriorityOrdered.class)) {
            // 8.3 添加实现了PriorityOrdered接口的BeanFactoryPostProcessor
            priorityOrderedPostProcessors.add(beanFactory.getBean(ppName, BeanFactoryPostProcessor.class));
        } else if (beanFactory.isTypeMatch(ppName, Ordered.class)) {
            // 8.4 添加实现了Ordered接口的BeanFactoryPostProcessor的beanName
            orderedPostProcessorNames.add(ppName);
        } else {
            // 8.5 添加剩下的普通BeanFactoryPostProcessor的beanName
            nonOrderedPostProcessorNames.add(ppName);
        }
    }
 
    // First, invoke the BeanFactoryPostProcessors that implement PriorityOrdered.
    // 9.调用所有实现PriorityOrdered接口的BeanFactoryPostProcessor
    // 9.1 对priorityOrderedPostProcessors排序
    sortPostProcessors(priorityOrderedPostProcessors, beanFactory);
    // 9.2 遍历priorityOrderedPostProcessors, 执行postProcessBeanFactory方法
    invokeBeanFactoryPostProcessors(priorityOrderedPostProcessors, beanFactory);
 
    // Next, invoke the BeanFactoryPostProcessors that implement Ordered.
    // 10.调用所有实现Ordered接口的BeanFactoryPostProcessor
    List<BeanFactoryPostProcessor> orderedPostProcessors = new ArrayList<BeanFactoryPostProcessor>();
    for (String postProcessorName : orderedPostProcessorNames) {
        // 10.1 获取postProcessorName对应的bean实例, 添加到orderedPostProcessors, 准备执行
        orderedPostProcessors.add(beanFactory.getBean(postProcessorName, BeanFactoryPostProcessor.class));
    }
    // 10.2 对orderedPostProcessors排序
    sortPostProcessors(orderedPostProcessors, beanFactory);
    // 10.3 遍历orderedPostProcessors, 执行postProcessBeanFactory方法
    invokeBeanFactoryPostProcessors(orderedPostProcessors, beanFactory);
 
    // Finally, invoke all other BeanFactoryPostProcessors.
    // 11.调用所有剩下的BeanFactoryPostProcessor
    List<BeanFactoryPostProcessor> nonOrderedPostProcessors = new ArrayList<BeanFactoryPostProcessor>();
    for (String postProcessorName : nonOrderedPostProcessorNames) {
        // 11.1 获取postProcessorName对应的bean实例, 添加到nonOrderedPostProcessors, 准备执行
        nonOrderedPostProcessors.add(beanFactory.getBean(postProcessorName, BeanFactoryPostProcessor.class));
    }
    // 11.2 遍历nonOrderedPostProcessors, 执行postProcessBeanFactory方法
    invokeBeanFactoryPostProcessors(nonOrderedPostProcessors, beanFactory);
 
    // Clear cached merged bean definitions since the post-processors might have
    // modified the original metadata, e.g. replacing placeholders in values...
    // 12.清除元数据缓存（mergedBeanDefinitions、allBeanNamesByType、singletonBeanNamesByType），
    // 因为后处理器可能已经修改了原始元数据，例如， 替换值中的占位符...
    beanFactory.clearMetadataCache();
}
```





[spring源码篇（二）核心概念熟悉] https://cloud.tencent.com/developer/article/1804977

[cglib 源码]： http://cglib.sourceforge.net/xref/index.html

[Spring注解@Configuration与cglib代理增强配置类]：https://blog.csdn.net/qq_35004494/article/details/102725522

[@Configuration简介]：https://www.cnblogs.com/think-in-java/p/11876997.html

[很棒的参考 Spring IoC源码学习：invokeBeanFactoryPostProcessors 详解]:https://blog.csdn.net/v123411739/article/details/87741251

[为什么增强之后才是单例]：https://www.jianshu.com/p/0822470c1b85?utm_campaign=shakespeare&utm_content=note&utm_medium=seo_notes&utm_source=recommendation

如果不增强的情况下，@Bean方法A希望在创建A的过程中调用@Bean方法B作为自身属性，那么必然是一个new的新对象B，无法保证单例B的存在，所以cglib后就是为了增加额外的判断保证单例

