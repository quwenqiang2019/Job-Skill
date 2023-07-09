
## Jyputer

### 1. 修改路径（方便导入自己的模块）：
1. 菜单中打开Anaconda Prompt，生成配置文件：jupyter notebook --generate-config
1. 打开C:\Users\Administrator\.jupyter\ jupyter_notebook_config，修改
1. c.NotebookApp.notebook_dir = r'D:\workspace\gitlab_proj\ospp-report'
1. 在开始菜单找到“Jupyte Notebook”快捷键，鼠标右击 – 属性 – 目标，去掉后面的 “%USERPROFILE%/”（很重要），然后点击“应用”，“确定”，修改起始位置：'D:\workspace\gitlab_proj\ospp-report'

### 2. 使用自己建立的Anaconda环境
1. 打开anaconda的终端命令窗口Anaconda Prompt
1. 激活自己建立的Anaconda环境（conda activate GANPytorch）
1. 运行jupyter（jupyter notebook）

### 3. 导出为pdf的最佳方式
- File-
- download as-
- HTML(.html)-
- cmd:ctrl+p-
- 另存为PDF，布局：横向

### 4. 给文件重命名
- 选定文件后，点击files下方的shundown按钮

