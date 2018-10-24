---
title: Lync Server 2013：呼叫允许控制报告
TOCTitle: 呼叫允许控制报告
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615043(v=OCS.15)
ms:contentKeyID: 49314622
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫允许控制报告

 

_**上一次修改主题：** 2015-03-09_

呼叫允许控制报告提供有关点对点和由呼叫允许控制设置限制下举行的会议会话的信息。在 Microsoft Lync Server 2010 中引入的呼叫允许控制为管理员提供一种方法，以允许（或不允许）基于带宽限制的通信会话。例如，管理员可创建对可用于语音和视频呼叫的带宽量施加限制的策略。如果已达到该带宽限制，则可进行新的语音和视频呼叫，直到其中的一个当前呼叫结束并释放所需的网络资源为止。

## 访问呼叫允许控制报告

从监控报告主页可访问呼叫允许控制报告。从呼叫允许控制报告可深入到下列任何报告：

  - 会议详细信息报告 - 要访问此报告，请从会议会话单击详细信息指标。

  - 点对点会话详细信息报告 – 要访问此报告，请单击点对点会话的详细信息指标。

## 充分利用呼叫允许控制报告

要获得因带宽不足而失败的呼叫的列表，请从呼叫类别下拉列表选择因呼叫允许控制拒绝的呼叫。大多数返回的呼叫将可能具有 5 个诊断 ID 之一：

建立会话带宽不足。尝试 PSTN 重新路由。

这指示呼叫允许控制限制阻止在 VoIP 网络上进行的呼叫。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，呼叫允许控制报告允许您按发起呼叫的用户或按被呼叫的用户筛选呼叫。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。

下表列出了可用于呼叫允许控制报告的筛选器。

### 呼叫允许控制报告的筛选器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>开始日期</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/17/12012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/17/12012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>池</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
<tr class="even">
<td><p><strong>活动类型</strong></p></td>
<td><p>活动的类型。选择下列活动之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>点对点</p></li>
<li><p>会议</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫类别</strong></p></td>
<td><p>指示对呼叫使用 CAC 的原因。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>由于呼叫允许控制，呼叫被拒绝</p></li>
<li><p>由于呼叫允许控制，呼叫通过 PSTN 重新路由</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 点对点会话的指标

下表列出了点对点会话（即，只涉及两个参与者的会话）的呼叫允许控制报告中提供的信息。

### 点对点会话的指标

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>详细信息</strong></p></td>
<td><p>否</p></td>
<td><p>单击此项时，报告将显示指定会话的点对点会话详细信息报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>来源用户</strong></p></td>
<td><p>是</p></td>
<td><p>发起会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目标用户</strong></p></td>
<td><p>是</p></td>
<td><p>受邀加入会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>是</p></td>
<td><p>会话期间使用的通信形式（如音频和视频）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀请时间</strong></p></td>
<td><p>是</p></td>
<td><p>向源用户发送初始会话邀请的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>响应时间</strong></p></td>
<td><p>是</p></td>
<td><p>收到邀请接受函的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td><p>是</p></td>
<td><p>会话结束的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>是</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</p></td>
</tr>
</tbody>
</table>


## 会议会话的指标

下表列出了会议会话（即，涉及三个或更多参与者的会话）的呼叫允许控制报告中提供的信息。

### 会议会话的指标

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>会议 URI</strong></p></td>
<td><p>是</p></td>
<td><p>会议的唯一标识符。单击此项时，报告将显示单个会议参与者。</p></td>
</tr>
<tr class="even">
<td><p><strong>组织者</strong></p></td>
<td><p>是</p></td>
<td><p>组织会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>池</strong></p></td>
<td><p>是</p></td>
<td><p>会议中使用的边缘服务器。</p></td>
</tr>
<tr class="even">
<td><p><strong>开始时间</strong></p></td>
<td><p>是</p></td>
<td><p>会议开始的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td><p>是</p></td>
<td><p>会议结束的日期和时间。</p></td>
</tr>
</tbody>
</table>


## 单个会议参与者的指标

下表列出了单个会议参与者的呼叫允许控制报告中提供的信息。

### 单个会议参与者的指标

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>角色</strong></p></td>
<td><p>否</p></td>
<td><p>会议参与者扮演的角色（例如“演示者”）。</p></td>
</tr>
<tr class="even">
<td><p><strong>参与者</strong></p></td>
<td><p>否</p></td>
<td><p>会议参与者的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>连接</strong></p></td>
<td><p>否</p></td>
<td><p>参与者的网络连接（通常为“来自内部”或“来自外部”）。</p></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>否</p></td>
<td><p>会议类型（例如 A/V 会议）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入时间</strong></p></td>
<td><p>否</p></td>
<td><p>参与者加入会议的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>离开时间</strong></p></td>
<td><p>否</p></td>
<td><p>参与者离开会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>否</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</p></td>
</tr>
</tbody>
</table>

