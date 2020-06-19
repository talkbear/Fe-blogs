## 【基础】
- meta viewport相关
    - width=device-width中的device-width是屏幕缩放比例100%时的逻辑像素(如iPhonex是375，而不是真实物理像素980),该属性会影响document.documentElement.clientWidth获取的值。
    
    
- 设计师使用PHOTOSHOP使用的单位是px即物理像素

- iOS 开发工程师和使用 Sketch 和 AdobeXD 软件设计界面的设计师使用的单位都是PT(即CSS像素)为单位，1pt=1dpi(dpi大小由具体的设备所决定)

- 在实际项目中，把与元素尺寸有关的css，如width,height,line-height,margin,padding等都以rem作为单位，这样页面在不同设备下就能保持一致的网页布局。

- **rem方案一（主流适配方案）：**
    - 动态设置根元素font-size（通常参考设计稿的标准(如设计稿750px标准)，设置根元素fontSize为：设备逻辑像素/750 * 200(为方便计算)；iphonex为例：375 / 750 * 200 = 100(px), 假设某div宽度100px，则width属性应该为1rem）；
    - 布局的时候，各元素的css尺寸=设计稿标注尺寸/根元素fontSize；
    - 容器元素的font-size都不用rem，需要额外地对font-size做媒介查询；
    > 淘宝flexible.js作者认为，是建议描述性的字体使用px，如果有slogan之类大于48px的，可以使用rem。现在绝大多数的字体文件都自带一些点阵尺寸，通常是16px和24px，所以我们不希望出现13px和15px这样的奇葩尺寸。所以在Flexible整个适配方案中，考虑文本还是使用px作为单位。只不过使用[data-dpr]属性来区分不同dpr下的文本字号大小。（当然也可以使用媒体查询实现该效果）
   
- **rem方案二（淘宝无限适配方案）**
    - 1 动态设置viewport的scale
    - 2 动态计算html的font-size
    - 3 布局的时候，各元素的css尺寸=设计稿标注尺寸/设计稿横向分辨率/10。
        > 采用除去10比采用除去100更合适，因为使用时小数点会更少，方便调试。
    - 4 font-size可能需要额外的媒介查询，并且font-size不使用rem，这一点跟网易是一样的。
        >设置了一个临界点，当设备竖着时横向物理分辨率大于1080时，html的font-size就不会变化了。
        
## 【移动端自适应布局开发建议】

- REM布局

- 【rem】字体设置rem导致不同手机表现不一致。
> 参考[手机淘宝页面方案](https://www.cnblogs.com/zhuanshen/p/7098707.html)

## 【常见IOS问题】
- 下面这句是解决placeholder在ios 端的input框中显示偏上

```
input::-webkit-input-placeholder {
    line-height: normal;
}
```


- position:fixed; input框ios端就不能输入了；
input{
    -webkit-user-select:auto!important;
    user-select:auto!important;
}

- ios webview避免使用position:fixed；

- position:fixed;可能引发问题汇总,ios输入框cursor问题；

- ios移动端 软键盘收起后 ，出现白底，未跟随软键盘收回；

```
$(input).on('blur', function(){
  window.scroll(0,0)
})
```

- 【ios问题记录】1 子div弹框，scrolltop滚动阻止父元素滚动；
```
body{
    height: 100%;
    position:fixed;
}
/* script */
// 记录弹框前的scrolltop值
var beforeTop = document.docElement.scrollTop
```
- 在匿名函数中调用苹果的媒体播放功能提示playSound error: NotAllowedError

>参考苹果[官方文档](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/Using_HTML5_Audio_Video/PlayingandSynthesizingSounds/PlayingandSynthesizingSounds.html#//apple_ref/doc/uid/TP40009523-CH6-SW5),明确写明播媒体文件必须是用户显示触发的事件回调里面。

即不能在settmeout,setinterval或立即执行函数等函数等和事件回调函数不一致的上下文中执行播放脚本。

```
document.querySelector('#play').addEventListener('click', function(){
    // 播放成功
    var audio = new Audio('test.mp3')
    audio.play()
    
    // 播放失败
    // 立即执行函数
    (function(){
        var audio = new Audio('test.mp3')
        audio.play()
    })()
    // settimeou/setinterval
    settimeout(function(){
        var audio = new Audio('test.mp3')
        audio.play()
    })
})
```


