1. 基础进阶02
	1. 模块
		Definition
			模块是一个包含所有你定义的函数和变量的文件，其后缀名是.py。模块可以被别的程序引入，以使用该模块中的函数等功能。这也是使用 python 标准库的方法。
		Notice
			1. 当解释器遇到 import 语句，如果模块在当前的搜索路径就会被导入。
			2. 搜索路径是一个解释器会先进行搜索的所有目录的列表。如想要导入模块 support，需要把命令放在脚本的顶端：
			3. from … import 语句   模块中导入一个指定的部分到当前命名空间中
			4. __name__属性
				一个模块被另一个程序第一次引入时，其主程序将运行。如果我们想在模块被引入时，模块中的某一程序块不执行，我们可以用__name__属性来使该程序块仅在该模块自身运行时执行。
				if __name__ == '__main__':
				   print('程序自身在运行')
				else:
				   print('我来自另一模块')
			5. 内置的函数 dir() 可以找到模块内定义的所有名称。以一个字符串列表的形式返回,如果没有给定参数，那么 dir() 函数会罗列出当前定义的所有名称
	2. 输入输出
		输出格式美化
			1. Python两种输出值的方式: 表达式语句和 print() 函数。
			2. 第三种方式是使用文件对象的 write() 方法，标准输出文件可以用 sys.stdout 引用。
			3. 如果你希望输出的形式更加多样，可以使用 str.format() 函数来格式化输出值。
			4. 如果你希望将输出的值转成字符串，可以使用 repr() 或 str() 函数来实现。
		Case
			1. print('{}网址： "{}!"'.format('菜鸟教程', 'www.runoob.com'))
				菜鸟教程网址： "www.runoob.com!"				括号及其里面的字符 (称作格式化字段) 将会被 format() 中的参数替换。
			2. print('常量 PI 的值近似为 {0:.3f}。'.format(math.pi))
				常量 PI 的值近似为 3.142。
			3. print('{0:10} ==> {1:10d}'.format(name, number))
				Runoob     ==>          2
				Taobao     ==>          3
				Google     ==>          1
		Function
			1. str()： 函数返回一个用户易读的表达形式。   不带引号
			2. repr()： 产生一个解释器易读的表达形式。		带引号
			3. input(): 用户输入
			
	3. File
		Function 
			1. open(filename, mode) : 返回文件对象
				filename：包含了你要访问的文件名称的字符串值。
				mode：决定了打开文件的模式：只读，写入，追加等。所有可取值见如下的完全列表。这个参数是非强制的，默认文件访问模式为只读(r)。
			2. file.close()
				关闭文件。关闭后文件不能再进行读写操作。
			3. file.flush()
				刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。
			4. file.isatty()
				如果文件连接到一个终端设备返回 True，否则返回 False。
			5. file.next()
				返回文件下一行。
			6. file.read([size])
				从文件读取指定的字节数，如果未给定或为负则读取所有。
			7. file.readline([size])
				读取整行，包括 "\n" 字符。
			8. file.readlines([sizeint])
				读取所有行并返回列表，若给定sizeint>0，返回总和大约为sizeint字节的行, 实际读取值可能比 sizeint 较大, 因为需要填充缓冲区。
			9. file.seek(offset[, whence])
				设置文件当前位置
			10. file.tell()
				返回文件当前位置。
			11. file.write(str)
				将字符串写入文件，返回的是写入的字符长度。
			12. file.writelines(sequence)
				向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。
		Notice
			1. 使用 open() 方法一定要保证关闭文件对象，即调用 close() 方法。
	4. 错误和异常
		Definition
			1. 语法错误
				语法错误或者称之为解析错
			2. 异常
				运行期检测到的错误被称为异常
		Case
			1. while True:
		        try:
		            x = int(input("Please enter a number: "))
		            break
		        except (RuntimeError, TypeError, NameError):
		            print("Oops!  That was no valid number.  Try again   ")
		        else:
			        print(x)
			    finally:
			    	print('继续执行')
		        1. 首先，执行try子句（在关键字try和关键字except之间的语句）
		       	2. 如果没有异常发生，忽略except子句，try子句执行后结束。
		       	3. 如果在执行try子句的过程中发生了异常，那么try子句余下的部分将被忽略。如果异常的类型和 except 之后的名称相符，那么对应的except子句将被执行。最后执行 try 语句之后的代码。
		       	4. 如果一个异常没有与任何的except匹配，那么这个异常将会传递给上层的try中
		       	5. else语句将在try子句没有发生任何异常的时候执行
		       	6. 不管 try 子句里面有没有发生异常，finally 子句都会执行
		    2. raise 
		    	1. 抛出一个指定的异常
		    	1. 它必须是一个异常的实例或者是异常的类（也就是 Exception 的子类）
	5. OS
		Definition
			1. os 模块提供了非常丰富的方法用来处理文件和目录
		Function
			1. os.getcwd()   返回当前工作目录
			2. http://www.runoob.com/python3/python3-os-file-methods.html