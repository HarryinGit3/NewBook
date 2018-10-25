---
title: 第一个Flask程序
tags: Python,Flask
---
### 第一个flask程序讲解
1. 注意
第一次创建创建项目的时候，要添加flask的虚拟环境
2. flask代码的详细解释
```
#从flask这个框架导入Flask这个类
from flask import Flask


# 初始化一个Flask对象
# Flask()
# 需要传递一个参数 __name__
# 1.方便flask框架去寻找资源
# 2.方便flask插件出现错误的时候，好去寻找问题所在的位置
app =Flask(__name__)


# 这个装饰器的作用是做一个url与视图函数的映射
# 127.0.0.1:5000/ ->去请求hello_world这个函数，然后将结果返回给浏览器
@app.route('/')
def hello_world():
    return '我是第一个flask程序'

if __name__ =='__main__':
    app.run()
```
### 设置debug模式：
1.在app.run()中传入一个关键字参数`debug`,`app.run(debug=True)`，就设置当前项目为debug模式。
2.debug模式的两大功能：
  当程序中出现问题的时候，可以在页面中看到错误信息和出错的位置。
  只要修改了项目中的`python`文件，程序会自动加载，不需要手动重新设置服务器。