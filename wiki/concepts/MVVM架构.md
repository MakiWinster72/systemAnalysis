---
sources: [summaries/18.2.3网页应用开发环境.md]
brief: MVVM是一种通过ViewModel层和数据绑定实现视图与模型解耦的架构模式，是MVC/MVP的演进。
---

# MVVM架构模式

## 定义

**MVVM（Model-View-ViewModel）** 是一种软件架构模式，在[[MVC架构]]和[[MVP架构]]的基础上发展而来。该架构通过引入ViewModel层和数据绑定、响应式编程思想，进一步解耦视图和模型，使每个组件的职责更加清晰明确。

## 架构演进

MVVM是软件设计模式的逐步演化发展的结果：

```
MVC → MVP → MVVM
```

### 与MVP的关系

- [[MVP架构]]隔离了M与V的直接联系，靠Presenter中转
- MVP中P直接调用View的接口（showData、showLoading等）来实现对视图的操作
- M与V已经隔离，方便测试，但代码还不够优雅简洁
- **MVVM弥补了这些缺陷**，实现了更优雅简洁的代码结构

## 核心组件

以[[Vue.js]]框架为例，MVVM架构包含以下四个核心组件：

### 1. Observer（数据监听器）

- 能够对数据对象的所有属性进行监听
- 如有变动可拿到最新值并通知订阅者
- 内部采用ES5的Object.defineProperty的getter和setter来实现

### 2. Compile（指令解析器）

- 解析v-for、v-if等指令
- 对每个元素节点的指令进行扫描和解析
- 根据指令模板替换数据，绑定相应的更新函数

### 3. Watcher（订阅者）

- 作为连接Observer和Compile的桥梁
- 订阅并收到每个属性变动的通知
- 执行指令绑定的相应回调函数

### 4. Dep（消息订阅器）

- 内部维护一个数组，用来收集订阅者（Watcher）
- 数据变动触发notify函数
- 调用订阅者的update方法

## 工作原理

```
数据变化 → Observer通知 → Dep.notify → Watcher.update → View更新
用户输入 → ViewModel处理 → Model更新
```

## 典型应用

基于MVVM架构的框架包括：

- **[[Vue.js]]** - 当前热门的前端框架
- **[[微信小程序]]** - 采用类似MVVM的数据绑定机制
- **AngularJS**
- **React**

## 优势

1. **更好的解耦**：ViewModel隔离了View和Model的直接交互
2. **数据绑定**：自动同步UI和数据状态
3. **响应式编程**：支持单向或双向数据流
4. **易于测试**：ViewModel不依赖View，便于单元测试
5. **代码优雅**：相比MVP更简洁、更易维护

## 来源

[[summaries/18.2.3网页应用开发环境]]