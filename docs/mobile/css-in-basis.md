# 移动端不同手机系统line-height:normal值的绝对值不相同，显示设置避免跨端兼容问题

```
// bad
.text{
  font-size: 12px;
  color: red;
  line-height: normal; // 可能出现不同文字实际line-height不相同
}

.text{
  font-size: 12px;
  color:red;
  line-height: 1; // 显示设置绝对值，可解决
}
```
