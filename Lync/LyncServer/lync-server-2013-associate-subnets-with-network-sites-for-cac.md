---
title: Lync Server 2013：将子网与 CAC 的网络站点关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde0eb443a643371072c4c0018c05e2cd4538d0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531599"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="6b45a-102">将子网与 Lync Server 2013 中的 CAC 的网络站点关联</span><span class="sxs-lookup"><span data-stu-id="6b45a-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b45a-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6b45a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6b45a-p101">网络中的每个子网必须与特定网络站点相关联。这是因为子网信息用于确定端点所在的网络站点。了解会话双方的位置后，呼叫允许控制 (CAC) 可以确定是否有足够的带宽来建立呼叫。</span><span class="sxs-lookup"><span data-stu-id="6b45a-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="6b45a-107">呼叫允许控制对于将子网与网络站点相关联没有任何特殊要求。</span><span class="sxs-lookup"><span data-stu-id="6b45a-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="6b45a-108">若要在拓扑中的子网和网络站点之间创建关联，请按照在 [Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)的过程。</span><span class="sxs-lookup"><span data-stu-id="6b45a-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="6b45a-109">若要查看网络站点 (及其各自的子网) 在呼叫允许控制的示例网络拓扑中，请参阅 "示例：在规划文档中 [收集 Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 中的呼叫允许控制的要求"。</span><span class="sxs-lookup"><span data-stu-id="6b45a-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

