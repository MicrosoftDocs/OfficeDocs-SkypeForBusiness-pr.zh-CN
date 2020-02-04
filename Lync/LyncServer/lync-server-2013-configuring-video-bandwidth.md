---
title: Lync Server 2013：配置视频带宽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="ff04b-102">在 Lync Server 2013 中配置视频带宽</span><span class="sxs-lookup"><span data-stu-id="ff04b-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff04b-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ff04b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ff04b-104">Lync Server 2013 包括多个用于管理两方呼叫和多方会议的视频的设置。</span><span class="sxs-lookup"><span data-stu-id="ff04b-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="ff04b-105">部署 Lync Server 2013 时，应评估默认设置是否适用于你的组织，并根据需要进行修改。</span><span class="sxs-lookup"><span data-stu-id="ff04b-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="ff04b-106">本部分中所述的参数适用于两方呼叫和多方会议。</span><span class="sxs-lookup"><span data-stu-id="ff04b-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="ff04b-107">使用以下 cmdlet 之一查看或修改这些设置：</span><span class="sxs-lookup"><span data-stu-id="ff04b-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="ff04b-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="ff04b-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="ff04b-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="ff04b-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="ff04b-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="ff04b-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="ff04b-111">验证会议策略中的以下设置：</span><span class="sxs-lookup"><span data-stu-id="ff04b-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="ff04b-112">**VideoBitRateKb**   此设置指定由用户发送的视频的最大视频比特率，以千位每秒（kbps）为单位。</span><span class="sxs-lookup"><span data-stu-id="ff04b-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="ff04b-113">默认值为 50000 kbps。</span><span class="sxs-lookup"><span data-stu-id="ff04b-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="ff04b-114">有效值为0到50000。</span><span class="sxs-lookup"><span data-stu-id="ff04b-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="ff04b-115">此设置分别适用于主视频和全景视频。</span><span class="sxs-lookup"><span data-stu-id="ff04b-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="ff04b-116">示例：如果你指定 2000 kbps，则 Lync Server 可以为全景视频流的主视频流和 2000 kbps 发送 2000 kbps。</span><span class="sxs-lookup"><span data-stu-id="ff04b-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff04b-117">对于全景视频，Lync 2013 终结点的最大视频网络带宽是 8000 kbps 的视频和 2500 kbps。</span><span class="sxs-lookup"><span data-stu-id="ff04b-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="ff04b-118">仅当接收或发送多个视频时，才达到这些最大值。</span><span class="sxs-lookup"><span data-stu-id="ff04b-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="ff04b-119">有关详细信息，请参阅<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中针对媒体流量的网络带宽要求</A>中的 "媒体流量网络使用情况" 部分。</span><span class="sxs-lookup"><span data-stu-id="ff04b-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="ff04b-120">本部分列出了所有支持的分辨率的最大和最典型视频流带宽。</span><span class="sxs-lookup"><span data-stu-id="ff04b-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="ff04b-121">**TotalReceiveVideoBitRateKb**   此设置（Lync Server 2013 中的新增功能）指定客户端接收的所有视频流的最大比特率（以 kb/秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ff04b-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="ff04b-122">也就是说，它指定客户端可以接收的除全景视频流之外的所有视频流的合并总计。</span><span class="sxs-lookup"><span data-stu-id="ff04b-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="ff04b-123">例如，如果你指定 1500 kbps，则客户端最多可接收 1500 kbps 的视频，其中可能包含多个视频流或单个视频流。</span><span class="sxs-lookup"><span data-stu-id="ff04b-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="ff04b-124">此设置仅适用于 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="ff04b-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="ff04b-125">**TotalReceiveVideoBitRateKb**的默认值为 50000 kbps。</span><span class="sxs-lookup"><span data-stu-id="ff04b-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="ff04b-126">如果库视图的**EnableMultiviewJoin**设置为 True，则不能在 420 kbps 以下设置**TotalReceiveVideoBitRateKb** 。</span><span class="sxs-lookup"><span data-stu-id="ff04b-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="ff04b-127">如果库视图的**EnableMultiviewJoin**设置为 False，则不能在 100 kbps 以下设置**TotalReceiveVideoBitRateKb** 。</span><span class="sxs-lookup"><span data-stu-id="ff04b-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="ff04b-128">如果**EnableMultiviewJoin**设置为 True，并且您将值设置为 420 kbps 的值，则这些值将默认为 "阈值" 值。</span><span class="sxs-lookup"><span data-stu-id="ff04b-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="ff04b-129">此阈值有助于防止意外的错误配置，可能导致用户体验不良。</span><span class="sxs-lookup"><span data-stu-id="ff04b-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff04b-130">有关<STRONG>EnableMultiviewJoin</STRONG>设置的详细信息，请参阅<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中配置库视图</A>。</span><span class="sxs-lookup"><span data-stu-id="ff04b-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="ff04b-131">**MaxVideoConferencingResolution**   此参数不再用于 lync server 2013 会议中的 lync server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="ff04b-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="ff04b-132">Lync Server 2013 会议使用本部分前面所述的比特率控件。</span><span class="sxs-lookup"><span data-stu-id="ff04b-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="ff04b-133">此设置仍用于加入 Lync Server 2013 会议的旧客户端。</span><span class="sxs-lookup"><span data-stu-id="ff04b-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="ff04b-134">此参数确定由在 Lync Server 2013 上托管的用户组织的会议中的旧客户端所允许的最大分辨率。</span><span class="sxs-lookup"><span data-stu-id="ff04b-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="ff04b-135">也就是说，旧客户端的处理方式与以前版本的 Lync Server 或 Office 通信服务器相同。</span><span class="sxs-lookup"><span data-stu-id="ff04b-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="ff04b-136">除了适用于用户的会议策略设置外，评估媒体配置设置。</span><span class="sxs-lookup"><span data-stu-id="ff04b-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="ff04b-137">使用以下 cmdlet 之一查看或修改这些设置：</span><span class="sxs-lookup"><span data-stu-id="ff04b-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="ff04b-138">**CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ff04b-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="ff04b-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ff04b-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="ff04b-140">**新-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ff04b-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="ff04b-141">验证以下设置：</span><span class="sxs-lookup"><span data-stu-id="ff04b-141">Verify the following setting:</span></span>

  - <span data-ttu-id="ff04b-142">**MaxVideoRateAllowed**   此每个池的设置指定将在客户端终结点传输视频信号的最大速率。</span><span class="sxs-lookup"><span data-stu-id="ff04b-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="ff04b-143">它仅适用于以前版本的 Lync Server 客户端。</span><span class="sxs-lookup"><span data-stu-id="ff04b-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff04b-144">Lync Server 2013 客户端忽略此设置，而改为使用会议策略中的 TotalReceiveVideoBitRateKb 设置。</span><span class="sxs-lookup"><span data-stu-id="ff04b-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="ff04b-145">默认值为 HD720P。</span><span class="sxs-lookup"><span data-stu-id="ff04b-145">The default value is HD720P.</span></span> <span data-ttu-id="ff04b-146">有效值为 HD720p15M、VGA600K 和 CIF250K。</span><span class="sxs-lookup"><span data-stu-id="ff04b-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="ff04b-147">示例：如果你指定 1500 kbps，则池中的所有旧客户端在两方或多方会议中最多可接收 1500 kbps 的视频。</span><span class="sxs-lookup"><span data-stu-id="ff04b-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="ff04b-148">以下过程是使用 Lync Server Management Shell 修改本部分中所述设置的示例。</span><span class="sxs-lookup"><span data-stu-id="ff04b-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="ff04b-149">修改视频设置的会议策略</span><span class="sxs-lookup"><span data-stu-id="ff04b-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="ff04b-150">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ff04b-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ff04b-151">在命令行中，运行以下 cmdlet 以编辑会议策略：</span><span class="sxs-lookup"><span data-stu-id="ff04b-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="ff04b-152">修改旧客户端的媒体配置</span><span class="sxs-lookup"><span data-stu-id="ff04b-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="ff04b-153">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ff04b-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ff04b-154">在命令行中，运行以下 cmdlet 以编辑媒体配置：</span><span class="sxs-lookup"><span data-stu-id="ff04b-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

