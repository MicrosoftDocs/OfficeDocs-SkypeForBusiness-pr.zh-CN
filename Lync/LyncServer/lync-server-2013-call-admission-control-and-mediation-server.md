---
title: Lync Server 2013：呼叫允许控制和中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="f1a8d-102">Lync Server 2013 中的呼叫允许控制和中介服务器</span><span class="sxs-lookup"><span data-stu-id="f1a8d-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1a8d-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f1a8d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f1a8d-104">呼叫许可控制（CAC），首次在 Lync Server 2010 中引入，可管理基于可用带宽的实时会话建立，以帮助防止用户在拥挤的网络上出现质量较差的用户（QoE）。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="f1a8d-105">为支持此功能，中介服务器提供企业语音基础设施和网关或 SIP 中继提供商之间的信号和媒体转换，负责在 Lync 上的两个交互中使用带宽管理服务器端和网关端。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="f1a8d-106">在呼叫允许控制中，呼叫的端接实体处理带宽预留。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="f1a8d-107">中介服务器与网关端交互的网关对等（PSTN 网关子、SBC）不支持 Lync Server 2013 呼叫许可控制。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="f1a8d-108">因此，中介服务器必须以网关对等的名义处理带宽交互。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="f1a8d-109">如果可能，中介服务器将提前预留带宽。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="f1a8d-110">如果不可能（例如，如果网关端的最终媒体终结点位置对于发往对等网关的传出呼叫是未知的），则会在发出呼叫时预留带宽。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="f1a8d-111">此行为可能导致带宽订阅过度，但这是防止错误响铃的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="f1a8d-112">媒体旁路和带宽预留相互排斥。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="f1a8d-113">如果将媒体绕过用于呼叫，则不会为该呼叫执行呼叫许可控制。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="f1a8d-114">此处假定前提是此次呼叫不涉及具有限定带宽的链接。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="f1a8d-115">如果呼叫许可控制用于涉及中介服务器的特定呼叫，则该呼叫无法使用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="f1a8d-116">有关媒体绕过或呼叫许可控制的详细信息，请参阅规划文档中的 "[在 lync server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)" 或 "[在 lync Server 2013 中规划呼叫许可控制](lync-server-2013-planning-for-call-admission-control.md)"。</span><span class="sxs-lookup"><span data-stu-id="f1a8d-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

