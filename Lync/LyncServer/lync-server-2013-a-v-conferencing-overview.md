---
title: Lync Server 2013 A/V 会议概述
description: Lync Server 2013 A/V 会议概述。
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
ms.openlocfilehash: 76ef4f76a4df0187a7c36394b2c95e99876df9be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568958"
---
# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="1fd6d-103">Lync Server 2013 中的 A/V 会议概述</span><span class="sxs-lookup"><span data-stu-id="1fd6d-103">Overview of A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd6d-104">_**上次修改的主题：** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="1fd6d-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="1fd6d-105">A/V 会议在您的用户之间实现实时音频和视频通信。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-105">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="1fd6d-106">在部署会议时，可以选择同时启用并使用 Web 会议和 A/V 会议，也可以仅启用并使用 Web 会议。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-106">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="1fd6d-107">要规划 A/V 会议，需了解组织所需会议媒体类型要求的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-107">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="1fd6d-108">这可能包括音频、视频和全景视频。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-108">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="1fd6d-109">在为用户启用 A/V 会议之前，请确保您的网络能够处理生成的负载。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-109">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="1fd6d-110">如果没有足够的网络带宽，用户体验可能会受到严重降低。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-110">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="1fd6d-111">您可以使用呼叫允许控制 (CAC) 来管理由 A/V 会议使用的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-111">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="1fd6d-112">对于受限制的网络（例如中央网站和分支网站之间的有限带宽链接），这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-112">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="1fd6d-113">有关详细信息，请参阅 [Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-113">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="1fd6d-114">有关媒体带宽要求的详细信息，请参阅 [Lync Server 2013 中媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-114">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="1fd6d-115">如果在网络中部署音频会议，用户将需要音频设备（如耳机）参加音频会议。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-115">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="1fd6d-116">如果您部署视频会议，则需要部署视频设备，例如用户的网络摄像机。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-116">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="1fd6d-117">我们建议您使用统一通信 (由 Microsoft 针对所有设备类型进行认证的 UC) 设备，以确保获得最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-117">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="1fd6d-118">有关 UC 认证设备的详细信息，请参阅位于的 "电话和设备（Lync）" [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) 。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-118">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="1fd6d-119">对于音频或视频设备、设备部署和用户培训是考虑和规划的重要步骤之一。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-119">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="1fd6d-120">以下各节介绍了音频和视频会议的功能，其中包括有关管理带宽和选择相应客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-120">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="1fd6d-121">音频会议功能</span><span class="sxs-lookup"><span data-stu-id="1fd6d-121">Audio Conferencing Features</span></span>

<span data-ttu-id="1fd6d-122">Lync Server 2013 提供了几个可用于为用户配置音频会议体验的功能，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="1fd6d-122">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="1fd6d-123">**访问群体静音**    演示者可以使用此设置将会议中的所有音频参与者设为静音，并将会议置于非演示者无法自行取消静音的状态中。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-123">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="1fd6d-124">**会议进入/退出通知**    如果已启用电话拨入式会议，演示者可以使用此设置打开或关闭 "进入和退出通知" 以最大限度地减少打扰，同时进行会议。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-124">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="1fd6d-125">**通过拨出**     添加用户向其授予权限的演示者和与会者可以向会议中添加 PSTN 号码，并让会议拨出到这些号码。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-125">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="1fd6d-126">视频会议功能</span><span class="sxs-lookup"><span data-stu-id="1fd6d-126">Video Conferencing Features</span></span>

<span data-ttu-id="1fd6d-127">Lync Server 2013 提供了几个可用于为用户配置视频会议体验的功能，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="1fd6d-127">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="1fd6d-128">**库视图**    在包含两人以上的视频会议中，用户可自动查看会议中的所有人。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-128">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="1fd6d-129">如果会议具有五个以上的参与者，则最活跃的参与者的视频显示在顶部行中，并且只有照片显示给其他参与者。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-129">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="1fd6d-130">默认情况下，多方视频处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-130">Multiparty video is turned on by default.</span></span> <span data-ttu-id="1fd6d-131">有关配置或关闭多方视频的详细信息，请参阅 [在 Lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-131">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="1fd6d-132">**全景视频**    如果在会议室中安装了圆桌会议视频会议设备，此功能将提供会议室的完整360度视图。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-132">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="1fd6d-133">全景视频条仅适用于圆桌会议设备。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-133">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="1fd6d-134">**仅演示者视频模式**    演示者可以对会议进行配置，以便仅显示来自演示者的视频。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-134">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="1fd6d-135">当多个视频流可用且锁定到不同的源时，这将阻止大型会议中的打扰。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-135">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="1fd6d-136">此模式还适用于由圆桌会议设备捕获和提供的视频。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-136">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="1fd6d-137">**HD 视频**    用户可在两方呼叫和多方会议中体验最高分辨率为 HD 1080P 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-137">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="1fd6d-138">**视频聚焦**    演示者可以对会议进行配置，以便会议中的其他参与者只能看到来自所选参与者的视频源中的视频。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-138">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="1fd6d-139">此模式还适用于由圆桌会议设备为全景视频捕获和提供的视频。</span><span class="sxs-lookup"><span data-stu-id="1fd6d-139">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

