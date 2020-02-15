# UpGoRemove_Flask (停止维护)
<p align = "center">

<img src="https://www.remove.bg/images/samples/combined/s5.jpg" />

<br><br>
<h1>UPGOREMOVE，一键去除图片背景。</h1>
<br><br>
<a href="https://github.com/wangxinleo/UpGoRemove_Flask/issues"><img alt="GitHub issues" src="https://img.shields.io/github/issues/wangxinleo/UpGoRemove_Flask"></a>
<a href="https://github.com/wangxinleo/UpGoRemove_Flask/network"><img alt="GitHub forks" src="https://img.shields.io/github/forks/wangxinleo/UpGoRemove_Flask"></a>
<a href="https://github.com/wangxinleo/UpGoRemove_Flask/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/wangxinleo/UpGoRemove_Flask"></a>
<a href="https://github.com/wangxinleo/UpGoRemove_Flask/blob/master/LICENSE"><img alt="GitHub license" src="https://img.shields.io/github/license/wangxinleo/UpGoRemove_Flask"></a>
</p>

## 💡 简介

[UPGOREMOVE](https://github.com/wangxinleo/UpGoRemove_Flask) 是一款快速、精细去除背景图片的AI web工具！！！

从照片中删除背景是一项繁琐的任务 ，就算是专业的设计师，使用最专业的软件，也需要花费大量时间去处理图片细节问题。

使用[UPGOREMOVE](https://github.com/wangxinleo/UpGoRemove_Flask)，您可以在5秒内自动100％剪切任何图像，不需要进一步输入：没有选择像素，没有标记人，什么都没有。

UPGOREMOVE 基于[REMOVEBG](https://www.remove.bg)，它有偿提供了自动删除背景的API接口，就算不了解人工智能，也能通过它提供的接口实现个人开发需求。

> 具体细节请浏览 [REMOVEBG/API](https://www.remove.bg/api)

### 为什么要花时间去研究这个？

先来一张效果对比图

![showimg.png](https://i.loli.net/2019/08/08/WmQYRlArafdzKcu.png)

对比之后明显发现，REMOVEBG API可以提供更丰满的图片效果。相比于一些抠图难度大的图片，REMOVEBG API可以更加帮助到设计师短时间完成自己的工作。

最重要的。。网上那些智能抠图工具有着致命和繁琐的套路

注册-->填信息-->收邮件-->打开邮箱-->确认邮件-->登录-->下载

对不起，打扰了~我选择死亡~[手动滑稽]

## 🗃 示例地址
[REMOVEBG_http://removebg.wangxinleo.cn/](http://removebg.wangxinleo.cn/)

## 🗃 演示

![show.gif](http://i.loli.net/2019/08/08/ulsbS64w3AGJNR1.gif)

## 🎨 界面

### 开始使用

PC端

![pc_key.png](https://i.loli.net/2019/08/08/ZEHnwR1yW4aU9Xo.png)

![pc_index.png](https://i.loli.net/2019/08/08/BTDPdEzk5CL1NWw.png)

![pc_index2.png](https://i.loli.net/2019/08/08/5K3OgqVcrthPAxp.png)

移动端

![mobie_index.png](https://i.loli.net/2019/08/08/xdeI5mMHcQXB17K.png)

### 处理完成

PC端

![pc_complete.png](https://i.loli.net/2019/08/08/InPGwcZXBM5NqE2.png)

移动端

![mobie_complete.png](https://i.loli.net/2019/08/08/T6Mrjb3sJg9m1CS.png)

### 错误页面

PC端

![pc_404.png](https://i.loli.net/2019/08/08/okfxKFCLsBnV8zU.png)

![pc_ugerror.png](https://i.loli.net/2019/08/08/eQmn8MjRt5bJ2Cv.png)

移动端

![mobie_404.png](https://i.loli.net/2019/08/08/grb41LC9fFm5SxJ.png)

![mobie_ugerror.png](https://i.loli.net/2019/08/08/rEO9oJxqym2FYkH.png)

## 🛠️ 安装

### 本地试用
1.下载并正确安装 [python ](https://www.python.org/)、[pip3](https://pypi.org/project/pip/#files)、mysql

2.[下载UpGoRemove_Flask](https://github.com/wangxinleo/UpGoRemove_Flask)，解压，进入解压目录

3.在项目目录中进入命令行模式（Windows进入cmd，linux进入shell），运行命令以下，安装依赖
```
pip install -r requirements.txt
```

4.在mysql中运行sql文件夹下的upGoremove.sql文件
    
- 4-1创建数据库
    - 数据库的字符集选择utf8mb4,字符集校对选择utf8mb4_general_cil
    
    ![image.png](https://i.loli.net/2019/09/18/yfNL1q6pB4V75vt.png)
- 4-2运行sql脚本
    - 注意选择正确的字符集
    
    ![image.png](https://i.loli.net/2019/09/18/KWTfupn8jX46Lqg.png)
    
5.更改config.py中关于 SQLALCHEMY_DATABASE_URI的值，指向自己的数据库

```
 SQLALCHEMY_DATABASE_URI = 'mysql+pymysql://用户名:密码@数据库地址:3306/upGoremove'
```

6.运行项目主程序，不要关掉黑色窗口
```
python manage.py
```

5.根据提示，打开  http://127.0.0.1:5000/  即可

### 获取密钥
要处理图像，您必须访问[Removebg API](https://www.remove.bg/api)

根据网站指引注册登录后即可获得免费密钥

### 处理图像目录
用户上传图片时，保存的目录：
```
uploadFile/
├── person.jpg
└── car.png
```

运行后将得到的图片目录：

```
uploadFile/
├── person.jpg
└── car.png

downloadFile/
├── person.png
├── person_blue.png
├── person_red.png
└── person_white.png

zipFile/
└── person.zip
```

### 隐私安全
关闭下载页面时，会触发关闭事件，删除与目标用户有关的图像数据，请试用的小伙伴及时保存好自己的图片数据

### 日志输出
默认将日志打印到error.log，请在项目目录中查看

## 🏘️ 提问

* [报告问题](https://github.com/wangxinleo/UpGoRemove_Flask/issues/new)

## 🙏 鸣谢

* [remove-bg](https://github.com/remove-bg/go)：一个基于GO语言的removebg API

## 🏘️ 社区

* 欢迎加入B3LOG的小众开源社区，详情请看[这里](https://hacpai.com/article/1463025124998)
