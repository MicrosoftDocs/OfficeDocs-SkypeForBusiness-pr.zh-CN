---
title: 'Lync Server 2013: 配置自动发现的支持'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中配置自动发现支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-01-21_

Lync Server web 服务**自动发现服务**首先在 Lync Server 2010 累积更新中显示:11 月2011。 此更新附带了 Lync 移动客户端的初始版本。 自动发现服务公开了移动服务, 称为 Mcx 服务。

自动发现服务用作所有客户端请求提供哪些服务和功能的相关信息的单个位置, 以及如何联系 sevices –通过完全限定的域名或 web 统一资源定位器参考。 自动发现公开了许多功能, 并且每个客户端将基于客户端可以使用的功能发出请求。 例如, 桌面 Lync 2013 客户端将使用 autodiscvoer 确定外部 web 服务, 但不会使用移动 (Mcx) 服务。 若要正确定义和启用客户端以使用它们可用的功能, 则应定义允许客户有效查找和使用自动发现条目的方案。 若要使用 autodoscover, 你的部署要求反向代理发布 Lync Server web 服务、DNS 记录配置为解析 Lync Server 自动发现服务和 Lync Server web 服务的 DNS 查询以及证书服务已针对你的特定方案正确配置。

<div>


> [!TIP]  
> 有关自动发现请求/响应中的元素的技术详细信息, 请参阅<A href="lync-server-2013-understanding-autodiscover.md">了解 Lync Server 2013 中的自动发现</A>。



</div>

以下信息和表根据方案定义需要实现哪些配置 (如果有) 才能提供自动发现服务的完整和有效使用。 以下主题中的信息特定于 Microsoft Lync Server 2013。 如果你正在寻找有关如何规划 Lync Server 2010 的移动的指南, 请参阅[http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)。 若要部署 Lync Server 2010 的移动版, 请参阅[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置自动发现的 DNS](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [在 Lync Server 2013 中配置自动发现的证书](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [在 Lync Server 2013 中配置自动发现的反向代理](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [在 Lync Server 2013 中为混合部署配置自动发现](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

