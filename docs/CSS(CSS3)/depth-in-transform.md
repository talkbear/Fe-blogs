# transform 


# transform属性和position:fixed

# transform:scale

**问题1 transform:scale后会导致元素出现空白区域**

> 通过设置transform元素子元素绝对定位后，父元素及transform元素高度变为0，空白区域消失；

```
body{
  transform: scale(0.9);
  transform: left top;
}
body .child{
  position:absolute; // 绝对定位后body元素高度为0，空白区域消失
  height: auto;
}
```

# transform:scale和IE

**问题1 IE中transform:scale后会导致元素出现空白区域**

> 通过设置transform元素子元素绝对定位后，父元素及transform元素高度变为0，空白区域消失；在IE中，无效，因为transform属性因为高度为0，无法继承，缩放失败。

解决方案是：使用zoom方案替代transform：scale方案；
