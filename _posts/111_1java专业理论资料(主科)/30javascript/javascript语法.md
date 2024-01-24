## javascript 将 string 转为 json


// JSON 字符串
var jsonString = '{"key": "value", "number": 42, "boolean": true, "array": [1, 2, 3]}';

// 将 JSON 字符串解析为 JSON 对象
var jsonObject = JSON.parse(jsonString);

// 输出 JSON 对象
console.log(jsonObject);

## idea 如何 将 一个 json 粘贴为 string

首先将换行符转为空格. 然后将字符粘贴在idea中, 则会生成一个合法的json字符串.
