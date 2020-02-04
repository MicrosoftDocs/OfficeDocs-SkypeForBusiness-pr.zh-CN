---
title: Lync Server 2013：配置视频示例方案
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
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>配置 Lync Server 2013 的视频示例方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

Lync 2013 添加了支持 1920 x 1080 完整高清（HD）视频和库观看视频的新视频功能。 基于客户数据的度量显示典型的视频带宽与 Lync 2010 相比稍有略微增加，但由于完全高清支持，最大视频流带宽已增加（有关详细信息，请参阅在[Lync Server 2013 中媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)中的 "媒体流量网络使用情况" 部分）。 因此，管理员可能希望限制某些用户（如分支机构中网络容量较少的用户）的视频带宽，并帮助确保其他用户（如管理人员）可能获得最佳视频质量。

下表提供了针对不同网络容量配置视频的推荐设置列表。 这些设置将限制某些用户方案发送和接收更高分辨率的视频（请参阅最右边的列）。 由于最大接收网络带宽不足，最小设置将导致库视频不可用。

### <a name="recommended-video-settings"></a>推荐的视频设置

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
<th>预期视频分辨率以获得优质视频</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最佳</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>对等：高达 1920 x 1080 视频分辨率</p>
<p>库视图：最高可达 2 1920 x 1080 视频或多个更小分辨率的视频</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>对等：高达 1280 x 720 视频分辨率</p>
<p>库视图：最高可达 5 640 x 360 分辨率的视频</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>对等：高达 960 x 540 视频分辨率</p>
<p>库视图：最高可达 5 424 x 240 分辨率的视频</p></td>
</tr>
<tr class="even">
<td><p>最低</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>对等：高达 424 x 240 视频分辨率</p>
<p>库视图：不可用</p></td>
</tr>
</tbody>
</table>


你可以使用上表中的信息部署新的 HD 视频和库查看组织中的某些用户的视频会议功能，同时允许其他人使用不同的视频分辨率。

在以下示例中，管理员推出了最高视频质量的新视频功能，仅供主管人员使用。 对于网络容量较低的远程分支机构中的员工，仅部署上表中的最小设置。 对于所有其他员工，将部署上表中的 "良好" 设置。

为了向高级管理人员推出新功能，管理员创建了一个名为 ExecutiveVideo 的会议策略。 此会议策略具有以下设置：

  - VideoBitRateKB 设置为 8000 Kbps

  - TotalReceiveVideoBitRateKB 设置为 8000 Kbps

  - AllowMultiview 设置为 True

  - EnableMultiviewJoin 设置为 True

对于分支机构中的员工，管理员创建名为 BranchOfficeVideo 的会议策略。 此会议策略具有以下设置：

  - VideoBitRateKB 设置为 350 Kbps

  - TotalReceiveVideoBitRateKB 设置为 350 Kbps

  - AllowMultiview 设置为 True

  - EnableMultiviewJoin 设置为 False

对于所有其他员工，管理员创建一个名为 StandardVideo 的会议策略。 此会议策略具有以下设置：

  - VideoBitRateKB 设置为 2500 Kbps

  - TotalReceiveVideoBitRateKB 设置为 2500 Kbps

  - AllowMultiview 设置为 True

  - EnableMultiviewJoin 设置为 True

管理员按如下方式向用户分配会议策略：

  - ExecutiveVideo 会议策略已分配给高级管理人员。

  - BranchOfficeVideo 会议策略已分配给分支机构中的所有员工。

  - StandardVideo 会议策略已分配给所有其他员工。

这些会议策略分配将导致以下用户体验：

  - 由任何用户支持库视图组织的所有会议，但分支机构中的员工无法体验库视图。

  - 对于任何两方或多方会议，高级管理人员都可以发送 1920 x 1080 完整的 HD 视频（如果其硬件和网络链接支持它），并且可以接收到其他参与者客户支持的 1920 x 1080 完整 HD 视频。

  - 非主管人员在他们的两方或多方会议中的执行官之间体验的员工越低，但仍能获得良好的解决方案。

  - 当 Lync 显示默认视频窗口大小时，分支机构中的员工将在两方通话中获得良好的视频质量;但是，如果将 Lync 窗口最大化到全屏，视频分辨率将不会增加。 对于多方会议，分支机构中的员工将仅看到一个活动视频。

</div>

<span> </span>

</div>

</div>

</div>

