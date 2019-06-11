---
title: Lync Server 2013：E9-1-1 概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="03d1f-102">Lync Server 2013 中的 E9-1-1 概述</span><span class="sxs-lookup"><span data-stu-id="03d1f-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03d1f-103">_**主题上次修改时间:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="03d1f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="03d1f-104">Microsoft Lync Server 2013 支持从 Lync 客户端和 Lync Phone Edition 设备进行增强的 9-1-1 (E9-1) 调用。</span><span class="sxs-lookup"><span data-stu-id="03d1f-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="03d1f-105">为 E9 配置 Lync Server 时, 由 Lync 2013 或 Lync Phone Edition 发出的紧急呼叫包括来自位置信息服务数据库的紧急响应位置 (ERL) 信息。</span><span class="sxs-lookup"><span data-stu-id="03d1f-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="03d1f-106">ERL 包含市政（即街道）地址，以及有助于确定在办公楼和其他多租户设施中的更精确位置的其他信息。</span><span class="sxs-lookup"><span data-stu-id="03d1f-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="03d1f-107">当用户进行紧急呼叫时, Lync 服务器通过中介服务器向 E9 服务提供商路由呼叫音频以及位置和回拨信息。</span><span class="sxs-lookup"><span data-stu-id="03d1f-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="03d1f-108">E9-1-1 服务提供商会使用呼叫者的市政地址，将呼叫路由到为呼叫者所在的位置提供服务的公共安全应答点 (PSAP)，并沿着 PSAP 用来查找呼叫者 ERL 的紧急服务查询键 (ESQK) 进行发送。</span><span class="sxs-lookup"><span data-stu-id="03d1f-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="03d1f-109">Lync Server 支持两种方法将紧急呼叫路由到 E9 服务提供商:</span><span class="sxs-lookup"><span data-stu-id="03d1f-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="03d1f-110">到合格的 E9-1-1 服务提供商的会话初始协议 (SIP) 中继连接</span><span class="sxs-lookup"><span data-stu-id="03d1f-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="03d1f-111">到基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商的紧急位置标识号 (ELIN) 网关</span><span class="sxs-lookup"><span data-stu-id="03d1f-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="03d1f-112">使用 SIP trunk E9 服务提供商时, 请将 ERLs 添加到位置信息服务数据库, 然后根据 E9 地址指南 (MSAG) 为-1 服务提供商维护的主要街道地址指南 () 验证位置。</span><span class="sxs-lookup"><span data-stu-id="03d1f-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="03d1f-113">如果 E9 服务提供商接收到的呼叫没有位置信息, 或者有尚未验证的位置以 MSAG, 则 E9-1 服务提供商将呼叫路由到国家/地区紧急呼叫回复中心 (ECRC), 这是口头获取呼叫方的位置 (如有可能), 并手动将呼叫路由到相应的 PSAP 的专门培训的人员。</span><span class="sxs-lookup"><span data-stu-id="03d1f-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="03d1f-114">(某些 SIP 中继 E9 服务提供商还向客户提供 PSTN 直接向内拨号 (已有) 号码给 ECRC, 该号码提供了路由9-1-1 呼叫的备用方法, 如果 SIP 干线因任何原因而失败。)</span><span class="sxs-lookup"><span data-stu-id="03d1f-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="03d1f-115">与时间段复用 (TDM) 和基于 IP 的专用分支 exchange (PBX) 手机 (具有固定位置) 不同, Lync 终结点可以很轻松地进行移动。</span><span class="sxs-lookup"><span data-stu-id="03d1f-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="03d1f-116">当您部署 E9-1 功能时, Lync 服务器有助于确保无论呼叫者身在何处, 紧急呼叫都可以路由到服务于呼叫者位置的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="03d1f-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="03d1f-117">例如，如果用户的总部位于华盛顿州的雷德蒙德，而用户从位于堪萨斯州威奇托的分支机构的计算机发出紧急呼叫，则基于 SIP 中继或 PSTN 的 E9-1-1 服务提供商会将该呼叫路由至威奇托的 PSAP，而不是雷德蒙德的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="03d1f-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="03d1f-118">使用 ELIN 网关时, 还会将 ERLs 添加到位置信息服务数据库, 但每个位置还包括一个 ELIN 号码。</span><span class="sxs-lookup"><span data-stu-id="03d1f-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="03d1f-119">ELIN 号码会在紧急呼叫过程中变为紧急呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="03d1f-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="03d1f-120">然后，你必须确保 PSTN 运营商将 ELIN 上载到自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="03d1f-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03d1f-121">连接到 Lync 的模拟设备无法接收位置信息服务中的位置信息或将位置信息发送到 E9 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="03d1f-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="03d1f-122">如果使用 SIP 中继 E9-1-1 服务提供商选项并需要通过模拟电话支持 E9-1-1，则有以下两个选项：</span><span class="sxs-lookup"><span data-stu-id="03d1f-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="03d1f-123"><STRONG>传统的 PS-阿里选项</STRONG>&nbsp;&nbsp;&nbsp;如果每个站点上都有本地 PSTN 网关, 并且每个模拟电话都有, 则可以直接使用专用开关/自动设置模拟设备的位置位置标识 (PS-阿里) 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="03d1f-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="03d1f-124">在这种情况下, 你将配置巧尽心思构建的 Lync 语音策略, 并将其分配给模拟设备联系人对象, 以便从这些电话直接通过本地网关将 E9 路由到服务该站点的 PSTN 提供商 (而不是路由拨打 E9 服务提供商 SIP 主干。</span><span class="sxs-lookup"><span data-stu-id="03d1f-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="03d1f-125">发出紧急呼叫后，与 PSTN 中继关联的 PS-ALI 提供商的数据库会将每个模拟电话的 DID 映射到一个物理位置并将此位置提供给 PSAP。</span><span class="sxs-lookup"><span data-stu-id="03d1f-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="03d1f-126">每当将电话移至不同的 ERL 时，必须通过 PS-ALI 服务提供商更新这些记录。</span><span class="sxs-lookup"><span data-stu-id="03d1f-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="03d1f-127"><STRONG>E9-1-1-1 服务提供商选项</STRONG>&nbsp;&nbsp;&nbsp;您可以向 E9-1 服务提供商注册模拟电话 DIDs 及其相应的 ERLs, 前提是 E9 服务提供商支持此服务提供商。</span><span class="sxs-lookup"><span data-stu-id="03d1f-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="03d1f-128">如果提供商收到来自 Lync Server 的不包含 PIDF 数据的呼叫, 则该提供商可以查看呼叫方的已做号码是否存在数据库匹配。</span><span class="sxs-lookup"><span data-stu-id="03d1f-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="03d1f-129">通过使用从数据库检索到的 ERL，提供商可自动将紧急呼叫路由至正确的 PSAP，该 PSAP 将收到模拟设备的 DID 和允许调度程序查找呼叫者位置的 ESQK 记录。</span><span class="sxs-lookup"><span data-stu-id="03d1f-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="03d1f-p108">如果您使用 ELIN 网关选项并需要通过模拟电话支持 E9-1-1，则可以直接向 PS-ALI 服务提供商提供模拟设备的位置，如上面第一个选项中所述。</span><span class="sxs-lookup"><span data-stu-id="03d1f-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="03d1f-131">从 Lync Server 的角度来看, E9 (1-1) 过程可以分为两个阶段:</span><span class="sxs-lookup"><span data-stu-id="03d1f-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="03d1f-132">阶段 1：获取位置</span><span class="sxs-lookup"><span data-stu-id="03d1f-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="03d1f-133">阶段 2：将紧急呼叫路由至 E9-1-1 服务提供商</span><span class="sxs-lookup"><span data-stu-id="03d1f-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="03d1f-134">本节介绍这些阶段的工作原理。</span><span class="sxs-lookup"><span data-stu-id="03d1f-134">This section describes how these stages work.</span></span>

<span data-ttu-id="03d1f-135">如果计划将基础结构配置为自动检测客户端位置，则首先需要确定将使用哪些网络元素将呼叫者映射到不同位置。</span><span class="sxs-lookup"><span data-stu-id="03d1f-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="03d1f-136">有关可能的选项的详细信息, 请参阅[定义用于确定 Lync Server 2013 中的位置的网络元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)。</span><span class="sxs-lookup"><span data-stu-id="03d1f-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="03d1f-137">本节内容</span><span class="sxs-lookup"><span data-stu-id="03d1f-137">In This Section</span></span>

  - [<span data-ttu-id="03d1f-138">在 Lync Server 2013 中获取位置</span><span class="sxs-lookup"><span data-stu-id="03d1f-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="03d1f-139">在 Lync Server 2013 中使用 SIP 中继路由 E9-1-1 呼叫</span><span class="sxs-lookup"><span data-stu-id="03d1f-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="03d1f-140">在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫</span><span class="sxs-lookup"><span data-stu-id="03d1f-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

