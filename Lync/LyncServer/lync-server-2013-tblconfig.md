---
title: Lync Server 2013：tblConfig
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558663(v=OCS.15)
ms:contentKeyID: 49313257
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblConfig

 

_**上一次修改主题：** 2015-03-09_

tblConfig 包含一些不支持 持久聊天服务器的配置（这些配置位于一个行中）。

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
<td><p>configLabel</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>包含“池”。</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>配置内容。</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID，不为 null</p></td>
<td><p>数据库实例的唯一 ID。</p></td>
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
<td><p>configLabel</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

