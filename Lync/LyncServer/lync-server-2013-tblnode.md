---
title: Lync Server 2013： tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee7c67421ae12d08e52bee1b013dfa6280472f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 中的 tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblNode 包含在 Lync Server 2013 控制面板和管理 cmdlet 中托管的对象树（包含类别或聊天室节点）。

### <a name="columns"></a>Columns

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
<td><p>个</p></td>
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
<td><p>位</p></td>
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
<td><p>日志</p></td>
<td><p>位</p></td>
<td><p>针对类别：</p>
<ul>
<li><p>如果聊天历史记录打开，则为 True。</p></li>
<li><p>如果聊天历史记录关闭，则为 False。</p></li>
</ul>
<p>针对聊天室：</p>
<ul>
<li><p>不适.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>位</p></td>
<td><p>针对类别：</p>
<ul>
<li><p>如果允许文件上载，则为 True。</p></li>
<li><p>如果不允许文件上载，则为 False。</p></li>
</ul>
<p>针对聊天室：</p>
<ul>
<li><p>不适.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>禁用</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果聊天室已禁用，则为 True。仅适用于聊天室。（对于类别则为 False。）</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>性能</p></td>
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


### <a name="keys"></a>Keys

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
<td><p>个</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>性能</p></td>
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


</div>

<span> </span>

</div>

</div>

</div>

