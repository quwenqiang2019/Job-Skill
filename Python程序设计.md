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


- + ：匹配前面的字符一次或多次
- ?：匹配前面的字符出现0次或1次；
- *：匹配前面的字符出现0次或多次
- \w：匹配任意一个字母或数字字符
- \s : 匹配任何空白字符，
- \d ： 匹配任何数字字符
- (..)：匹配括号中的字符串
- (?:) ：是一个非捕获组，表示匹配但不捕获括号中的内容
- [...]：匹配方括号中的任意一个字符
- |：或操作符



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
- 1、每行代码不要超过79个字符，可以使用括号或反斜杠来换行。
- 2、在二元运算符两侧、逗号后面、冒号后面等需要的地方添加空格，但是在括号内部不需要添加空格。当'='用于指示关键字参数或默认参数值时，不要在其两侧使用空格。函数的参数列表中，逗号之后要有空格。
- 3、常量名：常量命名使用大写字母，下划线分隔。
- 4、函数名：应该小写，如果有多个单词，应该用下划线连接。私有函数在函数前加一个下划线。
- 5、类名：所有单词首字母大写，多个单词时，每个单词开头字母都要大写，私有类可用一个下划线开头。（例如MyClass）。
- 6、模块名：应该短小，并且全部小写，如果有多个单词，应该用下划线连接。
- 7、函数和类的定义应该用两个空行隔开，而类的方法定义应该用一个空行隔开。
- 8、在注释中，应该遵循一定的格式，例如在#号后面添加一个空格。
- 9、如果使用了import语句，应该将标准库模块放在第一组，第三方库模块放在第二组，自己编写的模块放在第三组。
- 10、尽量避免使用单字符变量名，除非是在循环中使用。


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

