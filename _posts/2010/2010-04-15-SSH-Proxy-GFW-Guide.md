---
title: 利用SSH, Putty, FoxProxy完美翻Qiang指南（For Win）
layout: post
---

1. 得到一个SSH帐号。如果你购买了国外的虚拟主机或者VPS，一般都可以在控制面板开通SSH访问。如果没有，可以考虑在淘宝买一个。 
2. 下载<a href="http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html">Putty</a>。Putty是一个小巧的SSH客户端，支持ssh tunnel。 
3. 配置Putty以提供socks代理 打开connection->ssh->Tunnels。在Source port中填入本机要监听的端口，选”Dynamic”，然后再点Add就添加成功了。对于Port forwarding里的Loal ports accept connections from other hosts选项，如果你选中该选项的话，将映射本地所有端口到服务器上，默认只是映射你指定的端口 然后回到Session页面，输入你要SSH到的主机的主机名/IP。点Open，这时putty会同弹出一个终端，输入用户名，密码，登录主机成功。 
4. 打开Firefox，安装Firefox插件<a href="https://addons.mozilla.org/en-US/firefox/addon/2464">FoxyProxy</a> 
5. 配置FoxyProxy: 点击FireFox右下角FoxyProxy的图标。弹出配置对话框。在Proxies tab页，点击"Add New Proxy"。在Genral Tab中设置ProxyName并且勾选Perform remote DNS lookups on hostnames loading through this proxy。目的是访问域名解析被盾掉的网站，比如twitter和facebook。然后在Proxy Detail tab配置代理服务器地址，这里就是127.0.0.1。端口就是在ssh tunnels中设置的本机端口，1080 完成这一步后，右键单击Firefox右下角FoxyProxy的图标，选择Use 'Proxy Name' for all URL, 你就可以尽情冲浪了。 不过对很多网友来说，只是对于一些被盾掉的网站才需要proxy。FoxyProxy可以配置只对符合条件的url才使用proxy。你可以在你配置的proxy的URL Patterns中配置

大功告成

参考链接:

1. <a href="http://www.iokay.net/it-technology/ssh-proxy/">利用SSH代理爬墙</a> 
2. <a href="http://blog.magicfirm.com/2010/01/sshproxy/">Win,Mac,Linux上如何使用ssh代理图文教程</a>


