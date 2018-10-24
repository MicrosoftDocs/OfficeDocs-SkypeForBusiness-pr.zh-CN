---
title: Lync Server 2013：tblSiopWhiteList
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558607(v=OCS.15)
ms:contentKeyID: 49311880
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblSiopWhiteList

 

_**上一次修改主题：** 2015-03-09_

tblSiopWhiteList 是可与节点关联的注册外接程序的列表。

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
<td><p>siopID</p></td>
<td><p>GUID，不为 null</p></td>
<td><p>外接程序的 GUID。</p></td>
</tr>
<tr class="even">
<td><p>siopName</p></td>
<td><p>nvarchar (50)，不为 null</p></td>
<td><p>加载项的显示名称。</p></td>
</tr>
<tr class="odd">
<td><p>siopUrl</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>加载项的 URL。</p></td>
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
<td><p>siopID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

