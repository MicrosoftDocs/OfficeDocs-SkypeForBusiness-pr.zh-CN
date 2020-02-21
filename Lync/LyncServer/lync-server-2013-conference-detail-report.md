---
title: Lync Server 2013：会议详细信息报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 670696a0945464486e0872b17df330a6ca8140b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的会议详细信息报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

会议详细信息报告提供了参与会议的所有用户的详细信息。 例如，您可以查看用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的终结点的用户代理等信息。 您还可以查看用户在每个会议中的角色（例如，演示者或与会者）的信息。 最重要的是，您很快就会发现哪些用户成功加入会议并完成会议，哪些用户无法成功加入会议，也无法完成会议。

<div>

## <a name="accessing-the-conference-detail-report"></a>访问会议详细信息报告

可从以下报告访问会议详细信息报告：

  - [Lync Server 2013 中的呼叫允许控制报告](lync-server-2013-call-admission-control-report.md)（单击会议的详细信息指标）

  - [Lync Server 2013 中的故障列表报告](lync-server-2013-failure-list-report.md)（通过单击会议指标）

  - [Lync Server 2013 中的用户活动报告](lync-server-2013-user-activity-report.md)（通过单击 "会议 URI" 指标）

从会议详细信息报告中，您可以通过单击 "诊断报告（详细信息）" 指标来访问[Lync Server 2013 中的诊断报告](lync-server-2013-diagnostic-report.md)。

</div>

<div>

## <a name="filters"></a>筛选器

无。 无法筛选会议详细信息报告。

</div>

<div>

## <a name="metrics"></a>指标

下表列出了会议详细信息报告的 "会议信息" 部分提供的信息。

### <a name="conference-information-metrics"></a>会议信息指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>会议 URI</strong></p></td>
<td></td>
<td><p>分配给会议的 URI。 例如：</p>
<p>sip： kmyer@litwareinc; gruu; 不透明 = app：会议：焦点： id： drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>池 FQDN</strong></p></td>
<td></td>
<td><p>会话中涉及的注册器池或边缘服务器的完全限定域名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>开始时间</strong></p></td>
<td></td>
<td><p>会议开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td></td>
<td><p>组织会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td></td>
<td><p>会议结束的日期和时间。</p></td>
</tr>
</tbody>
</table>


下表列出了会议详细信息报告的会议参与部分提供的信息。

### <a name="conference-participation-metrics"></a>会议参与指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>用户</strong></p></td>
<td></td>
<td><p>参与会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>角色</strong></p></td>
<td></td>
<td><p>会议参与者扮演的角色（例如“演示者”）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>连接</strong></p></td>
<td></td>
<td><p>参与者的网络连接（通常为“来自内部”或“来自外部”）。</p></td>
</tr>
<tr class="even">
<td><p>加入时间</p></td>
<td></td>
<td><p>参与者加入会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>离开时间</strong></p></td>
<td></td>
<td><p>参与者离开会议的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>用户代理</strong></p></td>
<td></td>
<td><p>参与者终结点使用的软件的标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>诊断报告</strong></p></td>
<td></td>
<td><p>提供诊断和疑难解答信息。 包括 SIP 响应代码、诊断标头、会议加入时间，以及失败会话的诊断 Id。</p></td>
</tr>
</tbody>
</table>


下表列出了会议详细信息报告的 "会议形式" 部分提供的信息。

### <a name="conference-modalities-metrics"></a>会议形式指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>用户</strong></p></td>
<td></td>
<td><p>参与会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入时间</strong></p></td>
<td></td>
<td><p>参与者加入会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>离开时间</strong></p></td>
<td></td>
<td><p>参与者离开会议的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>会议服务器 URI</strong></p></td>
<td></td>
<td><p>会议中使用的会议服务器的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>诊断报告</strong></p></td>
<td></td>
<td><p>提供诊断和疑难解答信息。 包括 SIP 响应代码、诊断标头、会议加入时间，以及失败会话的诊断 Id。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

