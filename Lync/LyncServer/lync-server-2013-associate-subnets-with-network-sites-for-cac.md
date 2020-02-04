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
ms.openlocfilehash: bf447b2e34ff4f274ebcab9d36e40b65bedab7dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="a996b-102">将子网与 Lync Server 2013 中的 CAC 的网络站点关联</span><span class="sxs-lookup"><span data-stu-id="a996b-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a996b-103">_**主题上次修改时间：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a996b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a996b-104">您的网络中的每个子网都必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="a996b-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="a996b-105">这是因为子网信息用于确定终结点所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="a996b-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="a996b-106">当会话中双方双方的位置已知时，呼叫许可控制（CAC）可以确定是否有足够的带宽来建立呼叫。</span><span class="sxs-lookup"><span data-stu-id="a996b-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="a996b-107">呼叫许可控制不具有将子网与网络站点相关联的特殊要求。</span><span class="sxs-lookup"><span data-stu-id="a996b-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="a996b-108">若要在拓扑中的子网和网络站点之间创建关联，请按照[将子网与 Lync Server 2013 中的网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="a996b-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="a996b-109">要在呼叫许可控制的示例网络拓扑中查看网络站点（及其各自的子网），请参阅示例：在规划文档中[收集 Lync Server 2013 中的呼叫许可控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a996b-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

