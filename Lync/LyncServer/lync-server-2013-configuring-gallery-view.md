---
title: Lync Server 2013：配置库视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096272a2347c400a81e6d4684873c5f5828136a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="bfd53-102">在 Lync Server 2013 中配置库视图</span><span class="sxs-lookup"><span data-stu-id="bfd53-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfd53-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="bfd53-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="bfd53-104">在 Lync Server 2013 中，配置库在会议策略中查看视频会议。</span><span class="sxs-lookup"><span data-stu-id="bfd53-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="bfd53-105">默认情况下，库视图处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="bfd53-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="bfd53-106">如果您不希望允许使用库视图，或希望仅允许部分用户使用，则需要使用会议策略关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="bfd53-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="bfd53-107">当会议参与者的视频不可用时，如果部署高分辨率照片（Lync Server 2013 中的一项新功能），则用户的库视图体验会得到增强。</span><span class="sxs-lookup"><span data-stu-id="bfd53-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="bfd53-108">高分辨率照片为存储在 Active Directory 域服务中的较小、有限的分辨率联系人照片提供了另一种替代方案。</span><span class="sxs-lookup"><span data-stu-id="bfd53-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="bfd53-109">高分辨率照片存储在用户的 Exchange 2013 邮箱中，因此，需要将 Lync Server 2013 与 Exchange 2013 集成。</span><span class="sxs-lookup"><span data-stu-id="bfd53-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="bfd53-110">有关详细信息，请参阅 NextHop 博客文章 "集成 Exchange 2013 和 Lync Server 2013" [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)。</span><span class="sxs-lookup"><span data-stu-id="bfd53-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfd53-111">每个博客的内容及其 URL 如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="bfd53-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="bfd53-112">您可以通过使用 Lync Server 2013 控制面板或使用以下 cmdlet 之一来查看或修改库视图参数：</span><span class="sxs-lookup"><span data-stu-id="bfd53-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="bfd53-113">**Set-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="bfd53-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="bfd53-114">**Set-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="bfd53-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="bfd53-115">**新 Set-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="bfd53-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="bfd53-116">使用下列会议策略设置配置库视图：</span><span class="sxs-lookup"><span data-stu-id="bfd53-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="bfd53-117">**AllowMultiview**   此参数控制是否允许用户组织库观看视频会议。</span><span class="sxs-lookup"><span data-stu-id="bfd53-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="bfd53-118">此参数适用于用户创建的已安排的会议和临时会议。</span><span class="sxs-lookup"><span data-stu-id="bfd53-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="bfd53-119">示例：</span><span class="sxs-lookup"><span data-stu-id="bfd53-119">Examples:</span></span>
    
      - <span data-ttu-id="bfd53-120">对于在 Lync Server 2013 池上托管的用户 A，此参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="bfd53-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="bfd53-121">用户 A 组织的会议允许用户加入和接收多个视频流。</span><span class="sxs-lookup"><span data-stu-id="bfd53-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="bfd53-122">如果用户 B 驻留在 Lync Server 2013 池上，则此参数设置为 False。</span><span class="sxs-lookup"><span data-stu-id="bfd53-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="bfd53-123">用户 B 组织的会议具有一个视频流，这与 Lync Server 2010 提供的视频会议体验类似。</span><span class="sxs-lookup"><span data-stu-id="bfd53-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="bfd53-p106">此参数确定可组织允许多个视频流的会议的用户。允许多个视频流的会议中的参与者可能会也可能不会被允许接收多个视频流，这取决于他们各自的权限（请参阅 EnableMultiviewJoin 参数的描述）。</span><span class="sxs-lookup"><span data-stu-id="bfd53-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="bfd53-126">**EnableMultiviewJoin**   此参数控制会议中的参与者是否在允许会议的会议中接收库观看视频体验。</span><span class="sxs-lookup"><span data-stu-id="bfd53-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="bfd53-127">此参数控制用户参与的所有会议中的用户体验。</span><span class="sxs-lookup"><span data-stu-id="bfd53-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="bfd53-128">示例：</span><span class="sxs-lookup"><span data-stu-id="bfd53-128">Examples:</span></span>
    
      - <span data-ttu-id="bfd53-129">对于用户 C，此参数设置为 True。当用户加入组织或启动的会议时，用户 c 可以收到多个视频流。用户 C 收到一个与 Lync Server 2010 提供的视频会议体验类似的单一视频流参与由用户 B 组织或启动的会议。</span><span class="sxs-lookup"><span data-stu-id="bfd53-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="bfd53-130">对于用户 D，此参数设置为 False。用户 D 接收单个视频流，与 Lync Server 2010 在参与按用户 A 或用户 B 组织的任何会议时所提供的视频会议体验类似。</span><span class="sxs-lookup"><span data-stu-id="bfd53-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="bfd53-131">下面的过程是使用 Lync Server 命令行管理程序启用库观看视频会议的示例。</span><span class="sxs-lookup"><span data-stu-id="bfd53-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="bfd53-132">修改库视图视频会议的会议策略</span><span class="sxs-lookup"><span data-stu-id="bfd53-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="bfd53-133">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfd53-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bfd53-134">在命令行处，运行以下 cmdlet 以编辑会议策略：</span><span class="sxs-lookup"><span data-stu-id="bfd53-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

