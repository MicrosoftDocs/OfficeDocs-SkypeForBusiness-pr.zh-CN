---
title: Lync Server 2013：FocusJoinsAndLeaves 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4365e5bbfe92168047165adf6504333e1c34fab6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a>Lync Server 2013 中的 FocusJoinsAndLeaves 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

此表中的每条记录包含有关一个用户的加入的 CDR 信息，并为一个会议留下信息。 每次用户加入和离开会议时，每个会议都将在此表中由一条记录表示。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>键/索引</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外部</p></td>
<td><p>会议实例的时间。 与<strong>SessionIdSeq</strong>结合使用以唯一标识会议实例。 有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>标识会议实例的 ID 号。 与<strong>SessionIdTime</strong>结合使用以唯一标识会议实例。 有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外部</p></td>
<td><p>会话请求的时间。 与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>标识会话的 ID 号。 与<strong>SessionIdTime</strong>结合使用以唯一标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>标识此用户的唯一号码，从<a href="lync-server-2013-users-table.md">Lync Server 2013 的 "用户" 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>如果用户同时在多台计算机或设备上登录，则<strong>UserInstance</strong>用于唯一标识用户/设备组合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>用户是否已从内部登录。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>此用户在会议中的角色，如 "演示者" 或 "与会者"。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此用户加入会议的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此用户离开会议的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>用户的客户端软件版本，<a href="lync-server-2013-clientversions-table.md">在 Lync Server 2013 中引用 ClientVersions 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>标识符</p></td>
<td></td>
<td><p>会议中使用的终结点的全局唯一标识符（GUID）。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

