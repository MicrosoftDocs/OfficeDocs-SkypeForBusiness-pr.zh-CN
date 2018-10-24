---
title: Lync Server 2013：tblADUpdates
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615033(v=OCS.15)
ms:contentKeyID: 49314044
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblADUpdates

 

_**上一次修改主题：** 2015-03-09_

tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务 更改。

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
<td><p>被更改对象的主体 GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)，不为 null</p></td>
<td><p>对象的可分辨名称。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果对象至少有一个属性被更改，则为 True。</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果成员身份被更改，则为 True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit，不为 null</p></td>
<td><p>未使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果对象已删除，则为 True。</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime，不为 null</p></td>
<td><p>插入行时的时间戳。</p></td>
</tr>
</tbody>
</table>

