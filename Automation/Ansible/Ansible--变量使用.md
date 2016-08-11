# 变量
自动化技术使得重复做事变的更加容易，当系统有所不同，Ansible 可以是使用相同的 template，通过变量来处理不同系统。
Ansible 的变量名称可以以 **`字母、数字和下划线`** 命名，变量开头要以 **字母开头**

## 在 inventory 中定义变量
可以参考 「Ansible--入门」 inventory 章节介绍


## 在 playbook 中定义变量
```
- hosts: web
  vars:
    http_port: 80
```

# 使用变量
在 template 语言 jinjia2 的语法引用：利用中括号和点号来访问子属性
```
foo['field1']
foo.field2
```
