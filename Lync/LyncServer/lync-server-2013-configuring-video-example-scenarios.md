---
title: Lync Server 2013：配置视频示例方案
description: Lync Server 2013：配置视频示例方案。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575138"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="e62fa-103">为 Lync Server 2013 配置视频示例方案</span><span class="sxs-lookup"><span data-stu-id="e62fa-103">Configuring video example scenarios for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e62fa-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e62fa-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e62fa-105">Lync 2013 添加了新的视频功能，以支持 1920 x 1080 full high definition (HD) 视频和库观看视频。</span><span class="sxs-lookup"><span data-stu-id="e62fa-105">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="e62fa-106">基于客户数据的度量显示典型的视频带宽的增加仅与 Lync 2010 相比稍有不同，但由于完整的 HD (支持，最大视频流带宽增加了：有关详细信息，请参阅 [Lync Server 2013 中的媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)) 中的 "媒体流量网络使用情况" 部分。</span><span class="sxs-lookup"><span data-stu-id="e62fa-106">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="e62fa-107">因此，管理员可能希望限制某些用户 (的视频带宽，例如分支机构中网络容量较少的用户) 并帮助确保其他 (用户（如行政人员) ）可能获得最佳视频质量。</span><span class="sxs-lookup"><span data-stu-id="e62fa-107">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="e62fa-108">下表提供了针对不同网络容量配置视频的推荐设置的列表。</span><span class="sxs-lookup"><span data-stu-id="e62fa-108">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="e62fa-109">这些设置将限制某些用户方案发送和接收更高分辨率的视频 (请参阅最右边的列) 。</span><span class="sxs-lookup"><span data-stu-id="e62fa-109">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="e62fa-110">由于最大的接收网络带宽不足，最小设置将导致库视频不可用。</span><span class="sxs-lookup"><span data-stu-id="e62fa-110">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="e62fa-111">建议的视频设置</span><span class="sxs-lookup"><span data-stu-id="e62fa-111">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="e62fa-112">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="e62fa-112">AllowMultiView</span></span></th>
<th><span data-ttu-id="e62fa-113">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="e62fa-113">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="e62fa-114">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="e62fa-114">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="e62fa-115">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="e62fa-115">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="e62fa-116">预期视频分辨率以获得优质视频</span><span class="sxs-lookup"><span data-stu-id="e62fa-116">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e62fa-117">最好</span><span class="sxs-lookup"><span data-stu-id="e62fa-117">Best</span></span></p></td>
<td><p><span data-ttu-id="e62fa-118">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-118">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-119">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-119">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-120">8000</span><span class="sxs-lookup"><span data-stu-id="e62fa-120">8000</span></span></p></td>
<td><p><span data-ttu-id="e62fa-121">8000</span><span class="sxs-lookup"><span data-stu-id="e62fa-121">8000</span></span></p></td>
<td><p><span data-ttu-id="e62fa-122">对等：高达 1920 x 1080 的视频分辨率</span><span class="sxs-lookup"><span data-stu-id="e62fa-122">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="e62fa-123">库视图：最多 2 1920 x 1080 视频或多个更小的分辨率视频</span><span class="sxs-lookup"><span data-stu-id="e62fa-123">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e62fa-124">Good</span><span class="sxs-lookup"><span data-stu-id="e62fa-124">Good</span></span></p></td>
<td><p><span data-ttu-id="e62fa-125">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-125">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-126">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-126">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-127">2500</span><span class="sxs-lookup"><span data-stu-id="e62fa-127">2500</span></span></p></td>
<td><p><span data-ttu-id="e62fa-128">2500</span><span class="sxs-lookup"><span data-stu-id="e62fa-128">2500</span></span></p></td>
<td><p><span data-ttu-id="e62fa-129">对等：高达 1280 x 720 的视频分辨率</span><span class="sxs-lookup"><span data-stu-id="e62fa-129">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="e62fa-130">库视图：最高为 5 640 x 360 分辨率的视频</span><span class="sxs-lookup"><span data-stu-id="e62fa-130">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e62fa-131">中</span><span class="sxs-lookup"><span data-stu-id="e62fa-131">Medium</span></span></p></td>
<td><p><span data-ttu-id="e62fa-132">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-132">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-133">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-133">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-134">1000</span><span class="sxs-lookup"><span data-stu-id="e62fa-134">1000</span></span></p></td>
<td><p><span data-ttu-id="e62fa-135">1000</span><span class="sxs-lookup"><span data-stu-id="e62fa-135">1000</span></span></p></td>
<td><p><span data-ttu-id="e62fa-136">对等：高达 960 x 540 的视频分辨率</span><span class="sxs-lookup"><span data-stu-id="e62fa-136">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="e62fa-137">库视图：最高为 5 424 x 240 分辨率的视频</span><span class="sxs-lookup"><span data-stu-id="e62fa-137">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e62fa-138">最小值</span><span class="sxs-lookup"><span data-stu-id="e62fa-138">Minimum</span></span></p></td>
<td><p><span data-ttu-id="e62fa-139">True</span><span class="sxs-lookup"><span data-stu-id="e62fa-139">True</span></span></p></td>
<td><p><span data-ttu-id="e62fa-140">False</span><span class="sxs-lookup"><span data-stu-id="e62fa-140">False</span></span></p></td>
<td><p><span data-ttu-id="e62fa-141">350</span><span class="sxs-lookup"><span data-stu-id="e62fa-141">350</span></span></p></td>
<td><p><span data-ttu-id="e62fa-142">350</span><span class="sxs-lookup"><span data-stu-id="e62fa-142">350</span></span></p></td>
<td><p><span data-ttu-id="e62fa-143">对等：高达 424 x 240 的视频分辨率</span><span class="sxs-lookup"><span data-stu-id="e62fa-143">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="e62fa-144">库视图：不可用</span><span class="sxs-lookup"><span data-stu-id="e62fa-144">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e62fa-145">您可以使用上表中的信息部署新的 HD 视频和库，查看组织中的某些用户的视频会议功能，同时为其他用户提供不同的视频解决方案。</span><span class="sxs-lookup"><span data-stu-id="e62fa-145">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="e62fa-146">在下面的示例中，管理员将推出具有最高视频质量的新视频功能，仅供主管人员使用。</span><span class="sxs-lookup"><span data-stu-id="e62fa-146">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="e62fa-147">对于在网络容量较低的远程分支机构中的员工，仅部署上表中的最小设置。</span><span class="sxs-lookup"><span data-stu-id="e62fa-147">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="e62fa-148">对于所有其他员工，将部署上表中的 "正常" 设置。</span><span class="sxs-lookup"><span data-stu-id="e62fa-148">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="e62fa-149">若要向高级管理人员推出新功能，管理员将创建一个名为 ExecutiveVideo 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="e62fa-149">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="e62fa-150">此会议策略具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="e62fa-150">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="e62fa-151">VideoBitRateKB 设置为 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="e62fa-151">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="e62fa-152">TotalReceiveVideoBitRateKB 设置为 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="e62fa-152">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="e62fa-153">AllowMultiview 设置为 True</span><span class="sxs-lookup"><span data-stu-id="e62fa-153">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="e62fa-154">EnableMultiviewJoin 设置为 True</span><span class="sxs-lookup"><span data-stu-id="e62fa-154">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="e62fa-155">对于分支机构中的员工，管理员创建名为 BranchOfficeVideo 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="e62fa-155">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="e62fa-156">此会议策略具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="e62fa-156">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="e62fa-157">VideoBitRateKB 设置为 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="e62fa-157">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="e62fa-158">TotalReceiveVideoBitRateKB 设置为 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="e62fa-158">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="e62fa-159">AllowMultiview 设置为 True</span><span class="sxs-lookup"><span data-stu-id="e62fa-159">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="e62fa-160">EnableMultiviewJoin 设置为 False</span><span class="sxs-lookup"><span data-stu-id="e62fa-160">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="e62fa-161">对于所有其他员工，管理员创建一个名为 StandardVideo 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="e62fa-161">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="e62fa-162">此会议策略具有以下设置：</span><span class="sxs-lookup"><span data-stu-id="e62fa-162">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="e62fa-163">VideoBitRateKB 设置为 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="e62fa-163">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="e62fa-164">TotalReceiveVideoBitRateKB 设置为 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="e62fa-164">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="e62fa-165">AllowMultiview 设置为 True</span><span class="sxs-lookup"><span data-stu-id="e62fa-165">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="e62fa-166">EnableMultiviewJoin 设置为 True</span><span class="sxs-lookup"><span data-stu-id="e62fa-166">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="e62fa-167">管理员将会议策略分配给用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e62fa-167">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="e62fa-168">将 ExecutiveVideo 会议策略分配给高级管理人员。</span><span class="sxs-lookup"><span data-stu-id="e62fa-168">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="e62fa-169">将 BranchOfficeVideo 会议策略分配给分支机构中的所有员工。</span><span class="sxs-lookup"><span data-stu-id="e62fa-169">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="e62fa-170">将 StandardVideo 会议策略分配给其他所有员工。</span><span class="sxs-lookup"><span data-stu-id="e62fa-170">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="e62fa-171">这些会议策略分配将导致以下用户体验：</span><span class="sxs-lookup"><span data-stu-id="e62fa-171">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="e62fa-172">所有用户支持库视图组织的所有会议，但分支机构中的员工无法体验库视图。</span><span class="sxs-lookup"><span data-stu-id="e62fa-172">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="e62fa-173">对于任何双方或多方会议，高级管理者都可以发送 1920 x 1080 完整的 HD 视频，如果其硬件和网络链接支持它，并且可以接收其他参与者客户端支持的 1920 x 1080 完整 HD 视频。</span><span class="sxs-lookup"><span data-stu-id="e62fa-173">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="e62fa-174">非主管人员在其两方或多方会议中遇到低于管理人员的解决方案，但仍能获得良好的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e62fa-174">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="e62fa-175">当 Lync 显示默认视频窗口大小时，分支机构中的员工将在两方呼叫中获得良好的视频质量;但是，如果将 Lync 窗口最大化为全屏显示，视频分辨率将不会增加。</span><span class="sxs-lookup"><span data-stu-id="e62fa-175">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="e62fa-176">对于多方会议，分支机构中的员工将仅看到一个活动的视频。</span><span class="sxs-lookup"><span data-stu-id="e62fa-176">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

