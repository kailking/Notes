**介绍：**

MyCli是一个MySQL的命令行客户端，可以实现自动补全(auto-completion)和语法高亮，同时也可应用于MariaDB和Percona。

**功能特征：**

*   MyCli使用Python Prompt Toolkit编写。

*   支持语法高亮

*   当你输入SQL关键字，数据库的表格和列时可自动补全。

*   智能补全(默认启用)，会提示文本感应的(context-sensitive)补全。

*   配置文件在第一次启动时，自动创建在~/.myclirc

**安装：**
兼容性：
OS X和Linux上测试过。运行在Python 2.6,2.6,3.3,3.4和3.5。能够很好地处理unicode输入/输出。

_Python Package:_

```
$ pip install myclior$ easy_install mycli
```

 _Mac OS X:_
最简单的方法在OS X机器安装mycli是使用<a rel="nofollow" target="_blank" style="margin: 0px; padding: 0px; color: rgb(96, 127, 166); text-decoration: none; max-width: 100%; box-sizing: border-box !important; word-wrap: break-word !important;">homebrew</a>

```
$ brew update && brew install mycli
```

**_Linux:_**
Debian/Ubuntu Package:
mycli托管在debian软件包<a rel="nofollow" target="_blank" style="margin: 0px; padding: 0px; color: rgb(96, 127, 166); text-decoration: none; max-width: 100%; box-sizing: border-box !important; word-wrap: break-word !important;">packagecloud.io.</a>
添加gpg密钥packagecloud包验证。

```
 $ curl https://packagecloud.io/gpg.key | apt-key add -
```

安装apt-transport-https包，支持apt使用https下载包

```
$ apt-get install -y apt-transport-https
```

添加mycli安装源

```
$ echo "deb https://packagecloud.io/amjith/mycli/ubuntu/ trusty main" | sudo tee -a /etc/apt/sources.list
```

更新mycli的安装源，然后安装mycli

```
$ sudo apt-get update$ sudo apt-get install mycli
```

现在使用sudo apt-get upgrade mycli很容易使mycli升级！

_RHEL, Centos, Fedora:_
我还没有为mycli构建RPM包。所以请使用pip安装mycli。你可以在你的系统上安装pip使用:

```
$ sudo yum install python-pip python-devel
```

一旦安装pip,您可以如下安装mycli:

```
$ sudo pip install mycli
```
**效果图：**
_自动补全_
简单的完成如关键字和sql函数。

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0WtTF2sym1VN5aavonHKSccDv9ibibsYL7423bcCfoibPh1Kpia4iaLXichB4SQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1 "t1.png")</a>

_智能提示_
Table name completions after the 'FROM' keyword.

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0WtTvCqJ1HSZT6ag0XMSIcM4rqxW0tE1xcu2kUguIB3pibntrhGlNpLeOg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1 "t2.png")</a>

列名中引用的表的查询范围

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0WtofZNbUuLwSf1F0WoyJEUyPufl7oarrVUa39jhECOCSnsIWxiammF13A/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1 "t3.png")</a>

_别名支持_
列完成将即使工作表名称别名。

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0Wth7GxMIn8x7L8CyQpbtqQzbHPhVxw1CnUJ07lDCZoZmttrFzhUHrLWQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1 "t4.png")</a>

_语法高亮显示_
sql的语法高亮显示。

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0WtOI1w64rZHQp41clAnUM98CuSpuRKJ2vejxmKadZwnTMS1QBD6ibAnZg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1 "t5.png")</a>

_pager_
一个sql命令的输出是通过更少的命令自动输送。

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0WtODPqhKKzwdjhPy7iajt7FCwzvp7hqwMUVyxrFUwM5gqKovtpicKnoCJA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1 "t6.png")</a>

**动态效果图如下：
**

<a target="_blank" data-fancybox-group="thumb" rel="lightbox" style="margin: 0px; padding: 0px; color: rgb(21, 95, 170); text-decoration: none; max-width: 100%; box-sizing: border-box; word-wrap: break-word !important; cursor: pointer; background: 0px 0px;">![](http://mmbiz.qpic.cn/mmbiz/6vIhibryDTSPAQcRThzgovhvI8DHRH0WtH641ch896WqxuQIoPyeibm7bTWoWFVyeXbj5XfAZl0r32LEvZpiaJfrQ/0?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1 "dt.gif")</a>

