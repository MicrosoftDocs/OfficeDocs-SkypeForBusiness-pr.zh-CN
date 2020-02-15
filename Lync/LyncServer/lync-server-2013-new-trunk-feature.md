---
title: Lync Server 2013：新的中继功能
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
ms.openlocfilehash: 250b240ed0e1b42051e92e9393f10c01ebb753f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="96d7e-102">Lync Server 2013 中的新中继功能</span><span class="sxs-lookup"><span data-stu-id="96d7e-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96d7e-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="96d7e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="96d7e-104">在 Microsoft Lync Server 2013 中，可以定义中介服务器和网关之间的多个中继。</span><span class="sxs-lookup"><span data-stu-id="96d7e-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="96d7e-105">Microsoft Lync Server 2010 仅允许在中介服务器和 PSTN 网关之间实现单一中继。</span><span class="sxs-lookup"><span data-stu-id="96d7e-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="96d7e-106">此功能使您能够灵活地定义额外的中继。</span><span class="sxs-lookup"><span data-stu-id="96d7e-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="96d7e-107">中继是中介服务器 FQDN 和侦听端口与 PSTN 网关 FQDN 和侦听端口之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="96d7e-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="96d7e-108">这一新功能允许轻松进行恢复的中继定义（其中多个中介服务器可用于将呼叫路由到同一个 PSTN 网关），以实现 PBX 互操作性，在和之间可以使用具有不同关联策略的多个中继。IP-PBX 和中介服务器，以及针对不同站点中的中介服务器具有 SIP 中继的 SIP 中继配置，后者由同一个运营商 FQDN 引用的运营商。</span><span class="sxs-lookup"><span data-stu-id="96d7e-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="96d7e-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96d7e-109">See Also</span></span>


[<span data-ttu-id="96d7e-110">Lync Server 2013 中新的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="96d7e-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

