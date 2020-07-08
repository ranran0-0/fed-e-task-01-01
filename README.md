# fed-e-task-01-01
3天搞定前端核心框架Vue.js源码--第一天

选择题
1、下面关于虚拟 DOM 的说法正确的是：
A. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高程序的性能。
B. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高开发效率。
C. 虚拟 DOM 可以维护程序的状态，通过对比两次状态的差异更新真实 DOM。
D.虚拟DOM本质上是JavaScript对象，可以跨平台，例如服务器渲染，Weex开发等。

选：BD


2、下面关于 Snabbdom 库的描述错误的是：
A. Snabbdom 库是一个高效的虚拟 DOM 库，Vue.js 的虚拟 DOM 借鉴了 Snabbdom 库。
B. 使用 h() 函数创建 VNode 对象，描述真实 DOM 结构。
C. Snabbdom 库本身可以处理 DOM 的属性、事件、样式等操作。
D.使用patch（oldVnode，null）可以清空页面元素

选：D


简答题
请简述 patchVnode 函数的执行过程。

答案：
1.对比两个结点前，调用prepatch钩子函数和update钩子函数
2.对比过程：
    a.判断新节点中是否有text属性，若节点有text属性并且不等于旧节点的text属性，更新Dom文件的文本内容；
      若老节点有children，需移出老节点children对应的Dom元素，并设置新节点对应DOM元素的textContent
    b.若新老节点都有children，且不相等，需对比对应子节点并且更新子节点的差异
      若只有新节点有children属性，判断老节点中是否有text属性，若有，清空对应DOM元素的textContent并且添加所有的子节点
      若只有老节点有children属性，移出所有的老节点
    c.若只有老节点有text属性，清除对应元素的textContent
3。对比结束后，调用postpatch钩子函数
