---
title: Lync Server 2013：移动特性和功能
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
ms.openlocfilehash: a001a6fb76a0612f7f650a31de5cf788a7f69327
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="9e202-102">Lync Server 2013 中的移动特性和功能</span><span class="sxs-lookup"><span data-stu-id="9e202-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e202-103">_**上次修改的主题：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9e202-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9e202-104">Lync Server 2013 的累积更新中引入的移动功能：二月份2013支持 Lync 2010 移动和 Lync 2013 移动客户端功能。</span><span class="sxs-lookup"><span data-stu-id="9e202-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="9e202-105">在部署 Lync Server 2013 移动服务时，用户可以使用支持的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 移动设备执行诸如发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="9e202-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="9e202-106">此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。</span><span class="sxs-lookup"><span data-stu-id="9e202-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="9e202-107">Lync Server 2013 的累积更新中引入的新功能：二月份2013包括适用于会议与会者的 IP 语音（VoIP）功能和视频（）。</span><span class="sxs-lookup"><span data-stu-id="9e202-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="9e202-108">Lync Server 2013 的累积更新中引入的移动功能：2月2013支持 Lync 2013 移动客户端功能。</span><span class="sxs-lookup"><span data-stu-id="9e202-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="9e202-109">Lync Server 2013 的累积更新：2月2013安装统一通信 Web API 或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="9e202-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="9e202-110">UCWA 是用于 Lync 2013 移动客户端的组件。</span><span class="sxs-lookup"><span data-stu-id="9e202-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9e202-111">在 Lync Server 2013 中，Mcx 用于 Lync 2010 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="9e202-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="9e202-112">Lync Server 2013 的累积更新：二月份2013将 UCWA 作为移动服务的新入口点引入。</span><span class="sxs-lookup"><span data-stu-id="9e202-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="9e202-113">Lync Server 2013 在 Lync Server 2011 2010 的累积更新中引入了移动服务（Mcx），并为 Lync 2010 移动提供了支持。</span><span class="sxs-lookup"><span data-stu-id="9e202-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="9e202-114">在部署 Lync Server 2013 2013 的累积更新时，用户可以使用受支持的 Apple iOS、Android 和 Windows Phone 移动设备执行此类活动，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9e202-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9e202-115">移动服务从 Lync Server 2010 的累积更新支持的功能：11月2011日使用（Mcx）进行标注。</span><span class="sxs-lookup"><span data-stu-id="9e202-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="9e202-116">在 Lync Server 2013 的累积更新中引入的 UCWA 支持所有列出的功能：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="9e202-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="9e202-117">发送和接收即时消息（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="9e202-118">查看状态（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="9e202-119">查看联系人（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="9e202-120">单击以加入会议（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="9e202-121">通过工作呼叫（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="9e202-122">单个数字范围（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="9e202-123">语音邮件（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="9e202-124">未接来电通知（Mcx）</span><span class="sxs-lookup"><span data-stu-id="9e202-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="9e202-125">IP 电话 (VoIP)</span><span class="sxs-lookup"><span data-stu-id="9e202-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="9e202-126">与会者视频（H-p）</span><span class="sxs-lookup"><span data-stu-id="9e202-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e202-127">Lync 2010 Mobile 提供了适用于 Nokia Symbian 设备的客户端。</span><span class="sxs-lookup"><span data-stu-id="9e202-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="9e202-128">Lync 2013 Mobile 不会有客户端用于基于 Nokia Symbian 的设备。</span><span class="sxs-lookup"><span data-stu-id="9e202-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="9e202-129">Apple iPad 用户将可以访问增强功能。</span><span class="sxs-lookup"><span data-stu-id="9e202-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="9e202-130">使用音频呼叫回电加入会议后，iPad 用户将能够在会议中查看已上载的 Microsoft PowerPoint 演示文稿、共享应用程序和桌面、查看会议参与者列表，以及接收其他内容类型的通知会议中共享的。</span><span class="sxs-lookup"><span data-stu-id="9e202-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9e202-131">利用一号通功能，用户可以通过移动电话接收拨打至单位号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e202-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="9e202-132">通过工作的呼叫，用户通过使用工作电话号码而不是移动电话号码，从 Lync 移动客户端发出出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e202-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="9e202-133">通过拨出，客户端将向 Mcx 或 UCWA （基于 Lync Mobile 版本）发送请求，以便对其进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e202-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="9e202-134">服务器将发起呼叫，然后在移动电话上回拨用户。</span><span class="sxs-lookup"><span data-stu-id="9e202-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="9e202-135">当用户应答时，服务器将通过拨打另一方的号码来完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e202-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="9e202-136">通过使用单位电话呼叫功能，用户可以在呼叫期间维护其工作标识，这意味着呼叫接收方将看不到呼叫者的移动电话号码，并且呼叫者可免于支付出站呼叫费。</span><span class="sxs-lookup"><span data-stu-id="9e202-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9e202-137">并非所有功能在所有移动设备上的工作方式都相同。</span><span class="sxs-lookup"><span data-stu-id="9e202-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="9e202-138">有关移动设备支持的功能的详细信息，请参阅中<A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>的移动客户端比较表。</span><span class="sxs-lookup"><span data-stu-id="9e202-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="9e202-139">有关受支持的设备和操作系统的详细信息，请参阅在<A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013 中规划移动客户端</A>的要求主题。</span><span class="sxs-lookup"><span data-stu-id="9e202-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9e202-140">当您使用 Lync Server 2013 自动发现功能时，移动应用程序可以自动定位 Lync Server 2013 Web 服务，而无需用户在其设备设置中手动输入 Url。</span><span class="sxs-lookup"><span data-stu-id="9e202-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="9e202-141">在移动设备设置中手动输入 URL 也是受支持的，此操作主要用于进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="9e202-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9e202-142">Mcx 和 UCWA 是免费的服务，同时还部署了这两个服务，以支持 Lync 2010 移动和 Lync 2013 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="9e202-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9e202-143">Lync 2013 移动将无法登录 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="9e202-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="9e202-144">Lync 2010 Mobile 和 Lync 2013 移动版将能够使用 lync server 2013 部署，其中包含应用了 Lync Server 2013：二月份2013的累积更新。</span><span class="sxs-lookup"><span data-stu-id="9e202-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="9e202-145">移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。</span><span class="sxs-lookup"><span data-stu-id="9e202-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="9e202-146">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="9e202-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="9e202-147">例如，错过的即时消息（IM）邀请可能会导致推送通知。</span><span class="sxs-lookup"><span data-stu-id="9e202-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="9e202-148">Lync Server 2013 中提供了 Mcx、UCWA、自动发现服务和对推送通知的支持。</span><span class="sxs-lookup"><span data-stu-id="9e202-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="9e202-149">在 Lync Server 2013 的累积更新中引入了客户端功能、功能和使用 UCWA 作为移动入口点的更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="9e202-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

