# note
ilnux查看系统信息
# uname -a # 查看内核/操作系统/CPU信息 
# head -n 1 /etc/issue # 查看操作系统版本 
# cat /proc/cpuinfo # 查看CPU信息 
# hostname # 查看计算机名 
# lspci -tv # 列出所有PCI设备 
# lsusb -tv # 列出所有USB设备 
# lsmod # 列出加载的内核模块 
# env # 查看环境变量资源 
# free -m # 查看内存使用量和交换区使用量 
# df -h # 查看各分区使用情况 
# du -sh <目录名> # 查看指定目录的大小 
# grep MemTotal /proc/meminfo # 查看内存总量 
# grep MemFree /proc/meminfo # 查看空闲内存量 
# uptime # 查看系统运行时间、用户数、负载 
# cat /proc/loadavg # 查看系统负载磁盘和分区 
# mount | column -t # 查看挂接的分区状态 
# fdisk -l # 查看所有分区 
# swapon -s # 查看所有交换分区 
# hdparm -i /dev/hda # 查看磁盘参数(仅适用于IDE设备) 
# dmesg | grep IDE # 查看启动时IDE设备检测状况网络 
# ifconfig # 查看所有网络接口的属性 
# iptables -L # 查看防火墙设置 
# route -n # 查看路由表 
# netstat -lntp # 查看所有监听端口 
# netstat -antp # 查看所有已经建立的连接 
# netstat -s # 查看网络统计信息进程 
# ps -ef # 查看所有进程 
# top # 实时显示进程状态用户 
# w # 查看活动用户 
# id <用户名> # 查看指定用户信息 
# last # 查看用户登录日志 
# cut -d: -f1 /etc/passwd # 查看系统所有用户 
# cut -d: -f1 /etc/group # 查看系统所有组 
# crontab -l # 查看当前用户的计划任务服务 
# chkconfig –list # 列出所有系统服务 
# chkconfig –list | grep on # 列出所有启动的系统服务程序 
# rpm -qa # 查看所有安装的软件包

firewall-cmd --state查看火墙状态

firewall-cmd --get-active-zones列出当前被系统使用的域

firewall-cmd --get-default-zone查看火墙默认生效的域

firewall-cmd --get-zones查看默认的规则

firewall-cmd --list-all-zones查看所有的域

firewall-cmd --zone=public --list-all查看public域里面的信息

firewall-cmd --get-services列出系统中用名称表示的服务

firewall-cmd --set-default-zone=dmz 设定默认使用的域


十四、du -sh # 查看指定目录的大小 

十五、grep MemTotal /proc/meminfo # 查看内存总量 

十六、grep MemFree /proc/meminfo # 查看空闲内存量 

十七、uptime # 查看系统运行时间、用户数、负载 

十八、cat /proc/loadavg # 查看系统负载磁盘和分区 

十九、mount | column -t # 查看挂接的分区状态 

二十、fdisk -l # 查看所有分区 

二十一、swapon -s # 查看所有交换分区 

二十二、hdparm -i /dev/hda # 查看磁盘参数(仅适用于IDE设备) 

二十三、dmesg | grep IDE # 查看启动时IDE设备检测状况网络 

二十四、ifconfig # 查看所有网络接口的属性 

二十五、iptables -L # 查看防火墙设置 

二十六、route -n # 查看路由表 

二十七、netstat -lntp # 查看所有监听端口 

二十八、netstat -antp # 查看所有已经建立的连接 

二十九、netstat -s # 查看网络统计信息进程 

三十、ps -ef # 查看所有进程 

三十一、top # 实时显示进程状态用户 

三十二、w # 查看活动用户 

三十三、id # 查看指定用户信息 

三十四、last # 查看用户登录日志 

三十五、cut -d: -f1 /etc/passwd # 查看系统所有用户 

三十六、cut -d: -f1 /etc/group # 查看系统所有组 

三十七、crontab -l # 查看当前用户的计划任务服务 

三十七、chkconfig –list # 列出所有系统服务 

三十八、chkconfig –list | grep on # 列出所有启动的系统服务程序 

三十九、rpm -qa # 查看所有安装的软件包 

四十、cat /proc/cpuinfo ：查看CPU相关参数的linux系统命令 

四十一、cat /proc/partitions ：查看linux硬盘和分区信息的系统信息命令 

四十二、cat /proc/meminfo ：查看linux系统内存信息的linux系统命令 

四十三、cat /proc/version ：查看版本，类似uname -r 

四十四、cat /proc/ioports ：查看设备io端口 

四十五、cat /proc/interrupts ：查看中断 

四十六、cat /proc/pci ：查看pci设备的信息 

四十七、cat /proc/swaps ：查看所有swap分区的信息 


ps -ef | grep nginx

/usr/local/nginx 配置

/root/server/nginx-1.6.2/sbin/nginx 启动

/root/server/nginx-1.6.2/sbin/nginx -s reload            # 重新载入配置文件

/root/server/nginx-1.6.2/sbin/nginx -s reopen            # 重启 Nginx

/root/server/nginx-1.6.2/sbin/nginx -s stop              # 停止 Nginx

/root/server/nginx-1.6.2/sbin/nginx -t    检查配置文件nginx.conf的正确性命令


增加账号：root    IP： %（所有人） 的访问权限

GRANT ALL PRIVILEGES ON *.* TO 'qingshan'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;

马上生效（如果不运行该命令 可以重启来自动运行来生效）

FLUSH PRIVILEGES;


查看端口占用
netstat -tunlp
