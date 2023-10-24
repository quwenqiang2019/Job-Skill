
# web开发流程
- 需求分析（用户调研）
- 原型设计
	- 网站的首页是什么样
		- 导航是什么样的，内容，左边放什么，右边放什么
		- 交互的形式、流程是什么样子
	- 网站的内容页是什么样
	- 详细的列表页是什么样
- 前端
	- UI设计
		- 用图的方式展现原型图，增加一些页面设计，图标、图片、颜色搭配，要把页面设计的漂亮
	- UI交互实现
		- 图的表现形式，页面的动态交互效果换成代码的形式表示
- 后端 
	- 架构设计
		- 功能模块有哪些
		- 采用什么样的设计模式和理念
			- 程序模块分离与耦合
		- 服务器架构
			- Web服务器（网站运行的服务器）
			- 数据库的服务器
			- 服务器负载均衡
	- 数据库设计
		- 选用什么样的数据库，实现的具体的细节
			- 表的设计，关系
		- 是否要分库
		- 读写是否分离
	- 代码模块实现（业务功能实现）、单元测试（验证业务功能模块是否健壮）
		- A程序员完成用户管理模块
		- B程序员完成文章管理模块
		- ...
- 网站整合/（前后端联调）
	- 后端是写业务代码，前端是写页面的展现方式，需要整合在一起才是完整的网站 
	- 后端封装的代码，数据源需要传递给页面进行展示，数据和展现方式整合在一起
- 功能测试与集成测试
- 发布

# 开发环境
- win10
- python2.7.10
- django1.8.2
- mysql5.6.24
- mysql-python1.2.3
- pillow2.8.1

# 技术重难点
- 表单的提交与处理
- 文件的上传
- session和cookie
- ORM：对象关系映射，将数据库和python的对象进行映射关联，通过这种映射关联的关系，可以通过操作python的对象直接操作数据库，减少SQL操作的一些细节
- 模板
- JQuery
- Ajax
- json
- xml
- 后台管理
- 日志调式
- 缓存
- 安全



# blog项目

- 进入项目所在根文件夹
	- E:\python_blog\blog_project
- 配置虚拟环境环境
- 安装依赖库
	- 进入E:\python_blog\blog_project目录，直接执行pip3 install -r requirements.txt
		- win10+python2.7+django1.8+mysql+mysql-python+pillow
- 安装mysql
	- 安装mysql并设置用户名密码，创建数据库blogtest
		- user:wenqiang; pwd:Qu666666@
	- 修改blog_project/setting.py 修改数据库配置
- 初始化数据库
	- python manage.py makemigrations
	- python manage.py migrate
- 创建超级用户
	- python manage.py createsuperuser
- 启动程序
	- python manage.py runserver
- 查看项目结果
	- 浏览器输入 http://127.0.0.1:8080 即可访问
- 后台管理
	- http://127.0.0.1:8080/admin进入admin页面，添加文章
- 项目部署，上线
	- sea（别人的服务器）
	- PythonAnywhere（别人提供的免费的服务器）
	- nginx+uwsgi（阿里云或者腾讯云购买自己的服务器，公网IP）
		- 购买或租域名，绑定IP，备案


## 项目结构
- blog_project(项目的根目录)
	- blog(Django 应用程序)
		- admin.py(用于定义 Django 管理后台的配置)
		- forms.py(表单的提交与处理)
		- models.py(用于定义应用程序的数据模型)
		- test.py(用于编写应用程序的单元测试)
		- upload.py(文件上传)
		- urls.py(URL 映射到视图，用于指定哪个 URL 请求将调用哪个视图)
		- views.py(文件用于定义应用程序的视图函数，用于处理 Web 请求并返回响应)
	- blog_project(Django 项目)
		- settings.py(文件包含了 Django 项目的设置，例如数据库配置、静态文件路径、模板路径等等)
		- urls.py(文件包含了 Django 项目的 URL 映射关系)
		- wsgi.py(文件是使用 WSGI（Web 服务器网关接口）的入口文件)
	- log（日志文件）
	- static（静态文件，css、images、js）
	- templates（模板文件，html文件）
	- uploads（上传文件）
	- manage.py(是一个命令行工具，可以用来执行各种 Django 命令，例如启动开发服务器、执行数据库迁移等等)


