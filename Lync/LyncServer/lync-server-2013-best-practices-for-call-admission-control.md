---
title: Lync Server 2013：呼叫允许控制的最佳做法
description: Lync Server 2013：呼叫允许控制的最佳实践。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c32af904dc7fb48a1a5d1903bd6ed1f81f4cb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552128"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5d6b2-103">Lync Server 2013 中的呼叫允许控制最佳实践</span><span class="sxs-lookup"><span data-stu-id="5d6b2-103">Best practices for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d6b2-104">_**上次修改的主题：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="5d6b2-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="5d6b2-105">若要提高性能和促进部署，请在部署呼叫允许控制时应用以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="5d6b2-105">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="5d6b2-106">确保已为当前和预期的媒体流量充分设置了 Wan。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-106">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d6b2-107">我们建议您将缓冲区中的带宽限制考虑在内。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-107">We recommend that you factor in a buffer to your bandwidth limits.</span></span> <span data-ttu-id="5d6b2-108">有些方案（如争用条件）会影响使用的总带宽，并且可能会导致超出带宽限制的情况。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-108">There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded.</span></span> <span data-ttu-id="5d6b2-109">例如，如果在媒体流量接近带宽限制的情况下，两个呼叫尝试启动，则其中一个会被拒绝，因为另一个托管的会先启动。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-109">For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="5d6b2-110">监视网络使用情况和呼叫详细信息记录，以便您可以选择最佳 CAC 设置并在网络使用变化时更新 CAC 设置。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-110">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="5d6b2-111">使用 CAC 带宽策略来补充 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-111">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="5d6b2-112">如果要将阻止的呼叫重新路由到 PSTN，请验证 PSTN 功能和容量。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-112">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="5d6b2-113">有关详细信息，请参阅 [在 Lync Server 2013 中规划出站语音路由](lync-server-2013-planning-outbound-voice-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-113">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d6b2-114">容量是指需要打开以支持可能的 PSTN 重新路由的端口数。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-114">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

