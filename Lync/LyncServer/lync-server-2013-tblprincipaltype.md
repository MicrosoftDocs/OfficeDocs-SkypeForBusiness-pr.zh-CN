---
title: Lync Server 2013：tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-12_

tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。

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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ptypeID</p></td>
<td><p>smallint, not null</p></td>
<td><p>主体类型 ID。</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>类型的说明。</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>位, not null</p></td>
<td><p>如果类型对应于用于内部用途的主体, 则为 True。</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>位, not null</p></td>
<td><p>如果类型为用户类型, 则为 True。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>关键字

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
<th>角色</th>
<th>说明</th>
<th>用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>任意</p></td>
<td><p>没有已知类型的泛型主体。 未在 tblPrincipal 表中使用。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>用户类型的一般主体。 未在 tblPrincipal 表中使用。</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>具有组语义的常规主体。 未在 tblPrincipal 表中使用。</p></td>
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
<td><p>普通用户。</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>个</p></td>
<td><p>电源</p></td>
<td><p>Active Directory 域服务域控制器。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>db-9</p></td>
<td><p>团队</p></td>
<td><p>Active Directory 安全组。</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>收藏夹</p></td>
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

