20、conda 命令
1、创建环境
conda create -n py37 python=3.7
2、查看已有的环境
conda env list
conda info -e
conda info –envs
3、激活某个环境
conda activate env_name
4、删除环境/删除环境中的某个包
conda remove -n env_name –all
conda remove -n env_name  package_name
5、环境下的包
conda list
执行 conda list ，用pip安装的包显示的build项目为pypi。用conda 安装的包显示的是其他
6、在环境下安装包
6.1在线安装
conda install package_name或pip install package_name
6.2本地安装方式
pip install   ～/Downloads/a.whl
conda install --use-local  ~/Downloads/a.tar.bz2

conda install xxx：这种方式安装的库会放在anaconda3/pkgs目录下，这样的好处就是，当在某个环境下已经下载好了某个库，再在另一个环境中还需要这个库时，就可以直接从pkgs目录下将该库复制至新环境而不用重复下载。
pip install xxx：分两种情况，一种情况就是当前conda环境的python是conda安装的，和系统的不一样，那么xxx会被安装到anaconda3/envs/current_env/lib/python3.x/site-packages文件夹中，如果当前conda环境用的是系统的python，那么xxx会通常会被安装到~/.local/lib/python3.x/site-packages文件夹中 

conda可以管理非python包，pip只能管理python包。
conda自己可以用来创建环境，pip不能，需要依赖virtualenv之类的。
conda安装的包是编译好的二进制文件，安装包文件过程中会自动安装依赖包；pip安装的包是wheel或源码，装过程中不会去支持python语言之外的依赖项。
conda安装的包会统一下载到一个目录文件中，当环境B需要下载的包，之前其他环境安装过，就只需要把之间下载的文件复制到环境B中，下载一次多次安装。pip是直接下载到对应环境中。
conda只能在conda管理的环境中使用，例如比如conda所创建的虚环境中使用。pip可以在任何环境中使用，在conda创建的环境 中使用pip命令，需要先安装pip（conda install pip ），然后可以 环境A 中使用pip 。conda 安装的包，pip可以卸载，但不能卸载依赖包，pip安装的包，只能用pip卸载。

7、在环境下卸载包
conda uninstall package_name
8、查看包的版本信息
anaconda show <USER/PACKAGE>  
