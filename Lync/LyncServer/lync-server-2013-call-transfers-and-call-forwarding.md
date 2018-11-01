---
title: Lync Server 2013：呼叫转移和呼叫转接
TOCTitle: 呼叫转移和呼叫转接
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994051(v=OCS.15)
ms:contentKeyID: 52061074
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫转移和呼叫转接

 

_**上一次修改主题：** 2015-03-09_

当涉及 PSTN 终结点时，基于位置的路由将分析呼叫者的终结点以及呼叫将转接至的终结点（即转接目标）的位置。基于位置的路由根据两个终结点的位置确定是否应转接呼叫。

下表说明了与 PSTN 终结点进行呼叫的 Lync 用户的方案，Lync 用户将呼叫转接至另一个 Lync 用户。根据受让方的终结点的网络站点位置，基于位置的路由会影响呼叫转接的路由。

### 发起呼叫转接

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>发起呼叫转接的用户</th>
<th>目标终结点位于与发起呼叫转接的用户相同的网络站点中</th>
<th>目标终结点位于与发起呼叫转接的用户不同的网络站点中</th>
<th>目标终结点位于未知网络站点或者未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户</p></td>
<td><p>允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
</tr>
</tbody>
</table>

  

例如，一位与 PSTN 终结点进行呼叫的 Lync 用户将呼叫转接至相同网络站点中的另一 Lync 用户。在这种情况下，允许进行呼叫转接。

下表说明了与另一 Lync 用户进行呼叫的 Lync 用户的方案，其中一个用户将呼叫转接至 PSTN 终结点。根据呼叫转接至的用户的位置，表格详细介绍了基于位置的路由如何影响呼叫。

### 呼叫转接至 PSTN 终结点

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫转接终结点目标</th>
<th>Lync 用户位于相同网络站点中</th>
<th>Lync 用户位于不同网络站点中</th>
<th>一个或两个 Lync 用户位于未知网络站点或者未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>转接用户的站点语音路由策略允许呼叫转接</p></td>
<td><p>转接用户的站点语音路由策略允许呼叫转接</p></td>
<td><p>转接用户的语音策略仅允许通过未启用基于位置的路由的 Trunk 进行呼叫转接</p></td>
</tr>
</tbody>
</table>

  
例如，与相同网络站点中的另一 Lync 用户进行呼叫的 Lync 用户将呼叫转接至 PSTN 终结点，并且允许进行呼叫转接。

## 另请参阅

#### 其他资源

[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)

