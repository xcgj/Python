```python
#coding=utf-8
```
- 第一行加的声明是为了让 python版本2识别中文
- 也可以将其替换成python推荐的声明:  

```python    
#-*- coding:utf-8 -*-
```


# 注释
```python
print("xcgj")
#行注释
'''
块注释
'''
"""
asd asd
"""
a="xcgj"
print(a)
```


# intput()和print()
```python
b = 123
c = 'asd'
print(a)                #纯变量输出
print("a的值是%d"%b)    #格式化输出整数
print("name=%s"%c)      #格式化输出字符串
print("name=%s, age=%d, addr=%s"%(c, b, a))
```

## 注意点：
- 在python2中，input接收的用户输入会被当成代码执行，不接受字符串
- 在python3中，input接收的用户输入会被当成字符串
- 在python2中，input可以使用raw_input指定为字符串接收,python3没有这个函数:  

```python
a = input("python2只接受数字/代码计算，python3接受任意输入：")
if type(a) == type(1):
    print("刚刚输入的结果是：%d"%a)
elif type(a) == type('a'):
    print("刚刚输入的结果是：%s"%a)

#b = raw_input("可以接收任意输入：")
b = 'python3不支持raw_input()函数'
print(b)

# print()打印不换行的方法
print("*", end="")
# print()打印换行
print("")
```  

# 变量类型
- 数字（int long float complex）  
- 布尔  
- String：python的字符串一般不考虑\0，因此"ABC"占用的是3个字节的内存
- List
- Tuple（元组）
- Dictionary（字典）

可变类型：列表、字典
不可变类型：数字、字符串、元组，用来作为字典的键值  
内存存储字典数据时，会将键进行hash得到一串数字，然后将值存储到这串数字对应的内存地址中；因此要求字典的键是不可改变的，不然取数据时键发生过改变，会导致取出的值错误

id(a)查询变量a引用的地址

type(a)确定类型
```python
# python3的input默认将输入变成字符串，int强转
c = int(input("请输入一个数字："))
type(c)
d = str(c) #将整形转成字符串
```

# if-else
python 没有switch  

```python
if 条件:
  print(a)
  print(c)
elif 条件:
  pass
else :
  print(e)
print(f)
```
pass的作用是告诉编译器这里有代码，以后会补全，先别报错  

注意点：
- 不要忘了冒号
- 注意缩进

# 运算符
```python
a = 5
b = 2

c = a//b #取商

c = a**b #a的b次方--幂

c = "AB" * a # 重复字符串
print(c) # ABABABABAB

a <> b # 不等于，建议使用 !=
```

# while
python 没有do while  

```python3
while 条件:
  print(a)
  print(b)
print(c)
```
注意点：
- 不要忘了冒号
- 注意缩进  

# for
```python
str = "ABCD"
#依此打印出字符串中的每个字符,\0除外
for temp in str
  print(temp)
```
python语法for循环和else联用
```python
lst = [1,2,3]
# lst = []
for tmp in List:
  print(tmp)
  #break
else:
  print("test")
# 不管lst表是不是空，else语句都会被打印
# 如果for语句中有break，那么else语句不会打印
```
break

# 字符串

```python
mystr = "abcdefgh abcdefgh"
```

- 当一个变量是一个字符串时，在交互模式下，按".+tab"键查看所有字符串函数

- 字符串的负数下标，逆序取字符  

```python
a = "abcdefg"
print(a[-1]) # 'g'
print(a[-2]) # 'f'
```

- 字符串拼接  

```python
a = '123'
b = 'abc'
print(a + b) # '123abc'
print("===%s==="%(a+b)) # '===123abc==='
```

- 字符串切片   
[开始:结束),左闭右开,格式：[起始位置:终止位置:步长]  

```python
a = 'message'
a[2:6] # 'ssag'
a[2:-1] # 'ssag'

# 取到最后一个字符(步长取不到值为止)
a[2:] #ssage
# 错误写法
a[2:0] # ""

# 跳跃切片--步长，默认步长是1
a[1:-1:1] # 'essag'
a[1:-1:2] # 'esg'

# 利用步长逆序
a[-1::-1]  # 'egassem'
a[::-1] # 'egassem' 步长自动识别起始位置
```

- find()函数和rfind()  
能找到就返回匹配字符串首个字符的下标，找不到就返回-1  

```python
mystr.find("bcd") # 1 从左边开始匹配
mystr.rfind("bcd") # 10 从右边开始匹配
```

- index()函数和rindex()  
找不到就程序崩溃  

- count()  
检查指定字符串出现的次数

- replace()  
替换，参数三表示替换的次数  

```python
mystr.replace("abc", "kkkk", 1) # "kkkkdefg abcdefg"
```

- split()  
切割，按指定字符切割，切割结果列表展示  
如果括号内不填参数，默认切割全部空白字符

- capitalize()  
字符串第一个字母大写

- title()  
每个单词首字母大写

- startwith()和endwith()  

```python
mystr.startwith("abc") # True
mystr.endwith("abc") # False
```

- lower()和upper()  
转换字符串中所有字符的大小写

- ljust()和rjust()和center()   
括号内参数填宽度(int)  
左对齐、右对齐和居中，不够以空格填充

- lstrip()和rstrip()和strip()   
删除左、右、两边空格

- partition()和rpartition()   
以括号内字符串切割母串，返回元组  
只匹配一次  

```python
mystr.partition(' ')
# 返回元组
# ('abcdefg', ' ', 'abcdefg')
```

- splitlines()   
按换行符分割为列表

- isalpha()和isdigit()和isalnum()   
判断字符串是不是 纯字母 纯数字 字母数子混合

- join()   
将列表中的数据以一定的格式组成字符串  

```python
b = ['aaa', 'bbb', 'ccc']
c = '=='
d = c.join(b) # 'aaa==bbb==ccc'
"".join(b) # aaabbbccc
```


# 列表
可以同时存储多种不同类型的数据  

```python
a = [1,'acv', 3.14,567,0,1]
b = ['a','b','c']
```
增：  
- a.append(123)  整体添加成为1个元素
添加数据到列表结尾  
- a.insert(0, "aaa")  
指定位置添加数据    
- 列表相加
1. 直接使用 + 号：a+b  
2. a.extend(b)  扩展len(b)个元素到a里面
3. 分片赋值：a[len(a):] = b    

删    
- a.pop()  
删除最后一个元素并打印这个元素  
- a.remove(1)
删除从左往右找到的第一个元素  
- del.a[0]
删除列表的第0个元素

改
- a[1] = 'a'
下标索引修改

查
- in  

```python
if 111 in a:
  print("a列表有元素111")
else:
  print("a列表没有元素111")
```
- not in  


函数和方法  
- len(a)
求列表元素的个数


# 字典  

```python
a = {"name":"aaa", "b": 1}

b = {}
b["name"] = "bbb"
b["age"] = 10

c = [a]

c.append(b)

for tmp in c:
  # print(tmp)
  print(tmp['name'])
```
- 增  

```python
a["c"] = "ccc";
```
- 删  

```ptthon
del a["b"]
```
- 改  

```python
a["name"] = "aa"
```
- 查

```python
# 字典没有键值直接崩
a["ddd"]
# 字典没有键值不输出
a.get("ddd")
```  

- 函数和方法
1. len(a)
求a字典中键值对的对数
2. a.get("name")
检查a中有没有"name"这个键
3. a.keys()
python2返回一个列表，列表元素是a中所有键值对的键  
python3返回一个对象，对象中含有a中所有键值对的键
4. a.values()
python2返回一个列表，列表元素是a中所有键值对的值  
python3返回一个对象，对象中含有a中所有键值对的值
5. a.items()
python2返回一个列表，列表有len(a)个元素，每个元素都是由一对键和值组成的元组  
python3返回一个对象，对象中含有一个列表，列表有len(a)个元素，每个元素都是由一对键和值组成的元组  
items()的用法：  

```python
#python2交互模式
>>> a={}
>>> a["name"] = 10
>>> a["age"] = "A"
>>> a
{'age': 'A', 'name': 10}
>>> a.items()
[('age', 'A'), ('name', 10)]
>>> b,c = a.items()
>>> b
('age', 'A')
>>> c
('name', 10)
>>> print("name=%s, age=%d"%c)
name=name, age=10
>>> for x, y in a.items():
...     print("key=%s, val=%s"%(x,y))
...
key=age, val=A
key=name, val=10
```
6. a.sort()
```python
a.sort()              # 默认从小到大排序
a.sort(reverse=True)  # 从大到小排序
a.sort(key=len)       # 按元素的长度排序

lst=[{"name":"aa","age":30},{"name":"zz","age":20},{"name":"cc","age":80}]
lst.sort(key=lambda x:x["name"],reverse=True)
'''
适用于字典列表排序
key等于一个匿名函数，是一个lambda表达式，返回值（被比较的部分）是冒号后面的部分
: ：return
x：表示列表的每个元素，是一个字典
x["name"]：提取字典的name键，按他们的值比较排序
x["age"]：提取字典的age键，按他们的值比较排序
reverse=True：从大到小排序
'''
```


# 元组

```python
#创建单个元素的元组
>>> a=1,
>>> a
(1,)
>>>
```


# 函数
- 普通函数的封装  

```python
# 函数返回值
def foo(i,j=0,k=0): # 有缺省（默认）参数
  a=1
  b=2
  c=3
  return a,b,c # 返回的是元组
  # return [a,b,c] # 返回的是列表

a = foo(5,k=5)  # a是一个元组 (1,2,3)
                # 有命名参数，指定函数形参k的值是5
a,b,c = foo(1,1,1) # a=1, b=2, c=3
```
```python
# 命名参数指定形参的值
def fo(a, b, c=10, d=0, e=1):
  pass

fo(b=3, a=2, e=8, c=5)  
```
```python
# 函数的不定长参数1
def f1(a, b, *args):
  print(a)
  print(b)
  print(args)
  result = a + b
  for tmp in args:
    result += tmp
  return result

f(1,2)          # args是空元组，args=()
f(1,2,3,4,5,6)  # args=(3,4,5,6)
```
```python
# 函数的不定长参数2

#-*- coding:utf-8 -*-
def f2(a, b, c=0, *args, **kwargs):
    print(a)
    print(b)
    print(args)   # 元组
    print(kwargs) # 字典

f2(1,2,3,4,5,6,7,x=99,y=100)
```
```shell
# f2运行结果：
xcgj@xcgj:~$ python test.py  
1
2
(4, 5, 6, 7)
{'y': 100, 'x': 99}
```
```python
# 函数的不定长参数3--拆包

#-*- coding:utf-8 -*-
def f3(a, b, c=0, *args, **kwargs):
    print(a)
    print(b)
    print(args)   # 元组
    print(kwargs) # 字典

m=(4,5,6,7)
n={"abc":99, "def":100} # 疑问：当键值指定为整型（如10，11）或浮点型（如1.1，1.2）报错：TypeError: f3() keywords must be strings，为何？？？
f3(1,2,m,n)
print("="*10)
f3(1,2,*m,**n)
```
```shell
# f3运行结果：
xcgj@xcgj:~$ python3 test.py
1
2
({'def': 100, 'abc': 99},)
{}
==========
1
2
(5, 6, 7)
{'def': 100, 'abc': 99}
```

总结：  
```
1. 函数可以有多个返回值，可以返回元组、列表、字典
2. 命名参数可以不按照函数形参的顺序传递实参，命名参数的名字必须是形参名字的其中一个
3. 实参多于形参时，形参用 *变量名 接收没有名字(如a)的实参，组成元组；用 **变量名 接收有名字(如a=3)的实参，组成字典
4. 实参传元组变量或字典变量给形参时，若需要拆分，需要在实参元组变量前加 * ，在字典变量前加 **  
```

- 主函数的封装  

```python
'test.py文件'
def foo():
    a = 10
    print(a)

def main():
    foo()

main()
```

```shell
# 运行：
xcgj@xcgj:~$ python test.py
10
```
- 匿名函数  

```python
# 相当于回调函数
def test(a,b,func):
  return func(a,b)

num = test(1,2,lambda x,y:x+y)
print(num)

'''
test函数中的func函数是一个回调函数，他在test函数体内引用了实参传过来的匿名函数(lambda表达式)
lambda表达式的冒号是return的意思，返回了x+y的结果
'''
```
```python
# 函数自定义
def test(a,b,func):
  return func(a,b)

# python2的input接收的是一个表达式，程序不出错
fun1=input("请输入一个函数(python2)：") # lambda x,y:x*y
num = test(1,2,fun1)
print(num)

#python3的input接收的是一个字符串，需要用eval去掉字符串的引号变成表达式
fun2=input("请输入一个函数(python3)：") # lambda x,y:x/y
fun2=eval(fun2)
num = test(1,2,fun2)
print(num)
```


# 局部变量和全局变量
全局变量放在函数被调用之前，命名规范：g_变量名  

```python
a = 100
def f1():
  global a # 声明要使用全局变量a，而不是自己定义一个局部变量a，一般放在函数作用域开始的位置
  a = 10
  return a

print(f1()) # 10
print(a)  # 10
```
如果列表、字典等序列定义成了全局变量，  
若函数需要用到这个序列，不需要在函数内声明global，直接使用就行，  
但加上global会增加代码的可读性  

```python
# 可变类型和不可变类型对函数的影响
a = 100
lst = [200]
def test(num1, num2):
  num1 += num1
  num2 += num2
  print(num1) # 200
  print(num2) # [200, 200]

test(a, lst)  
print(a)    # 100
print(lst)  # [200, 200]
'''
如果函数变量所指向的全局变量是可变类型的，会直接对全局变量本体进行修改
如果函数变量所指向的全局变量是不可变类型，函数会自己定义一个同名变量，将结果放入自定义的变量里面
'''
```


# help()的使用
退出help界面使用 q
- 可以用来查看变量说明及系统函数说明

```python
a = [1,2]
help(a) # 会进入list类的说明
```

- 查看自定义函数说明   
前提是函数第一行已经用一对单引号或一对双引号或三对单引号或三对双引号注释过  

```python
def foo():
  '''函数说明'''
  pass
  return

help(foo)
```

# random
```python
import random #导入模块

#限定a的值在[0, 1, 2]之间
a = random.randint(0, 2)
```
