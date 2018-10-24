---
title: Lync Server 2013：tblPrincipalType
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558633(v=OCS.15)
ms:contentKeyID: 49312431
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPrincipalType

 

_**上一次修改主题：** 2015-03-09_

tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。

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
<td><p>ptypeID</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>主体类型 ID。</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>类型描述。</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit，不为 null</p></td>
<td><p>在类型与供内部使用的主体对应时为 True。</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit，不为 null</p></td>
<td><p>在类型为用户类型时为 True。</p></td>
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
<td><p>ptypeID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


### 主体值

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>角色</th>
<th>说明</th>
<th>用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>任意</p></td>
<td><p>未知类型的通用主体。不用于 tblPrincipal 表。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>用户类型的通用主体。不用于 tblPrincipal 表。</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>组语义的通用主体。不用于 tblPrincipal 表。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>供 持久聊天服务器内部使用的主体。</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>用户</p></td>
<td><p>常规用户。</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Active Directory 域服务 域控制器。</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>组</p></td>
<td><p>Active Directory 安全组。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>文件夹</p></td>
<td><p>Active Directory 容器或组织单位。</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Lync Server 2013 中的 tblPrincipal](lync-server-2013-tblprincipal.md)

