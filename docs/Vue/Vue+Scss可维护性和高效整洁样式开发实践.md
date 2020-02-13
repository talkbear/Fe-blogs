# CSS代码管理与如何编写高性能代码

## css代码管理
### css组织
### css规范
**命名规则**
**编写规范**
### css



## 如何编写高性能代码

### 加载性能

**文件压缩**

**按需加载**

### 渲染性能

**选择符**
不同的选择符号具备不同的性能，性能由高到低：
- ID 规则
– Class 规则
– 标签规则
– 通用规则



**选择更优的样式属性值**

相同效果下，某些属性值会占用内存值；如border属性的值0（0px），会触发渲染；none则不会触发渲染；

**减少选择器数量**

**代码压缩**

**避免使用CSS表达式（Expression）**



## 【补充】如何设计项目多主题样式方案

### 考虑因素

- 可维护性

**变量提取**

**利用CSS继承**

**命名规范**

**减少样式层叠**

**使用多重选择器**

**适当的注释**

**CSS代码排序**

**避免过度约束**
// bad
ul#someid {..}
.menu#otherid{..}

// good
#someid {..}
#otherid {..}

**后代选择符最烂**

日常开发中尽量避免使用后代选择器


修改组件中为深层dom样式
1.修改非组件中dom样式
2.修改组件中深层dom样式很头疼，因为无法：

通常的做法是：

一 代码覆盖
二 内联样式
三 important
四 新增class（推荐）


**避免链式（交集）选择符**
// bad
.menu.left.icon {..}

// good
.menu-left-icon {..}

**坚持KISS原则**

**避免不必要的命名空间**

 **尽可能精简规则**
 
 **避免不明确的命名约定**
 最好使用表示语义的名字。一个好的CSS类名应描述它是什么而不是它像什么。
 
 **避免 !importants**
 **组织好的代码格式**
 // bad
.someclass-a, .someclass-b, .someclass-c, .someclass-d {
…
}

// good
.someclass-a,
.someclass-b{
…
}





- 可拓展性

- 性能

1.方案一
2.方案二
3.方案三




# 参考

1.[React组件设计实践与总结系列文章](https://juejin.im/post/5cdad9c7f265da039b08915d)

2.[谷歌性能](https://developers.google.com/web/fundamentals/performance/why-performance-matters)

3.[如何构建高性能网站Steve Souders](http://stevesouders.com/)

4.[Web Performance](https://developer.mozilla.org/en-US/docs/Learn/Performance)

5.https://developers.google.com/speed/docs/insights/PrioritizeVisibleContent#UseEfficientCSSSelectors


