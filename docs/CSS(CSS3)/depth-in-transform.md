# transform 


# transform属性和position:fixed

# transform:scale和IE

IE下（包括edge浏览器），设置transform:scale后的元素保留有原有的高度，这会导致页面出现无效的空白区域；

**问题1 给body元素增加transform:scale，页面底部出现白色空白区域**

```
body{
  transform: scale(.9);
}
.child{
  backgroud-color: red;
}
```

**解决方案：**

设置子元素绝对定位，父元素高度则塌陷为0，则实现去掉父元素白色空白区域；
```
.child{
  position: absolute;
  top:0;
}
```
