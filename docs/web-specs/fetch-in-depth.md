# fetch标准
>[官方链接](https://fetch.spec.whatwg.org/)

# fetch标准规定如下(部分列出)：

**具备获取资源的接口或标签**
  - html: <img>
  - html: <script>
  - html: <link>
  - css: cursor属性
  - css: list-style-image,font-face,background-image属性
  - js: navigator.sendBeacon();self.importScripts()
  
 **本地协议以"about", "blob", or "data"开头**
 **fetch协议以"about", "blob", "data", "file"，"ftp"，"http" or "https"开头
  
 **关于Referer和Referer-Policy**
 
  - 主要是以下三种场景，会发送Referer字段。
    - 用户点击网页上的链接。
    - 用户发送表单。
    - 网页加载静态资源，比如加载图片、脚本、样式。
  - 改变默认Referer属性的方法
    - 单个元素定制：rel="noreferrer"属性是最简单的一种方法。适用a、area和form。
    - 全局定制：a.服务端返回Referrer-Policy头信息；b.meta name="referrer" content="origin";c.a、area、img、iframe和link标签，可以设置referrerpolicy 属性。
  
 - 
