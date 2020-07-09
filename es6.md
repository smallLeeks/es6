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
+ 合并对象：`const obj = { ...obj1, ...obj2 }`
+ 转换字符串为对象：`{ ..."hellow" }`
+ 转换数组为对象：`{ ...[1, 2] }`
+ 与对象解构赋值结合：`const { x, ...rest/spread } = { x: 1, y: 2, z: 3 }` 不能重复继承自身原型对象的属性
+ 修改现有对象部分属性：`const obj = { x：1, ...{ x: 2 } }`

##### 函数扩展
> 参数默认值：为函数参数指定默认值

+ 形式：`function func(x = 1, y = 2) {}`
+ 参数赋值：惰性求值（函数调用后才求值）
+ 参数位置：尾参数
+ 参数作用域：函数作用域
+ 声明方式：默认声明，不能用 `const` 和 `let` 再次声明
+ length：返回没有指定默认值的参数个数
+ 与解构赋值默认值结合：`function func({ x = 1, y = 2 } = {}) {}`
+ 应用
    + 指定某个参数不得省略，省略即抛出错误：`function func(x = throwMisssing()) {}`
    + 参数默认值设为 `undefined`，表明此参数可省略：`func(undefined, 1)`

> rest/spread参数（...）：返回函数多余参数

+ 形式：以数组的形式存在，之后不能再有其他参数
+ 作用：代替 `Arguments对象`
+ length：返回没有指定默认值的参数个数但不包括 `rest/spread参数`

> 严格模式：在严格条件下运行js

+ 应用：只要函数参数使用默认值、解构赋值、扩展运算符、那么函数内部就不能显示设定为严格模式

> name属性：返回函数的函数名：

+ 将匿名函数赋值给变量：`空字符串(es5)`、`变量名（es6）`
+ 将具名函数赋值给变量：`函数名（es5和es6）`
+ bind返回的函数：`bind 函数名（es5和es6）`
+ Function构造函数返回的函数实例：`anonymous（es5和es6）`

> 箭头函数（=>）：函数简写

+ 无参数：`() => {}`
+ 单个参数： `x => {}`
+ 多个参数：`(x, y) => {}`
+ 解构参数：`({x, y}) => {}`
+ 嵌套使用：部署管道机制
+ this指向固定化
    + 并非因为内部绑定 `this` 的机制，而是根本没有自己的 `this`，导致内部的 `this` 就是外层代码的 `this`
    + 因为没有 `this`，因此不能用作构造函数

> 尾调用优化：只保留内层函数的调用帧

+ 尾调用
    + 定义：某个函数的最后异步是调用另一个函数
    + 作用：只要使用尾部递归就不会发生栈溢出，相对节省内存
    + 实现：把所有用到的内部变量改写成函数的参数并使用参数默认值

> 箭头函数误区

+ 函数体内的 `this` 是 `定义时所在的对象` 而不是 `使用时所在的对象`
+ 可让 `this` 指向固定化，这种特性很有利于封装回调函数
+ 不可当作 `构造函数`，因此箭头函数不可使用 `new`
+ 不可使用 `yeild` 命令，因此箭头函数不能用作 `Genweator函数`
+ 不可使用 `Arguments` 对象，此对象在函数体内不存在（可用 `rest/spread参数` 代替）
+ 返回对象时必须在对象外面加上括号

##### 正则扩展

+ 变更RegExp构造函数入参：允许首参数为 `正则对象`，尾参数为 `正则修饰符` ( `返回的正则表达式会忽略原正则表达式的修饰符` )

+ 正则方法调用变更：字符串对象的 `match()`，`replace()`，`search()`，`split()` 内部调用转为调用 `RegExp` 实例对应的 `RegExp.prototype[symbol.方法]`

+ u修饰符：Unicode模式修饰符，正确处理大于 `\uFFF` 的 `Unicode字符`

+ `点字符（.）`
+ `Unicode表示法`
+ `量词`
+ `预定义模式`
+ `i修饰符`
+ `转义`

+ y修饰符：粘连修饰符，确保匹配必须从剩余的第一个位置开始全局匹配（与 `g修饰符` 作用类似）
+ unicode：是否设置 `u修饰符`
+ sticky：是否设置 `y修饰符`
+ flags：返回正则表达式的修饰符

> 重点难点

+ `y修饰符` 隐含头部匹配标志
+ 单单一个 `y修饰符` 对 `match()` 只能返回第一个匹配，必须与 `g修饰符` 联用才能返回所有匹配

##### Symbol

##### Set

##### Map

##### Proxy

+ 定义：修改某些操作的默认行为
+ 声明：`const proxy = new Proxy(target, handler)`
+ 入参：
    + target：拦截的目标对象
    + handler：定制拦截行为
+ 方法：
    + Proxy.revocable()：返回可取消的Proxy实例（返回 `{ proxy, revoke} `，通过revoke()取消代理 ）
+ 拦截方式
    + get()：拦截对象属性读取
    + set()：拦截对象属性设置，返回布尔值
    + has()：拦截对象属性检查 `key in obj`，返回布尔值
    + deleteProperty()：拦截对象属性删除 `delete obj[k]`，返回布尔值
    + defineProperty()：拦截对象属性定义 `Object.defineProperty()` 、Object.defineProperties()，返回布尔值
    + ownKeys()：拦截对象属性遍历 `for-in`、`Object.keys()`、`Object.getOwnPropertyNames()`、`Object.getOwnpropertySymbols()`，返回数组
    + getOwnpropertyDescriptor()：拦截对象属性描述读取Object.getOwnPropertyDescriptor，返回对象
    + 

##### reflect

##### Class

##### Module

##### Iterator

##### Promise

+ 定义：包含异步操作结果的对象
+ 状态
    + 进行中：`pending`
    + 已成功：`resolved`
    + 已失败：`rejected`
+ 特点：
    + 对象的状态不受外界的影响
    + 一旦状态改变就不会再变，任何时候都可以得到这个结果
+ 声明：`new Promise((resolve, reject) => {})`
+ 出参
    + resolve：将状态从 `未完成` 变为 `成功`，在异步操作成功时调用，并将异步操作的结果作为参数传递出去
    + reject: 状态将从 `未完成` 变为 `失败`，在异步操作失败时调用，并将异步操作的错误作为参数传递出去
+ 方法
    + then()：分别指定 `resolved状态` 和 `rejected状态` 的回调函数
        + 第一参数：状态变为 `resolved` 时调用
        + 第二参数：状态变为 `rehected` 时调用（可选）
    + catch()：指定发生错误时的回调函数
    + Promise.all()：将多个实例包装成一个新实例，返回全部实例状态变更后的结果数组（齐变更再返回）
        + 入参：具有 `Iterator接口` 的数据结构
        + 成功：只有全部实例状态变成 `fulfilled`，最终状态才变成 `fulfilled`
        + 失败：其中一个实例状态变成 `rejected`，最终状态就会变成 `rejected`
    + promise.race()：将多个实例包装成一个新实例，返回全部实例状态优先变更后的结果（先变更先返回）
        + 入参：具有 `Iterator接口` 的数据结构
        + 成功失败：哪个实例率先改变状态就返回哪个实例的状态
    + Promise.resolve()：将对象转为Promise对象(等价于 `new Promise(resolve => resolve())` )
        + Promise实例：原封不动的返回入参
        + Thenable对象：将此对象转为Promise对象并返回（Thenable为包含 `then()` 的对象，执行 `then()` 相当于执行此对象的 `then()`）
        + 不具有 `then()` 的对象：将此对象转为Promise对象并返回，状态为 `resolved`
        + 不带参数：返回Promise对象，状态为 `resolved`
    + Promise.reject()：将对象转为状态为 `rejected` 的Promise对象（等价于 `new Promise((resolve, reject) => reject())`）

> 应用场景

+ 加载图片
+ AJAX转为Promise对象

> 重点难点

+ 只有异步操作的结果可决定当前状态是哪一种，其他操作都无法改变这个状态
+ 状态只有两种可能：从 `pending` 变为 `resolved`、从 `pending` 变为 `rejected`
+ 一旦新建 `Promise对象` 就会立即执行，无法中途取消
+ 不设置回调函数，内部抛错不会反应到外部
+ 当处于 `pending` 时，无法得知目前进展到哪一个阶段
+ 实例状态变为 `resolved` 或 `rejected` 时，会触发 `then()` 绑定的回调函数
+ `resolve()` 和 `reject()` 的执行总是晚于本轮循环的同步任务
+ `then()` 返回新实例，其后可再调用另一个 `then()`
+ `then()` 运行抛出错误会被 `catch()` 捕获
+ 实例状态已变成 `resolved` 时，再抛出错误是无效的，不会被捕获，等于没有输出
+ 实例状态的错误具有 `冒泡` 性质，会一直向后传递直到被捕获为止，错误总是会被下一个 `catch()` 捕获
+ 不要在 `then()` 里面定义 `rejected` 状态的回调函数（不要使用其第二参数）
+ 建议使用 `catch()` 捕获错误，不要使用 `then()` 第二个参数捕获
+ 没有使用 `catch()` 捕获错误，实例抛错不会传递到外层代码，即 `不会有任何反应`
+ 作为参数的实例定义了 `catch()`，一旦被 `rejected` 并不会触发 `Promise.all()` 的 `catch()`
+ `Promise.reject()` 参数会原封不动地作为 `rejected` 的理由，变成后续方法的参数

##### Generator