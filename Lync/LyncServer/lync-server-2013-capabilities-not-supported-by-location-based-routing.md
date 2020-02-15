---
title: Lync Server 2013：基于位置的路由不支持的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e28778a8bd299d5ead25220f19b27927a63d44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="41bb5-102">Lync Server 2013 中基于位置的路由不支持的功能</span><span class="sxs-lookup"><span data-stu-id="41bb5-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41bb5-103">_**上次修改的主题：** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="41bb5-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="41bb5-104">基于位置的路由不适用于以下类型的交互。</span><span class="sxs-lookup"><span data-stu-id="41bb5-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="41bb5-105">当 Lync 终结点使用这些功能与 PSTN 终结点进行交互时，不会强制执行基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="41bb5-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="41bb5-106">PSTN 电话拨入会议</span><span class="sxs-lookup"><span data-stu-id="41bb5-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="41bb5-107">通过响应组的传入和传出 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="41bb5-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="41bb5-108">通过呼叫寄存呼叫寄存或检索 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="41bb5-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="41bb5-109">到公告服务的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="41bb5-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="41bb5-110">通过组呼叫应答检索的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="41bb5-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="41bb5-111">若要对以下列表中的交互类型强制执行基于位置的路由规则，您必须为会议启用基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="41bb5-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="41bb5-112">来自会议的 PSTN 拨出</span><span class="sxs-lookup"><span data-stu-id="41bb5-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="41bb5-113">从对等音频对话到涉及 PSTN 终结点的会议的升级</span><span class="sxs-lookup"><span data-stu-id="41bb5-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="41bb5-114">涉及 PSTN 终结点的咨询转移</span><span class="sxs-lookup"><span data-stu-id="41bb5-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="41bb5-115">若要为会议启用基于位置的路由，请参阅[Lync Server 2013 中的会议的基于位置的路由](lync-server-2013-location-based-routing-for-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="41bb5-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="41bb5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41bb5-116">See Also</span></span>


[<span data-ttu-id="41bb5-117">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="41bb5-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

