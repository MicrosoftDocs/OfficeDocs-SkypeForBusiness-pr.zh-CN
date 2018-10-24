---
title: Lync Server 2013：tblEnumAttribute
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558617(v=OCS.15)
ms:contentKeyID: 49312122
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblEnumAttribute

 

_**上一次修改主题：** 2015-03-09_

tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。

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
<td><p>attributeID</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>属性的 ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>属性的名称。</p></td>
</tr>
</tbody>
</table>


### 按键

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
<td><p>attributeID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


### 表值

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>可见性。</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>行为。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Lync Server 2013 中的 tblNode](lync-server-2013-tblnode.md)

