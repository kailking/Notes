## 环境介绍 ##

### 系统版本 ###
系统环境默认采用`CentOS Linux release 7.1.1503 (Core)`，


### 软件获取 ###

官方网站：[http://nginx.org](http://nginx.org)
最新稳定版本：[nginx-1.8.1.tar.gz](http://nginx.org/download/nginx-1.8.1.tar.gz)
帮助文档：[http://nginx.org/en/docs](http://nginx.org/en/docs)
编译参数说明：[http://nginx.org/en/docs/configure.html](http://nginx.org/en/docs/configure.html)

### 软件仓库 ###
yum仓库包含`centos`官方和`epel`两个安装源
```
rpm -ivh http://mirrors.yun-idc.com/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
```

## Nginx安装 ##

### 安装依赖软件 ###
* 安装pcre
```
\\ 使用rewrite功能
yum install pcre pcre-devel
```

* 安装openssl
```
\\ 如果需要ssl支持,不需要可以不安装
yum install openssl openssl-devel
```

### 安装nginx ###
```
tar -zxf nginx-1.8.1.tar.gz 
cd nginx-1.8.1/
./configure --prefix=/usr/local/nginx --with-http_ssl_module  --with-http_stub_status_module --with-pcre
make && make install 
```

* --with-http_ssl_module            ---支持https
* --with-http_stub_status_module    ---支持nginx状态查询
* --with-pcre                       ---支持rewrite

## nginx启动、停止、重启 ##

### 启动 ###
现在nginx就可以启动，不需要更改任何配置文件。
```
\\-c参数指定了配置文件的路径，如果不加-c，nginx就会默认加载其安装目录下面的conf目录下面的nginx.conf文件
/usr/local/nginx/sbin/nginx 
```
### 停止 ###
```
/usr/local/nginx/sbin/nginx -s stop[quit,reopen,reload]
```
Nginx的停止命令有很多，一般都是通过发送系统信号给nginx的主进程来停止nginx,例如：
```
\\停止nginx
kill –QUIT `主进程号`
kill -QUIT `cat /usr/local/nginx/logs/nginx.pid`
 
\\快速停止nginx
kill –TERM `主进程号`
kill –TERM `cat /usr/local/nginx/logs/nginx.pid`

kill –INT `主进程号`
kill –INT`cat /usr/local/nginx/logs/nginx.pid`

\\强制停止nginx
Kill -9 nginx
```

### 重启 ###
```
/usr/local/nginx/sbin/nginx -s reload[stop,quit,reopen]
```
同样可以通过信号来重启nginx
```
Kill –HUB `主进程号`
kill –HUB `cat /usr/local/nginx/logs/nginx.pid`
```
