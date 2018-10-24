---
title: Lync Server 2013：同时响铃
TOCTitle: 同时响铃
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994079(v=OCS.15)
ms:contentKeyID: 52061145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的同时响铃

 

_**上一次修改主题：** 2015-03-09_

当被呼叫方启用了同时响铃时，基于位置的路由将分析呼叫方的位置和被呼叫方的终结点以确定是否应路由呼叫。

下表说明配置了同时响铃的用户，同时响铃目标是位于相同网络站点中的用户、位于不同网络站点中的用户或者位于未知网络站点中的用户。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>传入 PSTN 呼叫</th>
<th>位于与被呼叫者相同的网络站点中</th>
<th>位于与被呼叫者不同的网络站点中</th>
<th>位于未知网络站点或者未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户</p></td>
<td><p>允许同时响铃</p></td>
<td><p>不允许同时响铃</p></td>
<td><p>不允许同时响铃</p></td>
</tr>
</tbody>
</table>

  
下表说明来自位于相同网络站点中、不同网络站点中或者未知网络站点中的 Lync 用户（即 Lync 呼叫者）的呼叫。被呼叫者将 PSTN 终结点（如移动电话）配置为同时响铃目标。在此方案中，基于位置的路由将确定呼叫是否应路由到被呼叫者的同时响铃目标（如移动电话）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同时响铃目标</th>
<th>位于与被呼叫者相同的网络站点中</th>
<th>位于与被呼叫者不同的网络站点中</th>
<th>位于未知网络站点或者未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>允许通过呼叫者的站点语音路由策略同时响铃</p></td>
<td><p>允许通过呼叫者的站点语音路由策略同时响铃</p></td>
<td><p>允许通过呼叫者的语音策略向未启用基于位置的路由的 Trunk 同时响铃</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 其他资源

[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)

