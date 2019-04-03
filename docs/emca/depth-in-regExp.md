> 该文章深入学习ecma对RegExp相关的知识点

# 目录

# 正文

## 关于RegExp构造函数
- 使用new RegExp()等同于直接调用RegExp，其都返回对应的RegExp实例对
- Reg可被继承，在class定义语句中使用extends关键字，注意在定义字类的构造函数中，必须执行super函数。

## 关于其他

- RegExp.prototype.test方法执行前默认使用toString方法转换为字符串


