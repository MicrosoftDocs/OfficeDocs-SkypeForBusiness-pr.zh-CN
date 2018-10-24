---
title: 基于位置的路由和咨询呼叫转接
TOCTitle: 基于位置的路由和咨询呼叫转接
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56271194
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 基于位置的路由和咨询呼叫转接

 

_**上一次修改主题：** 2015-03-09_

除了对 Lync 会议强制实施基于位置的路由之外，基于位置的路由会议应用程序将对发出到 PSTN 终结点的咨询呼叫转接强制实施基于位置的路由限制。咨询呼叫转接是指在两方（其中一方将呼叫转接给新用户）之间建立的呼叫。例如，PSTN 终结点呼叫用户 A（Lync 被叫方）。用户 A 确定 PSTN 用户应被转接给用户 B（Lync 用户）。用户 A 将与 PSTN 用户的呼叫置于保持状态，而呼叫用户 B。用户 B 同意与 PSTN 用户进行交谈。用户 A 将保持的呼叫转接给用户 B。

**咨询呼叫转接呼叫流**

![会议的基于位置的路由图示](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会议的基于位置的路由图示")

当启用了基于位置的路由的用户启动 PSTN 终结点的咨询呼叫转接时（如上图所示），这将创建两个活动呼叫：一个呼叫在 PSTN 用户和 Lync 用户 A 之间，另一个呼叫在 Lync 用户 A 与 Lync 用户 B 之间。基于位置的路由会议应用程序将强制实施以下行为：

  - 如果路由 PSTN 呼叫的 SIP 中继经过授权将 PSTN 呼叫重新路由到 Lync 用户 B（即转接目标）所在的网络站点，那么允许呼叫转接；否则，咨询呼叫转接将被阻止。此授权基于与将活动呼叫路由到 PSTN 终结点的 SIP 中继位于相同网络站点中的转接方的位置执行。

  - 如果路由入站 PSTN 呼叫的 SIP 中继未经授权将呼叫路由到转接方（Lync 用户 B）所在的网络站点或者转接方位于未知网络站点中，则至 PSTN 终结点（即呼叫转接目标）的咨询呼叫转接将被阻止。

下表介绍了基于位置的路由会议应用程序如何为咨询呼叫转接应用基于位置的路由限制。尽管 PBX 终结点不直接与网络站点相关联，但是可以向 PBX 连接至的 SIP 中继分配网络站点。因此，PBX 终结点可以间接地与网络站点相关联。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>呼叫转接方的网络站点</p></td>
<td><p>呼叫转接目标的网络站点</p></td>
<td><p>行为</p></td>
</tr>
<tr class="even">
<td><p>PSTN 终结点</p></td>
<td><p>相同网络站点（如站点 1）中的 Lync 用户</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>不同网络站点（如站点 2）中的 Lync 用户</p></td>
<td><p>禁止咨询呼叫转接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 终结点</p></td>
<td><p>未知网络站点中的 Lync 用户</p></td>
<td><p>禁止咨询呼叫转接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>联盟的 Lync 用户</p></td>
<td><p>禁止咨询呼叫转接</p></td>
</tr>
<tr class="even">
<td><p>PSTN 终结点</p></td>
<td><p>相同站点（如站点 1）中的 PBX 终结点</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>不同站点（如站点 2）中的 PBX 终结点</p></td>
<td><p>禁止咨询呼叫转接</p></td>
</tr>
<tr class="even">
<td><p>相同站点（如站点 1）中的 PBX 终结点</p></td>
<td><p>PSTN 终结点</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
<tr class="odd">
<td><p>不同站点（如站点 2）中的 PBX 终结点</p></td>
<td><p>PSTN 终结点</p></td>
<td><p>禁止咨询呼叫转接</p></td>
</tr>
<tr class="even">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>相同网络站点（如站点 1）中的 Lync 用户</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
<tr class="odd">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>不同网络站点（如站点 2）中的 Lync 用户</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
<tr class="even">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>未知网络站点中的 Lync 用户</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
<tr class="odd">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>联盟的 Lync 用户</p></td>
<td><p>允许咨询呼叫转接</p></td>
</tr>
</tbody>
</table>

