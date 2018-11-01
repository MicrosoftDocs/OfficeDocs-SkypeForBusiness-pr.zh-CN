---
title: Lync Server 2013：tblFileToken
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558646(v=OCS.15)
ms:contentKeyID: 49312749
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblFileToken

 

_**上一次修改主题：** 2015-03-09_

tblFileToken 包含用于文件传输的临时令牌。

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
<td><p>fileToken</p></td>
<td><p>nvarchar (50)，不为 null</p></td>
<td><p>唯一令牌（一个 GUID）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int，不为 null</p></td>
<td><p>要传输文件的主体的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID，不为 null</p></td>
<td><p>聊天室节点的 GUID。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime，不为 null</p></td>
<td><p>过期时间。除非固定，令牌的有效期为 30 分钟（请参阅此列中以下说明）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>已传输文件的 URL（用于合规性服务）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>已传输文件的缩略图的 URL（用于合规性服务）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>实际文件传输操作的时间戳（用于合规性服务）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bit</p></td>
<td><p>如果上载，则为 True；如果下载，则为 False（用于合规性服务）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果令牌是固定的，则为 True。它将不会用于保存表中的令牌，除非合规性服务有机会从其中检索相关字段。</p></td>
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
<td><p>fileToken</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>其查找包含在 tblNode.nodeGuid 表中的外键。</p></td>
</tr>
</tbody>
</table>

