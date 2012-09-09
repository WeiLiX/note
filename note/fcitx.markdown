安装fcitx
[来源](http://tpf880725.blog.163.com/blog/static/59897698201253113155145/)
今天装了fcitx，做个学习笔记。

随着fedora版本的不断更新，感觉易用性越来越好了，这次安装fcitx，没有用源码包，直接用yum install就装好了。

首先，先删除之前的ibus相关程序：

sudo yum remove imsettings imsettings-libs im-chooser

其次，yum install fcitx

之后，修改环境变量：

 vi ~/.bashrc
增加如下内容：
export GTK_IM_MODULE=xim
export XMODIFIERS="@im=fcitx"
export QT_IM_MODULE=xim
保存后退出。

接着，设置开机自动启动，打开终端，输入gnome-session-properties,在打开的图形界面中添加一条，名称和命令分别为fcitx fcitx就可以了。

最后，注销，登录就可以使用fcitx了。
 
安装搜狗词库，在此引用一个超链接 
[搜狗词库 for fcitx-utf8](http://www.linuxsir.org/bbs/thread372879.html)

##云输入法
fedora: fcitx-cloudpinyin
