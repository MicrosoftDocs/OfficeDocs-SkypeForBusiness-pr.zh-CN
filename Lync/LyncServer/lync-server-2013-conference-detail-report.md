---
title: 会议详细信息报告
TOCTitle: 会议详细信息报告
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204728(v=OCS.15)
ms:contentKeyID: 49312186
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会议详细信息报告

 

_**上一次修改主题：** 2015-03-09_

会议详细信息报告提供有关参与会议的所有用户的详细信息。例如，您可以查看用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的端点的用户代理等信息。还可以查看用户在每个会议中的角色的信息（例如，演示者或与会者）。可能最重要的是，您可以快速查看哪些用户成功加入和完成会议，哪些用户无法成功加入和完成会议。

## 访问会议详细信息报告

可从以下报告中访问会议详细信息报告：

  - [Lync Server 2013 中的呼叫允许控制报告](lync-server-2013-call-admission-control-report.md)（通过单击会议的“详细信息”指标）

  - [Lync Server 2013 中的故障列表报告](lync-server-2013-failure-list-report.md)（通过单击“会议”指标）

  - [Lync Server 2013 中的用户活动报告](lync-server-2013-user-activity-report.md)（通过单击“会议 URI”指标）

从会议详细信息报告中，可通过单击“诊断报告(详细信息)”指标来访问[Lync Server 2013 中的诊断报告](lync-server-2013-diagnostic-report.md)。

## 筛选器

无。您无法筛选会议详细信息报告。

## 指标

下表列出了会议详细信息报告的“会议信息”部分提供的信息。

### 会议信息指标

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
<td><p></p></td>
<td><p>分配给会议的 URI。例如：</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>池 FQDN</strong></p></td>
<td><p></p></td>
<td><p>会话中涉及的注册器池或边缘服务器的完全限定域名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>开始时间</strong></p></td>
<td><p></p></td>
<td><p>会议开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>组织者</strong></p></td>
<td><p></p></td>
<td><p>组织会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td><p></p></td>
<td><p>会议结束的日期和时间。</p></td>
</tr>
</tbody>
</table>


下表列出了会议详细信息报告的“会议参与”部分提供的信息。

### 会议参与指标

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
<td><p><strong>用户</strong></p></td>
<td><p></p></td>
<td><p>参与会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>角色</strong></p></td>
<td><p></p></td>
<td><p>会议参与者扮演的角色（例如“演示者”）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>连接</strong></p></td>
<td><p></p></td>
<td><p>参与者的网络连接（通常为“来自内部”或“来自外部”）。</p></td>
</tr>
<tr class="even">
<td><p>加入时间</p></td>
<td><p></p></td>
<td><p>参与者加入会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>离开时间</strong></p></td>
<td><p></p></td>
<td><p>参与者离开会议的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>用户代理</strong></p></td>
<td><p></p></td>
<td><p>参与者的端点所使用软件的标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>诊断报告</strong></p></td>
<td><p></p></td>
<td><p>提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。</p></td>
</tr>
</tbody>
</table>


下表列出了会议详细信息报告的“会议形式”部分提供的信息。

### 会议形式指标

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
<td><p><strong>用户</strong></p></td>
<td><p></p></td>
<td><p>参与会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入时间</strong></p></td>
<td><p></p></td>
<td><p>参与者加入会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>离开时间</strong></p></td>
<td><p></p></td>
<td><p>参与者离开会议的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>会议服务器 URI</strong></p></td>
<td><p></p></td>
<td><p>会议中使用的会议服务器的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>诊断报告</strong></p></td>
<td><p></p></td>
<td><p>提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。</p></td>
</tr>
</tbody>
</table>

