## Python-re模块
pat = re.compile(PATTERN)

- 字符串的查找替换
	- re.sub(pat,newpat,s)
- 字符串查找与匹配
	- re.findall(pat, s)
	- re.match(pat, s)
	- re.search(pat, s)
- 应用
	- 匹配网址url、邮箱
	- 使用中文正则表达式匹配指定的中文字符串
	- 使用正则表达式匹配提取字符串

- 案例
	- PATTERN=r'(?:https?:\/\/)?(?:www\.)?(?:github|gitee|gitlab)\.com\/[\w\-]+\/[\w\-]+\/(?:pulls|pull|merge_requests)\/[0-9]+'

		- `+ ：匹配前面的字符一次或多次`
		- `?：匹配前面的字符出现0次或1次`
		- `*：匹配前面的字符出现0次或多次`
		-` \w：匹配任意一个字母或数字字符`
		- `\s : 匹配任何空白字符`
		- `\d ： 匹配任何数字字符`
		- `(..)：匹配括号中的字符串`
		- `(?:) ：是一个非捕获组，表示匹配但不捕获括号中的内容`
		- `[...]：匹配方括号中的任意一个字符`
		- `|：或操作符`

## Python-OS模块
D:\工作\gitlab项目\ospp-report\data_mgmt_ospp_report\data_analysis\__init__.py下执行：

- 1、获取当前脚本的完整绝对路径（执行脚本）
	- os.path.abspath(__file__)  
- 2、两个或更多的路径名进行拼接
	- os.path.join()
	- path = os.path.join('data', 'subdir', 'file.txt')
- 3、获取上级目录
	- os.path.dirname(os.path.abspath(__file__))= os.getcwd()=os.path.dirname(__file__)
- 4、获取上上级目录
	- print(os.path.dirname(os.getcwd()))
- 5、获取上上上级目录
	- print(os.path.join(os.getcwd(), "../.."))
	- print(os.path.dirname(os.path.dirname(os.getcwd())))


## python常见的数据类型
Python常用的基本数据类型有7种：数字(Number)、布尔(Booleans)、字符串(String)、列表(List)、元组(Tuple)、字典(Dictionary)、集合(Set)。

- 数字(Numbers)： 整数, 浮点数, 复数
- 布尔(Booleans)： True和False
- 字符串(Strings)：Uniconde字符序列, 在引号内包含
- 列表(list)： 有序的值的序列[]，有序性、可变性、可重复性
- 元组(Tuples)： 有序的值的序列且不可改变()
- 集合(Sets)： 无序的不含重复值的序列{}
- 字典(Dictionaries)： 无序的键值对的组合{k:v}

引申数据类型

- 索引序列(Series)
- 数据框(Dataframe)
- 数组(np.array)


## Python 编码规范
- 每行代码不要超过79个字符，可以使用括号或反斜杠来换行。
- 在二元运算符两侧、逗号后面、冒号后面等需要的地方添加空格，但是在括号内部不需要添加空格。当'='用于指示关键字参数或默认参数值时，不要在其两侧使用空格。函数的参数列表中，逗号之后要有空格。
- 常量名：常量命名使用大写字母，下划线分隔。
- 函数名：应该小写，如果有多个单词，应该用下划线连接。私有函数在函数前加一个下划线。
- 类名：所有单词首字母大写，多个单词时，每个单词开头字母都要大写，私有类可用一个下划线开头。（例如MyClass）。
- 模块名：应该短小，并且全部小写，如果有多个单词，应该用下划线连接。
- 函数和类的定义应该用两个空行隔开，而类的方法定义应该用一个空行隔开。
- 在注释中，应该遵循一定的格式，例如在#号后面添加一个空格。
- 如果使用了import语句，应该将标准库模块放在第一组，第三方库模块放在第二组，自己编写的模块放在第三组。
- 尽量避免使用单字符变量名，除非是在循环中使用。


## 字符串格式化
- 使用%进行传递

query = '''
    SELECT salesperson, product, COUNT(*) AS num_sales
    FROM sales
    WHERE salesperson = %(salesperson)s
    GROUP BY salesperson, product
    HAVING num_sales >= %(min_sales)s
    ORDER BY num_sales DESC;
'''

formatted_query =query%{'salesperson': salesperson, 'min_sales': min_sales})

- 使用 format来指定参数名称

query = '''
    SELECT customer_id, COUNT(*) as num_orders
    FROM orders
    WHERE date >= '{start_date}' AND date <= '{end_date}'
    GROUP BY customer_id
    HAVING num_orders > {min_orders}
'''

formatted_query = query.format(start_date=start_date, end_date=end_date, min_orders=min_orders)

- 在 Python 3.6 及以上版本中，可以使用 f-string 来创建格式化字符串，即在字符串前面加上字母 "f"，然后在字符串中使用大括号 {} 来表示需要插入的值。

例如：
name = "Alice"
age = 30
print(f"My name is {name} and I am {age} years old.")
输出结果为：
My name is Alice and I am 30 years old.


## print 换行问题
- 输入单个打印值默认自动换行
- 输入多个打印值要换行设置 sep = ‘\n’ 


Print(“A”,”B”,”C”,sep=’\n’)
与
Print(‘A’)
Print(‘B’)
Print(‘C’)
等价


## Python *和**实现多参数的传入或变量的拆解
*：该位置接受任意多个非关键字（non-keyword）参数，在函数中将其转化为元组（1,2,3,4）

**：该位置接受任意多个关键字（keyword）参数，在函数**位置上转化为词典 [key:value, key:value ]，**kwargs 允许将不定长度的键值对作为参数传递给一个函数。如果想要在一个函数里处理带名字的参数，应该使用 **kwargs。

## Python使用多线程、多进程等技术来提高程序运行效率
- 多线程：使用 threading 模块可以创建多个线程，每个线程可以执行不同的任务，从而提高程序的并发能力。
- 多进程：使用 multiprocessing 模块可以创建多个进程，每个进程可以执行不同的任务，从而充分利用多核 CPU 的优势，提高程序的并发能力。例如：
- 协程：使用 asyncio 模块可以实现协程，协程是一种轻量级的线程，可以在单线程中实现并发执行。
- 多进程并发是通过创建多个进程来实现并发处理的。每个进程都有自己的地址空间和系统资源，它们之间相互独立，通过进程间通信来实现数据的共享。多进程并发的优点是稳定性高，一个进程崩溃不会影响其他进程的运行；缺点是创建进程的开销较大，进程间通信的开销也较大。
- 多线程并发是通过创建多个线程来实现并发处理的。所有线程共享同一个地址空间和系统资源，它们之间的切换开销较小。多线程并发的优点是创建线程的开销较小，线程间通信的开销也较小；缺点是稳定性较差，一个线程崩溃可能会导致整个进程崩溃。
- 在选择多进程并发和多线程并发时，需要根据实际情况进行选择。如果需要处理大量的计算密集型任务，多进程并发可能更适合，因为每个进程都有自己的 CPU 时间片；如果需要处理大量的 IO 操作，多线程并发可能更适合，因为线程切换的开销较小。



## Python 中，和；的用法
- ，主要用于给多个变量同时赋值
	- a, b, c = 1, 2, 3   # 将 1、2、3 赋值给 a、b、c
- ；主要用于一行写多个语句
	- a = 1; b = 2; c = 3
