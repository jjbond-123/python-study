# **Python**

#### 一、字符**串（str）

```
一、 字符串
#1、capitalize() 返回将字符串的第一个字符转换为大写的字符串
str1    =   '''hellow word这是一个测试模块
主要作用域IT教育
'''
# 结果：Hellow word这是一个测试模块   主要作用域it教育
print(str1.capitalize())

#2、center(width, fillchar) 返回一个指定的宽度 width（宽度） 居中的字符串，fillchar（文件夹） 为填充的字符，默认为空格
print('hello all'.center(50,'*'))
#center方法可以传递两个参数，一个必传参数指定字符的宽度，另一个选传参数，指定用什么字符来填补空白区域
# 结果：********************hello all*********************
print('a','\n''b','\n''c','\n''d')
print('a','b','c','d',sep='\n')
#以上两种都是将每一段换行

3、count(str, beg= 0,end=len(string))返回 str （字符串）在 string （字符串中）里面出现的次数，如果 beg （起始位置）或者 end（终止位置） 指定则返回指定范围内 str 出现的次数
list = ' 我是你好，它是那就好，就是那好是 '
num = list.count('是',0,10) #前10次有多少个是
num1 = list.count('是',0,len(list)) #从0到最后
print(num,num1)
#2  4

#4、bytes.decode(encoding="utf-8", errors="strict") Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。**
#5、encode(encoding='UTF-8',errors='strict') 以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'
a = 'hello word nihao jjbond'
code = a.encode(encoding='utf-8')        #编码 ， 比特流
code1 = a.encode(encoding='gbk')
print(code,code1)
print(code.decode()) #解码，括号里要一直
# b'hello word nihao jjbond' b'hello word nihao jjbond'
# hello word nihao jjbond

#6、endswith(suffix, beg=0, end=len(string)) 检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False.
Tab键和空格不能混着用，会出现报错

#7、expandtabs(tabsize=8) 把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。
c = 'hello word  nihao   jjbond'
print(c.expandtabs(tabsize=50))

#8、find(str, beg=0 end=len(string)) 检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1**
#rfind(str, beg=0,end=len(string)) 类似于 find()函数，不过是从右边开始查找.
str8    =   '''hellow word这是一\t个测试模块
主要作用\tIT教育模块 nihao
'''
print(str8.find('模块'))     #找到第一个‘模块’，则是在第18位
#结果：找到第一个匹配数：18
print(str8.find('模块',str8.find('模块')+1,-1))
#结果：找到最后匹配数：30
print(str8.rfind('模块'))    #与find相反，从右向左找
#结果：找到最后匹配数：30

#9、isalnum() 如果字符串至少有一个字符并且所有字符都是字母或数字则返回 True,否则返回 False0
result  = input('请输入您的ID： ')   #包含数字或者字母返回ture
if  result.isalnum():
    name=result
else:
    name='游戏ID非法'
print(name)

#10、isalpha() 如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False
result  = input('请输入您的ID： ') #包含字母返回Ture
if  result.isalpha():
    name=result
else:
    name='游戏ID非法'
print(name)

#11、isdigit() 如果字符串只包含数字则返回 True 否则返回 False..
result  = input('请输入您的ID： ') #包含字母返回Ture
if  result.isdigit():
    name=result
else:
    name='输入不是数字'
print(name)

#12、islower()  如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False
if  'Hello'.islower():
    print(Ture)
else:
    print('Hello'.lower())
结果：hello

#13、isnumeric()  如果字符串中只包含数字字符，则返回 True，否则返回 False
print('123'.isnumeric())
#True
print('onetwothree'.isnumeric())
#False
print('壹贰叁'.isnumeric())
#True

#14、isspace() 如果字符串中只包含空白，则返回 True，否则返回 False.**
print(' '.isspace())
True

#15、istitle() 如果字符串是标题化的(见 title())则返回 True，否则返回 False
c = 'hello ni hao'
print(c.title())
Hello Ni Hao

#16、join(seq) 以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串**
c = 'hello ni hao'
d = '  '.join(c)
print(d)
 #h  e  l  l  o     n  i     h  a  o

#17、len(string) 返回字符串长度**
c = 'hello ni hao'
print(len(c))
12

#18、ljust(width[, fillchar\]) 返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。
d = 'hello'
print(d.center(20,'*'))
print(d.ljust(20,'*'))
print(d.rjust(20,'*'))
*******hello********
hello***************
***************hello

#19、maketrans() 创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标
m = '1234'
n= 'abcd'
c=str.maketrans(m,n)
print(c)
#结果：{49: 97, 50: 98, 51: 99, 52: 100}

#20、translate(table, deletechars="") 根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中
j = 'asd 1234 jkl ouio'
print(j.translate(c))
#结果：asd abcd jkl ouio

#21、replace(old, new [, max\]) 把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。**
j = 'asd 1234 jkl ouio'
print(j.replace('asd','123'))
#结果：123 1234 jkl ouio
print(j.replace('asd','123').replace('jkl','jjbond'))
#123 1234 jjbond ouio

# 22、split(str="", num=string.count(str)) num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串**
num=input('请输入一个人数字： ')
print(num.split())
结果：请输入一个人数字： 1 2 3 4
['1', '2', '3', '4']


#23、splitlines([keepends\]) 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。
s='''
ajkdfhjkl
    lsfdglugyhgi
            dfiklwesd
'''
print(s.splitlines())
print(s.splitlines(keepends=True))
print(s.splitlines(keepends=False))
# ['', 'ajkdfhjkl', '    lsfdglugyhgi', '            dfiklwesd']
# ['\n', 'ajkdfhjkl\n', '    lsfdglugyhgi\n', '            dfiklwesd\n']
# ['', 'ajkdfhjkl', '    lsfdglugyhgi', '            dfiklwesd']
```



#### 二、列表（list）

```
#1、访问列表里的值
#使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取字符
list1 = ['Google', 'baidu', 1997, 2000]
list2 = [1, 2, 3, 4, 5, 6, 7 ]
print ("list1[0]: ", list1[0])
print ("list2[1:5]: ", list2[1:5])
#结果：
# list1[0]:  Google
#list2[1:5]:  [2, 3, 4, 5]

#2、更新列表
#你可以对列表的数据项进行修改或更新，你也可以使用append()方法来添加列表项
list = ['Google', 'baidu', 1997, 2000]
print ("第三个元素为 : ", list[2])
list[2] = 2001
print ("更新后的第三个元素为 : ", list[2])
#结果：
# 第三个元素为 :  1997
# 更新后的第三个元素为 :  2001

#3、删除列表元素
#可以使用 del 语句来删除列表的的元素
list = ['Google', 'baidu', 1997, 2000]
print ("原始列表 : ", list)
del list[2]
print ("删除第三个元素 : ", list)
# 结果：
# 原始列表 :  ['Google', 'baidu', 1997, 2000]
# 删除第三个元素 :  ['Google', 'baidu', 2000]

列表是有长度的（len），列表之间可以互相相加形成新的列表（+），列表是可以想乘的，会形成多个重复的数（*），列表也是可以迭代的

#4、列表的截取和拼、
list = [ 'abcd', 786 , 2.23, 'hello', 70.2 ]
tinylist = [123, 'hello']
print (list)            # 输出完整列表
print (list[0])         # 输出列表第一个元素
print (list[1:3])       # 从第二个开始输出到第三个元素
print (list[2:])        # 输出从第三个元素开始的所有元素
print (tinylist * 2)    # 输出两次列表
print (list + tinylist) # 连接列表
结果：
# ['abcd', 786, 2.23, 'hello', 70.2]
# abcd
# [786, 2.23]
# [2.23, 'hello', 70.2]
# [123, 'hello', 123, 'hello']
# ['abcd', 786, 2.23, 'hello', 70.2, 123, 'hello']

还支持拼接的操作
squares = [1, 4, 9, 16, 25]
squares += [36, 49, 64, 81, 100]
# squares
#[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

与Python字符串不一样的是，列表中的元素是可以改变的
a = [1,2,3,4,5,6]
a[0] = 9
print(a)
a[2:5] = [11,12,13]
print(a)
a[2:5]=[]
print(a)
#结果：
# [9, 2, 3, 4, 5, 6]
# [9, 2, 11, 12, 13, 6]
# [9, 2, 6]

#5、嵌套列表
# 使用嵌套列表即在列表里创建其它列表
a = ['a', 'b', 'c']
n = [1, 2, 3]
x = [a, n]
print(x)
n = x[0]
print(n)
m = x[0]

#list.append()的用法
#list5.append(10) 加入一个元数
# list5.append([1,2,3]) 将整个列表加进去
a = [1,2,3,4]
a.append(10)
print(a)
a.append([1,2,3])
print(a)
# 结果：
# [1, 2, 3, 4, 10]
# [1, 2, 3, 4, 10, [1, 2, 3]]
# list5.extend([1,2,3]) 可以将列表都加进去,并且加入其中
a = [1,2,3,4]
a.extend([1,2,3])
print(a)
# 这个与列表相加结果相同：
a = [1,2,3,4]
b = [1,2,3]
print(a+b)
# 结果：[1, 2, 3, 4, 1, 2, 3]
#list.count()的用法：
# print(list5.count(1)) 取当前列表有多少个这个数
list = [1,2,3,1,2,3,4,5,6,7,89,6546,12,12,45]
n = list.count(1)
print(n)
#结果：2
#list.index()的用法：
#print(list5.index(128)) 查找列表的这个数,会输出索引
list = [1,2,3,1,2,3,4,5,6,7,89,6546,12,12,45]
# c = list.index(89)
# print(c)
# 结果：10
#list.insert()的用法：
#list5.insert(0,'hello world') 在最前面加上个数
list = [1,2,3,4,6]
list.insert(1,89)
print(list)
# 结果：[1, 89, 2, 3, 4, 6]
#list.pop（）的用法：
#print(list5.pop()) 在括号里输入一个索引,就会去除那个值,不输入,则会出去最后一个,并且打印出来
list = [1,23,3,4,5,6,77]
list.pop(1)
print(list)
# 结果：[1, 3, 4, 5, 6, 77]
# list.remove()的用法
# list.remove()移除列表中某个值的第一个匹配项
list = ['Google', 'baidu', 1997, 2000]
a = list.remove(1997)
print(list)
# 结果：['Google', 'baidu', 2000]
#list.reverse()的用法
list.reverse() 反向列表中元素，会将list中的元素反向打印
list = [1,2,3,4,5,6]
list.reverse()
print(list)
#结果：[6, 5, 4, 3, 2, 1]
#list.sort()的用法
#list.sort( key=None, reverse=False) 对原列表进行排序
list = [1,2,48,23,7,5,14]
list.sort(reverse=False)  #从小到大排序
print(list)
list.sort(reverse=True)   #从大到小排序
print(list)
# 结果：[1, 2, 5, 7, 14, 23, 48]
# [48, 23, 14, 7, 5, 2, 1]
list = [('a',45),('b',67),('c',12),('d',29),('e',2)]
list.sort(key=lambda list:list[1],reverse=True)
print(list)
#结果：[('b', 67), ('a', 45), ('d', 29), ('c', 12), ('e', 2)]

import random
list6 = ['小明','老王','小汤','小张'] #随机去除一个
num = random.randint(0,len(list6) -1)
delete = list6.pop(num)
print(delete)
print(list6)
list6.remove('老王')
print(list6)

# remove、del和 pop 有什么区别?
remove() 删除第一个匹配的值
li = ['a','b','c','d']
li.remove('b')
print(li)
#结果：['a', 'c', 'd']
# del按索引删除元素
li = ['a','b','c','d']
del li[0]
print(li)
#结果：['b', 'c', 'd']
#pop() 按索引删除一个元素并返回该元素
li = ['a','b','c','d']
li.pop(2)  #取出并删除索引值为2的元素。
print(li)  #['a', 'b', 'd']
li.pop()   #取出并删除列表末尾的单个元素。
print(li)
#结果：['a', 'b']
# clear()， 用clear()方法，清空列表的元素。（杯子还在，水倒空了）
li = ['a','b','c','d']
li.clear()
print(li)
#结果：[]
#del  ，用del list 语句，销毁整个列表。（杯子和水都没有了）
li = ['a','b','c','d']
del li
print(li)
#结果：
#Traceback (most recent call last):
#File "<input>", line 1, in <module>
#NameError: name 'li' is not defined
# list.copy()的用法：
a = [1,2,3]
b = a.copy()    # 列表拷贝
print(id(a),id(b))
a[0] = 'world'
print(a,b)
结果:['world', 2, 3] [1, 2, 3]

# 深浅拷贝的区别
浅拷贝：copy()

import copy                         # 导入 copy 模块

list1_1 = [0, 1, 2, ['a', 'b']]
list1_2 = list1_1                   # 赋值
list1_3 = list1_1.copy()            # 浅拷贝;同 list1_3 = list1_1[:]
list1_4 = copy.copy(list1_1)        # 浅拷贝
list1_5 = copy.deepcopy(list1_1)    # 深拷贝

# 打印出拷贝后的 list1_1 ~ list1_5
print("list1_1 =", list1_1)
print("list1_2 =", list1_2)
print("list1_3 =", list1_3)
print("list1_4 =", list1_4)
print("list1_5 =", list1_5)
print('-'*40)                       # 分割线

list1_1.append(4)                   # 在 list1_1 末尾添加一个元素 4
list1_1[3].append('c')              # 向 list1_1 中内嵌的列表末尾添加一个元素 'c'

# 打印出更改后的 list1_1 ~ list1_5
print("list1_1' =", list1_1)
print("list1_2' =", list1_2)
print("list1_3' =", list1_3)
print("list1_4' =", list1_4)
print("list1_5' =", list1_5)
```

#### 三、元组（Tuple）

```
#元组
#元组的案例
#1、访问元组
元组可以使用下标索引来访问元组中的值
tup1 = ('Google', 'Baidu', 1997, 2000)
tup2 = (1, 2, 3, 4, 5, 6, 7 )
print ("tup1[0]: ", tup1[0])
print ("tup2[1:5]: ", tup2[1:5])
#结果：tup1[0]:  Google
#tup2[1:5]:  (2, 3, 4, 5)

#2、修改元组
元组中的元素值是不允许修改的，但我们可以对元组进行连接组合
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')   # 以下修改元组元素操作是非法的。
# tup1[0] = 100   # 创建一个新的元组
# 元组数据类型不可改变
tup3 = tup1 + tup2
print (tup3)
#结果：(12, 34.56, 'abc', 'xyz')

#删除元组
#元组中的元素值是不允许删除的，但我们可以使用del语句来删除整个元组
tup = ('Google', 'Baidu', 1997, 2000)
print (tup)
del tup
print ("删除后的元组 tup : ")
print (tup)
#会发生报错，因为元组被删除，则打印不出来
#结果：  File "D:/python项目/1.py", line 31
#         ^
#SyntaxError: invalid character in identifier

元组是可用len（）计算个数的，元组之间是可以连接的（+），是可以复制的（*），也是可以迭代的

元组的索引，和截取同列表是一样的
```

#### 四、集合（set）

```
student = {'Tom', 'Jim', 'Mary', 'Tom', 'Jack', 'Rose'}
student1    =   {'jj','bb','h','Tom','Jim'}
print(student)
print(student    -   student1)
print(student    |   student1)
print(student    &  student1)
print(student    ^  student1)
结果：{'Mary', 'Tom', 'Jim', 'Jack', 'Rose'}
{'Jack', 'Mary', 'Rose'}
{'Mary', 'Tom', 'bb', 'h', 'Jim', 'jj', 'Jack', 'Rose'}
{'Jim', 'Tom'}
{'bb', 'h', 'Mary', 'jj', 'Jack', 'Rose'}

a = set('abracadabra')
print(a)
b = set('alacazam')
print(a - b)
print(a | b)
print(a & b)
print(a ^ b)
结果：{'d', 'r', 'b'}
{'a', 'c', 'r', 'm', 'b', 'z', 'd', 'l'}
{'a', 'c'}
{'z', 'r', 'm', 'd', 'l', 'b'}

添加元素
thisset = set(("Google", "Baidu", "Taobao"))
thisset.add("Facebook")
print(thisset)
{'Facebook', 'Baidu', 'Taobao', 'Google'}
删除其中的元素
thisset = set(("Google", "Baidu", "Taobao"))
thisset.remove("Taobao")
print(thisset)
{'Google', 'Baidu'}
将元素 x 从集合 s 中移除，如果元素不存在，则会发生错误。
另一种删除元素的方法
thisset = set(("Google", "Baidu", "Taobao"))
thisset.discard("Facebook")  # 不存在不会发生错误
print(thisset)
{'Taobao', 'Baidu', 'Google'}
此外还有一个方法也是移除集合中的元素，且如果元素不存在，不会发生错误
随机删除一个元素
thisset = set(("Google", "Baidu", "Taobao", "Facebook"))
x = thisset.pop()
print(x)

集合内置方法完整列表
a = set(("1", "2", "3"))
a1 = set(("3","4","1","5"))
a.add("4")    #为集合添加元素 add()
print(a)
a.clear()     #移除集合中的所有元素 clear()
print(a)
b = a.copy()    #拷贝一个集合 copy（）
print(b)
c = a.difference(a1)   #返回多个集合的差集 difference()
print(c)
a1.difference_update(a) #移除集合中的元素，该元素在指定的集合也存在 difference_update()
print(a1)
a.discard(3)   #删除集合中指定的元素 discard()
print(a)
d = a.intersection(a1)  #返回集合的交集 intersection()
print(d)
d = a.isdisjoint(a1) #判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False   isdisjoint()
print(d)
d = a.issubset(a1) #判断指定集合是否为该方法参数集合的子集。指定集合为参数   issubset()
print(d)
d = a.issuperset(a1) #判断该方法的参数集合是否为指定集合的子集 issuperset()
print(d)
d = a.pop()   #随机移除元素，并且打印出来   pop()
print(d)
print(a)
a.remove("2")    #移除指定元素  remove()
print(a)
d = a.symmetric_difference(a1)   #**返回两个集合中不重复的元素集合。  symmetric_difference()
print(d)
d = a.symmetric_difference_update(a1) #移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。（取两个集合中不同的元素）   symmetric_difference_update()
print(a)
d = a.union(a1)          #返回两个集合的并集   union()
print(d)
a.update('14')       # 给集合添加元素   update()
print(a)
```

#### 五、字典（dict）

```
student = {'Tom', 'Jim', 'Mary', 'Tom', 'Jack', 'Rose'}
student1    =   {'jj','bb','h','Tom','Jim'}
print(student)
print(student    -   student1)
print(student    |   student1)
print(student    &  student1)
print(student    ^  student1)
结果：{'Mary', 'Tom', 'Jim', 'Jack', 'Rose'}
{'Jack', 'Mary', 'Rose'}
{'Mary', 'Tom', 'bb', 'h', 'Jim', 'jj', 'Jack', 'Rose'}
{'Jim', 'Tom'}
{'bb', 'h', 'Mary', 'jj', 'Jack', 'Rose'}

a = set('abracadabra')
print(a)
b = set('alacazam')
print(a - b)
print(a | b)
print(a & b)
print(a ^ b)
结果：{'d', 'r', 'b'}
{'a', 'c', 'r', 'm', 'b', 'z', 'd', 'l'}
{'a', 'c'}
{'z', 'r', 'm', 'd', 'l', 'b'}

添加元素
thisset = set(("Google", "Baidu", "Taobao"))
thisset.add("Facebook")
print(thisset)
{'Facebook', 'Baidu', 'Taobao', 'Google'}
删除其中的元素
thisset = set(("Google", "Baidu", "Taobao"))
thisset.remove("Taobao")
print(thisset)
{'Google', 'Baidu'}
将元素 x 从集合 s 中移除，如果元素不存在，则会发生错误。
另一种删除元素的方法
thisset = set(("Google", "Baidu", "Taobao"))
thisset.discard("Facebook")  # 不存在不会发生错误
print(thisset)
{'Taobao', 'Baidu', 'Google'}
此外还有一个方法也是移除集合中的元素，且如果元素不存在，不会发生错误
随机删除一个元素
thisset = set(("Google", "Baidu", "Taobao", "Facebook"))
x = thisset.pop()
print(x)

集合内置方法完整列表
a = set(("1", "2", "3"))
a1 = set(("3","4","1","5"))
a.add("4")    #为集合添加元素 add()
print(a)
a.clear()     #移除集合中的所有元素 clear()
print(a)
b = a.copy()    #拷贝一个集合 copy（）
print(b)
c = a.difference(a1)   #返回多个集合的差集 difference()
print(c)
a1.difference_update(a) #移除集合中的元素，该元素在指定的集合也存在 difference_update()
print(a1)
a.discard(3)   #删除集合中指定的元素 discard()
print(a)
d = a.intersection(a1)  #返回集合的交集 intersection()
print(d)
d = a.isdisjoint(a1) #判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False   isdisjoint()
print(d)
d = a.issubset(a1) #判断指定集合是否为该方法参数集合的子集。指定集合为参数   issubset()
print(d)
d = a.issuperset(a1) #判断该方法的参数集合是否为指定集合的子集 issuperset()
print(d)
d = a.pop()   #随机移除元素，并且打印出来   pop()
print(d)
print(a)
a.remove("2")    #移除指定元素  remove()
print(a)
d = a.symmetric_difference(a1)   #**返回两个集合中不重复的元素集合。  symmetric_difference()
print(d)
d = a.symmetric_difference_update(a1) #移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。（取两个集合中不同的元素）   symmetric_difference_update()
print(a)
d = a.union(a1)          #返回两个集合的并集   union()
print(d)
a.update('14')       # 给集合添加元素   update()
print(a)




Dictionary（字典）
dict1 = {}
dict1['one'] = "1 - hello"
dict1[2]     = "2 - nihao"
tinydict = {'name': 'hello','code':1, 'site': 'nihao'}
print (dict1['one'])       # 输出键为 'one' 的值
print (dict1[2])           # 输出键为 2 的值
print (tinydict)          # 输出完整的字典
print (tinydict.keys())   # 输出所有键
print (tinydict.values())  # 输出所有值


构造函数 dict() 可以直接从键值对序列中构建字典
b = dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)])
print(b)
d = {x: x**2 for x in (2,4,6)}
print(d)
k = dict(a1=1,b2=2,c3=3)
print(k)


访问字典里的值
dict = {'Name': 'Baidu', 'Age': 7, 'Class': 'First'}
print ("dict['Name']: ", dict['Name'])
print ("dict['Age']: ", dict['Age'])
访问的时候没有里面的值，会出现报错。

修改字典
dict = {'Name': 'Baidu', 'Age': 7, 'Class': 'First'}
dict['Age'] = 8                 # 更新 Age
dict['School'] = "qianfeng"     # 添加信息
print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])

删除字典的元素
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
del dict['Name'] # 删除键 'Name'
print(dict)
dict.clear()     # 清空字典
del dict         # 删除字典
print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
但这会引发一个异常，因为用执行 del 操作后字典不再存在,z则不会执行出结果

不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住，如下实例：
dict = {'Name': 'qianfeng', 'Age': 7, 'Name': 'xueyuan'}
print ("dict['Name']: ", dict['Name'])
键必须不可变，所以可以用数字，字符串或元组充当，而用列表就不行，如下实例：
dict = {['Name']: 'Baidu', 'Age': 7}
print ("dict['Name']: ", dict['Name'])

可以用打印字符串来表示
dict = {'Name': 'Baidu', 'Age': 7, 'Class': 'First'}
print(str(dict))
print(type(dict)) #可以打印变量的类型，是字典就会打印字典的类型


python字典包含的内置方法
a = {'Name': 'Baidu', 'Age': 7, 'Class': 'First'}
d = a.clear()         # 删除字典内所有元素
print(d)
m = a.copy()            #返回一个字典的浅复制
print(m)
seq = ('name','age','class')
s = a.fromkeys(seq)
print(s)

# dict 字典 是可迭代对象 无序的数据类型 可变的数据类型
dict1 = {'name':'laowang','gender':'laowang','name':'shuaiqibiren'}
dict2 = {'name':'laowang','class':2001,'class_people':[1,2,3]}
#print(list(dict2.values()))

dict3 = dict()
dict3['name'] = 'hello'  # 添加键值对
dict3['from'] = 'china'  # 添加键值对
dict3['name2'] = 'world'  # 修改键名为name的值
# print(dict3)
# print(dict3['name'])
# a = ['a','b','c']
import mail01
# for k,v in enumerate(a):
#     print(k,v)

# 数值 int() float() 1、数值类型 2、内容是数字的字符串类型
# 字符串 str() 1、数值类型 2、字符串类型 3、列表类型 4、元组类型 5、集合 6、字典
# 列表 list() 1、字符串类型 2、元组类型 3、集合类型 4、 字典类型 5、列表类型
# 元组 tuple() 1、元组类型  2、列表类型 3、集合类型 4、字典类型 5、字符串类型
# 集合 set()  1、列表类型 2、元组类型 3、集合类型 4、字典类型 5、字符串类型
# 字典 dict() 1、字典类型 2、json


# 生成字典的方法
#1、手动赋值
dict4 = {}
dict4['name'] = 'xiaoming'
dict4['gender'] = 'nan'

#2、通过枚举
a = ['a','b','c']
for i,v in dict(enumerate(a)).items():
    print(i,v)
#3、通过zip整合
a = [1,2,3]
b = ['a','b','c']
print(dict(zip(a,b)))

#4、fromkeys
a = ['hello','world','china']
b = dict.fromkeys(a,'123')
print(b)
c= b.setdefault('hellofff','不存在')
print(c)
print(b)
```

