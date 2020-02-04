---
title: Lync Server 2013：为分支用户创建 VoIP 路由策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="22586-102">在 Lync Server 2013 中为分支用户创建 VoIP 路由策略</span><span class="sxs-lookup"><span data-stu-id="22586-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22586-103">_**主题上次修改时间：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="22586-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="22586-104">我们建议为分支站点上的用户创建单独的 IP 语音（VoIP）策略。</span><span class="sxs-lookup"><span data-stu-id="22586-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="22586-105">此策略应包含来自 Survivable 分支装置网关的传出的路由或 Survivable 分支服务器外部网关以及从中心站点的网关传出的传出的备份路由。</span><span class="sxs-lookup"><span data-stu-id="22586-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="22586-106">无论用户在何处注册，都可以在 Survivable 分支装置或 Survivable 分支服务器上的注册机构或中心站点的备份注册机构群集上使用，用户的 VoIP 策略始终有效。</span><span class="sxs-lookup"><span data-stu-id="22586-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="22586-107">为分支用户配置 VoIP 路由策略</span><span class="sxs-lookup"><span data-stu-id="22586-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="22586-108">创建用户级拨号计划，并将其分配给分支用户。</span><span class="sxs-lookup"><span data-stu-id="22586-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="22586-109">（请参阅操作文档中的[Lync Server 2013 中的 "创建拨号计划](lync-server-2013-create-a-dial-plan.md)"。）</span><span class="sxs-lookup"><span data-stu-id="22586-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="22586-110">分配与在该网站上的用户的拨号习惯相对应的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="22586-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="22586-111">如果 Survivable 分支装置或 Survivable 分支服务器用户故障转移到中心站点的备份注册机构池，则相同的拨号计划将生效。</span><span class="sxs-lookup"><span data-stu-id="22586-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="22586-112">（请参阅操作文档中的[Lync Server 2013 中的 "创建拨号计划](lync-server-2013-create-a-dial-plan.md)"。）</span><span class="sxs-lookup"><span data-stu-id="22586-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="22586-113">配置从 Survivable 分支装置网关或 Survivable 分支服务器外部网关 egresses 的语音路由。</span><span class="sxs-lookup"><span data-stu-id="22586-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="22586-114">（请参阅在操作文档中在[Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。）</span><span class="sxs-lookup"><span data-stu-id="22586-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="22586-115">在 Survivable 分支装置或 Survivable 分支服务器网关上设置备份呼叫路由，以指向中心站点上的备份注册机构池（collocated 与中介服务器）。</span><span class="sxs-lookup"><span data-stu-id="22586-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="22586-116">（请参阅 Survivable 分支装置或 Survivable 分支服务器供应商文档。）</span><span class="sxs-lookup"><span data-stu-id="22586-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22586-117">此备份呼叫路由设置帮助确保在 Survivable 分支设备或 Survivable 分支服务器不可用时，对分支用户的入站调用将正常工作（例如，如果它已关闭）。</span><span class="sxs-lookup"><span data-stu-id="22586-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="22586-118">如果 Survivable 分支设备或 Survivable 分支服务器上的注册机构和中介服务器不可用，并且用户已向中心站点上的备份注册机构池注册，则入站呼叫仍可路由到用户。</span><span class="sxs-lookup"><span data-stu-id="22586-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="22586-119">**下一步**：[在 Lync Server 2013 中配置语音邮件重新路由设置](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="22586-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

