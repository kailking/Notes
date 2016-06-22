### Python模块

模块让你能能够有逻辑的组织你的Python代码块。把相关的代码分配到一个模块里让你的代码更好用，更易懂。模块也是python对象，具有随即的名字属性用来绑定或引用。简单的说，模块就是一个保存了python代码的文件，模块能够定义函数、类和变量。模块里也能够包含可执行的代码。

一个叫做`aname`的模块里的代码一般能够在一个叫做`aname.py`的文件中找到。创建一个简单的模块support.py

```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-

def print_func( par) :
    print "Hello :",par
    return        
```

---

#### inport语句

想使用python源文件，只需要在另外一个源文件中执行`import`语句`import module1[, module2][,...moduleN]`

当解释器遇到`import`语句，如果模块在当前的搜索路径就会被导入，搜索路径是一个解释器会先行搜索的所有目录列表，如果想要导入`support.py`，需要将命令放到脚本顶端。

```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-
import support

support.print_func("Zero")

//输出
Hello : Zero
```

一个模块只会被导入一次，不管你执行多少次import。这样可以防止导入模块被一遍一遍的执行。

---

#### from...import语句

python的from语句让你从模块中导入一个指定的部分到当前命名空间。`from modulename import name1[, name2][, nameN]`

例如：`from fib import fibonacci`，这个声明不会把整个fib模块导入当前命名空间中，他只会将fib里的fibonacci单个引用到执行这个声明的模块的全局符号表。

---

#### from...import* 语句

要把一个模块的所有内容全部导入当前命名空间也是可行的。`from modulename import *`这提供了一个简单的方法导入一个模块的所有项目，然而这种声明不该被过多的使用。

#### 定位模块

当你导入一个模块，python解释器对模块位置的搜索顺序是：

- 当前目录
- python在shell变量`PYTHONPATH` 下的每个目录
- 如果都到不到，python会查看默认路径。centos7 在`/usr/lib/python`

模块搜索路径存在`system`模块的`sys.path`变量中。变量包含当前目录，PYTHONPATH和安装的默认目录。

---

#### PYTHONPATH变量

作为环境变量，`PYTHONPATH`有装在一个列表中的许多目录组成。`PYTHONPATH`的语法和shell变量PATH相同。

---

#### 命名空间和作用域

变量是拥有匹配对象的名字（标识符）。命名空间是一个包含了变量名称们（键）和它们各自相应的对象们（值）的字典。

一个Python表达式可以访问局部命名空间和全局命名空间里的变量。如果一个局部变量和一个全局变量重名，则局部变量会覆盖全局变量。

每个函数都有自己的命名空间。类的方法的作用域规则和通常函数的一样。

Python会智能地猜测一个变量是局部的还是全局的，它假设任何在函数内赋值的变量都是局部的。

因此，如果要给全局变量在一个函数里赋值，必须使用global语句。

global VarName的表达式会告诉Python， VarName是一个全局变量，这样Python就不会在局部命名空间里寻找这个变量了。

例如，我们在全局命名空间里定义一个变量money。我们再在函数内给变量money赋值，然后Python会假定money是一个局部变量。然而，我们并没有在访问前声明一个局部变量money，结果就是会出现一个UnboundLocalError的错误。取消global语句的注释就能解决这个问题。

```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-
Money = 200
def AddMoney():
    #global Money   //变更全局变量
    Money += 1

print Money
AddMoney()
print Money
```

---

#### dir()函数

`dir()`一个排好序的字符串列表，内容是一个模块里定义过的名字。返回的列表容纳了一个模块里定义的所有模块、变量和函数。

```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-
import math

content = dir(math)

print content;

//输出
['__doc__', '__file__', '__name__', '__package__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'copysign', 'cos', 'cosh', 'degrees', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'hypot', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'modf', 'pi', 'pow', 'radians', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'trunc']
```

在这里，特殊字符串变量`__name__`指向模块的名字，`__file__`指向该模块的导入文件名。

---

#### globals()和locals()函数

根据调用地方的不同，globals()和locals()函数可被用来返回全局变量和局部命名空间的名字。

如果函数内部调用locals()，返回的是所有能在该函数里访问的命名

如果函数内部调用globals()，返回的是所有在该函数里能访问的全局名字

两个函数返回类型都是字典。所以他们能用key()函数摘取

---

reload()函数

当一个模块被导入一个脚本，模块顶层部分的代码只会被执行一次。如果你想重新执行模块里顶层部分的代码，可以使用reload()函数。还函数会重新导入之前导入过的模块。

```python
reload(module_name)
// 导入support模块
reload(support)
```

---

#### python中的包

包是一个分层次的文件目录结构，它定义了一个有模块及子包，和子包下的子包等组成的python的应用环境。考虑在一个phone目录下的`Pots.py`文件

```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-

def Pots():
    print "I'm Pots Phone"
```

同样的，有另外两个保存了不同函数的文件：

- Phone/lsdn.py 包含函数lsdn()
- Phone/G3.py 包含函数G3()

现在，在Phone目录下创建file` __init__.py`:

- Phone/`__init__py`

当你导入Phone时，为了能够使用所有函数，你需要在`__init__.py`里使用显示的导入语句：

```python
from Post import Pots
from Isdn import Isdn
from G3 import G3
```

当你把这些代码加到`__init__.py`之后，导入Phone包的时候这些类就全部是可用的了。

```python
#!/usr/bin/env python
# -*- codine: UTF-8 -*-

import Phone

Phone.Pots()
Phone.Isdn()
Phone.G3()

//输出
I'm Pots Phone
I'm Isdn Phone
I'm 3G Phone
```

上面只在一个文件里放置了一个函数，其实可以放置多个函数，也可以在这些文件里定义Python的类，然后为这些类键一个包
