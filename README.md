# Linux_commands
Linux常用命令手册
# Linux常用命令手册
1.0 帮助命令
1.0.1 man 获得帮助信息
• 基本语法
1.0.3 常用快捷键
## 常用快捷键
功能  
ctrl + c  停止进程  
ctrl+l  清屏；彻底清屏是：reset  
ctrl + q  退出  
善于用tab键  
提示(更重要的是可以防止敲错)  
上下键  
查找执行过的命令  
ctrl +alt  linux和Windows之间切换    
## 基本操作  

| 命令        | 说明        |  参数     |  
| ----------- | ----------- | ----------|
| pwd         | 显示当前目录 |  -p   显示确实路径    |
| ls          | 列出目录内容 |  ls -l (详细列表)<br>ls -a (显示隐藏文件) | 
| cd          | 切换目录     | cd /home<br>cd .. (上级目录) |
| mkdir       | 创建目录     | -m ：设置文件的权限，不需要看默认权限 <br> -p (递归创建) | 
| rmdir       | 删除空目录   | rm file.txt<br>rm -r folder (递归删除)<br>rm -rf folder (强制递归删除) |  
| rm          | 删除文件/目录 | cp file1 file2<br>cp -r dir1 dir2 (复制目录) |  
| cp          | 复制         | cp file1 file2<br>cp -r dir1 dir2 (复制目录) |  
| mv          | 移动/重命名   | mv old.txt new.txt<br>mv file /tmp/ |  
| touch       | 创建空文件/更新时间戳 | touch file.txt |
| man         | 线上求助      | man ls |

## 查看文件内容
| 命令        | 说明        |  参数     |  
| ----------- | ----------- | ----------|
|cat          |	显示整个文件	|cat file.txt
|less         |	分页查看文件	|less file.txt (按q退出)|
|more         |	分页查看文件	|more file.txt|
|head         |	显示文件开头	|head -n 10 file.txt (前10行)|
|tail         |	显示文件结尾	|tail -n 20 file.txt (后20行)<br>tail -f log.txt (实时跟踪)|
|file         |	查看文件类型	|file filename|

## 文件查找
| 命令        | 说明        |  参数     |  
| ----------- | ----------- | ----------|
|find         |	查找文件     |find /home -name "*.txt"<br>find . -type f -size +10M|
|locate      	|快速查找文件	|locate nginx.conf (需先更新数据库updatedb)|
|which        |	查找命令路径	|which python|
|whereis    	|查找二进制/源码/手册|	whereis ls|

## 文件权限属性
| 命令        | 说明        |  参数     |  
| ----------- | ----------- | ----------|
|chmod        |	修改权限     |	chmod 755 file<br>chmod+x script.sh|
|chown        |	修改所有者   |	chown user:group file<br>chown -R user folder/|
|chgrp        |	修改所属组   |	chgrp group file|

## 文件链接
| 命令        | 说明        |  参数     |  
| ----------- | ----------- | ----------|
|ln           | 创建链接     | ln -s /path/target link_name (软链接)|

## 压缩与归档
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|tar        	|归档工具      |	tar -czvf archive.tar.gz folder/ (创建)<br>tar -xzvf archive.tar.gz (解压)<br>tar -tjf archive.tar.gz (查看)
|gzip         |	压缩	      |gzip file<br>gunzip file.gz
|zip          |	ZIP压缩    	|zip archive.zip file1 file2<br>unzip archive.zip
|unzip        |	解压ZIP	    |unzip archive.zip

## 文本处理
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|grep        	|文本搜索      |	grep "pattern" file<br>grep -r "pattern" folder/ (递归)<br>grep -i "pattern" file (忽略大小写)
|sed	        |流编辑器      |	sed 's/old/new/g' file (替换)<br>sed -n '5,10p' file (打印5-10行)
|awk	        |文本处理      |	awk '{print $1}' file (打印第一列)<br>awk -F: '{print $1}' /etc/passwd (以:分隔)
|sort         |	排序	      |sort file<br>sort -r file (逆序)<br>sort -n file (数字排序)
|uniq        	|去重          |	uniq file<br>sort file | uniq (通常先排序)
|wc           |	字数统计    	|wc -l file (行数)<br>wc -w file (单词数)
|cut        	|提取列	      |cut -d: -f1 /etc/passwd (以:分隔取第1列)
|tr           |	字符替换     |	cat file | tr 'a-z' 'A-Z' (小写转大写)
|diff         |	比较文件     |	diff file1 file2
|vim / vi     |	文本编辑器   |	vim file.txt

## 磁盘与储存
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|fdisk        |	磁盘分区    	|sudo fdisk -l<br>sudo fdisk /dev/sda
|mount      	|挂载文件系统  |	mount /dev/sdb1 /mnt<br>mount -o ro /dev/cdrom /media
|umount       |	卸载	      |umount /mnt
|blkid        |	查看块设备   |UUID	blkid
|fsck         |	文件系统检查 |	fsck /dev/sda1


# 系统信息与监控

## 系统信息
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|uname        |	系统信息     |	uname -a (所有信息)|
|hostname     |	显示主机名   | hostname|
|uptime       |	运行时间与负载|	uptime|
|date         |	显示日期时间  |	date<br>date "+%Y-%m-%d %H:%M:%S"|
|whoami       |	当前用户名    |	whoami|

## 硬件信息
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|free         |	内存使用     |	free -h (人类可读格式)|
|df           |	磁盘空间     |	df -h|
|du          	|目录大小	    |du -sh folder (汇总大小)|
|top        	|实时进程监控	|top (按q退出)|
|htop        	|增强版top     |	htop (需安装)|
|lscpu        |	CPU信息	    |lscpu|
|lsblk      	|块设备信息	  |lsblk|

## 进程管理
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|ps	          |进程快照	    |ps aux<br>ps -ef | grep nginx
|kill         |	终止进程     |	kill 1234<br>kill -9 1234 (强制终止)
|pkill        |	按名称终止  	|pkill firefox
|killall      |	终止同名进程	|killall nginx
|jobs         |	查看后台任务 |	jobs
|bg / fg      |	后台/前台切换|bg %1<br>fg %1

# 网络相关

## 网络信息
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|


## 其他实用命令
| 命令        | 说明        |  参数     |
| ----------- | ----------- | ----------|
|history      |	命令历史     |	history<br>history | grep apt
|alias        |	命令别名     |	alias ll='ls -la'<br>alias (查看所有别名)
|echo         |	输出文本     |	echo "Hello"<br>echo $PATH (输出环境变量)
|export	      |设置环境变量   |	export PATH=$PATH:/new/path
|source      	|执行脚本文件  |	source ~/.bashrc
|man          |	查看手册     |	man ls
|info         |	查看信息页   |	info coreutils
|whatis       |	命令简要说明 |	whatis ls
|clear        |	清屏        |	clear 或 Ctrl+L
|watch        |	定期执行命令 |	watch -n 1 'df -h' (每秒刷新)
|crontab      |	定时任务     |	crontab -e (编辑)<br>crontab -l (查看)
