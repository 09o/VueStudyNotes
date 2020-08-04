# Vue Study Notes 学习Vue过程中的笔记整理

## Start

#### 关于什么是渐进式框架？
> 根据知乎用户Jim Liu的回答“它给你提供足够的optional，但并不主张很多required”，其实大概就是说我们可以根据自己的需求只使用框架中的部分功能，而不是必须采用大部分功能协同运作才可以。

## 数据渲染
---

1. 文本数据渲染
	 - {{ msg }}
	 可以完成运算或是一段js代码，但不建议这么做，对于需要进行计算操作的会通过Vue的`computed`方法来完成。具体效果例如：`{{ msg + 'hello vue' }}` / `{{ num + 1 }}` / `{{ 'helloVue'.split('').reverse().join('') }}`
	 - v-text="msg"

2. 条件与循环
	 - v-if="条件判断返回true/false"
	 - v-for="(item,index) in objectArray"

	 使用条件判断方法可以用来控制DOM中元素的插入/更新/移除效果，同样的`v-show`也可以实现相同功能。但是两者区别是，使用`v-if`会使元素从DOM结构中消失，而`v-show`则是利用了内联样式`display: none`来完成的元素显示隐藏功能。从这点上看，可以明白，如果要频繁/多次控制元素的显示状态，那么使用`v-show`。因为使用`v-if`每次都会对结构进行一次渲染，影响性能。

3. 处理用户输入
	- v-on:事件监听="运算/function" || @事件监听
	- v-model="dataAttr"
	> v-mode 实现表单输入和应用状态之间的双向绑定