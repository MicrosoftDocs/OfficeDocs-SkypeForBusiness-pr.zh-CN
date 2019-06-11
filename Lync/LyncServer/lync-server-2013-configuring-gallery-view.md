---
title: 'Lync Server 2013: 配置库视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7333c1928bd92dbe6145f238d828e81bbeb3d868
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="46add-102">在 Lync Server 2013 中配置库视图</span><span class="sxs-lookup"><span data-stu-id="46add-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46add-103">_**主题上次修改时间:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="46add-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="46add-104">在 Lync Server 2013 中, 你可以在会议策略中配置库查看视频会议。</span><span class="sxs-lookup"><span data-stu-id="46add-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="46add-105">默认情况下, 库视图处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="46add-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="46add-106">如果你不想允许库视图, 或者希望仅对某些用户允许它, 你需要关闭会议策略中的功能。</span><span class="sxs-lookup"><span data-stu-id="46add-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="46add-107">当会议参与者的视频不可用时, 如果在 Lync Server 2013 中部署高分辨率的照片, 则用户的库视图体验将会增强。</span><span class="sxs-lookup"><span data-stu-id="46add-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="46add-108">高分辨率照片为存储在 Active Directory 域服务中的较小的、有限的分辨率联系人照片提供备用方案。</span><span class="sxs-lookup"><span data-stu-id="46add-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="46add-109">高分辨率的照片存储在用户的 Exchange 2013 邮箱中, 因此需要您将 Lync Server 2013 与 Exchange 2013 集成。</span><span class="sxs-lookup"><span data-stu-id="46add-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="46add-110">有关详细信息, 请参阅 NextHop 博客文章 "集成 Exchange 2013 和 Lync Server 2013" [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)。</span><span class="sxs-lookup"><span data-stu-id="46add-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46add-111">每个博客的内容及其 URL 如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="46add-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="46add-112">你可以使用 Lync Server 2013 控制面板或使用以下 cmdlet 之一查看或修改库视图参数:</span><span class="sxs-lookup"><span data-stu-id="46add-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="46add-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="46add-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="46add-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="46add-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="46add-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="46add-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="46add-116">通过下列会议策略设置配置库视图:</span><span class="sxs-lookup"><span data-stu-id="46add-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="46add-117">**AllowMultiview**   此参数控制是否允许用户组织库观看视频会议。</span><span class="sxs-lookup"><span data-stu-id="46add-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="46add-118">此参数适用于用户创建的计划和临时会议。</span><span class="sxs-lookup"><span data-stu-id="46add-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="46add-119">说明</span><span class="sxs-lookup"><span data-stu-id="46add-119">Examples:</span></span>
    
      - <span data-ttu-id="46add-120">对于用户 A, 此参数设置为 True, 其托管在 Lync Server 2013 池中。</span><span class="sxs-lookup"><span data-stu-id="46add-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="46add-121">通过用户 A 组织的会议允许用户加入和接收多个视频流。</span><span class="sxs-lookup"><span data-stu-id="46add-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="46add-122">对于在 Lync Server 2013 池中托管的用户 B, 此参数设置为 "False"。</span><span class="sxs-lookup"><span data-stu-id="46add-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="46add-123">按用户 B 组织的会议的单个视频流与 Lync Server 2010 提供的视频会议体验类似。</span><span class="sxs-lookup"><span data-stu-id="46add-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="46add-124">此参数确定哪些人可以组织允许多个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="46add-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="46add-125">允许多个视频流的参与者可能或不允许多个视频流接收多个视频流, 具体取决于其各个权限 (请参阅 EnableMultiviewJoin 参数的说明)。</span><span class="sxs-lookup"><span data-stu-id="46add-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="46add-126">**EnableMultiviewJoin**   此参数控制会议中的参与者是否在允许会议的会议中接收库查看视频体验。</span><span class="sxs-lookup"><span data-stu-id="46add-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="46add-127">此参数控制用户在其参与的任何会议中的体验。</span><span class="sxs-lookup"><span data-stu-id="46add-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="46add-128">说明</span><span class="sxs-lookup"><span data-stu-id="46add-128">Examples:</span></span>
    
      - <span data-ttu-id="46add-129">对于用户 C, 此参数设置为 True。当参与由用户 A 组织或启动的会议时, 用户 C 可以接收多个视频流。用户 C 接收与 Lync Server 2010 提供的视频会议体验类似的单个视频流参与由用户 B 组织或启动的会议。</span><span class="sxs-lookup"><span data-stu-id="46add-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="46add-130">对于用户 D, 此参数设置为 False。用户 D 接收单个视频流, 该视频流与 Lync Server 2010 在参与由用户 A 或用户 B 组织的任何会议时所提供的视频会议体验类似。</span><span class="sxs-lookup"><span data-stu-id="46add-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="46add-131">以下过程是使用 Lync Server 命令行管理程序启用库观看视频会议的示例。</span><span class="sxs-lookup"><span data-stu-id="46add-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="46add-132">修改库的会议策略查看视频会议</span><span class="sxs-lookup"><span data-stu-id="46add-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="46add-133">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="46add-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="46add-134">在命令行中, 运行以下 cmdlet 以编辑会议策略:</span><span class="sxs-lookup"><span data-stu-id="46add-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

