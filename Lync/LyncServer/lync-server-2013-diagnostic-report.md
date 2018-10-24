---
title: Lync Server 2013：诊断报告
TOCTitle: 诊断报告
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615445(v=OCS.15)
ms:contentKeyID: 49313990
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的诊断报告

 

_**上一次修改主题：** 2016-12-08_

诊断报告提供失败的会话的诊断和故障排除信息。此信息包括在会话失败时所报告的诊断 ID 和诊断标头。诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），而诊断标头提供诊断 ID 的附带说明。该报告可能还包含报告组件所了解的有价值的故障排除详细信息。例如：

  - 由生成故障的 PSTN 网关提供的原因代码。在 PSTN 网络上，传出呼叫失败时，会自动生成 ISDN 用户部分 (ISUP) 原因代码。例如，PSTN 网关可能会发送原因代码 34，指示不存在可用于完成呼叫的任何电路或信道。

  - 针对连接失败的对等方 FQDN、端口和 Winsock 错误。

  - 针对 DNS 解析失败所查找的名称。每次客户端联系名称服务器并请求与指定的设备名称相对应的 IP 地址时，都会进行 DNS 解析。

## 访问诊断报告

可以通过单击[Lync Server 2013 中的点对点会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)或会议详细信息报告上的“诊断报告(详细信息)”指标，来访问诊断报告。

## 筛选器

无。您不能对诊断报告进行筛选。

## 指标

下表列出了各会话的诊断报告中提供的信息。

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
<td><p><strong>报告时间</strong></p></td>
<td><p>否</p></td>
<td><p>记录报告的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>响应代码</strong></p></td>
<td><p>否</p></td>
<td><p>会话失败时发送的 SIP 响应代码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>请求类型</strong></p></td>
<td><p>否</p></td>
<td><p>失败的 SIP 请求类型。例如，INVITE、BYE 或 SERVICE。</p></td>
</tr>
<tr class="even">
<td><p><strong>源</strong></p></td>
<td><p>否</p></td>
<td><p>错误的来源。</p></td>
</tr>
<tr class="odd">
<td><p><strong>源用户 URI</strong></p></td>
<td><p>否</p></td>
<td><p>发起会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>源用户代理</strong></p></td>
<td><p>否</p></td>
<td><p>发起会话的用户的终结点使用的软件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>否</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</p></td>
</tr>
<tr class="even">
<td><p><strong>内容类型</strong></p></td>
<td><p>否</p></td>
<td><p>失败的媒体内容类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。</p></td>
</tr>
<tr class="odd">
<td><p><strong>应用程序</strong></p></td>
<td><p>否</p></td>
<td><p>错误涉及的应用程序。</p></td>
</tr>
<tr class="even">
<td><p><strong>目标用户 URI</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p>会议加入时间（毫秒）</p></td>
<td><p>否</p></td>
<td><p>用户加入会议所需的时间量（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断标头</strong></p></td>
<td><p>否</p></td>
<td><p>诊断 ID 描述</p></td>
</tr>
</tbody>
</table>


可在 [Ms-Diagnostics 标头页](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx)上找到诊断错误的列表。

