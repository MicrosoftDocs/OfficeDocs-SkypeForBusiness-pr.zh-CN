---
title: 'Lync Server 2013: 配置视频示例方案'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="c8846-102">配置 Lync Server 2013 的视频示例方案</span><span class="sxs-lookup"><span data-stu-id="c8846-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8846-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c8846-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c8846-104">Lync 2013 添加了支持 1920 x 1080 完整高清 (HD) 视频和库观看视频的新视频功能。</span><span class="sxs-lookup"><span data-stu-id="c8846-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="c8846-105">基于客户数据的度量显示典型的视频带宽与 Lync 2010 相比稍有略微增加, 但由于完全高清支持, 最大视频流带宽已增加 (有关详细信息, 请参阅中[的 "媒体流量网络使用情况" 部分)。Lync Server 2013 中媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。</span><span class="sxs-lookup"><span data-stu-id="c8846-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="c8846-106">因此, 管理员可能希望限制某些用户 (如分支机构中网络容量较少的用户) 的视频带宽, 并帮助确保其他用户 (如管理人员) 可能获得最佳视频质量。</span><span class="sxs-lookup"><span data-stu-id="c8846-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="c8846-107">下表提供了针对不同网络容量配置视频的推荐设置列表。</span><span class="sxs-lookup"><span data-stu-id="c8846-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="c8846-108">这些设置将限制某些用户方案发送和接收更高分辨率的视频 (请参阅最右边的列)。</span><span class="sxs-lookup"><span data-stu-id="c8846-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="c8846-109">由于最大接收网络带宽不足, 最小设置将导致库视频不可用。</span><span class="sxs-lookup"><span data-stu-id="c8846-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="c8846-110">推荐的视频设置</span><span class="sxs-lookup"><span data-stu-id="c8846-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="c8846-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="c8846-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="c8846-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="c8846-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="c8846-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="c8846-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="c8846-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="c8846-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="c8846-115">预期视频分辨率以获得优质视频</span><span class="sxs-lookup"><span data-stu-id="c8846-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8846-116">最佳</span><span class="sxs-lookup"><span data-stu-id="c8846-116">Best</span></span></p></td>
<td><p><span data-ttu-id="c8846-117">True</span><span class="sxs-lookup"><span data-stu-id="c8846-117">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-118">True</span><span class="sxs-lookup"><span data-stu-id="c8846-118">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-119">8000</span><span class="sxs-lookup"><span data-stu-id="c8846-119">8000</span></span></p></td>
<td><p><span data-ttu-id="c8846-120">8000</span><span class="sxs-lookup"><span data-stu-id="c8846-120">8000</span></span></p></td>
<td><p><span data-ttu-id="c8846-121">对等: 高达 1920 x 1080 视频分辨率</span><span class="sxs-lookup"><span data-stu-id="c8846-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="c8846-122">库视图: 最高可达 2 1920 x 1080 视频或多个更小分辨率的视频</span><span class="sxs-lookup"><span data-stu-id="c8846-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8846-123">Good</span><span class="sxs-lookup"><span data-stu-id="c8846-123">Good</span></span></p></td>
<td><p><span data-ttu-id="c8846-124">True</span><span class="sxs-lookup"><span data-stu-id="c8846-124">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-125">True</span><span class="sxs-lookup"><span data-stu-id="c8846-125">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-126">2500</span><span class="sxs-lookup"><span data-stu-id="c8846-126">2500</span></span></p></td>
<td><p><span data-ttu-id="c8846-127">2500</span><span class="sxs-lookup"><span data-stu-id="c8846-127">2500</span></span></p></td>
<td><p><span data-ttu-id="c8846-128">对等: 高达 1280 x 720 视频分辨率</span><span class="sxs-lookup"><span data-stu-id="c8846-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="c8846-129">库视图: 最高可达 5 640 x 360 分辨率的视频</span><span class="sxs-lookup"><span data-stu-id="c8846-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8846-130">中</span><span class="sxs-lookup"><span data-stu-id="c8846-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="c8846-131">True</span><span class="sxs-lookup"><span data-stu-id="c8846-131">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-132">True</span><span class="sxs-lookup"><span data-stu-id="c8846-132">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-133">1000</span><span class="sxs-lookup"><span data-stu-id="c8846-133">1000</span></span></p></td>
<td><p><span data-ttu-id="c8846-134">1000</span><span class="sxs-lookup"><span data-stu-id="c8846-134">1000</span></span></p></td>
<td><p><span data-ttu-id="c8846-135">对等: 高达 960 x 540 视频分辨率</span><span class="sxs-lookup"><span data-stu-id="c8846-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="c8846-136">库视图: 最高可达 5 424 x 240 分辨率的视频</span><span class="sxs-lookup"><span data-stu-id="c8846-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8846-137">最低</span><span class="sxs-lookup"><span data-stu-id="c8846-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="c8846-138">True</span><span class="sxs-lookup"><span data-stu-id="c8846-138">True</span></span></p></td>
<td><p><span data-ttu-id="c8846-139">False</span><span class="sxs-lookup"><span data-stu-id="c8846-139">False</span></span></p></td>
<td><p><span data-ttu-id="c8846-140">350</span><span class="sxs-lookup"><span data-stu-id="c8846-140">350</span></span></p></td>
<td><p><span data-ttu-id="c8846-141">350</span><span class="sxs-lookup"><span data-stu-id="c8846-141">350</span></span></p></td>
<td><p><span data-ttu-id="c8846-142">对等: 高达 424 x 240 视频分辨率</span><span class="sxs-lookup"><span data-stu-id="c8846-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="c8846-143">库视图: 不可用</span><span class="sxs-lookup"><span data-stu-id="c8846-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8846-144">你可以使用上表中的信息部署新的 HD 视频和库查看组织中的某些用户的视频会议功能, 同时允许其他人使用不同的视频分辨率。</span><span class="sxs-lookup"><span data-stu-id="c8846-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="c8846-145">在以下示例中, 管理员推出了最高视频质量的新视频功能, 仅供主管人员使用。</span><span class="sxs-lookup"><span data-stu-id="c8846-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="c8846-146">对于网络容量较低的远程分支机构中的员工, 仅部署上表中的最小设置。</span><span class="sxs-lookup"><span data-stu-id="c8846-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="c8846-147">对于所有其他员工, 将部署上表中的 "良好" 设置。</span><span class="sxs-lookup"><span data-stu-id="c8846-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="c8846-148">为了向高级管理人员推出新功能, 管理员创建了一个名为 ExecutiveVideo 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="c8846-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="c8846-149">此会议策略具有以下设置:</span><span class="sxs-lookup"><span data-stu-id="c8846-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="c8846-150">VideoBitRateKB 设置为 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="c8846-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="c8846-151">TotalReceiveVideoBitRateKB 设置为 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="c8846-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="c8846-152">AllowMultiview 设置为 True</span><span class="sxs-lookup"><span data-stu-id="c8846-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="c8846-153">EnableMultiviewJoin 设置为 True</span><span class="sxs-lookup"><span data-stu-id="c8846-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="c8846-154">对于分支机构中的员工, 管理员创建名为 BranchOfficeVideo 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="c8846-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="c8846-155">此会议策略具有以下设置:</span><span class="sxs-lookup"><span data-stu-id="c8846-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="c8846-156">VideoBitRateKB 设置为 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="c8846-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="c8846-157">TotalReceiveVideoBitRateKB 设置为 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="c8846-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="c8846-158">AllowMultiview 设置为 True</span><span class="sxs-lookup"><span data-stu-id="c8846-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="c8846-159">EnableMultiviewJoin 设置为 False</span><span class="sxs-lookup"><span data-stu-id="c8846-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="c8846-160">对于所有其他员工, 管理员创建一个名为 StandardVideo 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="c8846-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="c8846-161">此会议策略具有以下设置:</span><span class="sxs-lookup"><span data-stu-id="c8846-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="c8846-162">VideoBitRateKB 设置为 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="c8846-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="c8846-163">TotalReceiveVideoBitRateKB 设置为 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="c8846-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="c8846-164">AllowMultiview 设置为 True</span><span class="sxs-lookup"><span data-stu-id="c8846-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="c8846-165">EnableMultiviewJoin 设置为 True</span><span class="sxs-lookup"><span data-stu-id="c8846-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="c8846-166">管理员按如下方式向用户分配会议策略:</span><span class="sxs-lookup"><span data-stu-id="c8846-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="c8846-167">ExecutiveVideo 会议策略已分配给高级管理人员。</span><span class="sxs-lookup"><span data-stu-id="c8846-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="c8846-168">BranchOfficeVideo 会议策略已分配给分支机构中的所有员工。</span><span class="sxs-lookup"><span data-stu-id="c8846-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="c8846-169">StandardVideo 会议策略已分配给所有其他员工。</span><span class="sxs-lookup"><span data-stu-id="c8846-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="c8846-170">这些会议策略分配将导致以下用户体验:</span><span class="sxs-lookup"><span data-stu-id="c8846-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="c8846-171">由任何用户支持库视图组织的所有会议, 但分支机构中的员工无法体验库视图。</span><span class="sxs-lookup"><span data-stu-id="c8846-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="c8846-172">对于任何两方或多方会议, 高级管理人员都可以发送 1920 x 1080 完整的 HD 视频 (如果其硬件和网络链接支持它), 并且可以接收到其他参与者客户支持的 1920 x 1080 完整 HD 视频。</span><span class="sxs-lookup"><span data-stu-id="c8846-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="c8846-173">非主管人员在他们的两方或多方会议中的执行官之间体验的员工越低, 但仍能获得良好的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c8846-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="c8846-174">当 Lync 显示默认视频窗口大小时, 分支机构中的员工将在两方通话中获得良好的视频质量;但是, 如果将 Lync 窗口最大化到全屏, 视频分辨率将不会增加。</span><span class="sxs-lookup"><span data-stu-id="c8846-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="c8846-175">对于多方会议, 分支机构中的员工将仅看到一个活动视频。</span><span class="sxs-lookup"><span data-stu-id="c8846-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

