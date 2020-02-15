---
title: Lync Server 2013：媒体旁路的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b962905870287ef6765ecb6e7ee9b3e321ac6a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ae2c3-102">Lync Server 2013 中媒体旁路的技术要求</span><span class="sxs-lookup"><span data-stu-id="ae2c3-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae2c3-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ae2c3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ae2c3-104">对于对 PSTN 的每个调用，中介服务器将确定是否可以直接向中介服务器对等方发送来自 Lync 终结点的媒体，而不遍历中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="ae2c3-105">对等方可以是与其中路由呼叫的中介服务器之间的中继关联的 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="ae2c3-106">当满足以下要求时，可采用媒体旁路功能：</span><span class="sxs-lookup"><span data-stu-id="ae2c3-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="ae2c3-107">中介服务器对等方必须支持媒体旁路的必要功能，最重要的是处理多个分叉响应的能力（称为 "早期对话框"）。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="ae2c3-108">与网关、PBX 制造商或 ITSP 联系，以获取网关、PBX 或 SBC 可接受的最大早期对话数的值。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="ae2c3-109">中介服务器对等方必须直接从 Lync 终结点接受媒体流量。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="ae2c3-110">许多 ITSPs 只允许其 SBC 接收来自中介服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="ae2c3-111">请联系你的 ITSP 以确定其 SBC 是否接受来自 Lync 终结点的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="ae2c3-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="ae2c3-112">Lync 客户端和中介服务器对等方必须进行良好的连接，这意味着它们要么位于同一网络区域中，也可以位于通过 WAN 链路连接到区域的网络站点，而这些链路没有带宽限制</span><span class="sxs-lookup"><span data-stu-id="ae2c3-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ae2c3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae2c3-113">See Also</span></span>


[<span data-ttu-id="ae2c3-114">Lync Server 2013 中的媒体旁路模式</span><span class="sxs-lookup"><span data-stu-id="ae2c3-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="ae2c3-115">Lync Server 2013 中的媒体旁路和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="ae2c3-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

