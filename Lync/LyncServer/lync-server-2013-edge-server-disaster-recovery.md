---
title: Lync Server 2013：边缘服务器灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 中的边缘服务器灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-12_

与其他服务器角色一样，为您的边缘服务器提供高可用性的最佳途径是在每个站点的池中部署多台边缘服务器。如果一台边缘服务器停机，池中的其他服务器将继续提供边缘服务。

要启用灾难恢复过程，必须在单独的站点部署单独的边缘服务器池。虽然您无需像对前端池那样明确将边缘池组成对，但是拥有多个边缘池仍能在某个完整边缘池出现故障时继续提供可用性。以下各节提供有关边缘服务器各项功能的灾难恢复的详细信息。

<div>

## <a name="remote-access"></a>远程访问

如果您有多个网站，每个站点都有一池的边缘服务器，而一个整个边缘池发生故障，则远程访问服务将继续运行，而无需管理员操作。 在不同站点中创建边缘池时，不能使用相同的 FQDN。 每个边缘池都必须具有唯一的 Fqdn （内部和外部）。 边缘池不使用反向代理发布规则与前端服务器交谈。 当客户端重新查询远程访问 DNS 服务记录，并且远程用户路由到另一个站点中的边缘服务器时，将发生自动故障转移。 客户端根据 DNS SRV 记录的优先级尝试每个外部边缘 FQDN。

<div>


> [!NOTE]  
> 若要使故障转移正常工作，请确保防火墙允许每个池中的前端服务器与所有边缘服务器进行通信。



</div>

</div>

<div>

## <a name="federation"></a>联合

对于与运行 Lync Server 的其他组织的联盟关系，只要您拥有类似 Geo DNS 的解决方案，入站联合请求将继续正常工作。 请务必了解，联合身份验证故障转移不会在 SRV 记录中提供优先级故障转移。 之前提供的解决方案可帮助您为入站联合提供灾难恢复功能。

出站联盟始终通过组织中的一个已发布边缘池或边缘服务器来设置。 如果此边缘池已经停机，必须使用拓扑生成器将出站联盟路由改为使用仍在运行的边缘池。 有关详细信息，请参阅[在 Lync server 2013 中对 Lync server 联合身份验证使用的边缘池故障](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>XMPP 联盟

对于 XMPP 联盟，如果被指定为 XMPP 联盟网关的边缘池出现故障，则出站和入站通信都将失败。 若要使 XMPP 联盟重新工作，必须将 XMPP 联盟改为使用一个不同的边缘池。 有关详细信息，请参阅[在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)。

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>边缘池出故障但前端池仍在运行

如果一个站点中的一个边缘池出现故障，但该站点中的前端池仍在运行，您需要在这第一个边缘池停机的情况下，将前端池改为使用其他站点上的其他边缘池。 有关详细信息，请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

