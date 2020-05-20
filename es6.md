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
    - `const命令` 和 `let命令` 只能在代码块中执行

- 赋值使用
    - `const命令` 声明常量后必须马上赋值
    - `let命令` 声明变量后可立马赋值或使用变量

- 声明方法 `var`、`cosnt`、`let`、`function`、`class`、`import`

> 重点

+ 不允许重复声明
+ 未定义就使用会报错：`const命令` 和 `let命令` 不存在变量的提升
+ 暂时性死区：代码快内使用 `const命令` 或 `let命令` 声明变量之前，该变量都不可用

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

##### 字符串扩展
+ Unicode表示法：`大括号包含` 表示Unicode字符（`\u{0xXX}` 或 `\u{0XX}`）
+ 字符串遍历：可通过 `for-of` 遍历字符串
+ 字符串模板：可单行、多行、变量的增强版字符串
+ 标签模板：函数参数的特殊调用
+ String.raw()：返回把字符串所有变量替换且对斜杠进行转义
+ String.fromCodePoint()：返回码点对应的字符
+ codePointAt()：返回字符串对应码点（`String.fromCodePoint()` 的逆操作）
+ normalize()：把字符串的不同表示方法统一为同样形式，返回 `新字符串` (Ubicode正规化)
+ repeat()：把字符串重复n次，返回 `新字符`
+ match()：返回正则表达式在字符串的所有匹配
+ includes()：是否存在指定字符串
+ startsWith()：是否存在字符串头部指定字符串
+ endsWith()：是否存在字符串尾部指定字符串
+ padStr()：把指定字符串填充到字符串头部，返回新字符串
+ padEnd()：把指定字符串填充到字符串尾部，返回新字符串
+ 直接输入U+2018和U+2019：字符串可直接输入 `行分割符` 和 `段分隔符`
+ trimStart()：消除字符串头部空格，返回新字符串
+ trimEnd()：消除字符串尾部空格，返回新字符串

> 重点

+ 以上扩展方法均可作用于由 `4个字节存储` 的 `Unicode字符` 上

##### 数值扩展

- 二进制表示法：`0b或0B开头` 表示二进制（`0bXX` 或 `0BXX`）
- 八进制表示法：`0o或0O开头` 表示八进制（`0oXX` 或 `0OXX`）
- Number.EPSILON：数值最小精度
- Number.min_SAFE_INTEGER：最小安全数值（-2^53）
- Number.MAX_SAFE_INTEGER：最大安全数值（2^53）
- Number.parseInt()：返回转换值得整数部分
- Number.parseFloat()：返回转换值得浮点数部分
- Number.isFinite()：是否为有限数值
- Number.isInteger()：是否为整数
- Number.isSafeInteger()：是否数值在安全返回内
- Math.trunc()：返回数值整数部分
- Math.sign()：返回数值类型（正数1、负数-1、零0）
- Math.cbrt()：返回数值立方根
- Math.clz32：返回数值的32位单精度浮点数形式
- Math.imul()：返回两个数值相乘
- Math.fround()：返回数值的32位单精度浮点数形式
- Math.hypot()：返回所有数值平方和的平方根
- Math.expm1()：返回 `e^n - 1`
- Math.log1p()：返回 `1 + n` 的自然数对数（`Math.log(1 + n)`）
- Math.log10()：返回10为底的n的对数
- Math.log2()：返回以2为底的n的对数
- Math.sinh()：返回n的双曲正弦
- Math.cosh()：返回n的双曲余弦
- Math.tanh()：返回n的双曲正切
- Math.asinh()：返回n的反双曲正弦
- Math.acosh()：返回n的反双曲余弦
- Math.atanh()：返回n的反双曲正切
- 指数幂运算符（**）：数值求幂（相当于Math.pow()）

##### 数组扩展

+ 扩展运算符：转换数组为逗号分隔的参数系列（`[...arr]`，相当于 `reset/spead` 参数的逆运算）
+ Array.from()：转化具有 `Iterator接口` 的数据结构为真正的数组，返回新的数组
    + 类数组对象：`包含length的对象`、`Aguments对象`、`NodeList对象` 
    + 可遍历对象：`Sting`、`Set`、`Map`、`Generator函数`
+ Array.of()：转换一组值为真正数组，返回新数组
+ copyWithin()：把指定位置的成员复制到其他位置，返回原数组
+ find()：返回第一个符合条件的成员
+ findIndex()：返回第一个符合条件的乘员索引值
+ some()：对数组的每一项都运行给定的函数，如果该函数任意一项都返回 `true`，则返回 `true`
+ every()：对数组的每一项都运行给定的函数，如果该函数每一项都返回 `true`，则返回 `true`
+ map()：返回一个新的数组
+ filter()：返回所有符合条件的成员
+ fill()：根据指定值填充整个数组。返回原数组
+ keys()：返回以索引值为遍历器的对象
+ values(): 返回以属性值为遍历器的对象
+ entries()：返回以索引值和属性值为遍历器的对象
+ 数组空位：ES6明确将数组空位转为 `undefined（空位处理规则不一，建议避免出现）`
+ includes()：是否存在指定成员

> 扩展应用

* 克隆数组：`const arr = [...arr]`
* 合并数组：`const arr = [...arr1, ...arr2]`
* 拼接数组：`arr.push(...arr1)`
* 代替apply：`Math.apply(null, [x, y]) => Math.max(...[x, y])`
* 转换字符串为数组：`[...'hellow']`
* 转换可遍历对象为数组：`[...Arguments, ...NodeList]`
* 转换可遍历对象为数组：`[...String, ...Set, ...Map, ...Generator]`
* 与数组解构赋值结合：`const [x, ...rest/spread] = [1, 2, 3]`
* 计算Unicode字符长度：`Array.from('hellow).length => [...'hellow'].length`

> 重点

- 使用 `keys`、`values`、`entries` 返回的遍历器对象，可用 `for-of` 自动遍历或 `next()` 手动遍历

##### 对象扩展

+ 简介表示发：直接写入变量和函数作为对象的属性和方法（`{ props, method() {} }`）
+ 属性名表达式：字面量定义对象时使用 `[]` 定义键（`[prop]`，不能与上同时使用）
+ 方法的name属性：返回方法函数名
    + 取值函数（getter）和存值函数（setter）：`get/set函数名` (属性的描述对象在 `get` 和 `set` 上)
    + bind返回的函数：`bound函数名`
    + Function构造函数返回的函数实例：`anonymous`
+ 属性的可枚举性和遍历：描述对象的 `enumerable`
+ super关键字：指向当前对象的原型对象（只能用在对象的简写方法中 `methos() {}`）
+ `Object.is()`：对比两值是否相当（类似 `===`，但 `Object.is(NaN, NaN)` 为 `false`）
+ Object.assign()：合并对象（浅拷贝），返回原对象
+ Object.getPrototypeOf()：返回对象的原型对象
+ Object.setPrototypeOf()：设置对象的原型对象
+ `__proto__`：返回或设置最想的原型对象
+ Object.getOwnPropertyDescriptors()：返回对象所有自身属性（非继承属性）的描述对象
+ Object.values()：返回以数值组成的对象
+ Object.entries()：返回以键和值组成的数组
+ 扩展运算符：转换对象为用逗号分隔的参数序列（`{ ...obj }`，相当于 `rest/spread` 参数的逆运算）
+ Object.fromEntries()：返回以键和值组成的对象（`Object.entries()` 的逆操作）
+ 链判断操作符（?.）：是否存在对象属性（不存在返回 `undefined` 且不再往下执行）
    + 对象属性：`obj?prop`、`obj?.[expr]`
    + 函数调用：func?.(...args)
+ 空判断操作符（??）：是否值为 `undefined` 或 `null`，是则使用默认值

> 属性遍历

+ 描述：`自身`、`可继承`、`可枚举`、`非枚举`、`Symbol`
+ 遍历：
    + `for-in`：遍历对象 `自身可继承可枚举` 属性
    + `Object.keys()`：返回对象 `自身可枚举` 属性键组成的数组
    + `Object.getOwnPropertyNames()`：返回对象 `非自身Symbol` 属性键组成的数组
    + `Object.getOwnPropertySymbols()`；返回对象 `自身Symbol` 属性键组成的数组
    + `Reflect.ownKeys()`：返回对象 `自身全部` 属性键组成的数组
+ 规则：
    + 首先遍历所有数值键，按照数值升序排列
    + 其次遍历所有字符串键，按照加入时间升序排列
    + 最后遍历所有Symbol键，按照加入时间升序排列

> 扩展应用

+ 克隆对象：`const obj = { __proto__: Object.getPrototypeOf(obj1), ...obj1 }`
+ 合并对象：`const obj = { ..obj1, ...obj2 }`
+ 转换字符串为对象：`{ ..."hellow" }`
+ 转换数组为对象：`{ ...[1, 2] }`
+ 与对象解构赋值结合：`const { x, ...rest/spread } = { x: 1, y: 2, z: 3 }` 不能重复继承自身原型对象的属性
+ 修改现有对象部分属性：`const obj = { x：1, ...{ x: 2 } }`

##### 函数扩展

##### 正则扩展

##### Symbol

##### Set

##### Map

##### Proxy

##### reflect

##### Class

##### Module

##### Iterator

##### Promise

##### Generator