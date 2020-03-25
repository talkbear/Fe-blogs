# zoom
最初在IE浏览器中出现，目前支持的浏览器包括Chrome,IE,Safari等；注意的是Firefox不支持。所以一定避免使用改属性；

## zoom与IE


IE下（包括edge浏览器），设置zoom元素后的元素保留有原有的高度，这会导致页面出现无效的空白区域；

**问题1 给body元素增加zoom，页面底部出现白色空白区域**

```
body{
  zoom: .9;
}
.child{
  backgroud-color: red;
}
```

**解决方案1：**（暂定无效）

设置子元素绝对定位，父元素高度则塌陷为0，则实现去掉父元素白色空白区域；
```
.child{
  width: 100%;
  position: absolute;
  top:0;
}
```


**解决方案2: overflow:hidden**
```
.container{
  overflow: hidden;
}
.container .scale_div{
 	overflow: hidden;
	-webkit-transform: scale(0.62);
    transform: scale(0.62);
    -webkit-transform-origin: 10% top;
    transform-origin: 10% top;
}

```


## transform:scale(x)——zoom属性替代方案

transform：scale(x)同样能够缩放html元素，且支持IE9以上；其他除opera浏览器外的新版浏览器中都支持。



