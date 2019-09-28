# note
## linux系统环境配置
## 1.安装jdk
	1.首先删除系统自带的（如果有）openjdk
	rpm -qa | grep java或者rpm -qa | grep jdk
	yum -y remove java
	source /etc/profile
	2.下载tar格式jdk安装包
	在/usr目录下新建java文件夹，命令行：mkdir /usr/java  
	3.将安装包放在该目录下解压,解压后删除对应压缩包
	cd /usr/java  
	tar xvf jdk-8u221-linux-x64.tar.gz
	rm jdk-8u221-linux-x64.tar.gz  y
	4.修改环境变量
	vi /etc/profile
	添加
	export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_131  
	export JRE_HOME=${JAVA_HOME}/jre  
	export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
	export  PATH=${JAVA_HOME}/bin:$PATH
	执行 source /etc/profile
## 2.安装mysql
	下载安装包
	wget http://repo.mysql.com/mysql57-community-release-el7-8.noarch.rpm
	未安装wget执行以下命令安装
	yum install wget
	安装mysql
	rpm -ivh mysql57-community-release-el7-8.noarch.rpm
	yum install mysql-server
	启动mysql
	systemctl start mysqld
	重启mysql
	systemctl restart mysqld
	查询初始密码
	grep ‘temporary password’ /var/log/mysqld.log
	配置mysql安装选项并修改密码
	mysql_secure_installation
	添加外部访问并刷新权限
	GRANT ALL PRIVILEGES ON *.* TO 'qingshan'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;
	FLUSH PRIVILEGES;
## 3.安装nginx
	安装依赖包
	yum -y install gcc zlib zlib-devel pcre-devel openssl openssl-devel
	下载安装包
	wget http://nginx.org/download/nginx-1.17.4.tar.gz
	解压
	tar -xvf nginx-1.17.4.tar.gz
	进入解压后的目录
	//执行命令
	./configure
	//执行make命令
	make
	//执行make install命令
	make install
	启动nginx
	/usr/local/nginx/sbin/nginx
	重启nginx
	/usr/local/nginx/sbin/nginx -s reload
	检查nginx配置文件
	/root/server/nginx-1.6.2/sbin/nginx -t 
## 4.安装tomcat
	下载tomcat
	解压
	bin目录下所有sh文件修改权限777
## 5.安装redis

## 6.安装svn服务端
