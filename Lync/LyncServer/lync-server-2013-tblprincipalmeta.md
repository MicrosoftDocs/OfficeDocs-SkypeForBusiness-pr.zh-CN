---
title: Lync Server 2013：tblPrincipalMeta
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615009(v=OCS.15)
ms:contentKeyID: 49313410
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPrincipalMeta

 

_**上一次修改主题：** 2015-03-09_

tblPrincipalMeta 表包含必须从 Active Directory 域服务 刷新的主体。

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
<td><p>prinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="even">
<td><p>prinAffiliationsDirty</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果必须刷新主体附属关系，则为 True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果必须刷新主体属性，则为 True。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果主体已删除，则为 True。</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>截止目前，已发生的尝试从 AD DS 刷新主体的次数。</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>datetime</p></td>
<td><p>最近尝试刷新主体的时间戳。如果尚未尝试任何刷新，可以为 null。</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>datetime</p></td>
<td><p>计划的下一次刷新的时间戳。如果尚未计划进一步刷新，可以为 null。</p></td>
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
<td><p>prinID</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>在 tblPrincipal.prinID 表中查找的外键。</p></td>
</tr>
</tbody>
</table>

