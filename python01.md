1.基础知识理解

```python
1.1数据类型
	数字:Number（数字）---->整数(int),布尔(bool),浮点(float),负数(complex )
	字符串:字符类型(String)
	列表:List
	元组:Tuple
	集合:Set
	字典:Dictionary
1.2 Notice
	不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；
	可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。
1.3 实例
1.3.1 Number
	1.3.1.1 整数(int)
			a=20
			print(type(a))-----><class 'int'>
	1.3.1.2 布尔(bool)
			b=True
			print(type(b))-----><class 'bool'>
	1.3.1.3 浮点(float)
			c=5.5
			print(type(c))-----><class 'float'>
	1.3.1.4 复数(complex)
			d=4+3j
			print(type(d))-----><class 'complex'>
			Notice:
				1.对于类型的判断可以使用isinstance(类型1,类型2)返回的是布尔值
				2.type()不会认为子类是一种父类类型。isinstance()会认为子类是一种父类类型。
				3.del 语法可以删除对象的引用和对象
				4.在除法运算中    / 返回一个浮点数，// 返回一个整数。
1.3.2 字符串(String)
		Case
			a="abcdef"
			变量[头下标:尾下标]
			a[0:-1] 截取第一个到倒数第二个的所有字符
			a[0]	截取字符串的第一个字符
			a[2:5]  截取第三个开始到第五个字符
			a[2:]	截取从第三个开始到最后的字符
		Notice
			1.字符使用单引号和双引号括起来,反斜杠\转义特殊字符
			2.字符串的下标,从左往右0开始,从右往左-1开始
			3.加号 + 是字符串的连接符， 星号 * 表示复制当前字符串，紧跟的数字为复制的次数
			4.下标的截取左包含,右不包含.
			5.字符串前面加上r可以输出原始字符,取消反斜杠的转义
			6.python中的字符串不能改变,即a[0]='c'会失败
		Function
			1.去除空格和特殊字符
				1.1 a.strip()		去掉空格和换行符
				1.2 a.strip('xx')	去除某个字符串
				1.3 a.istrip() 		去除左边的空格和换行符
				1.4 a.rstrip()		去除右边的空格和换行符
			2.字符串的搜索和替换
				2.1 a.count('x') 	查找某个字符在字符串里面的次数
				2.2 a.capitalize()	首字母大写
				2.3 a.center(n,'-')	首尾用-补齐
				2.4 a.find('x')		找到某个字符返回下标,多个返回第一个,不存在返回-1
				2.5 a.index('x')	找到某个字符返回下标,多个时返回第一个,不存在则报错
				2.6 a.replace(oldstr,newstr)	字符串替换
				2.7 a.format()		字符串格式化
				2.8 a.divmod(num1,num2)		返回一个元组,第一个值为相除的整数值,第二个为余数
			3.字符串的测试和替换函数
				3.1 a.startwith(prefix[,start[,end]])	是否以prefix开头
				3.2 a.endwith(suffix[,start[,end]]) 是否以suffix结尾
				3.3 a.isalnum()		是否全是字母和数字,并至少有一个字符
				3.4 a.isalpha() 是否全是字母,并至少有一个字符
				3.5 a.isdigit() 是否全是数字,并至少有一个字符
				3.6 a.isspace()	是否全是空白字符,并至少有一个字符
				3.7 a.islower()	a中的字母是否全是小写
				3.8 a.isupper()	a中的字母是否全是大写
				3.9 a.istitle()	a中的首字母是否大写
			4.字符串的分割
				4.1 a.split()	默认按照空格分割
				4.2 a.split(',') 按照逗号分割,返回一个元组
			5.连接字符串
				5.1 ','.join(a) 用逗号连接a变成一个字符串,a可以是字符,列表,字典(可迭代的对象).int类型不能被连接
			6.导入模块
				import string 
				string.ascii_uppercase  所有大写字母
				string.ascii_lowercase 所有小写字母
				string.ascii_letters  所有字母
				string.digits  所有数字
1.3.3 列表(List)
		Definition
			1. 类似与java里面的List集合,但是区别在于可以存储不同的数据类型
			   	list=['abcf',32,2.32]
			   	list2=['c']
		Case
			list[0] 	获取列表中的第一个元素
			list[1:4] 	获取列表中第二个到第5个元素,不包含第五个元素
			list[1:] 	获取从第二个元素开始到最后的所有元素
			list+list2	2个列表的拼接
		Notice
			1. 列表可以完成大多数集合类的数据结构实现,列表中的数据类型可以不相同
			2. 列表和字符串一样可以被索引和截取,列表被截取后返回一个包含所需元素的新列表
			3. 列表于字符串不同,里面的值是可以改变的,即list[0]='a'是可以执行的
			4. list中有字符串和数字的时候不能排序,排序针对同类型
		Function
			1. 创建列表
				list=['1',2,'abcd']
				lsit=[] 空列表
			2. 添加新元素
				list.append()	在list末尾增加一个元素
				list.insert(n,'x')	指定位置增加元素,如果指定下标不存在,则在末尾增加
				list.extend(list2) 合并list和list2中元素,相当于元素拼接
			3. 查看列表中的值
				print(list) 	遍历列表  等价于 for i in list 
													print(i)
				list.count(x) 	查看某个元素在列表中的个数,不存在则返回0
				list.index(x) 	找到元素的下标,如果多个返回第一个,不存在则报错
			4. 删除list中的元素
				list.pop()		删除最后一个元素
				list.pop(n)		删除指定的下标的元素,如果下标不存在则报错
				list.remove(x)	删除指定元素,如果有多个,删除第一个
				del list[n] 	删除指定下标对应的元素
				del list 		删除整个list列表(删除对象)
			5. 排序和反转
				list.reverse()	将列表反转
				list.sort()		列表排序,默认升序
				list.sort(reverse=Ture) 降序排列
			6. 列表操作的函数
				len(list)		计算列表中元素个数
				max(list)		返回列表中元素最大值
				min(list)		返回列表中元素最小值
				list(seq)		将元组转换为列表
				enumerate		打印元素对应的下标
			7. 列表生成式
				列表生成式即List Comprehensions，是Python内置的非常简单却强大的可以用来创建list的生成式。
				case 1 :	
					1-11的元素列表
					list = list(range(1,11))
					list [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
				case 2 :
					1-11中数字的平方元素列表
					list = list(x * x for x in range(1,11))
					list = [1x1, 2x2, 3x3, ..., 10x10]
				case 3 :
					1-11中偶数的平方元素列表
					list = list(x * x for x in range(1,11) if x%2== 0)
					list = [4,16,36,64,100]
				case 4 :
					使用两层循环，可以生成全排列
					list = [m + n for m in 'ABC' for n in 'XYZ']
					list = ['AX', 'AY', 'AZ', 'BX', 'BY', 'BZ', 'CX', 'CY', 'CZ']
				case 5 :
					for循环其实可以同时使用两个甚至多个变量，比如dict的items()可以同时迭代key和value
					d = {'x': 'A', 'y': 'B', 'z': 'C' }
					for k, v in d.items():
						print(k, '=', v)
					结果: y = B,x = A,z = C
				case 6 :
					列表切片的使用【start:stop:step】不包含stop 索引值
1.3.4 元组(Tuple)
		Definition
			元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 () 里，元素之间用逗号隔开。
		Notice
			1. 构造包含0个或1个元素的元组比较特殊,需要额外额语法规则
				tup1 = ()    # 空元组
				tup2 = (20,) # 一个元素，需要在元素后添加逗号
			2. string、list和tuple都属于sequence（序列）。
			3. 与字符串一样,元组的元素不能修改
			4. 元组索引和切片和字符串,列表相同
			5. 元组也可以使用+来实现拼接操作
		Functionn
			1. cmp(tuple1,tuple2) 比较2个元组元素
			2. 其他的于list基本相同
1.3.5 集合(Set)
		Definition
			集合(Set)是一个或多个形态各异的大小整体组成的,构成集合的事物或对象称作元素或是成员,基本功能是进行成员关系测试或删除重复元素
		Case
			1. 集合的创建
				set1 = {value1,value2}
				set(value1)
			2. 集合运算
				a-b 	a和b的差集			difference a中存在b中不存在的值
				a+b		a和b的并集			union	合并a中的元素和b中的元素
				a&b  	a和b的交集			intersection	取交集
				a^b 	a和b中不同时存在的元素	symmetric_difference 对称交集
1.3.6 字典(Dictionary)
		Definition
			内置数据类型,无序的对象集合,字典是一种映射类型,用{}来标识,是key:value对的集合
			对于key必须使用不可变数据类型,key必须唯一
		Case 
			1. 创建字典
				dict = {}						创建空字典
				dict['one'] = "1 - 菜鸟教程"
				dict[2]     = "2 - 菜鸟工具"		赋值key为2,value为"2 - 菜鸟工具"
				tinydict = {'name': 'runoob','code':1, 'site': 'www.runoob.com'}	
				print(tinydict.keys())			输出所有的键值
				print(tinydict.values())		输出所有的值
				dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)]) 	通过键值对序列构造字典
				{'Taobao': 3, 'Runoob': 1, 'Google': 2}
		Function
			1. 删除字典元素
				del dict[key] 		删除对应的key的value对
				dict.clear()		清空字典的所有条目
			2. 比较两个字典元素
				cmp(dict1,dict2)
			3. 输出字典打印的字符串表示
				str(dict)
			4. 判断字典中是否存在对应的key
				dict.has_key(key) 存在返回True,不存在返回False
			5. 将一个字典的信息填充到原来的字典中
				dict.update()
1.4 数据类型转换
	int(x)		将x转换为整数
	float(x)	将x转换为浮点型
	str(x)		将对象x转换为字符串 		str('111')   111
	repr(x)		将对象x转换为表达式字符串 repr('111')  '111'
	eval（str）	将字符串string对象转化为有效的表达式参与求值运算返回计算结果
	tuple(s)	将序列s转换为一个元组
	list(s)		将序列s转换为一个列表
	set(s)		转换为可变集合
	dict(d)		创建一个字典.d必须是一个序列(key,value)元组
	chr(x)		将一个整数转换为一个字符
	ord(x)		将一个字符转换为它的整数值
	hex(x)		将一个整数转换为一个十六进制的字符串
	oct(x)		将一个整数转换为一个八进制的字符串
```