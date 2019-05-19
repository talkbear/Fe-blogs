# 背景

维基百科解释：动画是操作图像使其以特定方式运动的一种方法。传统的动画起源于电影工业行业，其主要用于在电影中展示特定的动画效果，或者更广泛的应用——动画电影。

无论是传统电影行业还是其他动画应用领域，通常具备成熟的动画应用和体系。如CGI。

这里我们简单描述如何创建一个在浏览器中展示的动画过程。


# 基础

浏览器提供的层叠样式表(css)来控制超文本文档(html)在浏览器中的展示视觉效果。同时也提供了一个重要的特性——动画。利用这个特性我们能够利用css结合html方式，
实现在浏览器中展示动画效果。————（想想你可以自己做一个网页电影，再没有比这个更酷的了）；

一个最常见的例子：

首先，我们新建一个普通的txt文档，名称为index; 然后将他的后缀修改为.html(或htm)，然后添加下面的内容:

index.html

```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>hello</title>
</head>
<body>
    <div class="animation">hello world</div>
</body>
</html>
```
我们刚刚创建另一个最简单的html文件，现在你可以直接打开这个文件了，系统默认会使用浏览器来打开它。

接着，我们创建第一个动画，修改文件如下：

```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>hello</title>
    <style>
      @keyframes fadeIn{
        0%{
          opacity: 0;
        }
        
        100%{
          opacity: 1;ytf
        }
      }
      
      .animation{
        
        animation: fadeIn 2s linear;
      }
    </style>
</head>
<body>
    <div class="animation">hello world</div>
</body>
</html>
```

