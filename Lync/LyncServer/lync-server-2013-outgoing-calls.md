---
title: Lync Server 2013：传出呼叫
TOCTitle: 传出呼叫
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994049(v=OCS.15)
ms:contentKeyID: 52061066
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的传出呼叫

 

_**上一次修改主题：** 2015-03-09_

启用了基于位置的路由的用户的出站呼叫路由受用户的终结点的网络位置影响。下表说明了基于位置的路由如何根据呼叫者的终结点位置影响出站呼叫的路由。

### 向 PSTN 发出出站呼叫的呼叫者

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位于启用了基于位置的路由的网络站点中的用户终结点</th>
<th>位于未知网络站点或者未启用基于位置的路由的网络站点中的用户终结点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>出站呼叫授权</p></td>
<td><p>基于用户的语音策略授权呼叫</p></td>
<td><p>基于用户的语音策略授权呼叫</p></td>
</tr>
<tr class="even">
<td><p>出站呼叫路由</p></td>
<td><p>根据网络站点的语音路由策略路由呼叫</p></td>
<td><p>根据用户的语音策略仅通过未启用基于位置的路由的 Trunk 路由呼叫（如果可用）</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 其他资源

[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)

