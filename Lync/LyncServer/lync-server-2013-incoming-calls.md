---
title: Lync Server 2013：传入呼叫
TOCTitle: 传入呼叫
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994038(v=OCS.15)
ms:contentKeyID: 52061044
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的传入呼叫

 

_**上一次修改主题：** 2015-03-09_

发往启用了基于位置的路由的用户的传入呼叫基于用户的终结点位置进行路由。传入呼叫的路由通过以下方式受到影响。如果用户具有一个传入呼叫发往位于启用了基于位置的路由的网络站点内的终结点，并且该终结点位于与 PSTN 网关相同的网络站点中，则将路由呼叫。如果用户具有一个传入呼叫发往位于启用了基于位置的路由的网络站点内的终结点，并且该终结点位于与 PSTN 网关不同的网络站点中，则不路由呼叫。当用户没有终结点位于与从中发出传入呼叫的 PSTN 网关相同的网络站点中时，则传入呼叫将直接路由到用户的语音邮件，并且将向被呼叫方发送错过的呼叫通知。

启用了基于位置的路由的用户的呼叫转接设置将继续强制实施，然而，转接的呼叫受用户的基于位置的路由限制约束。

下表说明了基于位置的路由如何根据被呼叫者的终结点位置影响入站呼叫的路由。PSTN 网关的网络站点启用了基于位置的路由，并且基于位置的路由仅允许将 PSTN 呼叫路由到相同网络站点内的终结点。

### 从 PSTN 接收入站呼叫的被呼叫者

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位于与 PSTN 网关相同的网络站点中的被呼叫者终结点</th>
<th>不位于与 PSTN 网关相同的网络站点中的被呼叫者终结点</th>
<th>位于未知网络站点中或者没有启用基于位置的路由的被呼叫者终结点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>入站 PSTN 呼叫的路由</p></td>
<td><p>传入呼叫会路由到被呼叫者的终结点</p></td>
<td><p>传入呼叫不会路由到被呼叫者的终结点</p></td>
<td><p>传入呼叫不会路由到被呼叫者的终结点</p></td>
</tr>
</tbody>
</table>

  

## 另请参阅

#### 其他资源

[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)

