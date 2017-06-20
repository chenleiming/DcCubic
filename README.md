# DcCubic
#1、在ns2.35版本中仿真TCP Cubic，获得cwnd数据和图像，仿真脚本文件：cubic-2flows-dumbbell.tcl

    在 ns-allinone-2.35 目录下，执行命令：mkdir Test-Cubic ，新建文件夹Test-Cubic，把cubic-2flows-dumbbell.tcl放在Test-Cubic内；
    
    进入Test-Cubic文件夹的命令: cd Test-Cubic
    
    运行脚本命令： ns cubic-2flows-dumbbell.tcl 
    
    tcl文件中已经加入画图语句，运行后可直接显示cwnd图像
         （生成的cwnd数据存在 cwnd_1_cubic.tr 等文件中，也可通过 xgraph 画图工具画图，命令：xgraph cwnd_1_cubic.tr ）
    ns2中安装 xgraph 命令：apt-get install xgraph

#2、在ns2.35版本中仿真DCTCP ,仿真脚本文件：dctcp-dumbbell.tcl
   
    先把DCTCP加入ns2。 把文件dctcp.patch 放在 ns-allinone-2.35/ns-2.35 目录下 ，
    进入 ns-allinone-2.35/ns-2.35 目录,执行命令：patch -p1 --ignore-whitespace -i dctcp.patch
    然后 make ,即可安装好DCTCP.
    
    在 ns-allinone-2.35 目录下，执行命令：mkdir Test-DCTCP ，新建文件夹Test-DCTCP ,把dctcp-dumbbell.tcl 放在Test-DCTCP内；
    进入Test-DCTCP文件夹的命令: cd Test-DCTCP
    运行脚本命令： ns dctcp-dumbbell.tcl  ， 成功运行后产生cwnd 数据文件和图像。      

#3 tcp_cubic.c 文件是ns2中的cubic源文件 ，目录为：ns-allinone-2.35/ns-2.35/tcp/linux/src/ 

#4 tcp_cubic-linux2.6.22.6.c 是Linux-2.6.22.6内核中的cubic 源文件 ，目录为： linux-2.6.22.6/net/ipv4/
