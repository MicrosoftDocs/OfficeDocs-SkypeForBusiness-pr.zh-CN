---
title: Lync Server 2013：tblPrincipalMemberDifference
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558612(v=OCS.15)
ms:contentKeyID: 49311964
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPrincipalMemberDifference

 

_**上一次修改主题：** 2015-03-09_

PrincipalMemberDifference 包含尚未通过随后的 Active Directory 域服务 同步步骤处理的组成员身份更改（添加的和删除的成员）信息。

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
<td><p>prinGuid</p></td>
<td><p>GUID，不为 null</p></td>
<td><p>更改的组的主体 GUID。</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>成员的可分辨名称。</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved</p></td>
<td><p>bit，不为 null</p></td>
<td><p>在添加成员时，设置为 False。在删除成员时，设置为 True。</p></td>
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
<td><p>&lt;prinGuid, memberADPath&gt;</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

