---
title: Lync Server 2013：tblADCookie
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558610(v=OCS.15)
ms:contentKeyID: 49311944
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblADCookie

 

_**上一次修改主题：** 2015-03-09_

tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。

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
<td><p>要监控的域的主体 GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Active Directory 域服务 同步使用的当前域控制器的完全限定域名 (FQDN)。具有信息性值。</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (binary)</p></td>
<td><p>Active Directory 同步 Cookie。</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>具有行更新时间的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>为更改锁定行的截止时间。此时间是软件联锁机制的一部分，可确保一次仅使其中一个聊天服务执行 Active Directory 同步。</p></td>
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
<td><p>prinGuid</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>其查找包含在 Principal.prinGuid 表中的外键。</p></td>
</tr>
</tbody>
</table>

