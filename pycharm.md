## Pycharm分段执行代码（类似Jupyter）
在调试你的代码的时候不想管前面的代码，比如前面的代码要跑很久，对代码的其余部分进行编辑
```#%%```



## PyCharm支持的4种Python Interpreter和配置方法
- System Interpreter（python本地解释器）
- Virtualenv Environment（项目虚拟环境）
	- 进入到项目目录下D:\myProject
		- Python自3.3版本之后，官方自带了用于创建虚拟环境的venv模块
			- python -m venv [虚拟环境名称]
		- Python自3.3版本之前，
			- virtualenv [虚拟环境名称]
		- 创建完虚拟环境后，会在项目文件夹下生成一个虚拟环境文件夹
- Conda Environment（conda环境）
	- D:\software\Anaconda3\python.exe(anaconda的基础python解释器)
	- D:\software\Anaconda3\envs\env_name\python.exe(基于conda构建的python解释器)
		- 在这个python解释器下，也可以基于这个python解释器进一步为项目创建虚拟环境，在项目文件夹下生成一个虚拟环境文件夹。
- Pipenv Environment



## Pycharm快捷键

查找替换： Ctrl + R



## 在 Windows 上，在 Python 3 中创建虚拟环境：

- 打开命令提示符窗口（或 PowerShell 窗口）：
	- 在 Windows 10 上，按下 Win + R 键，输入 cmd 并按下回车键。
- 导航到你希望创建虚拟环境的目录：
	- 使用 cd 命令进入目标目录。例如，cd C:\Projects。
- 运行以下命令来创建虚拟环境：
	- python -m venv autogen
	- 这将在当前目录下创建一个名为 autogen 的虚拟环境。

- 激活虚拟环境：
	- 在命令提示符窗口中运行以下命令：
	- autogen\Scripts\activate.bat
	- 激活后，你会注意到命令提示符的前缀变为 (autogen)，表示你已经成功激活了虚拟环境。
- 现在，你已经成功创建并激活了名为 autogen 的虚拟环境。在该环境中，你可以安装和管理项目所需的包和库，而不会影响全局 Python 环境。如果你需要退出虚拟环境，只需在命令提示符窗口中运行 deactivate 命令即可。


#在 pip命令后自己设定收集源（-i +url）
- pip install [包名] -i
	- 阿里云 http://mirrors.aliyun.com/pypi/simple/
	- 中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
	- 豆瓣(douban) http://pypi.douban.com/simple/
	- 清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
	- 中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/
