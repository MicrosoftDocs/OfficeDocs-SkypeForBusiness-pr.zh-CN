---
title: Lync Server 2013：tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 中的 tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-12_

tblNode 包含在 Lync Server 2013 控制面板和管理 cmdlet 中托管的对象树 (包括类别或聊天室节点)。

### <a name="columns"></a>多

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
<td><p>a</p></td>
<td><p>int, not null</p></td>
<td><p>节点 ID (唯一编号)。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>节点 GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>父项的节点 ID。 根节点 (ID 为 1) 也将其本身包括到父节点。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>位, not null</p></td>
<td><p>如果节点是类别, 则为 True。</p>
<p>如果节点是聊天室, 则为 False。</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>节点名称。</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>节点说明。</p></td>
</tr>
<tr class="odd">
<td><p>邀请</p></td>
<td><p>bit</p></td>
<td><p>对于类别:</p>
<ul>
<li><p>如果邀请已打开, 则为 True。</p></li>
<li><p>如果邀请已关闭, 则为 False。</p></li>
</ul>
<p>对于会议室:</p>
<ul>
<li><p>如果邀请已关闭, 则为 False (覆盖父类别)。</p></li>
<li><p>如果 "邀请" 设置继承自父类别, 则为 Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>身份</p></td>
<td><p>bit</p></td>
<td><p>对于类别:</p>
<ul>
<li><p>如果打开聊天记录, 则为 True。</p></li>
<li><p>如果聊天历史记录处于关闭状态, 则为 False。</p></li>
</ul>
<p>对于会议室:</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>对于类别:</p>
<ul>
<li><p>如果允许文件上载, 则为 True。</p></li>
<li><p>如果不允许文件上载, 则为 False。</p></li>
</ul>
<p>对于会议室:</p>
<ul>
<li><p>Null.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>禁用</p></td>
<td><p>位, not null</p></td>
<td><p>如果禁用聊天室, 则为 True。 仅适用于聊天室。 (False 表示类别。)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>现象</p></td>
<td><p>smallint, not null</p></td>
<td><p>行为 (在 EnumValue 表中查看):</p>
<ul>
<li><p>4: 普通 (正常聊天室)。</p></li>
<li><p>5: Auditorium (Auditorium 聊天室, 只有演示者可以参与)。</p></li>
</ul>
<p>仅适用于聊天室。</p></td>
</tr>
<tr class="odd">
<td><p>了解</p></td>
<td><p>smallint, not null</p></td>
<td><p>可见性 (在 EnumValue 表上查看):</p>
<ul>
<li><p>2: 私密</p></li>
<li><p>3: 范围</p></li>
<li><p>6: 打开</p></li>
</ul>
<p>仅适用于聊天室。</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>加载项 GUID (如果外接程序与此聊天室相关联)。 (类别没有外接程序。)</p>
<p>外接程序信息在 SiopWhiteList 表中查找。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, not null</p></td>
<td><p>创建此节点的主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, not null</p></td>
<td><p>节点创建的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>执行此节点的最新更新的主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, not null</p></td>
<td><p>此节点的最新更新的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>最新的清除操作 (从 tblScopedPrincipal 表的作用域和 tblPrincipalRole 表中的角色删除) 影响此节点的时间。 此功能由聊天服务的内部缓存更新机制使用。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>标示

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
<td><p>a</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>现象</p></td>
<td><p>TblEnumValue 表中的 lookup 的外键。</p></td>
</tr>
<tr class="odd">
<td><p>了解</p></td>
<td><p>TblEnumValue 表中的 lookup 的外键。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>带有 tblNode 表中的 lookup 的外键。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>TblSiopWhiteList 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

