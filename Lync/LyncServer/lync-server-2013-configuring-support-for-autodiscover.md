---
title: Lync Server 2013：配置自动发现支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb9007562dfecdc4f38b6cf8ac3f1579094ed6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中配置自动发现支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-21_

Lync Server web services**自动发现服务**首先显示在 Lync Server 2010 累积更新中：11月2011。 此更新伴随 Lync 移动客户端的初始版本。 自动发现服务公开了移动服务，称为 Mcx 服务。

自动发现服务充当所有客户端的单个位置，以请求提供哪些服务和功能可用的信息，以及如何通过完全限定的域名或 web 统一资源定位器引用来联系 sevices –。 自动发现将公开许多功能，每个客户端将根据客户端可以使用的功能发出请求。 例如，桌面 Lync 2013 客户端将使用 autodiscvoer 来确定外部 web 服务，但不会使用移动（Mcx）服务。 若要正确定义和启用客户端以使用其可用的功能，则应定义允许客户端有效查找和使用自动发现项的方案。 若要使用 autodoscover，您的部署要求反向代理发布 Lync Server web 服务，并将 DNS 记录配置为解析 Lync Server 自动发现服务和 Lync Server web 服务的 DNS 查询，以及该证书服务为您的特定方案正确配置了。

<div>


> [!TIP]  
> 有关自动发现请求/响应中的元素的技术详细信息，请参阅<A href="lync-server-2013-understanding-autodiscover.md">了解 Lync Server 2013 中的自动发现</A>。



</div>

下面的信息和表根据应用场景定义需要实现哪些配置（如果有）才能提供自动发现服务的完整和有效使用。 以下主题中的信息特定于 Microsoft Lync Server 2013。 如果你正在寻找有关如何规划 Lync Server 2010 移动性的指南，请参阅[https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113)。 若要部署 Lync Server 2010 的移动功能，请参阅[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中配置用于自动发现的 DNS](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [在 Lync Server 2013 中配置自动发现的证书](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [在 Lync Server 2013 中为自动发现配置反向代理](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [在 Lync Server 2013 中配置自动发现以实现混合部署](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

