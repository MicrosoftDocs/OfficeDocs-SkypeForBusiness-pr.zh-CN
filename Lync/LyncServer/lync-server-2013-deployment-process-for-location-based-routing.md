---
title: Lync Server 2013：基于位置的路由的部署过程
TOCTitle: 基于位置的路由的部署过程
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994055(v=OCS.15)
ms:contentKeyID: 52061087
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中基于位置的路由的部署过程

 

_**上一次修改主题：** 2015-03-09_

本主题概述了配置基于位置的路由涉及的过程。在配置基于位置的路由之前，您必须部署 Lync Server企业版 或 标准版企业语音。在部署企业语音时，将安装并启用基于位置的路由所需的组件。

### 基于位置的路由部署过程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>所需的组和角色</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署企业语音</p></td>
<td><ul>
<li><p>配置 Trunk</p></li>
<li><p>创建语音策略</p></li>
<li><p>定义语音路由</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>部署企业语音</p></td>
</tr>
<tr class="even">
<td><p>验证企业语音部署</p></td>
<td><p></p></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>配置网络区域、站点和子网</p></td>
<td><ul>
<li><p>创建网络区域</p></li>
<li><p>创建网络站点</p></li>
<li><p>将子网与网络站点相关联</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>关于网络区域、站点和子网<br />
创建或修改网络区域<br />
创建或修改网络站点<br />
将子网与网络站点相关联</p></td>
</tr>
<tr class="even">
<td><p>配置基于位置的路由</p></td>
<td><ul>
<li><p>创建语音路由策略</p></li>
<li><p>为每个 Trunk 定义单独的 Trunk 配置</p></li>
<li><p>修改语音策略</p></li>
<li><p>启用基于位置的路由配置</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## 示例部署

以下部署用于进一步说明基于位置的路由启用的机制。

![基于位置的路由拓扑](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "基于位置的路由拓扑")

## 传入 PSTN 呼叫

管理员可以启用定义的 Trunk 以针对基于位置的路由将呼叫路由到“站点 1 网关”，并将“站点 1 网关”与站点 1 相关联。启用后，通过“站点 1 网关”路由的呼叫只能路由到站点 1 中的用户。通过“站点 1 网关”路由到不同站点（例如站点 2）中的用户的所有呼叫将被阻止，以防止 PSTN 收费绕路情形。

通过“站点 1 网关”路由的所有传入 PSTN 呼叫仅允许路由到站点 1 中的终结点。例如，当“Lync 用户 1”前往站点 2 时，通过“站点 1 网关”路由的所有传入 PSTN 呼叫不会路由到站点 2 中的“Lync 用户 1”终结点。如果“Lync 用户 1”前往无法确定位置的未知网络站点，相同规则适用。

下表概括了此上下文中“Lync 用户 1”的用户体验。


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
<th>位于网络站点 1 中的 Lync 用户 1 终结点</th>
<th>位于网络站点 2 中的 Lync 用户 1 终结点</th>
<th>位于未知网络站点中的 Lync 用户 1 终结点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>发往 Lync 用户 1 的入站 PSTN 呼叫</p></td>
<td><p>呼叫路由到此位置的终结点</p></td>
<td><p>呼叫未路由到此位置的终结点</p></td>
<td><p>呼叫未路由到此位置的终结点</p></td>
</tr>
</tbody>
</table>


## 传出 PSTN 呼叫

直接分配给用户的语音策略和分配给网络站点的语音路由策略中都引用了语音路由。两种策略都包含对路由的引用，可用于以不同方式路由呼叫。例如，管理员可以为网络站点 1 中的所有用户定义一个语音路由策略，以便通过“站点 1 网关”路由所有出站呼叫，而一些用户的语音策略定义通过“站点 2 网关”路由所有出站呼叫。这些用户都位于网络站点 1 中，其出站呼叫将通过“站点 1 网关”进行路由。

当用户位于配置了基于位置的路由的网络站点中时，网络站点的语音路由策略路由将替代用户的语音策略路由。此规则对于临时移动到不同站点的用户尤其有用。在这种特殊情形下，用户将始终使用其位置的本地网关；如果“Lync 用户 3”位于“站点 2”，则其所有出站呼叫将通过“站点 2 网关”进行路由，但是如果他前往站点 1，则其发出的所有出站呼叫将通过“站点 2 网关”进行路由。

下表说明了从以下网络站点发出出站呼叫的 Lync 用户 1 的用户体验。


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
<th>网络站点 1</th>
<th>网络站点 2</th>
<th>未知网络站点或者未启用基于位置的路由的网络站点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>出站呼叫授权</p></td>
<td><p>Lync 用户 1 语音策略</p></td>
<td><p>Lync 用户 1 语音策略</p></td>
<td><p>Lync 用户 1 语音策略</p></td>
</tr>
<tr class="even">
<td><p>出站呼叫路由</p></td>
<td><p>站点 1 语音路由策略</p></td>
<td><p>站点 2 语音路由策略</p></td>
<td><p>用户的语音策略，仅未启用基于位置的路由的系统</p></td>
</tr>
</tbody>
</table>


## 呼叫转接

当转接呼叫时，呼叫的路由受基于位置的路由影响。

下表说明了 Lync 用户 1 将 PSTN 呼叫转接至另一 Lync 用户。


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
<th>Lync 用户 2</th>
<th>Lync 用户 4</th>
<th>Lync 用户位于未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户 1</p></td>
<td><p>允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
</tr>
</tbody>
</table>

  
下表说明了基于位置的路由对如何基于被转接的 Lync 用户（Lync 用户 2、Lync 用户 4 等）的位置将呼叫路由至 PSTN 终结点的影响


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫转接至的终结点</th>
<th>Lync 用户 2</th>
<th>Lync 用户 4</th>
<th>Lync 用户位于未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>呼叫转接通过站点 1 语音路由策略进行路由，并通过站点 1 网关发出</p></td>
<td><p>呼叫转接通过站点 2 语音路由策略进行路由，并通过站点 2 网关发出</p></td>
<td><p>呼叫转接通过 Lync 用户语音策略进行路由，并通过未启用基于位置的路由的网关发出（如果可用）</p></td>
</tr>
</tbody>
</table>


## 同时响铃

在相同拓扑中配置基于位置的路由之后，将强制实施以下交互。

下表说明了基于位置的路由对于不同 Lync 用户（Lync 用户 2、Lync 用户 4 等）是否允许同时响铃。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>传入 PSTN 呼叫目标</th>
<th>Lync 用户 2</th>
<th>Lync 用户 4</th>
<th>Lync 用户位于未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户 1</p></td>
<td><p>允许同时响铃</p></td>
<td><p>允许同时拨打</p></td>
<td><p>允许同时拨打</p></td>
</tr>
</tbody>
</table>

  
下表说明了基于位置的路由是否允许从不同 Lync 用户（Lync 用户 2、Lync 用户 4 等）同时响铃至 PSTN 终结点。


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
<th>Lync 用户 2</th>
<th>Lync 用户 4</th>
<th>Lync 用户位于未启用基于位置的路由的网络站点中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户 1 移动电话（PSTN 终结点）</p></td>
<td><p>呼叫通过网络站点 1 的语音路由策略进行路由，并通过站点 1 网关发出</p></td>
<td><p>呼叫通过网络站点 2 的语音路由策略进行路由，并通过站点 2 网关发出</p></td>
<td><p>呼叫通过呼叫者语音策略进行路由，并通过未启用基于位置的路由的 PSTN 网关发出</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)

