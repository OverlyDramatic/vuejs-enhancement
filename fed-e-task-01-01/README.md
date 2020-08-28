# Vue.js 框架最为核心的 Virtual DOM 是如何实现的？

## 选择题

### 1、下面关于虚拟 DOM 的说法正确的是：(A、B、C、D)

### 2、下面关于 Snabbdom 库的描述错误的是：(D)

## 简答题

### 1、请简述 patchVnode 函数的执行过程。

1. 触发prepatch()
2. 触发update()
3. 新节点有text属性，且不等于旧节点
    - 如果老节点有children → 移除子节点children对应的DOM元素
    - 设置新节点对应DOM元素的textContent
4. 新老节点都有children，且不相等
    - 调用updateChildren()
    - 对比子节点，更新子节点差异
5. 只有新节点有children属性
    - 如果老节点有text属性 → 清空对应DOM元素的textContent
    - 添加所有的子节点
6. 只有老节点有children属性
    - 移除所有的老节点
7. 只有老节点有text属性
    - 清空对应DOM元素的textContent
8. 触发postpatch钩子函数
