---
title: Lync Server 2013：新的中继功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18296a9d1da060c9faaf8d4c765c38403a9cb224
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="5b72d-102">Lync Server 2013 中新的中继功能</span><span class="sxs-lookup"><span data-stu-id="5b72d-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b72d-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5b72d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5b72d-104">在 Microsoft Lync Server 2013 中, 可以定义中介服务器和网关之间的多个中继。</span><span class="sxs-lookup"><span data-stu-id="5b72d-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="5b72d-105">Microsoft Lync Server 2010 仅允许在中介服务器和 PSTN 网关之间进行单个中继。</span><span class="sxs-lookup"><span data-stu-id="5b72d-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="5b72d-106">此功能提供了定义其他中继的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5b72d-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="5b72d-107">主干是中介服务器 FQDN 和侦听端口与 PSTN 网关 FQDN 和侦听端口之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="5b72d-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="5b72d-108">此新功能允许轻松进行恢复的主干定义 (其中多个中介服务器可用于将呼叫路由到同一 PSTN 网关), 对于 PBX 互操作性, 可以在和之间使用具有不同关联策略的多个中继IP PBX 和中介服务器, 以及对于 SIP 中继配置, 在这种配置下, 不同站点上的中介服务器对同一运营商 FQDN 所引用的运营商具有 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="5b72d-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5b72d-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b72d-109">See Also</span></span>


[<span data-ttu-id="5b72d-110">Lync Server 2013 中新的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="5b72d-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

