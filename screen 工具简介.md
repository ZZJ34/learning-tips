## screen 工具简介

##### 创建一个新窗口：

1. 直接在命令行键入screen命令

   > [root@user ~]# screen

2. Screen命令后接要执行的命令

   > [root@user ~]# screen <执行程序>

3. 在已有的screen窗口建立新的窗口。在当前screen窗口键入 C-a c ，即⌃+a建，之后再按下c键，生成新的窗口并自动切换到新窗口

##### 中断会话：

在scren窗口键入C-a d，Screen会给出detached提示。

过后，找到对应的screnn会话

##### 杀掉一个窗口

> screen -X -S <session # you want to kill > quit
>
> screen -wipe
>
> C-a k

##### 一些小功能

​	启动一个初始状态断开的screen会话：

> screen -dmS <session name>

##### 常用的screen参数

> screen -s <name>  新建一个叫*name*的session

> screen -ls  列出当前的所有的session

> screen -r <name> 回到*name*这个session

> screen -d  -r <name> 结束当前的session并回到*name*这个session 

在每个screen session的下，所有信息都以**⌃+a**开始

> ? 显示所有键绑定信息
>
> c 创建一个新的运行shell的窗口并切换到该窗口
>
> n Next，切换到下一个window
>
> p Previous， 切换到前一个window
>
> C-a 在两个最近使用的window间切换
>
> d detach
>
> k 强行关闭当前的window
>
> [  进入copy mode下
>
> > C-b Backward
> >
> > C-f Forward
> >
> > H 将光标移到左上角
> >
> > L 将光标移到左小角
> >
> > 0 移到行首
> >
> > $ 行末
> >
> > esc 结束copy mode 
>
> ] Paste 把刚刚结束在copy mode 选定的内容贴上

