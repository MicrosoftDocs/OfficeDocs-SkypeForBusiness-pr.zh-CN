---
title: Lync Server 2013 A/V 会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2499b7cae2a6833612c34b877ca872f1a504fac9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="68c4d-102">Lync Server 2013 中的 A/V 会议概述</span><span class="sxs-lookup"><span data-stu-id="68c4d-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68c4d-103">_**上次修改的主题：** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="68c4d-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="68c4d-104">A/V 会议在您的用户之间实现实时音频和视频通信。</span><span class="sxs-lookup"><span data-stu-id="68c4d-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="68c4d-105">在部署会议时，可以选择同时启用并使用 Web 会议和 A/V 会议，也可以仅启用并使用 Web 会议。</span><span class="sxs-lookup"><span data-stu-id="68c4d-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="68c4d-106">要规划 A/V 会议，需了解组织所需会议媒体类型要求的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="68c4d-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="68c4d-107">这可能包括音频、视频和全景视频。</span><span class="sxs-lookup"><span data-stu-id="68c4d-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="68c4d-108">在为用户启用 A/V 会议之前，请确保您的网络能够处理生成的负载。</span><span class="sxs-lookup"><span data-stu-id="68c4d-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="68c4d-109">如果没有足够的网络带宽，用户体验可能会受到严重降低。</span><span class="sxs-lookup"><span data-stu-id="68c4d-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="68c4d-110">可以使用呼叫允许控制（CAC）管理由 A/V 会议使用的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="68c4d-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="68c4d-111">对于受限制的网络（例如中央网站和分支网站之间的有限带宽链接），这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="68c4d-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="68c4d-112">有关详细信息，请参阅[Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="68c4d-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="68c4d-113">有关媒体带宽要求的详细信息，请参阅[Lync Server 2013 中媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。</span><span class="sxs-lookup"><span data-stu-id="68c4d-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="68c4d-114">如果在网络中部署音频会议，用户将需要音频设备（如耳机）参加音频会议。</span><span class="sxs-lookup"><span data-stu-id="68c4d-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="68c4d-115">如果您部署视频会议，则需要部署视频设备，例如用户的网络摄像机。</span><span class="sxs-lookup"><span data-stu-id="68c4d-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="68c4d-116">我们建议您使用 Microsoft 针对所有设备类型认证的统一通信（UC）设备，以确保获得最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="68c4d-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="68c4d-117">有关 UC 认证设备的详细信息，请参阅位于[https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)的 "电话和设备（Lync）"。</span><span class="sxs-lookup"><span data-stu-id="68c4d-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="68c4d-118">对于音频或视频设备、设备部署和用户培训是考虑和规划的重要步骤之一。</span><span class="sxs-lookup"><span data-stu-id="68c4d-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="68c4d-119">以下各节介绍了音频和视频会议的功能，其中包括有关管理带宽和选择相应客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="68c4d-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="68c4d-120">音频会议功能</span><span class="sxs-lookup"><span data-stu-id="68c4d-120">Audio Conferencing Features</span></span>

<span data-ttu-id="68c4d-121">Lync Server 2013 提供了几个可用于为用户配置音频会议体验的功能，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="68c4d-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="68c4d-122">**访问群体静音**   演示者可以使用此设置将会议中的所有音频参与者静音，并将会议置于非演示者无法自行取消静音的状态中。</span><span class="sxs-lookup"><span data-stu-id="68c4d-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="68c4d-123">**会议进入/退出通知**   如果您已启用电话拨入式会议，演示者可以使用此设置打开或关闭 "进入和退出通知"，以在会议进行过程中最大限度地减少打扰。</span><span class="sxs-lookup"><span data-stu-id="68c4d-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="68c4d-124">**通过拨出**   演示者和已授予权限的与会者添加用户，可以向会议中添加 PSTN 号码，并让会议拨出到这些号码。</span><span class="sxs-lookup"><span data-stu-id="68c4d-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="68c4d-125">视频会议功能</span><span class="sxs-lookup"><span data-stu-id="68c4d-125">Video Conferencing Features</span></span>

<span data-ttu-id="68c4d-126">Lync Server 2013 提供了几个可用于为用户配置视频会议体验的功能，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="68c4d-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="68c4d-127">\*\*\*\*   包含两人以上的视频会议中的库视图，用户可自动查看会议中的所有人。</span><span class="sxs-lookup"><span data-stu-id="68c4d-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="68c4d-128">如果会议具有五个以上的参与者，则最活跃的参与者的视频显示在顶部行中，并且只有照片显示给其他参与者。</span><span class="sxs-lookup"><span data-stu-id="68c4d-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="68c4d-129">默认情况下，多方视频处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="68c4d-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="68c4d-130">有关配置或关闭多方视频的详细信息，请参阅[在 Lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="68c4d-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="68c4d-131">**全景视频**   如果在会议室中安装了圆桌会议视频会议设备，此功能将提供会议室的完整360度视图。</span><span class="sxs-lookup"><span data-stu-id="68c4d-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="68c4d-132">全景视频条仅适用于圆桌会议设备。</span><span class="sxs-lookup"><span data-stu-id="68c4d-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="68c4d-133">**演示者仅视频模式**   演示者可以对会议进行配置，以便仅显示演示者的视频。</span><span class="sxs-lookup"><span data-stu-id="68c4d-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="68c4d-134">当多个视频流可用且锁定到不同的源时，这将阻止大型会议中的打扰。</span><span class="sxs-lookup"><span data-stu-id="68c4d-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="68c4d-135">此模式还适用于由圆桌会议设备捕获和提供的视频。</span><span class="sxs-lookup"><span data-stu-id="68c4d-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="68c4d-136">**Hd 视频**   用户可在两方呼叫和多方会议中体验高达 HD 1080p 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="68c4d-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="68c4d-137">**视频聚焦**   演示者可以对会议进行配置，以便会议中的其他参与者只能看到来自所选参与者的视频源中的视频。</span><span class="sxs-lookup"><span data-stu-id="68c4d-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="68c4d-138">此模式还适用于由圆桌会议设备为全景视频捕获和提供的视频。</span><span class="sxs-lookup"><span data-stu-id="68c4d-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

