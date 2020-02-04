---
title: Lync Server 2013：tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a>Lync Server 2013 中的 tblFileToken

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-12_

tblFileToken 包含用于文件传输目的的临时令牌。

### <a name="columns"></a>多

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
<td><p>nvarchar （50），not null</p></td>
<td><p>唯一标记（GUID）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int，not null</p></td>
<td><p>传输文件的主体的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID，not null</p></td>
<td><p>聊天室节点的 GUID。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime，not null</p></td>
<td><p>过期时间。 （令牌将在30分钟后到期，除非已固定（请参阅本专栏中的以下说明）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>已传送文件的 URL （用于合规性服务使用）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>传输文件的缩略图的 URL （适用于合规性服务使用）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>实际文件传输操作的时间戳（用于合规性服务使用）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bit</p></td>
<td><p>如果上载，则为 True;如果下载（适用于合规性服务使用），则为 False。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>位，not null</p></td>
<td><p>如果标记已固定，则为 True。 它用于在表中保留令牌，直到合规性服务有机会从中检索相关字段。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>标示

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
<td><p>TblNode 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

