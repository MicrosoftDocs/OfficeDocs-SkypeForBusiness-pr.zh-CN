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
ms.openlocfilehash: cf9570f3df344c26da3296904a8394f59f8a907d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516969"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>为 Lync Server 2013 配置视频示例方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

Lync 2013 添加了新的视频功能，以支持 1920 x 1080 full high definition (HD) 视频和库观看视频。 基于客户数据的度量显示典型的视频带宽的增加仅与 Lync 2010 相比稍有不同，但由于完整的 HD (支持，最大视频流带宽增加了：有关详细信息，请参阅 [Lync Server 2013 中的媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)) 中的 "媒体流量网络使用情况" 部分。 因此，管理员可能希望限制某些用户 (的视频带宽，例如分支机构中网络容量较少的用户) 并帮助确保其他 (用户（如行政人员) ）可能获得最佳视频质量。

下表提供了针对不同网络容量配置视频的推荐设置的列表。 这些设置将限制某些用户方案发送和接收更高分辨率的视频 (请参阅最右边的列) 。 由于最大的接收网络带宽不足，最小设置将导致库视频不可用。

### <a name="recommended-video-settings"></a>建议的视频设置

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
<td><p>最好</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>对等：高达 1920 x 1080 的视频分辨率</p>
<p>库视图：最多 2 1920 x 1080 视频或多个更小的分辨率视频</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>对等：高达 1280 x 720 的视频分辨率</p>
<p>库视图：最高为 5 640 x 360 分辨率的视频</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>对等：高达 960 x 540 的视频分辨率</p>
<p>库视图：最高为 5 424 x 240 分辨率的视频</p></td>
</tr>
<tr class="even">
<td><p>最小值</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>对等：高达 424 x 240 的视频分辨率</p>
<p>库视图：不可用</p></td>
</tr>
</tbody>
</table>


您可以使用上表中的信息部署新的 HD 视频和库，查看组织中的某些用户的视频会议功能，同时为其他用户提供不同的视频解决方案。

在下面的示例中，管理员将推出具有最高视频质量的新视频功能，仅供主管人员使用。 对于在网络容量较低的远程分支机构中的员工，仅部署上表中的最小设置。 对于所有其他员工，将部署上表中的 "正常" 设置。

若要向高级管理人员推出新功能，管理员将创建一个名为 ExecutiveVideo 的会议策略。 此会议策略具有以下设置：

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

管理员将会议策略分配给用户，如下所示：

  - 将 ExecutiveVideo 会议策略分配给高级管理人员。

  - 将 BranchOfficeVideo 会议策略分配给分支机构中的所有员工。

  - 将 StandardVideo 会议策略分配给其他所有员工。

这些会议策略分配将导致以下用户体验：

  - 所有用户支持库视图组织的所有会议，但分支机构中的员工无法体验库视图。

  - 对于任何双方或多方会议，高级管理者都可以发送 1920 x 1080 完整的 HD 视频，如果其硬件和网络链接支持它，并且可以接收其他参与者客户端支持的 1920 x 1080 完整 HD 视频。

  - 非主管人员在其两方或多方会议中遇到低于管理人员的解决方案，但仍能获得良好的解决方案。

  - 当 Lync 显示默认视频窗口大小时，分支机构中的员工将在两方呼叫中获得良好的视频质量;但是，如果将 Lync 窗口最大化为全屏显示，视频分辨率将不会增加。 对于多方会议，分支机构中的员工将仅看到一个活动的视频。

</div>

<span> </span>

</div>

</div>

</div>

