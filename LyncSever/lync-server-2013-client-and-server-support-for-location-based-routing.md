---
title: Lync Server 2013：基于位置的路由的客户端和服务器支持
TOCTitle: 基于位置的路由的客户端和服务器支持
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994024(v=OCS.15)
ms:contentKeyID: 52060988
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中基于位置的路由的客户端和服务器支持

 

_**上一次修改主题：** 2015-03-09_

基于位置的路由由 Lync Server 强制实施。Lync Server 可以识别用户在企业网络内从中连接的网络站点。由于远程用户位于企业网络外，则其位置将被视为未知。

## Lync Server 支持

基于位置的路由要求在给定拓扑中的所有 前端池 和 Standard Edition 服务器 上部署 Lync Server 2013。如果拓扑中的特定 Lync 组件上未安装 Lync Server 2013 CU1，则无法完全强制实施基于位置的路由限制。

下表介绍了基于位置的路由支持的服务器角色和版本的组合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>池版本</th>
<th>中介服务器 版本</th>
<th>支持</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 2013 年 2 月累积更新</p></td>
<td><p>Lync Server 2013 2013 年 2 月累积更新</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 年 2 月累积更新</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 2013 年 2 月累积更新</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 年 2 月累积更新</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>任意</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>不支持</p></td>
</tr>
</tbody>
</table>


## Lync 客户端支持

下表介绍了基于位置的路由支持的客户端。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端类型</th>
<th>支持</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支持</p></td>
<td><p>包括 Lync 2013 2013 年 2 月累积更新</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>支持</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>不支持</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>支持</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync 助理</p></td>
<td><p>支持</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync for Windows 8</p></td>
<td><p>不支持</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>不支持</p></td>
<td><p>如果由启用了基于位置的路由的用户使用，则必须为 Lync Mobile 2013 客户端禁用 VoIP。</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>支持</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

> [!NOTE]  
> 要为 Lync Mobile 2013 客户端禁用 VoIP，请为启用了基于位置的路由的所有用户分配一个移动策略并禁用 IP 音频/视频设置。有关移动策略的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</a>。



## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)

