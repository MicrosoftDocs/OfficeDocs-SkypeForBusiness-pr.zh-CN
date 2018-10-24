---
title: Lync Server 2013：测试控制器
TOCTitle: 测试控制器
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398767(v=OCS.15)
ms:contentKeyID: 49313660
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中测试控制器

 

_**上一次修改主题：** 2012-09-08_

在此阶段，配置了控制器或控制器池，但域名系统 (DNS) SRV 条目仍将客户端指向通过池或 Standard Edition Server 登录。在更改 DNS 记录以使用控制器使 Lync 2013 客户端自动登录之前，可通过手动将客户端指向控制器来测试该客户端。

## 测试部署

1.  使用属于 **CSAdministrator** 组的域帐户登录到已安装 Lync Server 控制面板的计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在导航窗格中，单击“拓扑”，并在“状态”列中确认控制器或控制器池中存在带有箭头的绿色服务器（即 ![带绿色箭头的服务器图标](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "带绿色箭头的服务器图标")）。

4.  连接两台已安装 Lync Server 2013 客户端的客户端计算机，并使用已启用 Lync Server 2013 的其他用户帐户登录到每台计算机。

5.  在其中一台客户端计算机上，单击“选项”菜单，选择“个人”设置组，再依次单击“高级”和“手动配置”，然后将“内部服务器名称或 IP 地址”设置为新的控制器或控制器池的完全限定域名 (FQDN)。

6.  登录到这两个客户端，并确认使用控制器登录的客户端能够成功登录、查看其他用户的状态以及交换即时消息。

