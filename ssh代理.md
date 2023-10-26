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


# 代理服务器http(s)和socks5的区别
- 代理IP根据协议类型分为HTTP代理，HTTPS代理和SOCKS5（SOCKS代理的升级版）代理三种，它们都是目前较为常用的代理IP的协议类型。
- HTTP代理和HTTPS代理主要用于代理HTTP和HTTPS流量，而SOCKS代理是一种通用的代理协议，可以代理各种协议的流量。
- HTTP代理和HTTPS代理更适合用于Web浏览器和HTTP/HTTPS应用程序的代理设置，而SOCKS代理更适合用于网络层的代理需求。