## 利用代理访问内网和服务器
- SSH生成公私钥（平台和gitlab都得添加）
- git config --global user.name "wenqiang"
- git config --global user.email "wenqiang@nj.iscas.ac.cn"
- ssh-keygen -t rsa -C wenqiang@nj.iscas.ac.cn
- 将~/.ssh/id_rsa.pub或C:\Users\Administrator\.ssh\id_rsa.pub复制到gitlab

- 访问内网
	- 在C:\Users\Administrator\.ssh\config文件设置跳板
	```
	Host tiaoban
	    Hostname isrc.iscas.ac.cn
	    Port 5022
	    User wenqiang
	```
	- 在cmd输入：ssh -fCND 127.0.0.1:1081 -p 5022 tiaoban

- 访问内网中的服务器
	- 在C:\Users\Administrator\.ssh\config文件设置跳板
	```
	Host server
	    HostName 192.168.19.78
	    Port 22
	    User wenqiang
	    ProxyCommand ssh tiaoban -W %h:%p
	```
	```
	Host auto_ci
	    Hostname 192.168.19.78
	    Port 22
	    User wenqiang
	    ProxyCommand ssh -p 5022 wenqiang@isrc.iscas.ac.cn -W %h:%p
	 	IdentityFile C:/Users/Administrator/.ssh/id_rsa
	```
	- 在cmd输入：ssh -fCNL 127.0.0.1:31459:192.168.19.78:31459 tiaoban
