#学习python的心得体会 学习方式主要通过网上一些资料以及教程
+ 廖雪峰的官方网站教程[Python教程] (http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000)

+ python 主要通过解释器来运行 所以运行速度上不比c以及c++
+ python的主要用途 编写一些脚本工具 以及开发一些小的应用程序 开发web应用
+ python编写工具ide和其它语言语言一样很多 目前我学习主要用sublime (eclipse+pydev)据说提示不错 其它ide(pycharm)
+ python代码编写结束不能用;结尾
+ python打印输出 主要用print 方法 字符串连接不用+ 而是用,
+ python注释代码使用# 不用//或者/**/
+ python没有显示的数据类型 但是还是有数据类型的概念在在设置变量的时候可以这样写
>
     test = 'a' 字符  
     test = 10  整形  十六进制表示方法0x前缀  
     test = 10.0 浮点  
     test = true 布尔值  
     test = None 以及None值python特有的值 特殊的空值  

+ python字符串 用'' 如果像表示''可以用"" 也可用转义字符\
+ python如果多个字符需要转义 print r'\\\fsfds\f' 如此
+ python '''...'''表示多行的内容 要比\n方便一些
+ python 逻辑判断  
>
                   and 等同于 && 
				   or 等同于 ||
				   not 等同于 ！

+ python 没有常量类型 但是都会以大写字母表示常量 但这个变量还是可以经行赋值 约定大写字母就是常量
+ python u'aaaa' Unicode码 这里有个知识点 计算机在运行的时候用的是Unicode码 但是保存成文档后会转换+ 成utf-8

+ \#!/usr/bin/env python //这两行代码 说明在mac和linux系统里可以双击执行
+ \# -*- coding: utf-8 -*- //说明python类里的编码格式

+ print输出格式与c语言 使用占位符 %d %s 这种类型方式  '%2d-%02d' % (3, 1)  输出' 3-01'
+ python 3.x 中 u'xxxx'和'xxxx' 是一样的

+ python数据容器分成数组形式以及字典形式
+ 数组形式
>	`list  classmates = ['Michael', 'Bob', 'Tracy']`
	`tuple  classmates = ('Michael', 'Bob', 'Tracy')` tuple如果只一个数据 （1,）这样写就对了
	list与tuple的区别 就是list可以改变数值tuple不能改变数值的内容

+ 字典形式
>	`dict  d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}`  
	`d.pop('key')` 删除key  
    set 方式与dict一样 只是没有value值并且key只能是list方式 set中不能用重复的数据 即时有重复的数据也会被set过滤掉  
    s = set([1, 1, 2, 2, 3, 3])  
	set([1, 2, 3])

+ python条件判断
>  if <条件判断1>:    
   	 	<执行1>	  
   elif <条件判断2>:   
    	<执行2>   
   elif <条件判断3>:   
    	<执行3>    
   else:   
    	 <执行4>
 
+ python循环方法
> names = ['Michael', 'Bob', 'Tracy']  
 	for name in names:  
    print name 

+ python控制台程序 `raw_input()` 方法可以价加参数提示`raw_input('birth: ')`

+ python有许多内置函数可以通过[python官网查询](https://docs.python.org/2/library/functions.html)进行查询或者直接使用help(xxx)方法 例如help(abs)
+ python函数与其它语言差不多 比较特别的是python函数可以返回多个返回值 函数可以同时返回多个值，但其实就是一个tuple
>
	def move(x, y, step, angle=0):  
    	nx = x + step * math.cos(angle)   
	    ny = y - step * math.sin(angle)  
	return nx, ny  

+ python函数的 也可以先as3.0一样传入可变参数 用法是传入list或者tuple容器
>
	def calc(numbers): 
    	sum = 0  
	    for n in numbers:  
         sum = sum + n * n 
        return sum   
 	 calc([1, 2, 3])  
	 14 
 	 calc((1, 3, 5, 7))  
	 84 

不过这样有事比较麻烦 可以直接传入数据的方法 就是在参数前加入*
>
	def calc(*numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum
 	calc(1, 2)

如果已经有list和tuple可以直接用
>
	nums = [1, 2, 3]
    calc(*nums) 代替
   	calc(nums[0], nums[1], nums[2])

+ python函数还有一种关键字参数 **两个星号 关键字参数只能传入dict参数类型
+ python也一样可以调用递归 使用递归函数的优点是逻辑简单清晰，缺点是过深的调用会导致栈溢出。

+ ##python的一些高级特性  
  **切片**  
> 
	直接在数组中取值 不用循环就可以获取数组中的元素
	L[0:3]
	['Michael', 'Sarah', 'Tracy']
	L[0:3]表示，从索引0开始取，直到索引3为止，但不包括索引3。即索引0，1，2，正好是3个元素。  
	通过:经行获取  
>	
	前10个数，每两个取一个：
	L[:10:2]
	[0, 2, 4, 6, 8]
    第2个参数隔开数   

>
	'ABCDEFG'[:3]
	'ABC'
	'ABCDEFG'[::2]
	'ACEG'
    字符串也可以看成数组经行操作

  **迭代**

	python的迭代一般用的是
	for a in list

----------
但是如果是dict作为需要迭代的方法
  
	d = {'a': 1, 'b': 2, 'c': 3}
	for key in d:
	... print key
	...
	a
	c
	b

----------
默认情况下，dict迭代的是key。如果要迭代value，可以用for value in d.itervalues()如果要同时迭代key和value，可以用for k, v in d.iteritems()。

----------
当我们使用for循环时，只要作用于一个可迭代对象，for循环就可以正常运行，而我们不太关心该对象究竟是list还是其他数据类型。
如何判断是否为可迭代

	from collections import Iterable
	isinstance('abc', Iterable) # str是否可迭代
	True
	isinstance([1,2,3], Iterable) # list是否可迭代
	True
	isinstance(123, Iterable) # 整数是否可迭代
	False

----------
python如何在循环中获取循环下标呢? 通过enumerate函数

	for i, value in enumerate(['A', 'B', 'C']):
		   print i, value
	...
	0 A
	1 B
	2 C

**列表生成器**

	[x * x for x in range(1, 11)]
	[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
可以通过[]中的内容经行列表的生成 甚至可以多重循环

	[x * x for x in range(1, 11) if x % 2 == 0]
	[4, 16, 36, 64, 100]

**生成器**

列表生成器虽然好用，但是同时如果生成很多数据可能内存不够。所以python就有生成器在 Python中，这种一边循环一边计算的机制，称为生成器（Generator）
如何创建一个Generator 就是将列表生成器的[]改成() 然后调用next()就可以输出了。但是一般情况都是for n in Generator 这种方法

还有一种生成器就是函数的方式 通过yield关键字 来实现

	def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        yield b
        a, b = b, a + b
        n = n + 1

+ ##高阶函数

	map()  
	map()函数接收两个参数，一个是函数，一个是序列，map将传入的函数依次作用到序列的每个元素，并把结果作为新的list返回。

----------

	 def f(x):
     return x * x	
	 map(f, [1, 2, 3, 4, 5, 6, 7, 8, 9])
	 [1, 4, 9, 16, 25, 36, 49, 64, 81]

----------
reduce（）  
reduce把一个函数作用在一个序列[x1, x2, x3...]上，这个函数必须接收两个参数，reduce把结果继续和序列的下一个元素做累积计算

	def add(x, y):
	     return x + y

	reduce(add, [1, 3, 5, 7, 9])
	25
filter()

filter()把传入的函数依次作用于每个元素，然后根据返回值是True还是False决定保留还是丢弃该元素。

	def is_odd(n):
    return n % 2 == 1

	filter(is_odd, [1, 2, 4, 5, 6, 9, 10, 15])
	结果: [1, 5, 9, 15]
sorted()

常规定，对于两个元素x和y，如果认为x < y，则返回-1，如果认为x == y，则返回0，如果认为x > y，则返回1，这样，排序算法就不用关心具体的比较过程，而是根据比较结果直接排序。

	def reversed_cmp(x, y):
    if x > y:
        return -1
    if x < y:
        return 1
    return 0

----------
	 sorted([36, 5, 12, 9, 21], reversed_cmp)
	[36, 21, 12, 9, 5]

+ python函数可以作为返回值 作闭包函数  
  	匿名函数  
  	关键字lambda表示匿名函数，冒号前面的x表示函数参数。
 	匿名函数有个限制，就是只能有一个表达式，不用写return，返回值就是该表达式的结果。
>
    map(lambda x: x * x, [1, 2, 3, 4, 5, 6, 7, 8, 9])    
    [1, 4, 9, 16, 25, 36, 49, 64, 81]  

+ python装饰器
def log(func):  
>
	def wrapper(*args, **kw):  
    print 'call %s():' % func.__name__  
    return func(*args, **kw)  
    return wrapper  
>	
	@log  
	def now():   
    print '2013-12-25'  
	把@log放到now()函数的定义处，相当于执行了语句：  
	now = log(now)  

+ 偏函数
 
	简单总结functools.partial的作用就是，把一个函数的某些参数给固定住（也就是设置默认值），返回一个新的函数，调用这个新函数会更简单。
>
	import functools  
	int2 = functools.partial(int, base=2) 
	int2('1000000')  
	64  
    int2('1010101')  
	85    
   

----------

##模块
+ 包的概念 
  python一个文件夹就可以是一个包 但是文件夹下边必须有
`__init__.py`文件 文件内容可以为空 如果没有该文件python将视为普通的文件夹
+ 使用模块  
  `import xxx` 就可以导入模块了  
   模块中使用的别名的情况 

>  
	try:  
     	import cStringIO as StringIO  
	except ImportError: # 导入失败会捕获到ImportError
		import StringIO  
  
+ 作用域  
  python中所有的变量其实都是public 但是我们可以使用_xx或者__xx的命名方式来约束大家是public还是private
+ 安装第三包 中有许多包的管理概念推荐看一下[zengrong](http://zengrong.net/post/2169.htm) 的说明教程比较系统
+ 特别提供了`_future__`模块，让你在旧的版本中试验新版本的一些特性。

#面向对象的python
+ python的定义类方法 使用class
+  python构造函数用`__init__(self,xxxx)`必定有self  
>
	bart = Student('Bart Simpson', 59)  
	bart.name  
	'Bart Simpson'  
	bart.score  
	59

+ 类中定义函数 要定义一个方法，除了第一个参数是self外
+ 在类中定义属性 __xx就可以放置外部进行访问 再类中定义__xx其实也是可以访问的只是python解释器只是将__xx改成了`__class_xx`(`__类名__方法名`)
+  python 也有set以及get方法`set_xxx(self,arg)`以及`get_xxx(self)` `@property`的实现才能达到真正的set和get方法
+  python多态与继承 与其它语言一样 没什么好表
+  python type(xxx)展示出类的类型 isinstance(xxx,calssxx)判断实例是否是这个了类的实例 dir(xxx)获得一个对象的所有属性和方法getattr()、setattr()以及hasattr()判断获取设置类属性的方法
+ python可以动态添加属性以及方法
>  
	def set_age(self, age): # 定义一个函数作为实例方法  
	    self.age = age  	
	 from types import MethodType  
    s.set_age = MethodType(set_age, s, Student) # 给实例绑定一个方法  
	s.set_age(25) # 调用实例方法  
	s.age # 测试结果  
	25  
	
+ python通过定义`__slots__`来限制动态绑定的属性
+ python可以实现多重继承
>   
	`class MyTCPServer(TCPServer, CoroutineMixin):
    pass`

+ #python定制类  

+ 通过设置__str__()以及__repr__()输出格式
>
	class Student(object):  
    	def __init__(self, name):  
        	self.name = name  
    	def __str__(self):  
        	return 'Student object (name=%s)' % self.name  
    	__repr__ = __str__

+  通过设置`__iter__`来实现迭代循环 只要实现`next(self)`方法  

>
	class Fib(object):  
    	def __init__(self):  
        	self.a, self.b = 0, 1 # 初始化两个计数器a，b
    	def __iter__(self):  
        	return self # 实例本身就是迭代对象，故返回自己
    	def next(self):  
        	self.a, self.b = self.b, self.a + self.b # 计算下一个值  
        	if self.a > 100000: # 退出循环的条件  
            	raise StopIteration();  
        	return self.a # 返回下一个值  

+ 通过设置`__getitem__()`来实现list的取值操作
>
	class Fib(object):  
		def __getitem__(self, n):  
        	a, b = 1, 1  
        	for x in range(n):  
            	a, b = b, a + b  
        	return a  

`__setitem__()` `__delitem__()` 来实现dict可以作key的object

+ python `__getattr__()`如果类中没有设置的属性和函数 就可以查找这个方法来获取属性和函数
>
	class Student(object):
    	def __init__(self):
        	self.name = 'Michael'
    	def __getattr__(self, attr):
        	if attr=='score':
        	    return 99

+ python`__call__()`用于调用类实例的方法instance()
>
	class Student(object):
    	def __init__(self, name):
        	self.name = name
    	def __call__(self):
        	print('My name is %s.' % self.name)
	 s = Student('Michael')
	 s()
	 My name is Michael.

+ python通过callable()函数，我们就可以判断一个对象是否是“可调用”对象