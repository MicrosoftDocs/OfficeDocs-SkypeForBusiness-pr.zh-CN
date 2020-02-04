---
title: Lync Server 2013：语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42aa810f40a6c00c7f2779acdf39caf39d7b2f07
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="715cc-102">Lync Server 2013 中的语音路由</span><span class="sxs-lookup"><span data-stu-id="715cc-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="715cc-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="715cc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="715cc-104">呼叫路线指定 Lync 服务器如何处理由企业语音用户发出的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="715cc-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="715cc-105">当用户拨打电话号码时，前端服务器会根据需要将拨号字符串标准化为-164 格式，并尝试将其与 SIP URI 匹配。</span><span class="sxs-lookup"><span data-stu-id="715cc-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="715cc-106">如果服务器无法进行匹配，它将基于该号码应用传出呼叫路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="715cc-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="715cc-107">定义该逻辑的最后一步是为每个拨号计划中所列出的每组目标电话号码创建单独的命名呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="715cc-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="715cc-108">在定义出站呼叫路由之前，应当完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="715cc-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="715cc-109">部署一个或多个中继。</span><span class="sxs-lookup"><span data-stu-id="715cc-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="715cc-110">根据需要为站点、个人和联系人对象创建拨号计划。</span><span class="sxs-lookup"><span data-stu-id="715cc-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="715cc-111">创建公用电话交换网 (PSTN) 用法记录。</span><span class="sxs-lookup"><span data-stu-id="715cc-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="715cc-p102">另外，为了启用出站呼叫路由，您必须创建并分配一个或多个语音策略。您既可以在定义出站呼叫路由之前，也可以在这之后执行此操作。</span><span class="sxs-lookup"><span data-stu-id="715cc-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="715cc-114">对于每个路由，必须指定：</span><span class="sxs-lookup"><span data-stu-id="715cc-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="715cc-115">一个名称，用来方便地标识路由。</span><span class="sxs-lookup"><span data-stu-id="715cc-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="715cc-116">可选说明，在名称本身不足以描述路由时使用。</span><span class="sxs-lookup"><span data-stu-id="715cc-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="715cc-117">正则表达式匹配模式，可识别应用路由的目标电话号码，以及不应用匹配模式的例外情况。</span><span class="sxs-lookup"><span data-stu-id="715cc-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="715cc-118">要分配给路由的一个或多个中继。</span><span class="sxs-lookup"><span data-stu-id="715cc-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="715cc-119">PSTN 用法记录，用户必须拥有该记录才能呼叫与目标电话号码正则表达式相匹配的号码。</span><span class="sxs-lookup"><span data-stu-id="715cc-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="715cc-120">您可以在 Lync Server 控制面板中指定呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="715cc-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="715cc-121">这些呼叫路由将填充服务器路由表，Lync 服务器将使用该路由表路由发送到 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="715cc-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="715cc-122">M:N 中继支持</span><span class="sxs-lookup"><span data-stu-id="715cc-122">M:N Trunk Support</span></span>

<span data-ttu-id="715cc-123">Lync Server 提供了如何将呼叫路由到 PSTN 的灵活性。</span><span class="sxs-lookup"><span data-stu-id="715cc-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="715cc-124">语音路由可指定一组指向可用于特定语音呼叫的 PSTN 的中继。</span><span class="sxs-lookup"><span data-stu-id="715cc-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="715cc-125">主干将中介服务器和端口号与 PSTN 网关和侦听端口号相关联。</span><span class="sxs-lookup"><span data-stu-id="715cc-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="715cc-126">此逻辑关联使中介服务器可以与多个网关关联，并且具有多个连接到同一网关的连接。</span><span class="sxs-lookup"><span data-stu-id="715cc-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="715cc-127">定义呼叫路线时，指定与该路线关联的中继，但不指定哪些中介服务器与该路由关联。</span><span class="sxs-lookup"><span data-stu-id="715cc-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="715cc-128">若要通过定义中介服务器和 PSTN 网关、IP-Pbx 和会话边界控制器（SBCs）之间的关系创建中继，请使用拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="715cc-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="715cc-129">最低成本路由</span><span class="sxs-lookup"><span data-stu-id="715cc-129">Least-Cost Routing</span></span>

<span data-ttu-id="715cc-p105">由于您可以指定各个号码所路由到的中继，因此可以确定哪些路由成本最低并相应地实现这些路由。在选择中继时，一般规则是选择具有距离目标号码所在位置最近的网关的中继，以便尽可能降低长途费用。例如，如果您在纽约呼叫罗马的号码，则应当通过 IP 网络将电话传送至网关位于您驻罗马办事处的中继，这样就只会产生本地电话的费用。</span><span class="sxs-lookup"><span data-stu-id="715cc-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="715cc-133">有关如何使用最低成本路由的示例，请考虑以下内容：Fabrkam 决定允许德国用户使用美国中继拨打美国号码。</span><span class="sxs-lookup"><span data-stu-id="715cc-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="715cc-134">Fabrikam 还希望配置系统，以便从美国 Lync 服务器用户到德国的所有呼叫和邻近国家/地区的所有呼叫都将在德国的网关与主干上终止。</span><span class="sxs-lookup"><span data-stu-id="715cc-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="715cc-135">这种路由可以省钱，因为举例来说，从德国发往澳大利亚的呼叫比从美国发往澳大利亚的呼叫便宜。</span><span class="sxs-lookup"><span data-stu-id="715cc-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="715cc-136">转换出站拨号串</span><span class="sxs-lookup"><span data-stu-id="715cc-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="715cc-137">Lync Server 2013 （如它的直属前置任务）要求将所有拨号字符串正常化为格式，以便执行反向数字查找（RNL）。</span><span class="sxs-lookup"><span data-stu-id="715cc-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="715cc-138">对于需要以本地拨号格式转换数字的网关或专用分支交换（Pbx）的中继，Lync Server 2013 使你能够创建一个或多个规则，帮助你在将其路由到之前处理已调用的号码（主干.</span><span class="sxs-lookup"><span data-stu-id="715cc-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="715cc-139">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的规则。</span><span class="sxs-lookup"><span data-stu-id="715cc-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="715cc-140">在 Lync Server 2013 中，可以创建一个或多个规则，在将呼叫号码路由到主干之前对其进行协助操作。</span><span class="sxs-lookup"><span data-stu-id="715cc-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="715cc-141">在规划将网关与中介服务器：端口对相关联的中继时，对具有类似本地拨号要求的中继进行分组可能会很有用，从而减少所需翻译规则的数量以及写入它们所需的时间。</span><span class="sxs-lookup"><span data-stu-id="715cc-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="715cc-142">配置呼叫者 ID</span><span class="sxs-lookup"><span data-stu-id="715cc-142">Configuring Caller ID</span></span>

<span data-ttu-id="715cc-143">Lync 服务器提供一种操作呼叫方 ID 以进行出站呼叫的方法。</span><span class="sxs-lookup"><span data-stu-id="715cc-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="715cc-144">例如，如果组织想要掩盖员工的直接拨号分机，并将其替换为一般的公司或部门编号，管理员可以通过使用 Lync Server 控制面板取消呼叫方 ID 并将其替换为指定的备用呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="715cc-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="715cc-145">在规划路由逻辑时，请考虑您希望此选项面向哪些个人、组或站点 - 甚至也许面向所有员工。</span><span class="sxs-lookup"><span data-stu-id="715cc-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="715cc-p109">对于通过 PSTN 重新路由的呼叫，将显示常规呼叫者 ID，而不是原始呼叫者 ID。这可能会导致呼叫绕过被叫方可能已配置的“请勿打扰”或隐私设置。</span><span class="sxs-lookup"><span data-stu-id="715cc-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="715cc-148">其他路由逻辑</span><span class="sxs-lookup"><span data-stu-id="715cc-148">Additional Routing Logic</span></span>

<span data-ttu-id="715cc-149">在创建出站呼叫路由时，应当注意可能影响路由逻辑的以下因素：</span><span class="sxs-lookup"><span data-stu-id="715cc-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="715cc-150">如果呼叫是通过联盟边界建立的，则 URI 的域部分会将该呼叫路由到负责应用出站路由逻辑的企业。</span><span class="sxs-lookup"><span data-stu-id="715cc-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="715cc-151">如果请求 URI 的域部分不包含企业的支持域，则服务器上的出站路由组件不会处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="715cc-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="715cc-152">如果用户未启用企业语音，则服务器会根据需要应用其他路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="715cc-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="715cc-p110">如果呼叫路由到已被完全占用的网关（即所有的中继线路都繁忙），则网关会拒绝该呼叫，并且出站路由逻辑会将该呼叫重定向到下一个成本最低的路由。请对此认真考虑，因为大小适合国外小型办事处（例如，苏黎世办事处）的网关可能会针对发往瑞士的国际呼叫实际传送大量非本地流量。如果网关没有针对这个额外的流量正确地调整大小，则发往瑞士的呼叫可能会通过德国的网关路由，这会增加长途电话费。</span><span class="sxs-lookup"><span data-stu-id="715cc-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

