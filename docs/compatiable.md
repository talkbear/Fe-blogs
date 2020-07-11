# Javascript

- 火狐和IE window.location.reload方法刷新页面时iframe页面不会被刷新，使用location.src = location.src课强制刷新解决；
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
