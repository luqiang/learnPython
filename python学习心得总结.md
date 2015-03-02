+学习python的心得体会 学习方式主要通过网上一些资料已经教程
+[Python教程] (http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000)

+python 主要通过解释器来运行 所以运行速度上不比c以及c++
+python的主要用途 编写一些脚本工具 以及开发一些小的应用程序 开发web应用
+python编写工具ide和其它语言语言一样很多 目前我学习主要用sublime (eclipse+pydev)据说提示不错 其它ide(pycharm)
+python代码编写结束不能用;结尾
+python打印输出 主要用print 方法 字符串连接不用+ 而是用,
+python注释代码使用# 不用//或者/**/
+python没有显示的数据类型 但是还是有数据类型的概念在在设置变量的时候可以这样写

>test = 'a' 字符
test = 10  整形  十六进制表示方法0x前缀    
test = 10.0 浮点
test = true 布尔值
test = None 以及None值python特有的值 特殊的空值

python字符串 用'' 如果像表示''可以用"" 也可用转义字符\
python如果多个字符需要转义 print r'\\\fsfds\f' 如此
python '''...'''表示多行的内容 要比\n方便一些
python 逻辑判断  and 等同于 && 
				 or 等同于 ||
				 not 等同于 ！
python 没有常量类型 但是都会以大写字母表示常量 但这个变量还是可以经行赋值 约定大写字母就是常量
python u'aaaa' Unicode码 这里有个知识点 计算机在运行的时候用的是Unicode码 但是保存成文档后会转换成utf-8

>\#!/usr/bin/env python //这两行代码 说明在mac和linux系统里可以双击执行
>\# -*- coding: utf-8 -*- //说明python类里的编码格式

print输出格式与c语言 使用占位符 %d %s 这种类型方式  '%2d-%02d' % (3, 1)  输出' 3-01'
python 3.x 中 u'xxxx'和'xxxx' 是一样的

python数据容器分成数组形式以及字典形式
数组形式
	list  classmates = ['Michael', 'Bob', 'Tracy']
	tuple  classmates = ('Michael', 'Bob', 'Tracy') tuple如果只一个一个数据 （1,）这样写就对了
	list与tuple的区别 就是list可以改变数值tuple不能改变数值的内容
字典形式
	dict  d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
	d.pop('key') 删除key  
    set 方式与dict一样 只是没有value值并且key只能是list方式 set中不能用重复的数据 即时有重复的数据也会被set过滤掉
    >>> s = set([1, 1, 2, 2, 3, 3])
	>>> s
	set([1, 2, 3])

python条件判断
if <条件判断1>:
    <执行1>
elif <条件判断2>:
    <执行2>
elif <条件判断3>:
    <执行3>
else:
    <执行4>
python循环方法
names = ['Michael', 'Bob', 'Tracy']
for name in names:
    print name

python控制台程序 raw_input() 方法可以价加参数提示raw_input('birth: ')

python有许多内置函数可以通过https://docs.python.org/2/library/functions.html进行查询或者直接使用help(xxx)方法 例如help(abs)
python函数与其它语言差不多 比较特别的是python函数可以返回多个返回值 函数可以同时返回多个值，但其实就是一个tuple
def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny

python函数的 也可以先as3.0一样传入可变参数 用法是传入list或者tuple容器
def calc(numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum
 >>> calc([1, 2, 3])
14
>>> calc((1, 3, 5, 7))
84
不过这样有事比较麻烦 可以直接传入数据的方法 就是在参数前加入*
def calc(*numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum
>>> calc(1, 2)
如果已经有list和tuple可以直接用
>> nums = [1, 2, 3]
>>> calc(*nums) 代替
>>> calc(nums[0], nums[1], nums[2])
python函数还有一种关键字参数 **两个星号 关键字参数只能传入dict参数类型