---
title: Lync Server 2013：使用 ELIN 网关路由 E9-1-1 呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdb4b5879f92da79e8a6ec96f61e24fbe182c028
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="0e661-102">在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫</span><span class="sxs-lookup"><span data-stu-id="0e661-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e661-103">_**主题上次修改时间:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="0e661-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="0e661-104">统一通信开放互操作性计划中的某些合作伙伴提供了合格的支持紧急位置标识号 (ELIN) 的网关，该网关可充当合格 E9-1-1 服务提供商的 SIP 中继连接的备选项。</span><span class="sxs-lookup"><span data-stu-id="0e661-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="0e661-105">ELIN 网关支持 ISDN 或与基于公用电话交换网 (PSTN) 的 E9-1-1 服务的集中式自动通话记帐 (CAMA) 连接。</span><span class="sxs-lookup"><span data-stu-id="0e661-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="0e661-106">有关提供 ELIN 网关的合作伙伴以及其文档的链接的详细信息[http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425), 请参阅。</span><span class="sxs-lookup"><span data-stu-id="0e661-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="0e661-107">与 E9-1-1 服务提供商的 SIP 中继连接相似，ELIN 网关还提供了将紧急呼叫路由到呼叫者的最合适的公共安全应答点 (PSAP) 的方法，但这些网关将 ELIN 用作位置标识符。</span><span class="sxs-lookup"><span data-stu-id="0e661-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="0e661-108">为你的组织中的每个紧急响应位置 (ERL) 定义 ELINs (有关详细信息, 请参阅[在 Lync Server 2013 中管理 ELIN 网关的位置](lync-server-2013-managing-locations-for-elin-gateways.md))。</span><span class="sxs-lookup"><span data-stu-id="0e661-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="0e661-109">将 ELIN 网关用于紧急呼叫时, 你使用的是用于 SIP 中继连接的同一 Lync Server E9-1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="0e661-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="0e661-110">也就是说, 位置信息服务数据库提供 Lync Server 客户端的位置, 并且位置策略启用该功能并定义路由。</span><span class="sxs-lookup"><span data-stu-id="0e661-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="0e661-111">但是, 使用 ELIN 网关时, 你需要将 ELINs 添加到位置信息服务数据库, 并让 PSTN 运营商将其上传到自动位置识别 (阿里) 数据库。</span><span class="sxs-lookup"><span data-stu-id="0e661-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="0e661-112">当 Lync 客户从位置信息服务获取其位置时, 位置包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="0e661-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="0e661-113">在紧急呼叫期间，ELIN 将包含在发送到 ELIN 网关的位置中。</span><span class="sxs-lookup"><span data-stu-id="0e661-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="0e661-114">ELIN 网关会将此呼叫标识为紧急呼叫并将呼叫者的号码与 ELIN 交换。</span><span class="sxs-lookup"><span data-stu-id="0e661-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="0e661-115">ELIN 网关随后会将呼叫路由到带有作为主叫号码的 ELIN 的 PSTN。</span><span class="sxs-lookup"><span data-stu-id="0e661-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="0e661-116">PSTN E9-1-1 提供商将在 ALI 数据库中查找 ELIN，该数据库是主街道地址指南 (MSAG) 数据库的附带数据库。</span><span class="sxs-lookup"><span data-stu-id="0e661-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="0e661-117">PSTN 随后会根据 ALI 查找将呼叫发送到最合适的 PSAP，而 PSAP 会根据 ALI 查找将第一个响应者发送到呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="0e661-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="0e661-118">主叫号码将在 ELIN 网关上缓存一段预定时间以供回拨。</span><span class="sxs-lookup"><span data-stu-id="0e661-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="0e661-119">在回拨期间，PSAP 将到达 ELIN 网关，后者会将 ELIN 与呼叫者的直拨分机 (DID) 号码交换。</span><span class="sxs-lookup"><span data-stu-id="0e661-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="0e661-120">ELIN 网关仅支持来自您组织的网络中的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="0e661-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="0e661-121">它们不支持从您的网络外发出的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="0e661-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e661-122">有关使用 SIP 中继连接进行紧急呼叫的详细信息, 请参阅<A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">在 Lync Server 2013 中使用 sip 主干进行路由 E9 呼叫</A>。</span><span class="sxs-lookup"><span data-stu-id="0e661-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0e661-123">下图显示了使用 ELIN 网关时, 如何将紧急呼叫从 Lync Server 路由到 PSAP。</span><span class="sxs-lookup"><span data-stu-id="0e661-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="0e661-124">**使用 ELIN 网关路由 E9-1-1 呼叫**</span><span class="sxs-lookup"><span data-stu-id="0e661-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="0e661-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="0e661-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="0e661-126">包含位置、呼叫者的回拨号码以及 (可选) 通知 URL 和会议回呼号码的 SIP 邀请将路由到 Lync 服务器。</span><span class="sxs-lookup"><span data-stu-id="0e661-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="0e661-127">Lync Server 匹配紧急号码, 然后将呼叫路由 (基于在适用位置策略中定义的**PSTN 使用**值) 到中介服务器, 以及从此处到 ELIN 网关。</span><span class="sxs-lookup"><span data-stu-id="0e661-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="0e661-128">ELIN 网关通过 ISDN 或 CAMA 中继将呼叫路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="0e661-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="0e661-p106">PSTN 将呼叫标识为紧急呼叫并将其路由到网路中的 E9-1-1 选择性路由器。E9-1-1 选择性路由器在 ALI 数据库中查找呼叫者的号码以获取地理位置。E9-1-1 选择性路由器根据从 ALI 数据库中检索到的位置信息将呼叫发送到最合适的 PSAP。 </span><span class="sxs-lookup"><span data-stu-id="0e661-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="0e661-132">如果为通知配置了位置策略, 则会向一个或多个组织的安全专员发送特殊的 Lync 紧急通知即时消息。</span><span class="sxs-lookup"><span data-stu-id="0e661-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="0e661-133">此消息始终会在安全主管的屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员可以使用即时消息或语音快速应答紧急呼叫者。</span><span class="sxs-lookup"><span data-stu-id="0e661-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="0e661-p108">如果呼叫被永久性中断，PSAP 将使用 ELIN 直接联系呼叫者。ELIN 网关会将 ELIN 与呼叫者的 DID 交换。</span><span class="sxs-lookup"><span data-stu-id="0e661-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

