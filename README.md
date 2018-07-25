### 代码缩进

* 4个空格

### 分号

* 除代码块外的语句末尾都加分号

*不推荐*

```js
let baz = { a: 1 }
function foo() { return true };
if (foo) { bar = 0 };
```

*推荐*

```js
let baz = { a: 1 };
function foo() { return true; }
if (foo) { bar = 0; }
```

### 命名
#### 变量名/属性名

* 驼峰式 name / firstName / lastName 
* 标志型的体现标志 isLoading / hasLoaded
* 全局变量命名语义化，尽量详细 globalCityName

#### 函数名/方法名

* 驼峰式 goIndex
* 体现功能  getValue / setValue / sortResult

#### 样式名

* 下划线 mod_info
* 体现层级关系 city / city_name

#### 组件名/类名

* 首字母大写 Order
* 驼峰式 OrderList / OrderDetail

#### 文件名

* 中划线 order.js / order-list.js / order-detail.js
* 体现功能 order-reducer.js / order-action.js

### 空行
#### 代码块之间空行

* 方法与方法之间空行
* import与class之间空行

#### 拖尾换行

* 文件末尾留一空行

*在非空文件中，存在拖尾换行是一个常见的 UNIX 风格，它的好处是可以方便在串联和追加文件时不会打断 Shell 的提示。在日常的项目中，保留拖尾换行的好处是，可以减少版本控制时的代码冲突。*

### 空格

#### 操作符空格

* 操作符前后都需要添加空格

*不推荐*

```js
let sum=1+2;
```

*推荐*

```js
let sum = 1 + 2;
```

#### 关键字空格

* 关键字后面加空格

*不推荐*

```js
if(condition) { }
```

*推荐*

```js
if (condition) { }
```

#### 行末空格

* 行末不留空格

*不推荐*

```js
let a = 1;   
```

*推荐*

```js
let a = 1;
```

#### 函数命名/调用空格

* 函数声明与调用相同：参数左小括号前不加空格，右小括号后加空格

*不推荐*

```js
function func () {
  // do something
}
func ()
```

*推荐*

```js
function func() {
  // do something
}
func()
```

#### 逗号，冒号，分号空格

* 后面使用空格，前面不加空格
*注意行末不留空格*

*不推荐*

```js
[1,2,3]
let baz = { a:1 };
for (let a = 1;a <= 10;a++) { }
```

*推荐*

```js
[1, 2, 3]
let baz = { a: 1 };
for (let a = 1; a <= 10; a++) { }
```

#### 单行代码块空格

* 在单行代码块中使用空格，左花括号后与右花括号前空格

*不推荐*

```js
function foo() {return true;}
if (foo) {bar = 0}
```

*推荐*

```js
function foo() { return true; }
if (foo) { bar = 0 }
```

#### 圆括号空格

* 圆括号间不留空格

*不推荐*

```js
getName( name );
```

*推荐*

```js
getName(name);
```

#### 注释首尾空格

* 注释首尾留空格

*不推荐*

```js
//comment
/*comment*/
```

*推荐*

```js
// comment
/* comment */
```

#### 空格个数

* 除了缩进，不要使用多个空格。

*不推荐*

```js
const id =    1234;
```

*推荐*

```js
const id = 1234;
```

#### 无子元素组件闭合

* 使用单标签

*不推荐*

```html
<View></View>
```

*推荐*

```html
<View />
```

### 字符串

* 单引号
* 拼接变量统一ES6模板字符串

### 顺序

#### 函数内代码区域排序

* const/let/var
* 代码块内变量需提前声明

#### 模块js文件代码区域排序

* import
* const/let/global
* Class
* export

#### React生命周期方法与其他方法顺序问题

```js
constructor() { }
componentWillMount() { }
render() { }
componentDidMount() { }
componentWillReceiveProps() { }
shouldComponentUpdate() { }
componentWillUpdate() { }
componentDidUpdate() { }
componentWillUnmount() { }
// 其他方法...
```

### 目录结构

#### 非公共模块

不同模块的组件文件、样式文件、图片使用相同的目录存储

#### 公共模块

每个模块使用自己独立的组件目录、样式目录、图片目录（便于移植）

### 换行问题

* 一行代码字符过多时酌情换行处理（不要出现横向滚动条？）

### 温馨提示

* 短路操作符 `&&` `||` 在特定情境下需要转换为布尔值，否则可能会报错

```js
{!!length && <View />}
```

* 条件语句内合理使用隐式转换
禁止 a == false / a == null / a == 0 / a == '' / a == undefined