# Ad-Hoc
执行 Ad-Hoc 跟在 Linux 执行命令差不多， 用来快速完成简单的任务。

- 语法

```
ansible [host or group] -m  [module_name] -a [commond] [ ansible-options ]
```

- 执行安装程序， 安装 `python-simplejson`

```
ansible all -m raw -a 'yum -y install python-simplejson'
```

- 重启 web 服务
假如 web_server 是一个组， 这里组里面有很多webserver，先在需要在 web_server 组上的左右机器执行 reboot 命令， -f 参数会 fork 出 10 个子进程，以并行的方式执行 reboot，即每次重启 10 台
```
ansible web_server -a "/sbin/reboot" -f 10
```
在执行时，默认是以当前用户身份去执行该命令，如果需要执行执行用户，添加 `-u username`，或者需要使用 sudo 去执行,添加 `-u username --sudo [--ask-sudo-pass]`。如果不是以 passwordless 的模式执行 sudo,应加上 --ask-sudo-pass (-K)选项,加上之后会提示你输入 密码.使用 passwordless 模式的 sudo, 更容易实现自动化,但不要求一定要使用 passwordless sudo.

## 文件传输
ansible 的另外一种用法就是可以以并行的方式同时 scp 大量的文件到多台主机。

```
ansible all -m copy -a "src=/opt/ansible/test.txt dest=/opt/ansible/test.txt"
```
如果是用 playbook，择可以利用 template 模块来实现更高级操作。

使用 file 模块 可以修改文件的属主和权限
```
ansible all -m file -a 'dest=/opt/ansible/test.txt mode=600 owner=nobody group=nobody'
```

使用 file 模块还可以创建、删除目录和文件
```
// 创建目录
ansible all -m file -a 'dest=/opt/ansible/test mode=755 owner=root group=root state=directory'

// 删除目录和文件
ansible all -m file -a 'dest=/opt/ansible/test state=absent'
```
更多详见[copy模块说明](http://docs.ansible.com/ansible/copy_module.html)


## 包管理
ansible 提供了对 yum 和 apt 的支持，
```
 // 安装软件包
 ansible all -m yum -a 'name=vim state=present'

// 卸载软件包
 ansible all -m yum -a 'name=vim state=absent'
```
在不同的发行版的软件包管理软件， ansible 有其对应的模块， 如果没有，你可以使用 command 模块去安装软件。
更多详见[package模块说明](http://docs.ansible.com/ansible/list_of_packaging_modules.html)

## 用户和组管理
```
// 创建用户
ansible all -m user -a 'name=charlie password=123456 state=present'

// 修改用户， 增加属组和修改shell
ansible all -m user -a 'name=Cc groups=nobody shell=/sbin/nologin state=present'

//移除用户
ansible all -m user -a 'name=Cc state=absent'
```
更多参数详见[user模块说明](http://docs.ansible.com/ansible/user_module.html)

## 服务管理
```
// 启动服务
ansible all -m service -a 'name=rsyslog state=started'
// 重启服务
ansible all -m service -a 'name=rsyslog state=restarted'
// 停止服务
ansible all -m service -a 'name=rsyslog state=stopped'
```

## 系统自身变量获取
ansible 可以通过 setup 模块来获取客户端自身的以便固有信息，叫做 facts
```
// 获取所有 facts 变量
ansible all -m setup

// 通过 filter 获取某一个 fact 变量
ansible all -m setup -a 'filter=ansible_*mb'
```
