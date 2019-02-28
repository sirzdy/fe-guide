<!-- # 前端代码规范 -->
## 规范概述


规范的制定是我们长期以来对工作的积累与沉淀的产物，帮助我们更快、更好、更高效的完成繁重、复杂、多样化的任务，我们制作规范的主要目的在于：

* 降低每个组员介入项目的门槛成本；
* 提高工作效率及协同开发的便捷性；
* 高度统一的代码风格。

## 书写格式

### 缩进层级

* 4个空格
* switch 语句中的 case/default 子句的缩进级别为1 (4个空格)

*不推荐*
```javascript
switch (a) {
case 'a':
break;
case 'b':
break;
}
```

*推荐*
```javascript
switch (a) {
    case 'a':
        break;
    case 'b':
        break;
}
```

### 分号

* 语句末尾始终使用分号，不要依赖于引擎隐式插入（Automatic Semicolon Insertion，ASI）。
* 代码块外的语句末尾不加分号。`function` `for` `if` `switch` `try` `while`语句块末尾不需要加分号。

*不推荐*
```javascript
let baz = { a: 1 }
function foo() {
    return true
}
if (foo) { 
    bar = 0;
};
```

*推荐*
```javascript
let baz = { a: 1 };
function foo() {
    return true;
}
if (foo) {
    bar = 0;
}
```

### 空行

#### 代码块之间空行

* 方法与方法之间空行
* `import`与`class`之间空行
* 建议: 把不同业务逻辑的语句使用空行隔开，更易阅读

#### 拖尾换行

* 文件末尾留一空行

*在非空文件中，存在拖尾换行是一个常见的 UNIX 风格，它的好处是可以方便在串联和追加文件时不会打断 Shell 的提示。在日常的项目中，保留拖尾换行的好处是，可以减少版本控制时的代码冲突。*

### 空格

#### 操作符空格

* 操作符前后都需要添加空格

*不推荐*

```javascript
let sum=1+2
```

*推荐*
```javascript
let sum = 1 + 2
```

#### 关键字空格

* 关键字后面加空格 `if` `else` `switch` `case` `for` `while`

*不推荐*
```javascript
if(condition) { ... }
```

*推荐*
```javascript
if (condition) { ... }
```

#### 行末空格

* 行末不留空格

*不推荐*
```javascript
let a = 1;   
```

*推荐*
```javascript
let a = 1;
```

#### 函数命名/调用空格

* 函数声明：参数左小括号前不加空格，右小括号后加空格
* 函数调用：参数左小括号前不加空格

*不推荐*
```javascript
function func () {
// do something
}
func ()
```

*推荐*
```javascript
function func() {
// do something
}
func()
```

#### 逗号，冒号，分号空格

* 后面使用空格，前面不加空格
*注意行末不留空格*

*不推荐*
```javascript
[1,2,3]
let baz = { a:1 }
for (let a = 1;a <= 10;a++) { }
```

*推荐*

```javascript
[1, 2, 3]
let baz = { a: 1 }
for (let a = 1; a <= 10; a++) { }
```

#### 单行代码块空格

* 在单行代码块中使用空格，左花括号后与右花括号前空格

*不推荐*
```javascript
function foo() {return true;}
if (foo) {bar = 0}
```

*推荐*

```javascript
function foo() { return true; }
if (foo) { bar = 0 }
```

#### 圆括号空格

* 圆括号间不留空格

*不推荐*

```javascript
getName( name );
```

*推荐*

```javascript
getName(name);
```

#### 注释首尾空格

* 注释首尾留空格

*不推荐*

```javascript
//comment
/*comment*/
```

*推荐*

```javascript
// comment
/* comment */
```

#### 空格个数

* 除了缩进，不要使用多个空格。

*不推荐*

```javascript
const id =    1234;
```

*推荐*


```javascript
const id = 1234;
```

### 字符串

* 单引号
* 拼接变量统一ES6模板字符串

## 命名

### 文件名

* 中划线 order.js / order-list.js / order-detail.js
* 体现功能 order-reducer.js / order-action.js

### 变量名/属性名

* 驼峰式 `name` `firstName` `lastName` 
* 标志型的体现标志 `isLoading` `hasLoaded`
* 全局变量命名语义化，尽量详细 `globalCityName`

### 常量名

* 全部用大写字母，多个单词使用下划线 _ 连接 `PI` `MAX_COUNT`

### 样式名

* 下划线 `mod_info`
* 体现层级关系 `city` `city_name`

### 组件名/类名

* 首字母大写 `Order`
* 驼峰式 `OrderList` `OrderDetail`

### 函数名/方法名

* 驼峰式 `goIndex`
* 体现功能，动词  `getValue` `setValue` `sortResult`


## 项目与文件

### 目录结构

#### React Native 项目

**一般而言,公共模块使用自己独立的组件目录、样式目录、图片目录（便于移植）；非公共模块可以按照模块分，也可以按照页面样式图片分**

【示例：非公共模块按照模块分，仅供参考】

```
jsbundles
├─ JDReactWorldOfTomorrow
│    ├─ common
│    │    ├─ img
│    │    │    ├─ pic.png
│    │    │    ├─ pic@2x.png
│    │    │    └─ pic@3x.png
│    │    ├─ img.js
│    │    ├─ style.js
│    │    ├─ enum.js
│    │    ├─ fetch.js
│    │    └─ utils.js
│    ├─ components
│    │    ├─ loading
│    │    │    ├─ img
│    │    │    │    ├─ prefix-pic-suffix.png
│    │    │    │    ├─ prefix-pic-suffix@2x.png
│    │    │    │    └─ prefix-pic-suffix@3x.png
│    │    │    ├─ style
│    │    │    │    └─ index.js
│    │    │    ├─ index.js
│    │    │    └─ README.md
│    ├─ pages
│    │    ├─ order
│    │    │    ├─ img
│    │    │    │    ├─ prefix-pic-suffix.png
│    │    │    │    ├─ prefix-pic-suffix@2x.png
│    │    │    │    └─ prefix-pic-suffix@3x.png
│    │    │    ├─ style
│    │    │    │    ├─ header.js
│    │    │    │    ├─ body.js
│    │    │    │    ├─ footer.js
│    │    │    │    └─ index.js
│    │    │    ├─ header.js
│    │    │    ├─ body.js
│    │    │    ├─ footer.js
│    │    │    ├─ index.js
│    │    │    └─ README.md
│    ├─ reducers
│    │    ├─ root-reducer.js
│    │    └─ index.js
│    ├─ router.js
│    └─ app.js
├─ JDReactWorldOfTomorrow.js
├─ JDReactWorldOfTomorrow.version
└─ JDReactWorldOfTomorrow.web.js
```
### 换行问题

* 一行代码字符过多时酌情换行处理（不要出现横向滚动条）

### 书写顺序

#### 函数内代码区域排序

* const/let/var
* 就近声明，用时声明，更自然的在视角范围内。*为什么？ 当函数行数较多时，如果把变量声明全部放在顶部，阅读或修改时还需要滚动到顶部，甚为不便。*

#### 模块js文件代码区域排序

* import
* const/let/global (此项按实际应用来，亦可以定在Class之后，一般而言redux与img部分置后)
* Class
* export


#### React生命周期方法与其他方法顺序问题

##### 旧版本 16.3之前

书写顺序

```javascript
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

##### 新版本 16.3及之后

[生命周期官方文档](https://reactjs.org/docs/react-component.htm)
[生命周期更新博客](https://reactjs.org/blog/2018/03/29/react-v-16-3.html)

生命周期顺序

```javascript
// Mounting
constructor(props)
static getDerivedStateFromProps(props, state)
render()
componentDidMount()

// Updating
static getDerivedStateFromProps(props, state)
shouldComponentUpdate(nextProps, nextState)
render()
getSnapshotBeforeUpdate(prevProps, prevState)
componentDidUpdate(prevProps, prevState, snapshot)

// Unmounting
componentWillUnmount()

// Error Handling
static getDerivedStateFromError(error)
componentDidCatch(error, info)
```

书写顺序

```javascript
constructor(props)
static getDerivedStateFromProps(props, state)
render()
componentDidMount()
shouldComponentUpdate(nextProps, nextState)
getSnapshotBeforeUpdate(prevProps, prevState)
componentDidUpdate(prevProps, prevState, snapshot)
componentWillUnmount()
static getDerivedStateFromError(error)
componentDidCatch(error, info)
// 其他方法...
```

### 温馨提示

* 短路操作符 `&&` `||` 在特定情境下需要转换为布尔值，否则可能会报错（rn 0.45.1有问题，0.55.4没问题）正确使用方式`{!!length && <View />}`
