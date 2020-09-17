# 2020-personal-python
1. 每行长度
每行代码最大长度不超过80个字符。对于太长的行，需要分隔成多行，推荐使用圆括号，中括号，花括号来隐式的连接多行的内容，不推荐使用反斜杠，示例如下
x = ('This will build a very long long '
     'long long long long long long string')
当然，对于无法使用圆括号的情况，仍然需要使用反斜杠，示例如下
with open('/path/to/some/file/you/want/to/read') as file_1, \
     open('/path/to/some/file/being/written', 'w') as file_2:
    file_2.write(file_1.read())
2. 多行代码的缩进与对齐

多行代码推荐用缩进的方式使其看上去，直观的属于一个整体，一种写法是直接在圆括号，中括号，花括号之后换行，换行之后缩进4个空格，示例如下

my_list = [
    1, 2, 3,
    4, 5, 6,
]

foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
    
# 为了将参数和函数内部的代码进行区分，将参数又添加了4个空格的缩进
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one) 
当然，这里不是一定要4个空格，只是4个空格的写法最常见，另外一种写法在各种括号之后的第一个变量名之后换行，换行之后的变量和第一个变量名保持相同的缩进，示例如下

foo = long_function_name(var_one, var_two,
                         var_three, var_four)

3.  二元操作符的多行连接

二元操作符，即操作符两侧都有变量的操作符，当语句太长时，，二元操作符写在行首，这样可以直观的看出对变量进行的操作，示例如下

income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)

4. 空格的使用

二元操作符与其操作的对象之间添加一个空格，当多个具有不同优先级的操作符出现在同一句代码中时，优先级低的两侧添加空格，示例如下

i = i + 1
submitted += 1
x = x*2 - 1
hypot2 = x*x + y*y
c = (a+b) * (a-b)
括号内元素与左右两侧的括号之间不需要有空格，逗号，冒号，分号的前面不需要有空格，而应该在之后添加一个空格，示例如下

spam(ham[1], {eggs: 2})

if x == 4: print x, y; x, y = y, x
多行语句，不需要用空格来人为对齐，示例如下

x = 1
y = 2
long_variable = 3
函数参数列表中的等于号两侧，不需要空格，示例如下

def complex(real, imag=0.0):
    return magic(r=real, i=imag)

5. 分号的使用

即使语句很简短，也不要采用分号将多条语句写成一行，这样不容易看出程序结构，正确的写法示例如下

if foo == 'blah':
    do_blah_thing()
do_one()
do_two()
do_three()

6. 注释

编写注释可以提高程序可读性，对于一个函数，模块，类等，推荐使用文档字符串来编写注释，示例如下

def extract_fastq(id, fq):
    """Fetches seqs from a fastq file by input id.

    Args:
        id: input seq ids.
        fq: the fastq file

    Returns:
        A list contain the extract sequences

        [
            'AT...GTAGCTGC',
            'GCTAATGTGC..GTA',
        ]
    """
    pass

7. 模块导入

模块的导入应该独占一行，导入同一个模块中的多个方法可以写成一行，示例如下

import os
import sys
from subprocess import Popen, PIPE

8. 命名

变量名应该有意义，不要使用单个字母作为变量名，为了变量名有意义，可能需要多个单词来表示，此时可以用下划线进行连接，比如hello_world。

变量名，函数，模块名称等都推荐用小写字母，常量用全部大写字母表示，比如MAX_THREADS。

在Python中，对于变量名有如下约定

单下划线开头的变量表示模块或者类的私有变量

双下划线开头的变量表示类内私有

双下划线开头，并且双下划线结尾的变量是python的保留变量，比如__all__, 自定义的变量不要采用这样的写法

