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

- 【IOS】copy到粘贴板 不兼容iphnee7p
```

  var copyToClipboard = function copyToClipboard(text) {
  return new Promise(function (resolve, reject) {
    var fallbackCopyTextToClipboard = function fallbackCopyTextToClipboard(text) {
      var textArea = document.createElement('textarea');
      textArea.value = text;
      textArea.style.position = 'fixed'; // avoid scrolling to bottom
      document.body.appendChild(textArea);
      textArea.focus();
      var isIOS = /iPad|iPhone|iPod/.test(navigator.platform) || (navigator.platform === 'MacIntel' && navigator.maxTouchPoints > 1);

      if(isIOS){
        var range = document.createRange();

        textArea.contentEditable = true;
        textArea.readOnly = false;
        range.selectNodeContents(textArea);

        var s = window.getSelection();
        s.removeAllRanges();
        s.addRange(range);

        textArea.setSelectionRange(0, 999999); // A big number, to cover anything that could be inside the element.
      }else{
        textArea.select();
      }

      try {
        var successful = document.execCommand('copy');
        resolve({
          data: successful
        });
      } catch (err) {
        reject(err);
      }

      document.body.removeChild(textArea);
    };

    var copyTextToClipboard = function copyTextToClipboard(text) {
      if (!navigator.clipboard) {
        console.log('not surrpport', text)
        fallbackCopyTextToClipboard(text);
        return;
      }

      navigator.clipboard.writeText(text).then(function () {
        console.log('surrpport', text)
        resolve({
          data: 1
        });
      }, function (err) {
        reject(err);
      });
    };

    copyTextToClipboard(text);
  });
};
```
- 【IE】SVG dashoffset 值尽量大于svg图形的length长度，否则会出现偏差

- 【IOS,Android】html,body 100vh 和100% 处理方式不一样
  - IOS 100vh高度包含了上下导航位置的高度，因此会出现滚动条
  - android 100vh高度则不包含上下导航位置高度，因此不会出现滚动条
  
  - 安卓IOS,100%表现形式一致，都是可视窗口高度
  
  
