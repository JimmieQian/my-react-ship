# 前言Ⅰ(React简介)

ReactJS 是 Facebook 推出的 JavaScript 函式庫.它的的目标是: `Learn once, write everywhere` .它的特点主要可以归纳为以下几点:
* 组件化开发(Component)
* 虚拟 DOM (Virtual DOM)
* 一律重绘（Always Redraw）
* JSX(声明式UI Declarative UI)
* 单向数据流（Unidirectional Data Flow）
* 在 JavaScript 里写 CSS：Inline Style

## 组件化开发(Component)
![Alt text](./img/component_view.png)

在 React 中最基本的单元为组件（Component），每個组件也可以包含一个以上的子组件，并依照需求组成一个组合式的（Composable）组件.
具有 `封裝（encapsulation）` 、 `注重分离 (Separation of Concerns)`、`可复用 (Reuse)` 、`易于维护` 等特点
react中的两类组件
1. 状态组件 `stateless components` 继承自 `React.Component`,有状态的改变和自己的生命周期
```javascript
//  采用es6+ 的语法规则来编写
// es5 使用 React.createClass 来创建组件
class MyComponent extends React.Component {
    // render 是组件的必要方法
    render() {
        return (
            <div>Hello, World!</div>
        );
    }
}

// 将 <MyComponent /> 插入 DOM 节点
ReactDOM.render(<MyComponent/>, document.getElementById('app'));
```
2. 非状态组件 `Functional Component` ,没有状态,ref 和 生命周期
(资源消耗小于 状态组件 , 所以能用 非状态组件 尽量使用)
```javascript
// 可操作props,打不可操作state
// 要有return UI元素
// 可能出现 this 等问题
function MyComponent() {
    return  <div>Hello, World!</div>;
}

// 使用 arrow function,让 UI 更单纯，減少副作用（side effect）
// 建议使用
const MyComponent = () => (
    <div>Hello, World!</div>;
);

ReactDOM.render(<MyComponent/>, document.getElementById('app'));
```

## JSX(声明式UI Declarative UI)
为了使开发者能够在定义UI 语法时更顺手，Fackbook 为了React 提供了一种看起来很像是XML 的JavaScript 语法扩充─ JSX.
JSX并不是一个新的语言，他更像是一种帮助开发体验的语法糖衣。经由像是Babel这样的转码器，JSX会被编译成原生JavaScript程式码，才能够在浏览器上顺利运作.
让组件的使用方式,就像HTML的标签一样使用. `十分方便.也更易于理解.`
```javascript
// 如上诉的 MyComponent 组件的使用
<MyComponent />
```

## 虚拟 DOM (Virtual DOM)
DOM 操作的效能成本非常的高，React 为了解决开发者在手动操作DOM 时可能造成的效能低落或失误，建立了一套虚拟DOM（Virtual DOM，以下简称VDOM）的机制，程式记忆体中将有一份对应真正DOM 的VDOM 物件，以代管UI 储存的资料与逻辑。当一个UI 因为资料改变而需要进行画面变动的时候，React 会根据新的UI 状态重绘一份新的VDOM Tree，并且与变动前的旧VDOM Tree 以高效率的Diff 演算法进行比对，然后其中的差异才会真正的由React 自动帮你更新到实际的DOM 上，反应出画面的变更。

透过VDOM 的机制，开发者将不必烦恼如何操作DOM，而可以专心于撰写UI 的定义与互动逻辑。并且由于React 能够自动去最佳化的处理DOM 操作，前端UI 程式将可以有效的降低操作成本而达到优秀的效能。

## 一律重绘（Always Redraw）
React 对于View 与Model 之间采用了的是单向资料流，也是说所有UI 的呈现都要依照Model 目前的内容而绘制出来，当Model 改变时，UI 应当跟着改变。

**一律重新绘制」不是指重绘整个画面真正的DOM，而是一旦Model资料发生改变，React会在程式记忆体中根据最新的Model资料重新建立一份全新的VDOM.**

这样不能影响性能,这正是Virtual DOM 的作用,react的魅力所在.

## 单向数据流（Unidirectional Data Flow
React 应用的核心设计模式，数据流向自顶向下. 它不是硬性要求使用的. 但是想要更好的管理react应用.单向数据流无疑是很好的操作方式. 目前主要有官方推荐的单向流模式 flux及其扩展 redux等.

## 在 JavaScript 里写 CSS：Inline Style
将css样式,直接写在 `.jsx` 文件中
```javascript
const myStyle = {
  color: 'red',
};

const MyComponent = () => (
    <div style = {myStyle}>Hello, World!</div>;
);
```

## 参考文章
1. [ReactJS 与 Component 设计入门介绍][1]
2. [精益 React 学习指南 （Lean React）- 1.1 React 介绍][2]


  [1]: https://github.com/carlleton/reactjs101/tree/zh-CN/Ch03
  [2]: https://segmentfault.com/a/1190000005140569