---
title: Lync Server 2013：新的呼叫寄存应用程序功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Call Park application features
ms:assetid: bddff13c-92cc-47fd-bfd4-6e8bfbfed11b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412927(v=OCS.15)
ms:contentKeyID: 48185277
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38053645858c2fcec52f94259485184801236240
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="6c3a1-102">Lync Server 2013 中的新呼叫寄存应用程序功能</span><span class="sxs-lookup"><span data-stu-id="6c3a1-102">New Call Park application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c3a1-103">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="6c3a1-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="6c3a1-104">呼叫寄存应用程序使企业语音用户可以将呼叫置于保持状态，然后在以后从任何电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="6c3a1-104">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="6c3a1-105">停用呼叫的用户可以拨打呼叫寄存提供的通道号码以检索寄存的呼叫，或使用外部机制（如即时消息（IM）或寻呼系统）来请求其他人检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="6c3a1-105">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="6c3a1-106">Lync Server 2013 以故障转移和故障回复进程的形式提供了新的灾难恢复机制。</span><span class="sxs-lookup"><span data-stu-id="6c3a1-106">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="6c3a1-107">这些故障转移和故障回复进程通过允许驻留在主池中的用户在主池中发生中断时利用备份池的呼叫寄存应用程序，来支持呼叫寄存功能的恢复。</span><span class="sxs-lookup"><span data-stu-id="6c3a1-107">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="6c3a1-108">对呼叫寄存应用程序的灾难恢复的支持作为成对前端池的配置和部署的一部分进行启用。</span><span class="sxs-lookup"><span data-stu-id="6c3a1-108">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6c3a1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c3a1-109">See Also</span></span>


[<span data-ttu-id="6c3a1-110">在 Lync Server 2013 中规划呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="6c3a1-110">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

