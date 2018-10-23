---
title: Lync Server 2013：tblNode
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615024(v=OCS.15)
ms:contentKeyID: 49313813
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblNode

 

_**上一次修改主题：** 2015-03-09_

tblNode 包含的对象树（包含类别或聊天室节点）与 Lync Server 2013 控制面板和管理 cmdlet 中所管理的树相同。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>节点 ID（唯一编号）。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID，不为 null</p></td>
<td><p>节点 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>父节点 ID。根节点（ID 为 1）将其自身用作父项。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果节点是类别，则为 True。</p>
<p>如果节点是聊天室，则为 False。</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>节点名称。</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>节点描述。</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>bit</p></td>
<td><p>针对类别：</p>
<ul>
<li><p>如果邀请打开，则为 True。</p></li>
<li><p>如果邀请关闭，则为 False。</p></li>
</ul>
<p>针对聊天室：</p>
<ul>
<li><p>如果邀请关闭，则为 False（覆盖父类别）。</p></li>
<li><p>如果邀请设置是继承自父类别，则为 Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>logged</p></td>
<td><p>bit</p></td>
<td><p>针对类别：</p>
<ul>
<li><p>如果聊天历史记录打开，则为 True。</p></li>
<li><p>如果聊天历史记录关闭，则为 False。</p></li>
</ul>
<p>针对聊天室：</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>针对类别：</p>
<ul>
<li><p>如果允许文件上载，则为 True。</p></li>
<li><p>如果不允许文件上载，则为 False。</p></li>
</ul>
<p>针对聊天室：</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>disabled</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果聊天室已禁用，则为 True。仅适用于聊天室。（对于类别则为 False。）</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>行为（在 EnumValue 表中查找）：</p>
<ul>
<li><p>4：普通（普通聊天室）。</p></li>
<li><p>5：大会堂（大会堂聊天室，仅演示者可以参与）。</p></li>
</ul>
<p>仅适用于聊天室。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>可见性（在 EnumValue 表中查找）：</p>
<ul>
<li><p>2：专用</p></li>
<li><p>3：范围</p></li>
<li><p>6：打开</p></li>
</ul>
<p>仅适用于聊天室。</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>如果外接程序与此聊天室关联，则为外接程序 GUID。（类别没有外接程序。）</p>
<p>外接程序信息在 SiopWhiteList 表中进行查找。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>创建此节点的主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>节点创建的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>对此节点执行最新更新的主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>此节点最新更新的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>影响此节点的最近一次清除操作（从 tblScopedPrincipal 表中删除范围，从 tblPrincipalRole 表中删除角色）的时间。用于聊天服务的内部缓存更新机制。</p></td>
</tr>
</tbody>
</table>


### 键

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>在 tblEnumValue.valueID 表中查找的外键。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>在 tblEnumValue.valueID 表中查找的外键。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>在 tblNode.nodeID 表中查找的外键。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>在 tblSiopWhiteList.siopId 表中查找的外键。</p></td>
</tr>
</tbody>
</table>

