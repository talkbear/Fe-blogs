# 组件样式的复用性和耦合性

## css增加复用性

## 降低耦合性

### 命名空间

命名空间方案有很多，诸如BEM,原子命名等；

** BEM 命名**

### 创建优于复用

编写样式时，优先使用新建classname新增样式属性替换直接使用原有样式追加样式方式。


### 组合优于继承

通过新建classname和原有class组合使用，实现组件或文档样式，避免使用样式继承性及覆盖性方式。便于样式复用及解耦。


# 组件的样式管理

## 1.组件的样式应该高度可定制化

组件的样式应该是可以自由定制的, 开发者应该考虑组件的各种使用场景. 所以一个好的组件必须暴露相关的样式定制接口. 至少需要支持为顶层元素配置className和style属性。

## 2.避免使用内联 CSS

## 3.优先使用原生 CSS

对性能要求较高的组件库，使用更高性能的原生css实现就够了。

## 4. 使用 svgr 转换 svg 图标

## 5.结合使用 rem 和 em 等相对单位, 创建更有弹性的组件



# 规范

## 促进建立统一的 UI 设计规范

## CSS 编写规范

- [Airbnb CSS/Sass styleguide](https://github.com/airbnb/css)

## 使用stylint进行样式规范检查

# 参考

1.[React组件设计实践总结03 - 样式的管理](https://juejin.im/post/5cdad9c7f265da039b08915d)
2.[svg sprite](https://github.com/jkphl/svg-sprite)


