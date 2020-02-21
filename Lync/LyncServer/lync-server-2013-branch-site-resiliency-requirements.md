---
title: Lync Server 2013：分支站点恢复要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e8fb2cdbf2b9192411f74c5099930d8bd7d7a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="9b461-102">Lync Server 2013 的分支站点恢复要求</span><span class="sxs-lookup"><span data-stu-id="9b461-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b461-103">_**上次修改的主题：** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="9b461-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="9b461-104">本主题将帮助您为用户准备分支站点恢复能力和语音邮件生存能力，并且还会指定相关的软硬件要求。</span><span class="sxs-lookup"><span data-stu-id="9b461-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="9b461-105">为分支用户准备分支站点恢复能力</span><span class="sxs-lookup"><span data-stu-id="9b461-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="9b461-106">通过将注册器池设置为 Survivable 分支机构（SBA）或 Survivable 分支服务器，为用户准备分支站点恢复能力。</span><span class="sxs-lookup"><span data-stu-id="9b461-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="9b461-107">分支用户的注册器分配</span><span class="sxs-lookup"><span data-stu-id="9b461-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="9b461-108">无论您选择哪个分支站点恢复解决方案，您都需要为每个用户分配一个主注册器。</span><span class="sxs-lookup"><span data-stu-id="9b461-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="9b461-109">分支站点用户应始终向分支站点上的注册机构注册，而不管该注册器是驻留在 Survivable 分支设备、Survivable 分支服务器还是独立 Lync Server 2013 Standard 或 Enterprise Edition server 中。</span><span class="sxs-lookup"><span data-stu-id="9b461-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="9b461-110">需要域名系统 (DNS) 服务 (SRV) 资源记录，客户端才能发现其注册器池。</span><span class="sxs-lookup"><span data-stu-id="9b461-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="9b461-111">如果 Survivable 分支设备变得不可用，则分支站点客户端将自动发现备份注册器。</span><span class="sxs-lookup"><span data-stu-id="9b461-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="9b461-112">如果分支站点没有 DNS 服务器，则可以使用两种备选方式来配置 Survivable 分支设备或 Survivable 分支服务器的发现：</span><span class="sxs-lookup"><span data-stu-id="9b461-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="9b461-113">将分支站点的动态主机配置协议（DHCP）服务器上的 DHCP 选项120配置为指向 Survivable 分支机构或 Survivable 分支服务器的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="9b461-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="9b461-114">将 Survivable 分支装置或 Survivable 分支服务器配置为对 DHCP 120 查询做出响应。</span><span class="sxs-lookup"><span data-stu-id="9b461-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="9b461-115">分支用户的语音路由</span><span class="sxs-lookup"><span data-stu-id="9b461-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="9b461-116">我们建议您为分支站点中的用户创建单独的用户级别 IP 语音 (VoIP) 策略。</span><span class="sxs-lookup"><span data-stu-id="9b461-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="9b461-117">此策略应包括使用 Survivable 分支装置或分支服务器网关的主路由，以及一个或多个在中央站点上使用具有公用交换电话网络（PSTN）网关的中继的备份路由。</span><span class="sxs-lookup"><span data-stu-id="9b461-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="9b461-118">如果主路由不可用，则将改用使用一个或多个中央站点网关的备份路由。</span><span class="sxs-lookup"><span data-stu-id="9b461-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="9b461-119">这样，不管是在分支站点注册器还是在中央站点的备份注册器池中注册用户，用户的 VoIP 策略将始终有效。</span><span class="sxs-lookup"><span data-stu-id="9b461-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="9b461-120">这对于处理故障转移的情况是很重要的。</span><span class="sxs-lookup"><span data-stu-id="9b461-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="9b461-121">例如，如果您需要重命名 Survivable 分支设备或重新配置 Survivable 分支设备以连接到中央站点的备份注册器池，则必须将分支站点用户移动到中央站点，持续时间。</span><span class="sxs-lookup"><span data-stu-id="9b461-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="9b461-122">（有关重命名或重新配置 Survivable 分支设备的详细信息，请参阅部署文档中的[附录 B：在 Lync Server 2013 中管理 Survivable 分支设备](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md)。）如果这些用户没有用户级 VoIP 策略或用户级拨号计划，则当用户移动到另一个站点时，中心站点的站点级别 VoIP 策略和站点级别的拨号计划将默认应用于用户，而不是分支站点站点级别的 VoIP 策略和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="9b461-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="9b461-123">在这种情况下，除非备份注册器池所用的站点级别 VoIP 策略和站点级别拨号计划也能应用到这些分支站点用户，否则他们的呼叫将失败。</span><span class="sxs-lookup"><span data-stu-id="9b461-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="9b461-124">例如，如果某个位于日本的分支站点上的用户移到位于雷蒙德的中央站点上，那么，其规范化规则是在所有 7 位数字呼叫之前附加 +1425 的拨号计划就可能不会采用适当的方式转换对这些用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b461-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9b461-125">创建分支机构备份路由时，建议将两个 PSTN 电话用法记录添加到分支机构用户策略中，并为每个记录分配单独的路由。</span><span class="sxs-lookup"><span data-stu-id="9b461-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="9b461-126">第一个或主路由将直接调用与 Survivable 分支机构（SBA）或分支服务器关联的网关。第二个或 "备份" 路由将直接调用中央站点的网关。</span><span class="sxs-lookup"><span data-stu-id="9b461-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="9b461-127">在定向呼叫时，SBA 或分支服务器会在尝试所有分配给第一个 PSTN 用法记录的路由后，再尝试第二个用法记录。</span><span class="sxs-lookup"><span data-stu-id="9b461-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="9b461-128">为了帮助确保在分支网关或 Survivable 分支机构网站的 Windows 组件不可用时（例如，如果 Survivable 分支设备或分支，则会发生这种情况），对分支网站用户的入站呼叫将到达这些用户。网关关闭以进行维护），请在网关上创建故障转移路由（或使用直接向内拨号（已）提供程序）将传入呼叫重定向到中央站点的备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="9b461-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="9b461-129">在此处，呼叫将会通过 WAN 链路路由到分支用户。</span><span class="sxs-lookup"><span data-stu-id="9b461-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="9b461-130">请确保路由会转换这些号码以符合 PSTN 网关要求或其他中继对等方接受的电话号码格式。</span><span class="sxs-lookup"><span data-stu-id="9b461-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="9b461-131">有关创建故障转移路由的详细信息，请参阅[Lync Server 2013 中的配置故障转移路由](lync-server-2013-configuring-a-failover-route.md)。</span><span class="sxs-lookup"><span data-stu-id="9b461-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="9b461-132">另外，您还可以为与分支站点网关相关联的中继创建服务级别拨号计划，以规范化传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b461-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="9b461-133">如果在一个分支站点有两个 Survivable 分支机构，则可以为这两个分支机构创建一个站点级别的拨号计划，除非每个都需要一个单独的服务级别计划。</span><span class="sxs-lookup"><span data-stu-id="9b461-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b461-134">要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点进行注册。</span><span class="sxs-lookup"><span data-stu-id="9b461-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="9b461-135">对分支站点用户的数量（包括在 Survivable 分支设备中注册的用户），目前没有限制。</span><span class="sxs-lookup"><span data-stu-id="9b461-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="9b461-136">我们还建议您创建一个用户级别的拨号计划和语音策略，然后将它分配给分支站点用户。</span><span class="sxs-lookup"><span data-stu-id="9b461-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="9b461-137">有关详细信息，请参阅部署文档中的在 lync [server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)和在[lync server 2013 中为分支用户创建 VoIP 路由策略](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)。</span><span class="sxs-lookup"><span data-stu-id="9b461-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="9b461-138">路由分机号</span><span class="sxs-lookup"><span data-stu-id="9b461-138">Routing Extension Numbers</span></span>

<span data-ttu-id="9b461-139">为分支站点用户准备拨号计划和语音策略时，请确保包含与 msRTCSIP （或 Line URI）属性中使用的字符串和数字格式相匹配的规范化规则和转换规则，以便在 branch 之间启用 Lync 2013 调用网站用户和中央网站用户将被正确路由—尤其是当由于 WAN 链接不可用而必须在 PSTN 上重新路由呼叫时。</span><span class="sxs-lookup"><span data-stu-id="9b461-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="9b461-140">此外，还需要特别注意包括分机号的已拨号码，而不只是电话号码。</span><span class="sxs-lookup"><span data-stu-id="9b461-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="9b461-p108">与包含分机号（无论是只包含一个完整的 E.164 电话号码还是包含其他的电话号码）的线路 URI 匹配的标准化规则和转换规则还有其他要求。本节介绍了为带分机号的线路 URI 路由呼叫的几种示例情况。</span><span class="sxs-lookup"><span data-stu-id="9b461-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="9b461-p109">如果您的组织没有为单个用户配置外线直拨分机 (DID) 电话号码，并且每个用户的线路 URI *只* 配置了一个分机号，则内部用户只需拨打分机号即可相互呼叫。但是，您必须配置规范化规则，并且这些规则要能应用到与这些分机号相匹配的从分支站点用户发给中央站点用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b461-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="9b461-p110">如果分支站点和中央站点之间的 WAN 链路可用，那么分支站点用户发给中央站点用户的呼叫就无需通过匹配的规范化规则来转换号码，因为该呼叫不会通过 PSTN 来路由。例如：</span><span class="sxs-lookup"><span data-stu-id="9b461-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b461-147">规则名称</span><span class="sxs-lookup"><span data-stu-id="9b461-147">Rule name</span></span></th>
<th><span data-ttu-id="9b461-148">说明</span><span class="sxs-lookup"><span data-stu-id="9b461-148">Description</span></span></th>
<th><span data-ttu-id="9b461-149">号码模式</span><span class="sxs-lookup"><span data-stu-id="9b461-149">Number pattern</span></span></th>
<th><span data-ttu-id="9b461-150">Translation</span><span class="sxs-lookup"><span data-stu-id="9b461-150">Translation</span></span></th>
<th><span data-ttu-id="9b461-151">示例</span><span class="sxs-lookup"><span data-stu-id="9b461-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b461-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="9b461-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="9b461-153">不要转换 5 位数字</span><span class="sxs-lookup"><span data-stu-id="9b461-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="9b461-154">^ （\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="9b461-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="9b461-155">$1</span><span class="sxs-lookup"><span data-stu-id="9b461-155">$1</span></span></p></td>
<td><p><span data-ttu-id="9b461-156">10001 无法转换</span><span class="sxs-lookup"><span data-stu-id="9b461-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9b461-p111">您还必须针对特定的方案考虑分机号，如分支站点和中央站点之间的 WAN 链路不可用，以及必须通过 PSTN 路由来自分支站点的呼叫等情况。在 WAN 链路中断期间，如果分支站点用户只通过拨打中央站点用户的分机号来呼叫中央站点用户，则您必须制定一个可添加中央站点用户的完整电话号码的出站转换规则。如果用户的线路 URI 包含了组织完整的电话号码和用户唯一的分机号（非用户唯一的完整电话号码），则您必须制定改为添加组织的完整电话号码的出站转换规则。例如：</span><span class="sxs-lookup"><span data-stu-id="9b461-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b461-161">说明</span><span class="sxs-lookup"><span data-stu-id="9b461-161">Description</span></span></th>
<th><span data-ttu-id="9b461-162">匹配模式</span><span class="sxs-lookup"><span data-stu-id="9b461-162">Matching pattern</span></span></th>
<th><span data-ttu-id="9b461-163">Translation</span><span class="sxs-lookup"><span data-stu-id="9b461-163">Translation</span></span></th>
<th><span data-ttu-id="9b461-164">示例</span><span class="sxs-lookup"><span data-stu-id="9b461-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b461-165">将 5 位数号码转换为用户的电话号码和分机号</span><span class="sxs-lookup"><span data-stu-id="9b461-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="9b461-166">^ （\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="9b461-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="9b461-167">+ 14255550123; ext = $ 1</span><span class="sxs-lookup"><span data-stu-id="9b461-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="9b461-168">10001 将转换为 +14255550123;ext=10001</span><span class="sxs-lookup"><span data-stu-id="9b461-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-169">将 5 位数号码转换为组织的电话号码和用户分机号</span><span class="sxs-lookup"><span data-stu-id="9b461-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="9b461-170">^ （\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="9b461-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="9b461-171">+ 14255550100; ext = $ 1</span><span class="sxs-lookup"><span data-stu-id="9b461-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="9b461-172">10001 将转换为 +14255550100;ext=10001</span><span class="sxs-lookup"><span data-stu-id="9b461-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9b461-p112">在这种情况下，如果处理 PSTN 重新路由任务的中继对等方不支持分机号，则出站转换规则还必须删除分机号。例如：</span><span class="sxs-lookup"><span data-stu-id="9b461-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b461-175">说明</span><span class="sxs-lookup"><span data-stu-id="9b461-175">Description</span></span></th>
<th><span data-ttu-id="9b461-176">匹配模式</span><span class="sxs-lookup"><span data-stu-id="9b461-176">Matching pattern</span></span></th>
<th><span data-ttu-id="9b461-177">Translation</span><span class="sxs-lookup"><span data-stu-id="9b461-177">Translation</span></span></th>
<th><span data-ttu-id="9b461-178">示例</span><span class="sxs-lookup"><span data-stu-id="9b461-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b461-179">从包含分机号的电话号码中删除分机号</span><span class="sxs-lookup"><span data-stu-id="9b461-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="9b461-180">^\+（\d *）; ext = （\d*） $</span><span class="sxs-lookup"><span data-stu-id="9b461-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="9b461-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="9b461-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="9b461-182">+14255550123;ext=10001 将转换为 +14255550123</span><span class="sxs-lookup"><span data-stu-id="9b461-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9b461-p113">无论 WAN 链路是否可用，如果组织没有为单个用户配置 DID 号码，并且用户的线路 URI 包含组织电话号码和用户唯一的分机号，则您必须为组织的电话号码线路 URI 配置可由分支站点中继对等方或 PSTN 网关接通的号码。您还必须配置组织的电话号码线路 URI，为路由到该号码的呼叫添加自己的唯一分机号。</span><span class="sxs-lookup"><span data-stu-id="9b461-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="9b461-185">有关在 WAN 链路不可用时中央站点用户向分支站点用户发送呼叫的详细信息，请参阅本主题后面的“准备语音邮件生存能力”。</span><span class="sxs-lookup"><span data-stu-id="9b461-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="9b461-186">有关拨号计划和规范化规则的详细信息（包括其他示例规则），请参阅部署文档中的规划文档和[在 Lync server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)中的[lync server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="9b461-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="9b461-187">有关出站转换规则的详细信息，请参阅部署文档中的规划文档和定义 Lync Server 2013 中的[Lync server 2013 中的转换规则](lync-server-2013-translation-rules.md)和在[lync Server 中定义转换规则](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="9b461-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="9b461-188">准备语音邮件生存能力</span><span class="sxs-lookup"><span data-stu-id="9b461-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="9b461-189">Exchange 统一消息（UM）通常仅在中央站点上安装，而不是在分支站点上安装。</span><span class="sxs-lookup"><span data-stu-id="9b461-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="9b461-190">即使分支站点和中央站点之间的 WAN 链路不可用，呼叫者也应能够留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="9b461-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="9b461-191">因此，为分支站点用户提供语音邮件的 Exchange UM 自动助理电话号码配置行 URI 需要特殊注意事项，以及适用于该语音邮件的语音策略、拨号计划和规范化规则多种.</span><span class="sxs-lookup"><span data-stu-id="9b461-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="9b461-192">Survivable 分支装置（Sba）和 Survivable 分支服务器在 WAN 中断期间为分支用户提供语音邮件留存。</span><span class="sxs-lookup"><span data-stu-id="9b461-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="9b461-193">具体来说，如果您使用的是 Survivable 分支机构或 Survivable 分支服务器，而 WAN 变为不可用，则 SBA 或 Survivable 分支服务器会将未应答的呼叫通过 PSTN 重新路由到 Exchange UM 中的中央站点。</span><span class="sxs-lookup"><span data-stu-id="9b461-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="9b461-194">通过 SBA 或 Survivable 分支服务器，用户还可以在 WAN 中断期间通过 PSTN 检索语音邮件消息。</span><span class="sxs-lookup"><span data-stu-id="9b461-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="9b461-195">最后，在 WAN 中断过程中，Survivable 分支设备或 Survivable 分支服务器会对未接来电通知进行排队，然后在 WAN 恢复时将其上载到 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="9b461-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="9b461-196">为了帮助确保语音邮件重新路由是可恢复的，请确保将中心站点池的 FQDN 的条目和边缘服务器 FQDN 的条目添加到 Survivable 分支服务器上的 hosts 文件中。</span><span class="sxs-lookup"><span data-stu-id="9b461-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="9b461-197">否则，在分支站点上没有 DNS 服务器的情况下，DNS 解析可能会超时。</span><span class="sxs-lookup"><span data-stu-id="9b461-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="9b461-198">我们建议使用以下配置为分支站点用户配置语音邮件生存能力：</span><span class="sxs-lookup"><span data-stu-id="9b461-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="9b461-199">Microsoft Exchange 管理员应将 Exchange UM 自动助理（AA）配置为仅接受邮件。</span><span class="sxs-lookup"><span data-stu-id="9b461-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="9b461-200">该配置禁用所有其他常规功能（例如，转接给用户或转接给操作员）并将 AA 限制为仅接受邮件。</span><span class="sxs-lookup"><span data-stu-id="9b461-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="9b461-201">或者，Exchange 管理员也可以使用常规 AA 或自定义 AA 将呼叫路由至操作员。</span><span class="sxs-lookup"><span data-stu-id="9b461-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="9b461-202">Lync Server 管理员应采用 AA 电话号码，并将该电话号码用作 Survivable 分支设备或分支服务器的语音邮件重新路由设置中的**exchange um 自动助理**编号。</span><span class="sxs-lookup"><span data-stu-id="9b461-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="9b461-203">Lync Server 管理员应获取 Exchange UM 订阅者访问电话号码，并将该号码用作 Survivable 分支机构或 Survivable 分支服务器的语音邮件重新路由设置中的**订阅者访问**号码。</span><span class="sxs-lookup"><span data-stu-id="9b461-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="9b461-204">Lync Server 管理员应配置 Exchange UM，以便在 WAN 中断期间，只有一个拨号计划与需要访问语音邮件的所有分支用户相关联。</span><span class="sxs-lookup"><span data-stu-id="9b461-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="9b461-205">当 WAN 链路不可用时，向分支站点用户发送的呼叫可以路由到用户的 Exchange 统一消息 (UM) 语音邮箱，但还必须满足以下条件，即应用到该呼叫的语音策略指定的语音邮件电话号码是唯一的并且不含分机号。</span><span class="sxs-lookup"><span data-stu-id="9b461-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="9b461-206">分支站点恢复能力的软硬件要求</span><span class="sxs-lookup"><span data-stu-id="9b461-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="9b461-207">根据您的恢复能力解决方案，软硬件要求可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="9b461-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="9b461-208">Survivable Branch Appliance 的要求</span><span class="sxs-lookup"><span data-stu-id="9b461-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="9b461-209">必需的硬件和软件内置在 Survivable 分支设备中。</span><span class="sxs-lookup"><span data-stu-id="9b461-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="9b461-210">但是，我们还是建议每个分支站点部署 DHCP 服务器以获取客户端 IP 地址；否则，当 DHCP 租赁到期时，客户端将失去 IP 连接。</span><span class="sxs-lookup"><span data-stu-id="9b461-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="9b461-211">如果企业 DNS 服务器仅位于中央站点中，分支站点用户在 WAN 中断期间将无法连接到它们，因此使用 DNS SRV （服务（SRV）资源记录）的 Lync Server 发现将会失败。</span><span class="sxs-lookup"><span data-stu-id="9b461-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="9b461-212">要确保在 WAN 中断期间提示重新路由语音邮件，必须在分支站点上缓存 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9b461-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="9b461-213">如果分支路由器支持 DNS 缓存，则为分支路由器启用 DNS 缓存。</span><span class="sxs-lookup"><span data-stu-id="9b461-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="9b461-214">或者，可以在分支上部署 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="9b461-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="9b461-215">这可以是独立服务器，也可以是支持 DNS 功能的 Survivable 分支设备的版本。</span><span class="sxs-lookup"><span data-stu-id="9b461-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="9b461-216">有关详细信息，请与你的 Survivable 分支设备提供商联系。</span><span class="sxs-lookup"><span data-stu-id="9b461-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b461-217">分支站点中不必有域控制器。</span><span class="sxs-lookup"><span data-stu-id="9b461-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="9b461-218">Survivable 分支设备使用特殊证书对客户端进行身份验证，该证书在客户端登录时向客户端的证书请求发送响应。</span><span class="sxs-lookup"><span data-stu-id="9b461-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="9b461-219">Lync 客户端可以使用 DHCP 选项120（SIP 注册器选项）发现 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="9b461-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="9b461-220">可通过以下两种方法之一配置该功能：</span><span class="sxs-lookup"><span data-stu-id="9b461-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="9b461-221">在分支站点上配置 DHCP 服务器以回复 DHCP 120 查询，该查询将在 Survivable 分支机构或 Survivable 分支服务器上返回注册器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9b461-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="9b461-222">打开 Lync Server DHCP。</span><span class="sxs-lookup"><span data-stu-id="9b461-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="9b461-223">如果启用此选项，Lync Server 注册器将响应 DHCP 选项120查询。</span><span class="sxs-lookup"><span data-stu-id="9b461-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="9b461-224">请注意，该注册器不会响应除 DHCP 选项 120 之外的任何 DHCP 查询。</span><span class="sxs-lookup"><span data-stu-id="9b461-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="9b461-225">此外，对于具有多个子网的大型分支站点，应启用 DHCP 中继代理来将 DHCP 选项 120 查询转发给 DHCP 服务器（配置 1）或注册器（配置 2）。</span><span class="sxs-lookup"><span data-stu-id="9b461-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="9b461-226">最后，必须为企业语音配置分支站点用户，并使用适当的统一通信终结点进行预配。</span><span class="sxs-lookup"><span data-stu-id="9b461-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="9b461-227">Survivable Branch Server 的要求</span><span class="sxs-lookup"><span data-stu-id="9b461-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="9b461-228">Survivable 分支服务器的要求与前端服务器的要求相同。</span><span class="sxs-lookup"><span data-stu-id="9b461-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="9b461-229">有关详细信息，请参阅规划文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="9b461-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="9b461-230">全面部署 Lync Server 分支站点的要求</span><span class="sxs-lookup"><span data-stu-id="9b461-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="9b461-231">有关详细信息，请参阅规划文档中的[确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b461-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

