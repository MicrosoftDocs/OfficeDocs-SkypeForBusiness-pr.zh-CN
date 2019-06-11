---
title: Lync Server 2013：边缘服务器灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 中的边缘服务器灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-03-12_

与其他服务器角色一样, 为 Edge 服务器提供高可用性的最佳方式是在每个网站的池中部署多台边缘服务器。 如果一台边缘服务器出现故障, 则池中的其他服务器将继续提供 Edge 服务。

若要启用灾难恢复过程, 必须在单独的网站上部署单独的 Edge 服务器池。 你无需将边缘池与前端池一起进行显式配对, 但如果一个整个边缘池停机, 则具有多个边缘池的功能仍可提供。 以下部分提供了有关边缘服务器的各种功能的灾难恢复的详细信息。

<div>

## <a name="remote-access"></a>远程访问

如果你有多个网站, 每个网站都有一个边缘服务器池, 一个整个边缘池出现故障, 则远程访问服务将继续运行, 而不需要管理员操作。 在不同的网站中创建边缘池时, 无法使用相同的 FQDN。 每个 Edge 池必须具有唯一的 Fqdn (内部和外部)。 边缘池不使用反向代理发布规则与前端服务器交谈。 当客户端重新查询远程访问 DNS 服务记录, 并且远程用户路由到另一个站点中的边缘服务器时, 将发生自动故障转移。 客户根据 DNS SRV 记录的优先级尝试每个外部边缘 FQDN。

<div>


> [!NOTE]  
> 若要使故障转移顺利工作, 请确保防火墙允许每个池中的前端服务器与所有边缘服务器通信。



</div>

</div>

<div>

## <a name="federation"></a>联合身份验证

对于其他运行 Lync Server 的组织的联盟关系, 只要你有类似于 Geo DNS 的解决方案, 入站联合请求将继续正常工作。 请务必了解, 联合身份验证故障转移不会提供 SRV 记录中优先级的故障转移。 以前提供的解决方案可帮助你提供入站联合身份验证的灾难恢复功能。

出站联盟始终在组织中的一个已发布的 Edge 池或边缘服务器上设置。 如果此边缘池已关闭, 则必须使用拓扑生成器将出站联盟路由以使用仍在运行的边缘池。 有关详细信息, 请参阅[在 lync server 2013 中针对 Lync server 联合使用的边缘池故障](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>XMPP 联盟

对于 XMPP 联合身份验证, 如果指定为 XMPP 联合网关的边缘池已关闭, 则出站流量和入站流量都将失败。 若要使 XMPP 联合身份验证再次运行, 必须将 XMPP 联盟更改为使用其他边缘池。 有关详细信息, 请参阅[在 Lync Server 2013 中用于 XMPP 联合身份验证的边缘池故障](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)。

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Edge 池失败, 但前端池仍在运行

如果某个边缘池在网站上失败, 但该网站上的前端池仍在运行, 则需要更改前端池以在另一个网站上使用不同的边缘池, 而第一个边缘池已关闭。 有关详细信息, 请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

