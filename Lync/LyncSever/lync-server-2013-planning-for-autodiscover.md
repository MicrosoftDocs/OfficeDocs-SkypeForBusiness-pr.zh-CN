---
title: 规划自动发现
TOCTitle: 规划自动发现
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945628(v=OCS.15)
ms:contentKeyID: 52061023
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 规划自动发现

 

_**上一次修改主题：** 2013-02-16_

在 Lync Server 2010 累积更新 2011 年 11 月版中为 Lync Server 引入了自动发现。此自动发现的初次实现的主要目的是为 Lync Mobile 提供一种查找移动服务 (Mcx) 的方法。Lync Server 2013 中的自动发现服务现在是供所有客户端用于查找服务器和用户服务的服务。Microsoft Lync Server 2013 自动发现服务运行在控制器和前端服务器上。

> [!TIP]  
> 若要对自动发现和传送到客户端的内容有更多技术性理解，请参阅<a href="lync-server-2013-understanding-autodiscover.md">了解自动发现</a>。<br />
移动仍是显著的方案，并且移动服务仍需要一些特殊规划。有关其他详细信息，请参阅<a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动功能</a>。

在 Lync Server 2010 中引入自动发现后，需要进行折衷才能实现需要对现有服务器部署进行潜在证书更改的服务。自动发现可通过端口 TCP 443 用于 HTTPS 或通过端口 TCP 80 用于 HTTP。如果决定使用 HTTPS，则需要重新颁发反向代理、控制器和前端服务器上的证书才能容纳所需的 `lyncdiscover.<域>` 和 `lyncdiscoverinternal.<域>` DNS 记录。如果决定使用 HTTP，则可以避免重新颁发证书，方法是使用 DNS CNAME（或别名）记录来使用证书上的现有名称。使用 HTTP 确实意味着初始通信未加密。

因为 Lync Server 2013 对所有客户端使用自动发现，所以主要方案是独占使用 HTTPS 并使用 lyncdiscover.\<域\> 创建证书作为反向代理、控制器和前端服务器的配置的一部分。如果从 Lync Server 2010 将自动发现实现到升级的部署中，则可能需要使用 HTTP 来避免重新颁发证书。以下各节中提供了有关这两种方案的指南。

> [!IMPORTANT]
> 外部 Web 服务发布规则所使用的证书上的使用者替代名称列表必须包含组织中的每个 SIP 域的 <em>lyncdiscover.&lt;sip 域&gt;</em> 条目。有关控制器、前端服务器和反向代理所需的使用者替代名称条目的详细信息，请参阅<a href="lync-server-2013-certificate-summary-autodiscover.md">证书摘要 - 自动发现</a>。


## 本部分内容

  - [证书摘要 - 自动发现](lync-server-2013-certificate-summary-autodiscover.md)

  - [Lync Server 2013 中的端口摘要 - 自动发现](lync-server-2013-port-summary-autodiscover.md)

  - [Lync Server 2013 中的 DNS 摘要 - 自动发现](lync-server-2013-dns-summary-autodiscover.md)

  - [混合和拆分域 - 自动发现](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

