## Pycharm分段执行代码（类似Jupyter）
在调试你的代码的时候不想管前面的代码，比如前面的代码要跑很久，对代码的其余部分进行编辑
```#%%```



## PyCharm支持的4种Python Interpreter和配置方法
- System Interpreter（python的基础本地环境）
- Virtualenv Environment（基于python构建的虚拟环境）
	- virtualenv [虚拟环境名称] 来创建虚拟Python环境
- Conda Environment（需要安装anaconda，基于conda构建的虚拟环境）
	- D:\software\Anaconda3\python.exe(anaconda的基础python环境)
	- D:\software\Anaconda3\envs\env_name\python.exe(基于conda构建的虚拟python环境)
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