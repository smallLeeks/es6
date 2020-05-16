## ES6

##### 声明

> const命令：声明常量
> let命令：声明变量


> 作用

- 作用域
    - 全局作用域
    - 函数作用域
    - 块级作用域

- 作用范围
    - `var命令` 在全局代码中执行
    - `const命令和let命令` 只能在代码块中执行

- 赋值使用
    - `const命令` 声明常量后必须马上赋值
    - `let命令` 声明变量后可立马赋值或使用变量

- 声明方法 `var`、`cosnt`、`let`、`function`、`class`、`import`


> 重点

+ 不允许重复声明
+ 未定义就使用会报错：`const命令`和`let命令`不存在变量的提升
+ 暂时性死区：代码快内使用`const命令`或`let命令`声明变量之前，该变量都不可用

##### 解构赋值
+ 字符串解构：`const { a, b, b, d, e } = "hellow"`
+ 数值解构：`const { toString: a } = 0123456`
+ 布尔解构： `const { toSring: a } = false`
+ 对象解构：
    + 形式：`const { x, y } = { x: 1, y: 2 }`
    + 默认：`const { x, y = 2 } = { x: 1 }`
    + 改名：`const { x, y: z } = { x: 1, y: 2 }`
+ 数组解构：
    + 规则：数组结构具有 `Iterator接口` 可采用数组的形式的解构赋值
    + 形式：`const [x, y] = [1, 2]`
    + 改名：`const [x, y = 2] = [1]`
+ 函数参数解构：
    + 数组解构：`([x = 0, y = 1]) => {}`
    + 对象解构：`({x = 0, y = 1}) => {}`

> 应用场景

* 交换变量值：`[x, y] = [y, x]`
* 返回函数多个值：`const [x, y, z] = ()`
* 定义函数参数：`([1, 2])`
* 提取JSON数据：`const { name, id, data: { sort } } = json`
* 定义函数参数默认值：`({ x = 1, y = 2 } = {}) => {}`
* 遍历Map结构：`for (cosnt [key, value] of Map) {}`
* 输入模块指定属性和方法：`const { readFile, writeFile } = require('fs')`

> 重点

- 匹配模式：
- 解构赋值规则：
- 解构默认值生效条件：
- 解构遵循匹配模式
- 解构不成功时变量的值等于 `undefined`
- `undefined` 和 `null` 无法转为对象，因此无法进行解构

