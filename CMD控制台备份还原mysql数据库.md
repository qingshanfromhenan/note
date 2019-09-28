# note

## Windows中用cmd控制台备份mysql数据
1.	打开控制台
开始->搜索cmd回车
 
 
2.	进入到mysql安装的bin目录
 
 
3.	输入命令备份数据库mysqldump -h127.0.0.1 -uroot -p123 wx0223 > d:/backupfile.sql
其中
mysqldump是备份命令
-h127.0.0.1中-h是mysql主机127.0.0.1是主机ip地址
-uroot中-u是用户命令root是用户名
-p123中-p是密码命令123是密码
wx0223是要备份的数据库名
> d:/backupfile.sql是备份到d盘根目录备份的文件名是backupfile.sql
 
备份成功 


## Windows中用cmd控制台还原mysql数据
1.	进入mysql控制台F:\bin>mysql -uroot –p
输入密码回车
 
2.	创建数据库wx0224然后还原或者直接直接在原数据库wx0223还原
2.1创建数据库wx0224并设置编码格式为utf8(utf-8)
create database wx0224 default character set utf8 collate utf8_general_ci;
 
2.2选择要还原的数据库use wx0224
 
2.3还原数据及还原过程
Source D:\ backupfile.sql
Source是还原命令
D:\ backupfile.sql是要还原的数据文件及文件路径
还原过程请勿做任何操作
 
2.4还原成功
 
注:若要将数据还原到wx0223数据库可省去步骤2.1创建数据库操作,
直接在2.2开始(use wx0223)即可
方法2
直接使用mysql控制台备份还原数据
1备份数据
1.1进入mysql控制台
开始菜单找到mysql服务客户端MySQL 5.5 Command Line Client  
点击进入
 
或者找到mysql安装目录 
点击mysql.exe进入
 
方法2
Mysql控制台直接还原数据
开始菜单栏找到mysql服务的客户端
 
点击进入,输入密码123
 
还原操作同方法1中步骤2的2.1,2.2,2.3,2.4相同
