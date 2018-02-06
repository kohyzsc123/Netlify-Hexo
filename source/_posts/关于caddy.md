title: 这两天折腾caddy的那点事儿
date: 2018-2-6
---
这两天自己折腾博客一开始使用的是宝塔面板，但是因为刚开始学习，对防火墙认识不清，直接使用宝塔面板后搭建的网站与其他应用总是出现冲突，nginx的配置有一些复杂，不是很适合我，于是重做系统，使用caddy进行网站配置。

Caddy的配置对新手真的十分友好，文档也很好阅读，安装也十分顺利，在配置网站过程中查资料发现Caddy有filemanager插件，可以当网盘使用！但是我通`caddy -plugins`命令查询后发现自己没有安装该插件！于是有google如何增加插件，找到个`caddyext插件`，按照要求进行安装却发现文件不全！可能项目停更了吧。最后还是通过直接在官网下载配置好的二进制文件进行替换来安装的。

在配置filemanager的时候发现一个问题，即我在配置文件内使用root /XXX指定网盘的默认访问路径但登陆后仍然在网站根目录下，需要在网站的settings里进行更改，尝试多次依然不对。

列几个caddy的命令备用：

* `service caddy start` 开启服务
* `service caddy stop` 停止服务
* `service caddy restart` 重启服务
* `whereis caddy` 查看caddy安装和配置的路径