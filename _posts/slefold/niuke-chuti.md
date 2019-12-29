---
layout: post
title: niuke出题
tags: study
categories: dailystudy
---

今天学到了什么题目？since 20191109<br>

## 2019-11-09-CPP
- include 
    ```
    执行Main.cpp会输出什么？
    文件EndBrace.h:
    }
    文件Main.cpp:
    #include <iostream>
    int main() {
        int a = 2, b = 3;
        int result = a * b;
        std::cout << result << std::endl;
    #include "EndBrace.h"
    \\ ouput: 6
    ```
    
- empalce
    - 考点：vector的长度不够时resize会复制一次 & push_back会在Main中生成一次然后复制到目标vector中 
    ```
    如下代码会输出什么？
    struct Vertex
    {
        float x, y, z;

        Vertex(float x, float y, float z) : x(x), y(y), z(z)
        {
        }

        Vertex(const Vertex& vertex) : x(vertex.x), y(vertex.y), z(vertex.z)
        {
            std::cout << "copied!" << std::endl;
        }
    };

    int main()
    {
        std::vector<Vertex> vertices;
        vertices.push_back({ 1,2,3 });
        vertices.push_back({ 4,5,6 });
        vertices.push_back({ 7,8,9 });
        std::cin.get();
        return 0;
        ////output:
        ////copied!
        ////copied!
        ////copied!
        ////copied!
        ////copied!
        ////copied!

        //case2:
        //std::vector<Vertex> vertices(3); 
        ////output:编译错误：没有合适的默认构造函数可用	
        
        //case3:
        //std::vector<Vertex> vertices;
        //vertices.reserve(3);
        //vertices.push_back({ 1,2,3 });
        //vertices.push_back({ 4,5,6 });
        //vertices.push_back({ 7,8,9 });
        //std::cin.get();
        //return 0;
        ////output:
        ////copied!
        ////copied!
        ////copied!

        //case4:
        //std::vector<Vertex> vertices;
        //vertices.reserve(3);
        //vertices.emplace_back(1, 2, 3);
        //vertices.emplace_back(4, 5, 6);
        //vertices.emplace_back(7, 8, 9);
        //std::cin.get();
        //return 0;
        //// output: nothing
    }    
    ```