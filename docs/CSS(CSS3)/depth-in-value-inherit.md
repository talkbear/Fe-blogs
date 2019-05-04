# inherit


# inherit 

## width: inherit;
 inherit关键字使得元素获取其父元素的计算值。它可以应用于任何CSS属性，包括CSS简写 all。
 
 > 注意：即使是触发了[BFC](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context)的元素，也能通过inherit值获取其非BFC
 父元素的对应属性值。
 
 比如容器内子元素设置fixed定位后，其宽度默认值为auto，且相对于视窗宽度。我们想让固定后的子元素宽度不变：
 
 ```
 .parent{width:300px;}
 .child{width: inherit;position:fixed;top:0;} // inherit保证即使是固定定位后依旧与原来保持同样宽度
 <div class="parent">
    <ul class="child"></ul>
 </div>
 ```
 
 ## others
