# 循环
Ansible的循环也与编程语言中的类似，循环可以帮你重复做一件事，直到它收到某一个特定结果。

## 标准循环

- 简写重复的任务

```
- name: add server users
  user: name={{ item }} state=present group=wheel
  with_items:
    - testuser1
    - testuser2
```

- 变量中使用 YAML 列表
```
// 在变量中使用 YAML 列表
with_itm_items: "{{ somelist }}"

// 等同于
- name: add_user testuser1
  user: name=testuser1 state=present group=wheel
- name: add_user testuser2
  user: name=testuser2 state=present group=wheel

// 支持哈希列表
- name: add serveral user
  user: name={{ item.name }} state=present groups={{ item.groups }}
  with_itm_items:
    - { name: 'testuser1', groups: 'wheel' }
    - { name: 'testuser2', groups: 'root'}
```

## 嵌套循环
```
- name: give users access to multiple databases
  mysql_user: name={{ item[0] }} priv={{ item[1] }}.*:ALL append_privs=yes password=foo
  with_nested:
    - [ 'alice', 'bob']
    - [ 'clientdb', 'employeedb', 'providerdb']
```
或者
```
- name: here. 'users' contains the above list of employees
  mysql_user: name={{ itme[0] }} priv={{ item[1] }}.*:ALL append_privs=yes password=foo
  with_nested:
    - "{{users}}"
    - [ 'clientdb', 'employeedb', 'providerdb' ]
```

## 对哈希表使用循环
使用 `with_dict` 来循环哈希表中的元素,下面打印用户名和电话号码
```
---
- hosts: all
  vars:
    users:
      alice:
        name: Alice Appleworth
        telephone: 123-456-789
      bob:
        name: Bob Bananarama
        telephone: 987-654-321
  tasks:
    - name: print phone records
      debug: msg="User {{ item.key }} is {{ item.value.name }} ({{ item.value.telephone }}]"
      with_dict: "{{users}}"
```

## 对文件列表使用循环
使用 `with_fileglob` 可以以非递归的方式来匹配单个目录的文件
```
---
- hosts: all
  tasks:
    # first ensure out target directory exists
    - file: dest=/tmp/fooapp state=directory
    # copy each file over that matches the given pattern
    - copy: src={{ item }} dest=/tmp/fooapp/ owner=root mode=600
      with_fileglob:
        - /opt/ansible/playbooks/fooapp/*
```

## 对并行数据使用循环
```
// 变量
alpha: ['a', 'b', 'c' 'd' ]
numbers: [ 1, 2, 3, 4 ]
// 得到 '(a,1)' 和 ‘(b,2)’,可以使用`with_together`
tasks:
  - debug: msg="{{ item.0 }} and {{ item.1 }}"
    with_together:
      - "{{ alpha }}"
      - "{{ numbers }}"
```

## 对子元素使用循环
```
---


```
