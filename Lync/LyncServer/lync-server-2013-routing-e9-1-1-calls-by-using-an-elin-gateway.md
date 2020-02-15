---
title: Lync Server 2013：使用 ELIN 网关路由 E9-1-1 呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: befa9ad077780eb57d4690790673fc0a5452af60
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="aa0b1-102">在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫</span><span class="sxs-lookup"><span data-stu-id="aa0b1-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0b1-103">_**上次修改的主题：** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="aa0b1-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="aa0b1-104">统一通信开放互操作性计划中的一些合作伙伴提供启用了合格的紧急位置识别号码 (ELIN) 的网关，可以充当到合格的 E9-1-1 服务提供商的 SIP 中继连接的替代之选。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="aa0b1-105">ELIN 网关支持与基于公用电话交换网 (PSTN) 的 E9-1-1 服务的 ISDN 或集中式自动信息计算 (CAMA) 连接。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="aa0b1-106">有关提供 ELIN 网关的合作伙伴以及其文档的链接的详细信息[http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="aa0b1-107">与 E9-1-1 服务提供商的 SIP 中继连接一样，ELIN 网关还提供了将紧急呼叫路由到呼叫者最合适的公共安全应答点（PSAP）的方法，但这些网关使用 ELIN 作为位置标识符。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="aa0b1-108">您可以为组织中的每个紧急响应位置（ERL）定义 Elin （有关详细信息，请参阅[在 Lync Server 2013 中管理 ELIN 网关的位置](lync-server-2013-managing-locations-for-elin-gateways.md)）。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="aa0b1-109">当您使用 ELIN 网关进行紧急呼叫时，请使用与您将用于 SIP 中继连接的同一 Lync Server E9-1 基础结构。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="aa0b1-110">也就是说，位置信息服务数据库提供了 Lync Server 客户端的位置，并且位置策略启用了该功能并定义了路由。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="aa0b1-111">但是，使用 ELIN 网关时，您需要将 Elin 添加到位置信息服务数据库，并让 PSTN 运营商将其上载到自动位置标识（阿里）数据库。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="aa0b1-112">当 Lync 客户端从 Location 信息服务获取其位置时，该位置包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="aa0b1-113">在紧急呼叫期间，ELIN 包括在发送到 ELIN 网关的位置中。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="aa0b1-114">ELIN 网关将该呼叫识别为紧急呼叫并将呼叫方的号码交换为 ELIN。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="aa0b1-115">然后 ELIN 网关使用 ELIN 作为呼叫号码将呼叫路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="aa0b1-116">PSTN E9-1-1 提供商在 ALI 数据库中查找 ELIN，该数据库与主街道地址指南 (MSAG) 数据库是配套数据库。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="aa0b1-117">然后 PSTN 根据 ALI 查询将呼叫发送到最适宜的 PSAP，随后 PSAP 根据 ALI 查询将首位响应者发送到呼叫者位置。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="aa0b1-118">呼叫号码在 ELIN 网关上缓存预定义的一段时间以便回叫。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="aa0b1-119">在回叫期间，PSAP 到达 ELIN 网关，后者将 ELIN 交换为呼叫者的直接拨入 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="aa0b1-120">ELIN 网关仅支持来自组织网络的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="aa0b1-121">它们不支持从您网络外部发出的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa0b1-122">有关使用 SIP 中继连接进行紧急呼叫的详细信息，请参阅<A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">通过在 Lync Server 2013 中使用 sip 中继路由 E9-1-1 呼叫</A>。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="aa0b1-123">下图显示了在使用 ELIN 网关时，紧急呼叫如何从 Lync Server 路由到 PSAP。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="aa0b1-124">**使用 ELIN 网关路由 E9-1-1 呼叫**</span><span class="sxs-lookup"><span data-stu-id="aa0b1-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="aa0b1-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="aa0b1-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="aa0b1-126">包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回拨号码的 SIP INVITE 将路由到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="aa0b1-127">Lync Server 匹配紧急号码，然后将呼叫路由到中介服务器，并**将其路由**到中介服务器，并从此处发送到 ELIN 网关。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="aa0b1-128">ELIN 网关通过 ISDN 或 CAMA 中继将呼叫路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="aa0b1-p106">PSTN 将呼叫标识为紧急呼叫并将其路由到网路中的 E9-1-1 选择性路由器。E9-1-1 选择性路由器在 ALI 数据库中查找呼叫者的号码以获取地理位置。E9-1-1 选择性路由器根据从 ALI 数据库中检索到的位置信息将呼叫发送到最合适的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="aa0b1-132">如果为通知配置了位置策略，则会向一个或多个组织的安全主管发送特殊的 Lync 急诊通知即时消息。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="aa0b1-133">此消息始终会在安全人员的屏幕上弹出，并且包含呼叫者的姓名、电话号码、时间和位置，这就让安全人员可以使用即时消息或语音快速响应紧急呼叫者。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="aa0b1-p108">如果呼叫过早地中断，那么 PSAP 使用 ELIN 直接联系呼叫者。ELIN 网关将 ELIN 交换为呼叫者的 DID。</span><span class="sxs-lookup"><span data-stu-id="aa0b1-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

