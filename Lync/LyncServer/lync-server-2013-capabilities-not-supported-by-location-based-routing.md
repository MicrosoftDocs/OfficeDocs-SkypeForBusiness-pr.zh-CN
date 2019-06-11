---
title: Lync Server 2013：基于位置的路由不支持的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca2d775fc17d0919ceb31a38b242e54d37b6a55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="c38e7-102">Lync Server 2013 中基于位置的路由不支持的功能</span><span class="sxs-lookup"><span data-stu-id="c38e7-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c38e7-103">_**主题上次修改时间:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="c38e7-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="c38e7-104">基于位置的路由不适用于以下类型的交互。</span><span class="sxs-lookup"><span data-stu-id="c38e7-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="c38e7-105">当 Lync 终结点使用这些功能与 PSTN 终结点交互时, 不会强制执行基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="c38e7-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="c38e7-106">PSTN 电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="c38e7-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="c38e7-107">通过响应组的传入和传出 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="c38e7-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="c38e7-108">通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索</span><span class="sxs-lookup"><span data-stu-id="c38e7-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="c38e7-109">到公告服务的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="c38e7-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="c38e7-110">通过组内呼叫应答检索的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="c38e7-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="c38e7-111">若要对下表中的交互类型强制使用基于位置的路由规则, 必须为会议启用基于位置的路由:</span><span class="sxs-lookup"><span data-stu-id="c38e7-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="c38e7-112">PSTN 电话拨出式会议</span><span class="sxs-lookup"><span data-stu-id="c38e7-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="c38e7-113">从点对点音频对话升级到涉及 PSTN 终结点的音频会议</span><span class="sxs-lookup"><span data-stu-id="c38e7-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="c38e7-114">涉及 PSTN 终结点的咨询转接</span><span class="sxs-lookup"><span data-stu-id="c38e7-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="c38e7-115">若要为会议启用基于位置的路由, 请参阅[Lync Server 2013 中的会议基于位置的路由](lync-server-2013-location-based-routing-for-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="c38e7-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c38e7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c38e7-116">See Also</span></span>


[<span data-ttu-id="c38e7-117">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="c38e7-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

