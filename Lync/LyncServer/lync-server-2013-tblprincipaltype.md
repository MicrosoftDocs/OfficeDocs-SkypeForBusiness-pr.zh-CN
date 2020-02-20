---
title: Lync Server 2013： tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f1c43c0e000e0c8adc3516304b931a68111072d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。

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


### <a name="key"></a>键

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


### <a name="principal-values"></a>主体值

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
<th>Role</th>
<th>说明</th>
<th>用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>任意</p></td>
<td><p>未知类型的通用主体。不用于 tblPrincipal 表。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>双面</p></td>
<td><p>AnyUser</p></td>
<td><p>用户类型的通用主体。不用于 tblPrincipal 表。</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>第三章</p></td>
<td><p>AnyGroup</p></td>
<td><p>组语义的通用主体。不用于 tblPrincipal 表。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>持久聊天服务器在内部使用的主体。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>用户</p></td>
<td><p>常规用户。</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>DC</p></td>
<td><p>Active Directory 域服务域控制器。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Group</p></td>
<td><p>Active Directory 安全组。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>Folder</p></td>
<td><p>Active Directory 容器或组织单位。</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的 tblPrincipal](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

