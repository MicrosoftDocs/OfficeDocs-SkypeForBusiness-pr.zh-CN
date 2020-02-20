---
title: Lync Server 2013： tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf1c04cb24f8fee668cd21f24fc7c9c1c5341d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a>Lync Server 2013 中的 tblAdminLock

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-25_

tblAdminLock 包含运行一些管理员命令所需的管理员锁。

### <a name="columns"></a>Columns

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime，不为 null</p></td>
<td><p>锁到期日期和时间。所有者可以定期延长该值。</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int，不为 null</p></td>
<td><p>拥有锁的服务器的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int，不为 null</p></td>
<td><p>拥有锁的主体的 ID。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

