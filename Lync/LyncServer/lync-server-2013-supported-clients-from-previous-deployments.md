---
title: Lync Server 2013：先前部署中支持的客户端
TOCTitle: 先前部署中支持的客户端
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398499(v=OCS.15)
ms:contentKeyID: 49313123
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 先前部署中支持的客户端

 

_**上一次修改主题：** 2015-03-09_

在共存方案中， Lync Server 2013 客户端可与来自早期版本的 Lync Server 和 Office Communications Server 的客户端交互。与早期版本不同， Lync Server 2010 支持新的 Lync 2013 客户端。这将允许从 Lync Server 2010 升级的组织独立于 Lync Server 升级推出新的客户端。

## 支持的服务器和客户端组合

下表显示受支持的客户端版本和服务器版本的组合。Lync Server 2013 支持两个早期客户端版本， Lync Server 2010 支持新的 Lync 2013 客户端。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 群聊</p></td>
<td><p>不适用</p></td>
<td><p>支持1</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>不支持2</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>可互操作3</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
</tbody>
</table>


1在 Microsoft Lync Server 2010 中，群聊功能适用于群聊服务器，它是用于 Lync Server 2010 的第三方受信任应用程序。Lync 2013 客户端与 Lync Server 2010 群聊不兼容。

2Lync Web App 2013 现在提供一个完整的会议内体验，包括计算机音频和视频，可取代 Lync 2010 Attendee。

3Office Communicator 2007 R2 中的状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。在从 Office Communications Server 2007 R2 迁移的过程中， Office Communicator 2007 R2 可提供状态和 IM 互操作性，但用户应使用 Lync Web App 2013 来加入 Lync Server 2013 会议。

> [!NOTE]  
> 有关 Lync Server 2013 客户端与来自早期版本的 Lync Server 和 Office Communications Server 的客户端共存和交互的能力的详细信息，请参阅规划文档中的 <a href="lync-server-2013-client-interoperability-in-lync-2013.md">Lync 2013 中的客户端互操作性</a>。

