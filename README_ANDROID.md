# Android使用指南
准备工作不用多说，下载安卓的SSR客户端即可。

## 配置管理界面
------

打开程序以后，点击上方的“shadowsocks R ▼”字样即可进入配置管理界面。

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/2750202005.jpg)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/2750202005.jpg)

### 添加配置

点击右下角的“+”之后就会出现图中所示的5种配置添加方式，根据情况自己选择即可，这部分就不需要过多解释了，基础配置之类的与Windows版无异。

### 删除配置

能加当然就能删，左滑或者右滑一条配置即可删除该配置。

误删了怎么办？别担心，你删除之后下方会提示你可以点击“撤销”来撤销刚才的删除操作。

### 每条配置下方的文字以及右侧的按钮

*   **下方的文字**  
    从左到右依次表示 累积上行流量、累积下载流量、节点延迟、服务器组名（如果有）。
*   **闪电图标**  
    点击即可以检测此节点的延迟（ping）。
*   **分享按钮**  
    能干什么我就不用说了，点进去一看就懂。

### 右上角的三个图标

*   **一个闪电加上一个A**  
    ping列表中的所有服务器。
*   **三道杠**  
    基于ping自动由低到高排序。
*   **那个看上去像是复制的按钮**  
    对，就是复制来的。点一下就会把你目前所有配置的ssr链接复制到剪贴板中，然后你可以发给其他设备或者朋友什么的。

主界面
---

点击右上角的小飞机图标即可开启代理。第一次连接会弹出一个请求V*N连接权限的窗口，允许即可。

[![](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/2980865243.jpg)](https://blog-1257171214.file.myqcloud.com/usr/uploads/2017/09/2980865243.jpg)

### 服务器设置

你可以改当前配置的配置（听起来有点怪怪的）。

### 功能设置

*   **路由**  
    参见Windows版的[代理规则](#代理规则)。
    *   **自定义ACL文件（少用）**  
        类似于Windows版中的PAC代理模式，能根据文件中的规则智能翻*。如果需要使用此模式，选中后会让你填写ACL文件地址，这个地址通常由SSR供应商给出。
*   **IPv6 路由**  
    如果代理服务器支持IPv6，那么开启此选项之后你可以访问IPv6网站（即使你在IPv4环境下）。
*   **分应用代理**  
    开启后可以指定某几个应用的流量走代理。
*   **UDP 转发**  
    在手机上很少需要使用。如果你要代理的外服手游有使用到UDP通信那么就需要开启（例如BangDream的多人联机）。
*   **China DNS**  
    若你路由选了含有“绕过大陆”的选项，那么将使用 China DNS 来解析大陆域名。
*   **DNS**  
    默认解析所使用的DNS。

### 其他

*   **自动连接**  
    开机就会自动连。
*   **TCP Fast Open**  
    几乎不会用到的功能。
*   **NAT 模式**  
    使用旧的、需要ROOT的代理模式。用于安卓4.0以下的系统，或者当你使用V*N模式无法正常连接时再考虑使用。
*   **重置**  
    就是重置。当不小心玩坏了的时候可以试一下。
*   **ACL 文件更新**  
    当你的“路由”选的是“自定义ACL文件时”，点击此项可以更新ACL文件。
*   **前置代理**  
    参见Windows版的[前置代理](#选项设置)。

常见问题
----

### 点了检测延迟，哇，怎么延迟高达1000+

因为使用的是 TCP 方式去检测延迟，初次会不准，多点几次才能测得稳定下来的延迟数值

### 连上了代理但是无法上谷歌、推特等

如果你确定你的代理是可用的，那么开关一次飞行模式即可解决99%的这类问题。

这是 DNS 污染所致，想更详细的了解有关于 DNS 污染的知识请看：[DNS污染是什么](/technology/hosts-for-steam-fgo.html#DNS污染是什么 "DNS污染是什么")

### 网络正常但是无法正常使用代理

具体表现为，能 Ping 通代理服务器，但是连上以后就是无法通过代理上网。

请依次尝试以下步骤看看是否能解决你的问题：

*   如果你开启了 UDP 转发，那么尝试关掉它
*   尝试使用 NAT 模式（需要 Root 权限）