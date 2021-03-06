正则表达式(regular expression)主要功能是从字符串(string)中通过特定的模式(pattern)，搜索想要找到的内容。

## 语法
之前，我们简介了字符串相关的处理函数。我们可以通过这些函数实现简单的搜索功能，比如说从字符串“I love you”中搜索是否有“you”这一子字符串。但有些时候，我们只是模糊地知道我们想要找什么，而不能具体说出我是在找“you”，比如说，我想找出字符串中包含的数字，这些数字可以是0到9中的任何一个。这些模糊的目标可以作为信息写入正则表达式，传递给Python，从而让Python知道我们想要找的是什么。
[官方documentation](https://docs.python.org/3/library/re.html)

在Python中使用正则表达式需要标准库中的一个包re。
```
import re
m = re.search('[0-9]','abcd4ef')
print(m.group(0))
```
re.search()接收两个参数，第一个'[0-9]'就是我们所说的正则表达式，它告诉Python的是，“听着，我从字符串想要找的是从0到9的一个数字字符”。
re.search()如果从第二个参数找到符合要求的子字符串，就返回一个对象m，你可以通过m.group()的方法查看搜索到的结果。如果没有找到符合要求的字符，re.search()会返回None。

如果你熟悉Linux或者Perl, 你应该已经熟悉正则表达式。当我们打开Linux shell的时候，可以用正则表达式去查找或着删除我们想要的文件，比如说：
```
$rm book[0-9][0-9].txt
```

这就是要删除类似于book02.txt的文件。book[0-9][0-9].txt所包含的信息是，以book开头，后面跟两个数字字符，之后跟有".txt"的文件名。如果不符合条件的文件名，比如说:

bo12.txt
book1.txt
book99.text
都不会被选中。

Perl中内建有正则表达式的功能，据说是所有正则表达式系统中最强的，这也是Perl成为系统管理员利器的一个原因。

## 正则表达式的函数
```
m = re.search(pattern, string)  # 搜索整个字符串，直到发现符合的子字符串。
m = re.match(pattern, string)   # 从头开始检查字符串是否符合正则表达式。必须从字符串的第一个字符开始就相符。
```
可以从这两个函数中选择一个进行搜索。上面的例子中，我们如果使用re.match()的话，则会得到None，因为字符串的起始为‘a’， 不符合'[0-9]'的要求。
对于返回的m, 我们使用m.group()来调用结果。（我们会在后面更详细解释m.group()）

我们还可以在搜索之后将搜索到的子字符串进行替换：
```
str = re.sub(pattern, replacement, string)
```
在string中利用正则变换pattern进行搜索，对于搜索到的字符串，用另一字符串replacement替换。返回替换后的字符串。

此外，常用的正则表达式函数还有
```
re.split()    # 根据正则表达式分割字符串， 将分割后的所有子字符串放在一个表(list)中返回
re.findall()  # 根据正则表达式搜索字符串，将所有符合的子字符串放在一给表(list)中返回
```
(在熟悉了上面的函数后，可以看一下re.compile()，以便于提高搜索效率。)

### 写一个正则表达式
关键在于将信息写成一个正则表达式。我们先看正则表达式的常用语法：

- 单个字符

```
.          任意的一个字符
a|b        字符a或字符b
[afg]      a或者f或者g的一个字符        
[0-4]      0-4范围内的一个字符
[a-f]      a-f范围内的一个字符
[^m]       不是m的一个字符
\s         一个空格
\S         一个非空格
\d         [0-9]
\D         [^0-9]
\w         [0-9a-zA-Z]
\W         [^0-9a-zA-Z]
```

- 重复

```
紧跟在单个字符之后，表示多个这样类似的字符
*         重复 >=0 次
+         重复 >=1 次
?         重复 0或者1 次
{m}       重复m次。比如说 a{4}相当于aaaa，再比如说[1-3]{2}相当于[1-3][1-3]
{m, n}    重复m到n次。比如说a{2, 5}表示a重复2到5次。小于m次的重复，或者大于n次的重复都不符合条件。
```

- 正则表达          

```
相符的字符串举例
[0-9]{3,5}       9678
a?b              b
a+b              aaaaab
```
- 位置

```
^         字符串的起始位置
$         字符串的结尾位置
```
```
正则表达  相符的字符串举例  不相符字符串

^ab.*c$    abeec   cabeec如果用re.search(), 将无法找到
```

- 返回控制

我们有可能对搜索的结果进行进一步精简信息。比如下面一个正则表达式：
```
output_(\d{4})
```
该正则表达式用括号()包围了一个小的正则表达式，\d{4}。 这个小的正则表达式被用于从结果中筛选想要的信息（在这里是四位数字）。这样被括号圈起来的正则表达式的一部分，称为群(group)。
我们可以m.group(number)的方法来查询群。group(0)是整个正则表达的搜索结果，group(1)是第一个群……
```
import re
m = re.search("output_(\d{4})", "output_1986.txt")
print(m.group(1))
```

我们还可以将群命名，以便更好地使用m.group查询:
```
import re
m = re.search("output_(?P<year>\d{4})", "output_1986.txt")   #(?P<name>...) 为group命名
print(m.group("year"))
```
