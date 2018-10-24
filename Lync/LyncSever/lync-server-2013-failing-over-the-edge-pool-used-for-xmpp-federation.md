---
title: Lync Server 2013：对用于 XMPP 联盟的边缘池进行故障转移
TOCTitle: 对用于 XMPP 联盟的边缘池进行故障转移
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49888428
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移

 

_**上一次修改主题：** 2012-10-19_

在您的组织中，已将一个边缘池指定为用于 XMPP 联盟的池。如果该池出现故障，您必须先对 XMPP 联盟进行故障转移以使用其他边缘池，直到 XMPP 联盟可重新正常工作。

在您首次安装边缘池并启用 XMPP 联盟时，您可以通过为 XMPP 联盟的所有（而不只是一个）边缘池设置外部 DNS SRV 记录来简化灾难恢复过程。所有这些 SRV 记录都必须具有不同的优先级设置。所有 XMPP 联盟流量将通过具有优先级最高的 SRV 记录的池。有关启用并设置 XMPP 联盟的详细信息，请参阅 [在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)。

在以下过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在承载 XMPP 联盟的池。

## 故障转移用于 XMPP 联盟的边缘池

1.  如果您尚未部署另一个边缘池（当前出现故障的边缘池之外的池），请部署该池。有关详细信息，请参阅 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

2.  在现在承载 XMPP 联盟的新边缘池 (EdgePool2) 中的每个边缘服务器上，运行以下 cmdlet：
    
        Stop-CsWindowsService

3.  运行以下 cmdlet 可将 XMPP 联盟路由重新指向 EdgePool2：
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在此示例中，Site2 是包括现在承载 XMPP 联盟路由的边缘池的站点，EdgeServer2.contoso.com 是该池中某个边缘服务器的 FQDN。

4.  在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。

5.  如果您尚未拥有解析到此时将承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加该记录，如下例所示。该 SRV 记录的端口值必须为 5269。
    
        _xmpp-server._tcp.contoso.com

6.  确认此时将承载 XMPP 联盟的边缘池已将端口 5269 向外部开放。

7.  在现在承载 XMPP 联盟的边缘池中的所有边缘服务器上启动服务：
    
        Start-CsWindowsService

