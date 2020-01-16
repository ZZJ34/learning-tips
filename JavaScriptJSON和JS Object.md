#### JavaScript:JSON和JS Object

**JSON（JavaScript Object Notation）**仅仅是一种数据格式（或者叫数据形式）。数据格式其实就是一种规范，按照这种规范来存诸和交换数据。就好像 XML 格式一样。

| 区别     | Json                                                         | Javascript对象                                          |
| :------- | :----------------------------------------------------------- | :------------------------------------------------------ |
| 含义     | 仅仅是一种数据格式                                           | 对象的实例                                              |
| 传输     | 可以跨平台数据传输，速度快                                   | 不能传输                                                |
| 表现     | 1. 键值对 2. 键必须加双引号 3. 值不能为方法函数/undefined/NaN | 1.键值对 2.值可以是函数、对象、字符串、数字、boolean 等 |
| 相互转换 | Json → JS 对象： 1. `var obj = JSON.parse(jsonstring);` 2. `var obj = eval("("+jsonstring+")");` | JS 对象 → Json： `JSON.stringify(obj);`                 |

```
var obj1 = {}; // 这只是 JS 对象

// 可把这个称做：JSON 格式的 JavaScript 对象 
var obj2 = {"width":100,"height":200,"name":"rose"};

// 可把这个称做：JSON 格式的字符串
var str1 = '{"width":100,"height":200,"name":"rose"}';

// 这个可叫 JSON 格式的数组，是 JSON 的稍复杂一点的形式
var arr = [
    {"width":100,"height":200,"name":"rose"},
    {"width":100,"height":200,"name":"rose"},
    {"width":100,"height":200,"name":"rose"},
];
        
// 这个可叫稍复杂一点的 JSON 格式的字符串     
var str2='['+
    '{"width":100,"height":200,"name":"rose"},'+
    '{"width":100,"height":200,"name":"rose"},'+
    '{"width":100,"height":200,"name":"rose"},'+
']';
```

在.js文件中创建的都是JS Object不是JSON。

但 JSON 和 JavaScript 确实存在渊源，JSON 本身的意思就是 JavaScript 对象表示法（JavaScript Object Notation），可以说这种数据格式是从 JavaScript 对象中演变出来的。**JSON 语法是 JavaScript 对象表示法语法的子集**。

JSON 格式的数据，主要是为了跨平台交流数据用的。JSON 独立于语言和平台，JSON 解析器和 JSON 库支持许多不同的编程语言。