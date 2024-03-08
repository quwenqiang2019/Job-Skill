## conda 命令
- 创建环境
	- conda create -n py37 python=3.7
- 查看已有的环境
	- conda env list
	- conda info -e
	- conda info –envs
- 激活某个环境
	- conda activate env_name
- 删除环境/删除环境中的某个包
	- conda remove -n env_name -–all
	- conda remove -n env_name  package_name
- 查看环境下的包
	- conda list
	- 执行 conda list ，用pip安装的包显示的build项目为pypi。用conda 安装的包显示的是其他
- 在环境下安装包
	- 在线安装
		- conda install package_name或pip install package_name
			- conda install xxx：这种方式安装的库会放在anaconda3/pkgs目录下，这样的好处就是，当在某个环境下已经下载好了某个库，再在另一个环境中还需要这个库时，就可以直接从pkgs目录下将该库复制至新环境而不用重复下载。
			- pip install xxx：
				- 如果当前conda环境的python是conda安装的，和系统的不一样，那么xxx会被安装到anaconda3/envs/current_env/lib/site-packages文件夹中，
				- 如果当前conda环境用的是系统的python，那么xxx会通常会被安装到python12/lib/site-packages文件夹中 
	- 本地安装方式
		- pip install   ～/Downloads/a.whl
		- conda install --use-local  ~/Downloads/a.tar.bz2
- 在环境下卸载包
	- conda uninstall package_name
- 查看包的版本信息
	- anaconda show <USER/PACKAGE>  
- 查看anaconda环境下的python版本
	- python --version

- 查看conda（pip）下各个包的版本：conda（pip） list
- 查看指定包版本（以matplotlib为例）： conda list matplotlib
- 查看python环境下能下载哪些版本的包（以matplotlib为例）：conda search xxx
- pip install 包名==：能够列出当前版本的Python支持的所有第三方库的版本

## conda和pip的区别
- conda可以管理非python包，pip只能管理python包。
- conda自己可以用来创建环境，pip不能，需要依赖virtualenv之类的。
	- pip install virtualenv
	- virtualenv [虚拟环境的名字]
	- 进入到虚拟环境的Scripts文件夹中，然后执行activate
- conda安装的包是编译好的二进制文件，安装包文件过程中会自动安装依赖包；pip安装的包是wheel或源码，装过程中不会去支持python语言之外的依赖项。
- conda安装的包会统一下载到一个目录文件中，当环境B需要下载的包，之前其他环境安装过，就只需要把之间下载的文件复制到环境B中，下载一次多次安装。pip是直接下载到对应环境中。
- conda只能在conda管理的环境中使用，例如比如conda所创建的虚环境中使用。pip可以在任何环境中使用，在conda创建的环境 中使用pip命令，需要先安装pip（conda install pip ），然后可以环境A 中使用pip。conda 安装的包，pip可以卸载，但不能卸载依赖包，pip安装的包，只能用pip卸载。


## 国内软件源
- 软件源是指**存储软件包和依赖库的服务器或镜像站点**，用户可以通过软件包管理器或下载工具从这些源中下载所需的软件包或依赖库。
- 国内的软件源通常是指在中国境内搭建的软件源，例如阿里云、华为云、清华大学镜像站等。使用国内的软件源可以提高软件下载速度和稳定性，减少因为网络延迟和不稳定性导致的下载失败和下载速度慢的问题。此外，使用国内的软件源还可以避免因为访问国外软件源而受到网络限制或审查的影响。
- 在实际应用中，为了提高软件下载速度和稳定性，许多开发者和运维人员会选择使用国内的软件源来下载软件包和依赖库。**一些常用的国内软件源包括：阿里云、华为云、清华大学镜像站、中科大镜像站等**。


#在 pip命令后自己设定收集源（-i +url）
- pip install [包名] -i
	- 阿里云 http://mirrors.aliyun.com/pypi/simple/
	- 中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
	- 豆瓣(douban) http://pypi.douban.com/simple/
	- 清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
	- 中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/