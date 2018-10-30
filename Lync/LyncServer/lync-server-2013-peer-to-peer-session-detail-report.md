---
title: Lync Server 2013：点对点会话详细信息报告
TOCTitle: 点对点会话详细信息报告
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558659(v=OCS.15)
ms:contentKeyID: 49313164
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的点对点会话详细信息报告

 

_**上一次修改主题：** 2015-03-09_

点对点会话详细信息报告返回有关点对点会话的详细信息。例如，如果您选择即时消息会话，则此报告将告知您会话中两个用户各自发送的消息数。

## 访问点对点会话详细信息报告

可以从下列任一报告（可从监控报告主页中访问所有这些报告）访问点对点会话详细信息报告：

  - IP 电话清单报告

  - 用户活动报告

  - 呼叫允许控制报告

  - 故障列表报告

在点对点会话详细信息报告中，可通过单击“诊断报告（详细信息）”指标来访问[Lync Server 2013 中的诊断报告](lync-server-2013-diagnostic-report.md)。此外，还可以通过单击这两个指标之一来访问主要故障报告：

  - 响应

  - 诊断 ID

## 最充分地利用点对点会话详细信息报告

点对点会话详细信息报告包括大量指标，其中有许多指标是系统管理员所不熟悉的。不过，通常您只需将鼠标指针悬停在指标标签的上方即可查看提供了指标的简要说明的工具提示。

请注意，给定报告上显示的实际指标将取决于您所选的点对点会话的类型。音频/视频会话将报告一组与即时消息会话不同的指标。

还可以将鼠标指针悬停在响应代码和诊断 ID 指标的上方来获取这些值的描述：

## 筛选器

无。无法筛选点对点会话详细信息报告。

## 会话信息指标

下表列出了每个会话的点对点会话详细信息报告中提供的信息。

### 会话信息指标

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
<td><p><strong>池 FQDN</strong></p></td>
<td><p>会话中涉及的注册器池或边缘服务器的完全限定域名 (FQDN)。</p></td>
</tr>
<tr class="even">
<td><p><strong>邀请时间</strong></p></td>
<td><p>最初发送会话邀请的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>响应时间</strong></p></td>
<td><p>收到邀请接受函的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>来源用户</strong></p></td>
<td><p>发起会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>源用户代理</strong></p></td>
<td><p>发起会话的用户的终结点使用的软件。</p></td>
</tr>
<tr class="even">
<td><p><strong>源用户为内部用户</strong></p></td>
<td><p>指示启动会话的用户是否登录到内部网络。</p></td>
</tr>
<tr class="odd">
<td><p><strong>源用户与桌面电话集成</strong></p></td>
<td><p>指示启动会话的用户使用的终结点是否与其桌面电话集成。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话优先级</strong></p></td>
<td><p>分配给会话的优先级。有效优先级有：未知、非紧急、正常和紧急。</p></td>
</tr>
<tr class="odd">
<td><p><strong>响应代码</strong></p></td>
<td><p>会话失败时发送的 SIP 响应代码。</p></td>
</tr>
<tr class="even">
<td><p><strong>前端</strong></p></td>
<td><p>会议中使用的前端服务器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>捕获时间</strong></p></td>
<td><p>记录会话信息的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束时间</strong></p></td>
<td><p>会话结束的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目标用户</strong></p></td>
<td><p>受邀加入会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>目标用户代理</strong></p></td>
<td><p>受邀加入会话的用户的终结点使用的软件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目标用户为内部用户</strong></p></td>
<td><p>指示受邀加入会话的用户是否登录到内部网络。</p></td>
</tr>
<tr class="even">
<td><p><strong>目标用户与桌面电话集成</strong></p></td>
<td><p>指示受邀加入会话的用户使用的终结点是否与其桌面电话集成。</p></td>
</tr>
<tr class="odd">
<td><p><strong>为重试会话</strong></p></td>
<td><p>指示会话是否是在尝试重试以前失败的会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。将光标停留在 ID 号上可查看有关该 ID 的其他信息。</p></td>
</tr>
</tbody>
</table>


## 形式指标

下表列出了每种会话形式的点对点会话详细信息报告中提供的信息。

### 形式指标

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
<td><p><strong>形式</strong></p></td>
<td><p>否</p></td>
<td><p>会话中使用的形式。例如，即时消息 (IM) 或文件传输。</p></td>
</tr>
<tr class="even">
<td><p><strong>源用户消息</strong></p></td>
<td><p>否</p></td>
<td><p>启动会话的用户发送的消息数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目标用户消息</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入会话的用户发送的消息数。</p></td>
</tr>
</tbody>
</table>


## 诊断报告指标

下表列出了每个诊断报告的点对点会话详细信息报告中提供的信息。

### 诊断报告指标

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
<td><p>当您单击此项时，报告显示会话的诊断报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>报告时间</strong></p></td>
<td><p>否</p></td>
<td><p>记录报告的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>请求</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 请求类型。例如 INVITE 或 BYE。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>否</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</p></td>
</tr>
<tr class="odd">
<td><p><strong>内容类型</strong></p></td>
<td><p>否</p></td>
<td><p>会议中使用的媒体内容的类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。</p></td>
</tr>
<tr class="even">
<td><p><strong>报告者</strong></p></td>
<td><p>否</p></td>
<td><p>报告问题的计算机（即客户端或服务器）。</p></td>
</tr>
</tbody>
</table>

