---
title: Lync Server 2013：移动功能和特性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="96c82-102">Lync Server 2013 中的移动功能和特性</span><span class="sxs-lookup"><span data-stu-id="96c82-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c82-103">_**主题上次修改时间：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="96c82-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="96c82-104">Lync Server 2013 的累积更新中引入的移动功能：2月2013支持 Lync 2010 手机和 Lync 2013 移动客户端功能。</span><span class="sxs-lookup"><span data-stu-id="96c82-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="96c82-105">部署 Lync Server 2013 移动服务时，用户可以使用支持的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 移动设备执行诸如发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="96c82-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="96c82-106">此外，移动设备支持某些企业语音功能，例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="96c82-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="96c82-107">Lync Server 2013 的累积更新中引入的新功能：2月2013包括适用于会议与会者的 IP 语音（VoIP）功能和视频（H-p）。</span><span class="sxs-lookup"><span data-stu-id="96c82-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="96c82-108">Lync Server 2013 的累积更新中引入的移动功能：2月2013支持 Lync 2013 移动客户端功能。</span><span class="sxs-lookup"><span data-stu-id="96c82-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="96c82-109">Lync Server 2013 的累积更新：2月2013安装统一通信 Web API 或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="96c82-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="96c82-110">UCWA 是用于 Lync 2013 移动客户端的组件。</span><span class="sxs-lookup"><span data-stu-id="96c82-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="96c82-111">在 Lync Server 2013 中，Mcx 用于 Lync 2010 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="96c82-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="96c82-112">Lync Server 2013 的累积更新：2月2013将 UCWA 引入新的移动服务入口点。</span><span class="sxs-lookup"><span data-stu-id="96c82-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="96c82-113">Lync Server 2013 同时实现了在 Lync Server 2010 的累积更新中引入的移动服务（Mcx）：年 11 2011 月，并提供了对 Lync 2010 Mobile 的支持。</span><span class="sxs-lookup"><span data-stu-id="96c82-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="96c82-114">当你部署 Lync Server 2013 的累积更新时：2月2013，用户可以使用支持的 Apple iOS、Android 和 Windows Phone 移动设备执行如下活动：</span><span class="sxs-lookup"><span data-stu-id="96c82-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96c82-115">Lync Server 2010 的累积更新中的移动服务支持的功能：11月2011（Mcx）注明。</span><span class="sxs-lookup"><span data-stu-id="96c82-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="96c82-116">在 Lync Server 2013 的累积更新中引入的 UCWA 支持所有列出的功能：2月2013。</span><span class="sxs-lookup"><span data-stu-id="96c82-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="96c82-117">发送和接收即时消息（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="96c82-118">查看状态（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="96c82-119">查看联系人（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="96c82-120">单击以加入会议（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="96c82-121">通过工作进行通话（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="96c82-122">单数字到达（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="96c82-123">语音邮件（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="96c82-124">未接来电通知（Mcx）</span><span class="sxs-lookup"><span data-stu-id="96c82-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="96c82-125">IP 语音 (VoIP)</span><span class="sxs-lookup"><span data-stu-id="96c82-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="96c82-126">与会者视频 (H.264)</span><span class="sxs-lookup"><span data-stu-id="96c82-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96c82-127">Lync 2010 Mobile 提供了适用于 Nokia Symbian 设备的客户端。</span><span class="sxs-lookup"><span data-stu-id="96c82-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="96c82-128">Lync 2013 Mobile 将没有基于 Nokia Symbian 设备的客户端。</span><span class="sxs-lookup"><span data-stu-id="96c82-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="96c82-129">Apple iPad 用户将有权访问增强功能。</span><span class="sxs-lookup"><span data-stu-id="96c82-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="96c82-130">通过使用音频呼叫加入会议后，iPad 用户将能够在会议内查看上载的 Microsoft PowerPoint 演示文稿、共享应用程序和桌面、查看会议参与者列表以及接收其他内容类型的通知会议中共享的。</span><span class="sxs-lookup"><span data-stu-id="96c82-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="96c82-131">通过单个号码，用户可在移动电话上接收已拨至工作电话号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="96c82-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="96c82-132">通过工作电话，用户通过使用工作电话号码（而不是移动电话号码），从 Lync 移动客户端处发出出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="96c82-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="96c82-133">通过拨出，客户端将向 Mcx 或 UCWA （基于 Lync Mobile 版本）发送请求以进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="96c82-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="96c82-134">服务器启动呼叫，然后通过移动电话回拨用户。</span><span class="sxs-lookup"><span data-stu-id="96c82-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="96c82-135">当用户接听时，服务器将通过拨另一方来完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="96c82-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="96c82-136">通过使用 "通过工作呼叫"，用户可以在通话期间维护其工作标识，这意味着呼叫收件人看不到呼叫者的移动电话号码，并且呼叫者避免发出出站通话费用。</span><span class="sxs-lookup"><span data-stu-id="96c82-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="96c82-137">并非所有功能在所有移动设备上都具有完全相同的效果。</span><span class="sxs-lookup"><span data-stu-id="96c82-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="96c82-138">有关移动设备支持的功能的详细信息，请参阅中的移动客户<A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>端比较表。</span><span class="sxs-lookup"><span data-stu-id="96c82-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="96c82-139">有关支持的设备和操作系统的详细信息，请参阅<A href="lync-server-2013-planning-for-mobile-clients.md">规划 Lync Server 2013 中的移动客户端中</A>的 "要求" 主题。</span><span class="sxs-lookup"><span data-stu-id="96c82-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="96c82-140">使用 Lync Server 2013 自动发现功能时，移动应用程序可以自动查找 Lync Server 2013 Web 服务，而无需用户在其设备设置中手动输入 Url。</span><span class="sxs-lookup"><span data-stu-id="96c82-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="96c82-141">在移动设备设置中也支持手动输入 Url，这主要是出于故障排除目的。</span><span class="sxs-lookup"><span data-stu-id="96c82-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96c82-142">Mcx 和 UCWA 是免费服务，并且都是为支持 Lync 2010 移动版和 Lync 2013 移动客户端而部署的。</span><span class="sxs-lookup"><span data-stu-id="96c82-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="96c82-143">Lync 2013 Mobile 将无法登录 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="96c82-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="96c82-144">Lync 2010 手机和 Lync 2013 移动版将能够使用 lync server 2013 部署和 Lync Server 2013 的累积更新：应用了 2 2013 月。</span><span class="sxs-lookup"><span data-stu-id="96c82-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="96c82-145">移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。</span><span class="sxs-lookup"><span data-stu-id="96c82-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="96c82-146">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="96c82-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="96c82-147">例如，错过的即时消息（IM）邀请可能会导致推送通知。</span><span class="sxs-lookup"><span data-stu-id="96c82-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="96c82-148">Mcx、UCWA、自动发现服务和推送通知支持均在 Lync Server 2013 中提供。</span><span class="sxs-lookup"><span data-stu-id="96c82-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="96c82-149">在 Lync Server 2013 的累积更新中引入了客户端功能、功能和使用 UCWA 作为移动入口点：2月2013。</span><span class="sxs-lookup"><span data-stu-id="96c82-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

