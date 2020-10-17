---
title: Lync Server 2013：新的中继功能
description: Lync Server 2013：新的中继功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f923ceada899608cc350bd1343345c12d0996b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541938"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="704e4-103">Lync Server 2013 中的新中继功能</span><span class="sxs-lookup"><span data-stu-id="704e4-103">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="704e4-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="704e4-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="704e4-105">在 Microsoft Lync Server 2013 中，可以定义中介服务器和网关之间的多个中继。</span><span class="sxs-lookup"><span data-stu-id="704e4-105">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="704e4-106">Microsoft Lync Server 2010 仅允许在中介服务器和 PSTN 网关之间实现单一中继。</span><span class="sxs-lookup"><span data-stu-id="704e4-106">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="704e4-107">此功能使您能够灵活地定义额外的中继。</span><span class="sxs-lookup"><span data-stu-id="704e4-107">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="704e4-108">中继是中介服务器 FQDN 和侦听端口与 PSTN 网关 FQDN 和侦听端口之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="704e4-108">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="704e4-109">这一新功能允许轻松进行弹性 (的中继定义，在这种情况下，可以使用多个中介服务器将呼叫路由到同一个 PSTN 网关) ，以实现 PBX 互操作性，其中可以在和 ip-pbx 和中介服务器之间使用具有不同关联策略的多个中继，以及在同一运营商 FQDN 所引用的运营商的 SIP 中继配置。</span><span class="sxs-lookup"><span data-stu-id="704e4-109">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="704e4-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="704e4-110">See Also</span></span>


[<span data-ttu-id="704e4-111">Lync Server 2013 中新的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="704e4-111">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

