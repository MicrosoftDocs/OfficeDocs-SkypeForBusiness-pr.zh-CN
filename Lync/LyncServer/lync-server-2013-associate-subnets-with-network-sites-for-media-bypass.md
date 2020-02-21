---
title: Lync Server 2013：将子网与网络站点关联以实现媒体旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5565be047443ebb0bf84358a592dc0b1f9314c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>将子网与 Lync Server 2013 中的媒体旁路的网络站点相关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

<div>


> [!NOTE]  
> 本主题假设已配置了媒体旁路全局设置，并为媒体旁路配置了网络区域和网络站点。



</div>

网络中的每个子网必须与特定网络站点相关联。这是因为子网信息用于确定端点所在的网络站点。当会话双方的位置已知时，媒体旁路可以确定将媒体发送到何处进行处理。

媒体旁路对于将子网与网络站点关联没有特殊要求。 若要在拓扑中的子网和网络站点之间创建关联，请按照在[Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)的过程。

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>后续步骤：创建带宽策略配置文件

为实现媒体旁路而将子网与网络站点关联后，必须创建一个或多个带宽策略配置文件，将子网区分为具有良好连接和不具有良好连接，从而方便进行媒体旁路。其网络站点没有带宽限制的网络区域中的所有子网均具有良好的连接，因此这些子网可以使用媒体旁路。

有关配置带宽策略配置文件的过程，请参阅[在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

