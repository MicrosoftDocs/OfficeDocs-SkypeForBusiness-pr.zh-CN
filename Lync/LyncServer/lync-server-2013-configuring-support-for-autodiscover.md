---
title: 为自动发现配置支持
TOCTitle: 为自动发现配置支持
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945622(v=OCS.15)
ms:contentKeyID: 52061001
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为自动发现配置支持

 

_**上一次修改主题：** 2016-12-08_

Lync Server Web 服务**自动发现服务**首先出现在 2011 年 11 月版的 Lync Server 2010 累积更新中。此更新随 Lync Mobile 客户端的初版一起发布。自动发现服务公开了 Mobility Service（称为 Mcx 服务）。

自动发现服务充当所有客户端的共同位置，以请求关于哪些服务和功能可用以及如何联系服务（通过完全限定域名或 Web 统一资源定位器引用）的信息。自动发现公开了许多功能，并且每个客户端将基于客户端可以使用的功能来进行请求。例如，桌面 Lync 2013 客户端将使用自动发现来确定外部 Web 服务，但不会使用 Mobility Service (Mcx)。若要正确定义您的客户端并使其能够使用对其可用的功能，应定义允许客户端有效查找并使用自动发现条目的方案。若要使用自动发现，您的部署要求反向代理发布 Lync Server Web 服务、DNS 记录被配置为解析 Lync Server 自动发现服务和 Lync Server Web 服务的 DNS 查询，并且针对您的特定方案正确配置了证书服务。

> [!TIP]
> 有关自动发现请求/响应中元素的用途的技术详细信息，请参阅<a href="lync-server-2013-understanding-autodiscover.md">了解自动发现</a>。


下列信息和表定义了每个方案中您需要实施哪些配置（如果有）才能充分而高效地使用自动发现服务。下列主题中的信息特定于 Microsoft Lync Server 2013。如果您要查找关于如何规划 Lync Server 2010 的 Mobility 的指南，请参阅 <http://go.microsoft.com/fwlink/?linkid=275113>。若要部署 Lync Server 2010 的 Mobility，请参阅 <http://go.microsoft.com/fwlink/?linkid=275114>

## 本部分内容

  - [为自动发现配置 DNS](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [为自动发现配置证书](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [为自动发现配置反向代理](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [为混合部署配置自动发现](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

