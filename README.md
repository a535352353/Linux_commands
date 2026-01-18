# Linux_commands
Linux常用命令手册
# Linux常用命令手册（一）
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
| pwd         | 显示当前目录       |  -p   显示确实路径   |  |
| ls          | 列出目录内容        |  ls -l (详细列表)<br>ls -a (显示隐藏文件) | 
| cd          | 切换目录 | cd /home<br>cd .. (上级目录) |
| mkdir       | 创建目录 | -m ：设置文件的权限，不需要看默认权限 <br> -p (递归创建) | 
| rmdir       | 删除空目录 | rm file.txt<br>rm -r folder (递归删除)<br>rm -rf folder (强制递归删除) |  
| rm          | 删除文件/目录 | cp file1 file2<br>cp -r dir1 dir2 (复制目录) |  
| cp          | 复制 | cp file1 file2<br>cp -r dir1 dir2 (复制目录) |  
| mv          | 移动/重命名 | mv old.txt new.txt<br>mv file /tmp/ |  
| touch       | 创建空文件/更新时间戳 | touch file.txt |
| man         | 线上求助 | man ls |

## 查看文件内容
| 命令        | 说明        |  参数     |  
| ----------- | ----------- | ----------|
|cat|	显示整个文件	|cat file.txt
|less|	分页查看文件	|less file.txt (按q退出)|
|more|	分页查看文件	|more file.txt|
|head|	显示文件开头	|head -n 10 file.txt (前10行)|
|tail|	显示文件结尾	|tail -n 20 file.txt (后20行)<br>tail -f log.txt (实时跟踪)|
|file|	查看文件类型	|file filename|

