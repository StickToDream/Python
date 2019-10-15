1. 基础进阶01
	1. 条件控制
		Definition
			Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。
		Case
			1.1 if 语句
				if condition_1:
				    statement_block_1
				elif condition_2:
				    statement_block_2
				else:
				    statement_block_3
		Notice
			1.1 每个条件后面要使用冒号 :，表示接下来是满足条件后要执行的语句块。
			1.2 使用缩进来划分代码块,相同缩进数的语句在一起组成一个语句块
			1.3 在Python中不存在 switch--case 语句
			1.4 if嵌套的判断要注意语句块的划分
	2. 循环语句
		2.1 for
			1. for可以遍历任何序列的项目,etc 列表或者字符串
			2. 格式:for <variable> in <sequence>:
					    <statements>
					else:
					    <statements>
			3. 遍历数字序列,可以使用内置的range()函数,range(a,b,c) a,b为区间,c为步长
			4. list[range(5)]	通过range函数来创建列表
		2.2 while 
			1. 无限循环,通过一个标志来让其终止循环
			2. while ... else ...
		2.3 break和continue,pass
			1. break 语句可以跳出 for 和 while 的循环体。如果你从 for 或 while 循环中终止，任何对应的循环 else 块将不执行。
			2. break 跳出循环,continue 跳过当前循环,执行下一轮循环
			3. pass为占位语句
	3. 迭代器和生成器
		3.1 迭代器
			Definition
				1. 访问元素的一种方式
				2. 迭代器是一个可以记住遍历位置的对象
				3. 迭代器对象从集合的第一个元素开始访问,知道所有的元素被访问结束.迭代器只能往前不能往后
			Funciton
				1. next()
				2. iter()
			Case
				1. list=[1,2,3,4]
 				   	it = iter(list)    		# 创建迭代器对象
				 	print (next(it))   	1	# 输出迭代器的下一个元素
 					print (next(it)) 	2
 				2. StopIteration 
 					while True:
					    try:
					        print (next(it))
					    except StopIteration:
					        sys.exit()
 					异常用于标识迭代的完成，防止出现无限循环的情况，在 __next__() 方法中我们可以设置在完成指定循环次数后触发 StopIteration 异常来结束迭代。
 		3.2 生成器
 			Definition
 				1. 使用了 yield 的函数被称为生成器（generator）
 				2. 生成器是一个返回迭代器的函数，只能用于迭代操作，更简单点理解生成器就是一个迭代器。
 				3. 在调用生成器运行的过程中，每次遇到 yield 时函数会暂停并保存当前所有的运行信息，返回 yield 的值, 并在下一次执行 next() 方法时从当前位置继续运行。
	4. 函数
		Definition
			1. 函数是组织好的,可以重复使用,用来实现单一或相关联功能的代码块
			2. 函数能提高应用的模块性和代码的重复利用率
			3. 自定义一个函数
				3.1 规则
					(1). 函数代码块以 def 关键词开头，后接函数标识符名称和圆括号 ()。
					(2). 任何传入参数和自变量必须放在圆括号中间，圆括号之间可以用于定义参数。
					(3). 函数的第一行语句可以选择性地使用文档字符串-----用于存放函数说明。
					(4). 函数内容以冒号起始，并且缩进。
					(5). return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。
		Case
			1. def area(width, height):
    			return width * height
    		2. 函数与函数之间可以相互调用
    		3. 参数传递
    			a=[1,2,3]		a="Runoob"
				以上代码中，[1,2,3] 是 List 类型，"Runoob" 是 String 类型，而变量 a 是没有类型，她仅仅是一个对象的引用（一个指针），可以是指向 List 类型对象，也可以是指向 String 类型对象。
	5. 数据结构
		List 
			Function
				append 		把元素添加到列表的结尾
				extend 		添加指定列表的所有元素来扩充列表
				insert		指定位置插入元素,第一个参数为索引,第二个参数为值
				remove		删除列表中值为x的第一个元素,如果没有这个元素,会报错
				pop			指定位置移除元素,返回值
				clear		移除列表中所有的项
				index 		返回指定索引的值
				count		返回某个元素出现的次数
				sort		对列表中元素进行排序
				reverse		列表中元素倒序
				copy		复制列表元素
			Extend
				1. 列表当作堆栈使用
					堆栈作为特定的数据结构，最先进入的元素最后一个被释放（后进先出）。用 append() 方法可以把一个元素添加到堆栈顶。用不指定索引的 pop() 方法可以把一个元素从堆栈顶释放出来 (尾部为栈的开始)
				2. 列表当作队列使用 (效率低)
					也可以把列表当做队列用，只是在队列里第一加入的元素，第一个取出来；但是拿列表用作这样的目的效率不高。在列表的最后添加或者弹出元素速度快，然而在列表里插入或者从头部弹出速度却不快（因为所有其他的元素都得一个一个地移动）。
				3. 列表推导式
					列表推导式提供了从序列创建列表的简单途径。通常应用程序将一些操作应用于某个序列的每个元素，用其获得的结果作为生成新列表的元素，或者根据确定的判定条件创建子序列。每个列表推导式都在 for 之后跟一个表达式，然后有零到多个 for 或 if 子句。返回结果是一个根据表达从其后的 for 和 if 上下文环境中生成出来的列表。如果希望表达式推导出一个元组，就必须使用括号。
					Case
						1. vec = [2, 4, 6]   [3*x for x in vec]
						2. [[x, x**2] for x in vec]
						3. [3*x for x in vec if x > 3]
						4. [vec1[i]*vec2[i] for i in range(len(vec1))]
				4. 嵌套列表解析
					Case 
						1. matrix = [ [1, 2, 3, 4],[5, 6, 7, 8],[9, 10, 11, 12],]
						2. [[row[i] for row in matrix] for i in range(4)]   [[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
				5. del语句
					Defination
						使用 del 语句可以从一个列表中依索引而不是值来删除一个元素。这与使用 pop() 返回一个值不同。可以用 del 语句从列表中删除一个切割，或清空整个列表（我们以前介绍的方法是给该切割赋一个空列表）
				6. 元组和序列
					Notice
						1. 元组由若干逗号分隔的值组成
						2. 元组在输出时总是有括号的，以便于正确表达嵌套结构。在输入时可能有或没有括号， 不过括号通常是必须的（如果元组是更大的表达式的一部分）
				7.集合
					Notice
					 	1. 集合是一个无序不重复元素的集。基本功能包括关系测试和消除重复元素。
 						2. 可以用大括号({})创建集合。注意：如果要创建一个空集合，你必须用 set() 而不是 {} ；后者创建一个空的字典
 						3. 也支持推导式
 				8. 字典
 					Notice
 						1. 序列是以连续的整数为索引，与此不同的是，字典以关键字为索引，关键字可以是任意不可变类型，通常用字符串或数值。
 						2. 理解字典的最佳方式是把它看做无序的键=>值对集合。在同一个字典之内，关键字必须是互不相同。一对大括号创建一个空的字典：{}。
 				