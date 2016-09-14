# Linux
安装 lrzsz
#yum -y install lrzsz

开机启动
#chkconfig    servicename   on

新建文件
#touch filename

更改文件所属用户组，若是整个目次下的都改，则加-R参数用于递归。
#chgrp users file

转变文件拥有者
#chown user file

根据进程的PID值来查找执行文件的及其路径
#lsof -p PID

登陆mysql
#mysql -uroot -p
#mysql>show processlist;
#mysql>show status;

查看系统CPU占用率
#top
#vmstat

查找包含特定字符串的文件位置
#grep "string" /filename/*
#find /home/uocbcp -type f -name '*.xml'|xargs grep '12202610'


如果你想在当前目录下 查找"hello,world!"字符串,可以这样:
 
grep -rn "hello,world!" *
 
* : 表示当前目录所有文件，也可以是某个文件名
-r 是递归查找
-n 是显示行号
-R 查找所有文件包含子目录
-i 忽略大小写

2，xargs配合grep查找
find -type f -name '*.php'|xargs grep 'GroupRecord'


从 本地 复制到 远程 
scp /home/daisy/full.tar.gz root@172.19.2.75:/home/root （然后会提示你输入另外那台172.19.2.75主机的root用户的登录密码，接着就开始copy了），复制目录加参数 -r 即可 

从 远程 复制到 本地 
scp root@/172.19.2.75:/home/root/full.tar.gz /home/daisy/full.tar.gz

全局替换
:%s/vivian/sky/g（等同于 :g/vivian/s//sky/g） 替换每一行中所有 vivian 为 sky 

上一个目录
cd -

创建用户
useradd



Linux配置IP
#vi /etc/sysconfig/network-scripts/ifcfg-eth0

...
ONBOOT=yes
BOOTPROTO=static
IPADDR=10.42.120.185
NETMASK=255.255.255.0
GATEWAY=10.42.120.1
NM_CONTROLLER="no"(这行删除)
...

LInux配置VNCSERVER
vim /etc/sysconfig/vncservers
VNCSERVERS="1:root"
VNCSERVERARGS[1]="-geometry 1280x728 -nolisten tcp -alwaysshared"
vncpasswd
/etc/init.d/iptables stop
service vncserver restart

