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
ms.openlocfilehash: 2f1eb39099f51da36b62360282bc89c06ab94817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="559f8-102">在 Lync Server 2013 中配置视频带宽</span><span class="sxs-lookup"><span data-stu-id="559f8-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="559f8-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="559f8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="559f8-104">Lync Server 2013 包括用于管理两方呼叫和多方会议的视频的多个设置。</span><span class="sxs-lookup"><span data-stu-id="559f8-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="559f8-105">在部署 Lync Server 2013 时，应评估默认设置是否适用于您的组织，并根据需要进行修改。</span><span class="sxs-lookup"><span data-stu-id="559f8-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="559f8-p102">本节中描述的参数适用于双方呼叫和多方会议。可使用下列 cmdlet 之一来查看或修改这些设置：</span><span class="sxs-lookup"><span data-stu-id="559f8-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="559f8-108">**Set-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="559f8-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="559f8-109">**Set-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="559f8-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="559f8-110">**新 Set-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="559f8-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="559f8-111">验证会议策略中的下列设置：</span><span class="sxs-lookup"><span data-stu-id="559f8-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="559f8-112">**VideoBitRateKb**   此设置指定用于用户发送的视频的最大视频比特率（以千位/秒（kbps）为单位）。</span><span class="sxs-lookup"><span data-stu-id="559f8-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="559f8-113">默认值为 50000 kbps。</span><span class="sxs-lookup"><span data-stu-id="559f8-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="559f8-114">有效值介于 0 和 50000 之间。</span><span class="sxs-lookup"><span data-stu-id="559f8-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="559f8-115">此设置单独应用于主要视频和全景视频。</span><span class="sxs-lookup"><span data-stu-id="559f8-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="559f8-116">示例：如果指定 2000 kbps，则 Lync Server 可以为全景视频流的主视频流和 2000 kbps 发送 2000 kbps。</span><span class="sxs-lookup"><span data-stu-id="559f8-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="559f8-117">对于用于全景视频的主视频和 2500 kbps，Lync 2013 终结点的最大视频网络带宽为 8000 kbps。</span><span class="sxs-lookup"><span data-stu-id="559f8-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="559f8-118">仅当接收或发送多个视频时才达到这些最大值。</span><span class="sxs-lookup"><span data-stu-id="559f8-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="559f8-119">有关详细信息，请参阅<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中的媒体流量要求的网络带宽要求</A>中的 "媒体流量网络使用情况" 部分。</span><span class="sxs-lookup"><span data-stu-id="559f8-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="559f8-120">本节列出了所有受支持的分辨率的最大和典型视频流带宽。</span><span class="sxs-lookup"><span data-stu-id="559f8-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="559f8-121">**TotalReceiveVideoBitRateKb**   此设置（在 Lync Server 2013 中为 "新建"），指定客户端接收的所有视频流的最大允许比特率（以千位/秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="559f8-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="559f8-122">也就是说，此设置指定了客户端可接收的所有视频流（全景视频流除外）的合并总计。</span><span class="sxs-lookup"><span data-stu-id="559f8-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="559f8-123">例如，如果您指定 1500 kbps，则客户端最多可接收 1500 kbps 的视频，此视频可能包含多个视频流或单个视频流。</span><span class="sxs-lookup"><span data-stu-id="559f8-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="559f8-124">此设置仅适用于 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="559f8-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="559f8-p106">**TotalReceiveVideoBitRateKb** 的默认值是 50000 kbps。如果将库视图的 **EnableMultiviewJoin** 设置设为 True，则不得将 **TotalReceiveVideoBitRateKb** 设置为小于 420 kbps 的值。如果将库视图的 **EnableMultiviewJoin** 设置设为 False，则不得将 **TotalReceiveVideoBitRateKb** 设置为小于 100 kbps 的值。如果将 **EnableMultiviewJoin** 设为 True 并将值设置为小于 420 kbps 的值，则这些值将默认为阈值。此阈值可帮助阻止可能会导致极差的用户体验的意外配置错误。</span><span class="sxs-lookup"><span data-stu-id="559f8-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="559f8-130">有关<STRONG>EnableMultiviewJoin</STRONG>设置的详细信息，请参阅<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中配置库视图</A>。</span><span class="sxs-lookup"><span data-stu-id="559f8-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="559f8-131">**MaxVideoConferencingResolution**   该参数不再用于 lync server 2013 会议中的 lync server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="559f8-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="559f8-132">Lync Server 2013 会议使用此部分前面所述的比特率控件。</span><span class="sxs-lookup"><span data-stu-id="559f8-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="559f8-133">此设置仍用于加入 Lync Server 2013 会议的旧版客户端。</span><span class="sxs-lookup"><span data-stu-id="559f8-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="559f8-134">此参数确定在由驻留在 Lync Server 2013 上的用户组织的会议中允许的旧客户端的最大分辨率。</span><span class="sxs-lookup"><span data-stu-id="559f8-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="559f8-135">也就是说，旧客户端的处理方式与在以前版本的 Lync Server 或 Office 通信服务器中相同。</span><span class="sxs-lookup"><span data-stu-id="559f8-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="559f8-p108">除了适用于用户的会议策略设置之外，还将评估媒体配置设置。可使用下列 cmdlet 之一来查看或修改这些设置：</span><span class="sxs-lookup"><span data-stu-id="559f8-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="559f8-138">**Set-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="559f8-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="559f8-139">**Set-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="559f8-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="559f8-140">**新 Set-csmediaconfiguration**</span><span class="sxs-lookup"><span data-stu-id="559f8-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="559f8-141">验证以下设置：</span><span class="sxs-lookup"><span data-stu-id="559f8-141">Verify the following setting:</span></span>

  - <span data-ttu-id="559f8-142">**MaxVideoRateAllowed**   此每池设置指定将在客户端终结点传输视频信号的最大速率。</span><span class="sxs-lookup"><span data-stu-id="559f8-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="559f8-143">它仅适用于早期版本的 Lync Server 客户端。</span><span class="sxs-lookup"><span data-stu-id="559f8-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="559f8-144">Lync Server 2013 客户端忽略此设置，并改用会议策略中的 TotalReceiveVideoBitRateKb 设置。</span><span class="sxs-lookup"><span data-stu-id="559f8-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="559f8-p110">默认值为 HD720P。有效值为 HD720p15M、VGA600K 和 CIF250K。</span><span class="sxs-lookup"><span data-stu-id="559f8-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="559f8-147">示例：如果您指定 1500 kbps，则池中的所有旧客户端最多可接收双方或多方会议中的 1500 kbps 的视频。</span><span class="sxs-lookup"><span data-stu-id="559f8-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="559f8-148">以下过程是使用 Lync Server 命令行管理程序修改此部分中所述设置的示例。</span><span class="sxs-lookup"><span data-stu-id="559f8-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="559f8-149">修改视频设置的会议策略</span><span class="sxs-lookup"><span data-stu-id="559f8-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="559f8-150">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="559f8-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="559f8-151">在命令行处，运行以下 cmdlet 以编辑会议策略：</span><span class="sxs-lookup"><span data-stu-id="559f8-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="559f8-152">修改旧客户端的媒体配置</span><span class="sxs-lookup"><span data-stu-id="559f8-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="559f8-153">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="559f8-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="559f8-154">在命令行处，运行以下 cmdlet 以编辑媒体配置：</span><span class="sxs-lookup"><span data-stu-id="559f8-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

