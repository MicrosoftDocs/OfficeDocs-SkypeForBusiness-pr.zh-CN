---
title: 配置视频示例方案
TOCTitle: 配置视频示例方案
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205297(v=OCS.15)
ms:contentKeyID: 49314425
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置视频示例方案

 

_**上一次修改主题：** 2015-03-09_

Lync 2013 增加了新的视频功能，可支持 1920 x 1080 全高清 (HD) 视频和图库视图视频。基于客户数据的测量表明，与 Lync 2010 相比，典型视频带宽仅略微提高，但最大视频流带宽由于全 HD 支持而有所增加（有关详细信息，请参阅[Lync Server 2013 中的媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)中的“媒体流量网络使用情况”一节）。因此，管理员可能需要限制某些用户（如网络容量较低的分支机构中的用户）的视频带宽并帮助确保其他用户（如管理人员）获得可能的最佳视频质量。

下表给出了为不同网络容量配置视频的推荐设置列表。这些设置将限制某些用户方案发送和接收高分辨率视频（见最右侧的一列）。最低设置将使图库视频由于最大接收网络带宽低而不可用。

### 推荐的视频设置

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
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>良好质量视频的预期视频分辨率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最好</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>对等：最高 1920 x 1080 视频分辨率</p>
<p>图库视图：最多两个 1920 x 1080 视频或多个低分辨率视频</p></td>
</tr>
<tr class="even">
<td><p>良好</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>对等：最高 1280 x 720 视频分辨率</p>
<p>图库视图：最多五个 640 x 360 分辨率视频</p></td>
</tr>
<tr class="odd">
<td><p>中等</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>对等：最高 960 x 540 视频分辨率</p>
<p>图库视图：最多五个 424 x 240 分辨率视频</p></td>
</tr>
<tr class="even">
<td><p>最低</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>对等：最高 424 x 240 视频分辨率</p>
<p>图库视图：不可用</p></td>
</tr>
</tbody>
</table>


可以使用上表中的信息为组织中的某些用户部署新的 HD 视频和图库视图视频会议功能，同时允许其他用户使用不同的视频分辨率。

在以下示例中，管理员仅向管理人员推出具有最高视频质量的新视频功能。对于网络容量较低的远端分支机构中的员工，仅部署上表中的最低设置。对于所有其他员工，部署上表中的“良好”设置。

为向管理人员推出新功能，管理员创建一个名为 ExecutiveVideo 的会议策略。该会议策略具有以下设置：

  - VideoBitRateKB 设置为 8000 Kbps

  - TotalReceiveVideoBitRateKB 设置为 8000 Kbps

  - AllowMultiview 设置为 True

  - EnableMultiviewJoin 设置为 True

对于分支机构中的员工，管理员创建一个名为 BranchOfficeVideo 的会议策略。该会议策略具有以下设置：

  - VideoBitRateKB 设置为 350 Kbps

  - TotalReceiveVideoBitRateKB 设置为 350 Kbps

  - AllowMultiview 设置为 True

  - EnableMultiviewJoin 设置为 False

对于所有其他员工，管理员创建一个名为 StandardVideo 的会议策略。该会议策略具有以下设置：

  - VideoBitRateKB 设置为 2500 Kbps

  - TotalReceiveVideoBitRateKB 设置为 2500 Kbps

  - AllowMultiview 设置为 True

  - EnableMultiviewJoin 设置为 True

管理员按如下方式为用户分配会议策略：

  - 将 ExecutiveVideo 会议策略分配给管理人员。

  - 将 BranchOfficeVideo 会议策略分配给分支机构中的所有员工。

  - 将 StandardVideo 会议策略分配给所有其他员工。

这些会议策略分配会产生以下用户体验：

  - 任何用户组织的所有会议都支持图库视图，但分支机构中的员工无法体验图库视图。

  - 对于任何双方或多方会议，管理人员都可以发送 1920 x 1080 全 HD 视频（只要他们的硬件和网络链路支持），并可以接收 1920 x 1080 全 HD 视频（只要其他参与客户端支持）。

  - 不是管理人员的员工在双方或多方会议中体验到的分辨率比管理人员低，但仍可获得良好的分辨率。

  - 当 Lync 显示默认视频窗口大小时，分支机构中的员工在双方通话中将获得良好的视频质量；但是，如果 Lync 窗口最大化到全屏，视频分辨率不会增加。对于多方会议，分支机构中的员工只能看到一个活动视频。

