---
title: Lync Server 2013：tblPrincipalAffiliations
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558642(v=OCS.15)
ms:contentKeyID: 49312711
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPrincipalAffiliations

 

_**上一次修改主题：** 2015-03-09_

tblPrincipalAffiliations 包含的主体附属关系介绍包括 Active Directory 域服务 安全组的位置中、Active Directory 容器中以及域中的成员身份。

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
<td><p>principalID</p></td>
<td><p>int，不为 null</p></td>
<td><p>附属主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int，不为 null</p></td>
<td><p>表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。</p></td>
</tr>
<tr class="odd">
<td><p>索引</p></td>
<td><p>int，不为 null</p></td>
<td><p>索引。自附属关系的值为 -1，对于其他附属关系，该值在每个 &lt;principalID, affiliationId&gt; 桶中按顺序从 1 递增。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>进行最新更新的主体。这通常为 1，表示 Active Directory 同步。</p></td>
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
<td><p>&lt;principalID, index, affiliationID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>在 tblPrincipal.prinID 表中查找的外键。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>在 tblPrincipal.prinID 表中查找的外键。</p></td>
</tr>
</tbody>
</table>

