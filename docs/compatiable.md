# Javascript

- 【火狐和IE】 window.location.reload方法刷新页面时iframe页面不会被刷新，使用location.src = location.src课强制刷新解决；
- 【IE】svg动态修改stroke-dashoffset偶尔出现不渲染的问题
```
// 反复测试后，发现在挂载dom之前设置的stroke-dashoffset值能正常渲染，因此解决方案如下：
// valinajs
setTimeout(function(){
  var svg = document.creElemente('svg')
  svg.setAttribute('stroke-dashoffset', '-100')
  documeng.querySelector('.svg_box').append(svg)
})
// in vue
<svg v-if="isLoad"></svg>
settimeout(function(){
  this.isLoad = true
})
```
- 【IE】svg动态修改stroke-dashoffset不支持动画
```
暂未找到解决方案，使用canvas或许可以替代
```

- 【IE】filter:url(#svgid)方式直接引用svg文件实现模糊效果，无效；
```
// 方法一： 网上教程，使用background-image引用歹有模糊效果的svg图片作为背景，经测试似乎无效
background-image： url(/path/to/svg)
```
```
// 方法二： canvas方案 利用canvas对象自带的函数可实现
// 略
```
- 【IOS】Safari不支持stroke-dashoffset的负数值
- 【IOS】添加overflow-y:auto|scroll;后 页面滑动不流畅
```
-webkit-overflow-scrolling:touch;
```
- 【IOS】负margin值在ios webview出现滑动时被遮住的问题
```
！！！！避免使用负的margin值
```
