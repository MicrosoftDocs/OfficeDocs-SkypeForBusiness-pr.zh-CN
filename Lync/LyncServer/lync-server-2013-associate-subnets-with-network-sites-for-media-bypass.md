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
ms.openlocfilehash: e74f007accc53158a1f541dbe4ac6aa821cd8be4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="9a02c-102">将子网与 Lync Server 2013 中的媒体旁路的网络站点相关联</span><span class="sxs-lookup"><span data-stu-id="9a02c-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a02c-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9a02c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a02c-104">本主题假设已配置了媒体旁路全局设置，并为媒体旁路配置了网络区域和网络站点。</span><span class="sxs-lookup"><span data-stu-id="9a02c-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="9a02c-p101">网络中的每个子网必须与特定网络站点相关联。这是因为子网信息用于确定端点所在的网络站点。当会话双方的位置已知时，媒体旁路可以确定将媒体发送到何处进行处理。</span><span class="sxs-lookup"><span data-stu-id="9a02c-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="9a02c-108">媒体旁路对于将子网与网络站点关联没有特殊要求。</span><span class="sxs-lookup"><span data-stu-id="9a02c-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="9a02c-109">若要在拓扑中的子网和网络站点之间创建关联，请按照在[Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)的过程。</span><span class="sxs-lookup"><span data-stu-id="9a02c-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="9a02c-110">后续步骤：创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="9a02c-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="9a02c-p103">为实现媒体旁路而将子网与网络站点关联后，必须创建一个或多个带宽策略配置文件，将子网区分为具有良好连接和不具有良好连接，从而方便进行媒体旁路。其网络站点没有带宽限制的网络区域中的所有子网均具有良好的连接，因此这些子网可以使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9a02c-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="9a02c-113">有关配置带宽策略配置文件的过程，请参阅[在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="9a02c-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

