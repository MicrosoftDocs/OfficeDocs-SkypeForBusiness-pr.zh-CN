---
title: Lync Server 2013：中继间路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01b391f66754cf9530bbe66fb66e9f1ae542f297
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525249"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="a7e19-102">Lync Server 2013 中的中继间路由</span><span class="sxs-lookup"><span data-stu-id="a7e19-102">Intertrunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7e19-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a7e19-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a7e19-104">Lync Server 2013 可以将 ip-pbx 互连到公用电话交换网（ (PSTN) 网关），以便可以将来自 PBX 电话的呼叫路由到 PSTN，并将传入 PSTN 呼叫路由到专用分支 exchange (PBX) 电话。</span><span class="sxs-lookup"><span data-stu-id="a7e19-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="a7e19-105">同样，Lync Server 2013 可以互连两个或更多个 ip-pbx 系统，以便可以在不同的 ip-pbx 系统的 PBX 电话之间进行呼叫和接收。</span><span class="sxs-lookup"><span data-stu-id="a7e19-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="a7e19-106">可以使用 Lync Server 命令行管理程序 cmdlet， **remove-cstrunkconfiguration**，使用新参数 PstnUsages 配置此中继间路由功能。</span><span class="sxs-lookup"><span data-stu-id="a7e19-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="a7e19-107">此参数指定一组要使用的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="a7e19-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="a7e19-108">中继使用此 PSTN 用法来确定路由并相应地路由所有传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7e19-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="a7e19-109">下图说明了 Lync Server 2013 在 PSTN 网关和 IP-PBX 之间提供 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="a7e19-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="a7e19-110">**网关与 IP PBX 之间的中继间路由**</span><span class="sxs-lookup"><span data-stu-id="a7e19-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="a7e19-111">![连接 PSTN 网关（IP PBX 图）的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "连接 PSTN 网关（IP PBX 图）的 Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a7e19-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="a7e19-112">下图说明了 Lync Server 2013 互连两个 ip-pbx 系统。</span><span class="sxs-lookup"><span data-stu-id="a7e19-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="a7e19-113">**两个 IP PBX 之间的中继间路由**</span><span class="sxs-lookup"><span data-stu-id="a7e19-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="a7e19-114">![Lync Server 互连 IP-PAX 系统关系图](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互连 IP-PAX 系统关系图")</span><span class="sxs-lookup"><span data-stu-id="a7e19-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

