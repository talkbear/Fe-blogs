# 浏览器加载顺序

**图片简要描述：**

![loading progress of page](https://github.com/ethanbear/fe-blogs/raw/master/assets/images/fp_firstPaint-1.jpg)

**文字详细描述**

1. 输入url后，请求首页html；
2. html文档下载完成后，解析文档；
3. 加载外链css,js和ico；（注：现代某些浏览器会很智能的提前'偷窥'html中是否有如link,img,script等外链标签，并着手提前加载对应资源；）
4. 解析body
  4.1 解析普通标签。
  4.2 解析过程碰到script标签，按下面逻辑处理：
  
    4.2.1 如果该脚本之前的css和js已经加载并执行完时，立即触发渲染（已有cssdom+htmldom的render）。第一个script触发的渲染即通常称之为FP或FCP；
    
    4.2.2 如果该脚本之前的css和js还未加载完成时，则会等待所有脚本执行完后触发渲染；
    
5.解析body的标签，通常为script标签

6.完成html解析

# 优化策略分析


# 优化实践总结

# 关于浏览器渲染进阶知识

- 浏览器会提前渲染html中所有link,script,img类似外链的文件资源，不会等到渲染对应标签时才去请求对应资源；
- First Paint和DOMContentLoaded、load事件的触发没有绝对的关系，没有固定的顺序；
- body中第一个脚本前的css文件中，引用外部字体文件，则渲染过程会在字体下载完成后执行；
- 默认情况下，CSS外链之间是谁先加载完成谁先解析，但是JS外链之间即使先加载完成，也得按顺序执行。

# 参考文章
- [eux.baidu.com: chrome的First Paint](http://eux.baidu.com/blog/fe/Chrome%E7%9A%84First%20Paint)
- [Render Blocking Css](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css)
- [markdown中插入图片](https://www.zhihu.com/question/21065229)
