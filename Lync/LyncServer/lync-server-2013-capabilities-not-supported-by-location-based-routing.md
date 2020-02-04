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
ms.openlocfilehash: 967b5b7388ce60eafd46791c226bf1a3edbe0c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="87403-102">Lync Server 2013 中基于位置的路由不支持的功能</span><span class="sxs-lookup"><span data-stu-id="87403-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87403-103">_**主题上次修改时间：** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="87403-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="87403-104">基于位置的路由不适用于以下类型的交互。</span><span class="sxs-lookup"><span data-stu-id="87403-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="87403-105">当 Lync 终结点使用这些功能与 PSTN 终结点交互时，不会强制执行基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="87403-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="87403-106">PSTN 电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="87403-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="87403-107">通过响应组的传入和传出 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="87403-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="87403-108">通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索</span><span class="sxs-lookup"><span data-stu-id="87403-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="87403-109">到公告服务的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="87403-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="87403-110">通过组内呼叫应答检索的传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="87403-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="87403-111">若要对下表中的交互类型强制使用基于位置的路由规则，必须为会议启用基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="87403-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="87403-112">PSTN 电话拨出式会议</span><span class="sxs-lookup"><span data-stu-id="87403-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="87403-113">从点对点音频对话升级到涉及 PSTN 终结点的音频会议</span><span class="sxs-lookup"><span data-stu-id="87403-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="87403-114">涉及 PSTN 终结点的咨询转接</span><span class="sxs-lookup"><span data-stu-id="87403-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="87403-115">若要为会议启用基于位置的路由，请参阅[Lync Server 2013 中的会议基于位置的路由](lync-server-2013-location-based-routing-for-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="87403-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="87403-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87403-116">See Also</span></span>


[<span data-ttu-id="87403-117">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="87403-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

