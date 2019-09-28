# note
## 1.修改端口
根目录名
tomcat7-4580----->tomcat7-4680
根目录文件名
install.sh	4580全部替换4680
remove.sh	4580全部替换4680
tomcat-4580.service	文件名修改,文件内容	4580全部替换4680
一级目录
webapps/tm4580目录名修改tm4680
conf/server.xml 文件内查询45全部 替换46
## 2.上传到linux服务器
## 3.解压
## 4.更改权限根目录,权限代码777(所有权限)
tomcat-4580.service
remove.sh
install.sh
bin目录下所有.sh文件
## 5.注册服务
cd tomcat7-4580
sudo ./install.sh
## 6.	nginx添加tomact
nginx目录下conf目录下tomcat_manager.txt文件添加tomcat
	location /tm4580/ {
		proxy_pass    http://127.0.0.1:4580/tm4580/;
		proxy_redirect default ;
	}
## 7.重启nginx服务
sudo nginx -s reload
## 8.nginx添加tomcat服务应用
nginx目录下conf目录下default.conf文件
		location /pwsls/ {
				proxy_pass    http://127.0.0.1:4580/pwsls/;
				proxy_redirect default ;
		}
重启nginx服务
sudo nginx -s reload
## 9.进入tomcat服务管理工具
ip:tm4580/



## 10重启tomcat服务
sudo systemctl start tomcat-5380




查看  服务
nginx
ps -ef|grep nginx
tomcat
ps -ef|grep java


重启nginx报错(13: Permission denied)
查看用户
ps aux | grep "nginx: worker process" | awk '{print $1}'
检查nginx安装目录下nginx.conf文件user 用户
如果和ps aux | grep "nginx: worker process" | awk '{print $1}'命令返回结果不一致,修改一致
然后重启nginx服务
nginx -s reload


重启nginx报错
报错信息
nginx: [error] open() "/run/nginx.pid" failed (2: No such file or directory)
nginx: [emerg] open() "/usr/share/nginx/nginx.conf" failed (2: No such file or directory)
处理方式
nginx -c /etc/nginx/nginx.conf
nginx -s reload



