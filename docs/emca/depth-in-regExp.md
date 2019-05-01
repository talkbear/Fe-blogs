> 该文章深入学习ecma对RegExp相关的知识点

# 目录
- 断言(#边界)
# 正文

## 断言

包含先行断言，后视断言和条件表达式；

Character | 描述
--|--
x(?=y)|先行断言：匹配后面紧跟y的x
x(?!y)|否定先行断言：匹配后面未紧跟y的x
(?<=y)x|后视断言：匹配紧跟在y后面的x （注意Javascript不支持）
(?<!y)x|否定后视断言：匹配未紧跟在y后面的x（注意Javascript不支持）

## 边界

匹配行的首尾或单词首尾；
^ $ \b \B

## 角色类
除常用外，其他如[\b](backspace),\cX(控制类快捷键)，\xhh(两位16进制)，\uhhhh(utf16四位字符)；

## 分组和范围
除常用外其他进阶用法：

- \n 向后引用 n为正整数
- (?<Name>x) 命名捕获组；matches.groups[Name]可以获取对应组
- (?:x) 非捕获组： 匹配x但不捕获进分组
  
## 量词

除常用外其他进阶用法：

- 量词后紧跟?  如：x*?,x+?,x??,x{n,m}?，非贪婪模式。默认量词为贪婪模式即尽量匹配尽可能多的字符。

## Unicode

- \uFFFF 四位16进制数（JavaScript只支持这种方式匹配单个unicode字符）

## 关于RegExp构造函数
- 使用new RegExp()等同于直接调用RegExp，其都返回对应的RegExp实例对
- Reg可被继承，在class定义语句中使用extends关键字，注意在定义字类的构造函数中，必须执行super函数。

## 关于其他

- RegExp.prototype.test方法执行前默认使用toString方法转换为字符串

# 参考
1. [mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
2. [reg practices](https://alf.nu/RegexGolf)


