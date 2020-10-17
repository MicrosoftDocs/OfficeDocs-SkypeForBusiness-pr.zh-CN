---
title: Lync Server 2013：为 Lync Server 启用的用户帐户
description: Lync Server 2013：为 Lync Server 启用的用户帐户。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569868"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a>为 Lync Server 2013 启用的用户帐户

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-18_

本节中的主题提供了配置用户设置的分步过程，您可以使用 Lync Server 2013 控制面板来执行这些设置。

<div>


> [!IMPORTANT]  
> 您不能使用 Lync Server 控制面板来管理属于 Active Directory Domain Admins 组成员的用户。 对于域管理员用户，只能使用 Lync Server 控制面板执行只读的搜索操作。 对域管理员用户执行写入操作 (例如，为 Lync Server 控制面板 "启用或禁用"、"更改池" 或 "策略分配"、"电话服务设置"、"SIP 地址") ，在以域管理员用户身份登录时必须使用 Windows PowerShell cmdlet。 有关使用 Windows PowerShell cmdlet 管理用户的详细信息，请参阅 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 命令行管理</A>程序。



</div>

当您执行涉及搜索用户或筛选用户搜索结果的任何 Lync Server 2013 管理任务时，会有一些用户属性作为属性存在于 Active Directory 域服务中，但在部署 Microsoft Exchange Server 之前不会复制到全局编录中。 Microsoft Exchange （而不是 Lync Server）在安装时将以下属性标记为用于复制到全局编录：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用户信息</th>
<th>地址和电话</th>
<th>组织</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initials</p></td>
<td><p>街道地址</p>
<p>国家/地区</p>
<p>值班</p>
<p>Fax</p>
<p>移动版</p></td>
<td><p>标题</p>
<p>公司</p>
<p>部门</p>
<p>办公室</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本部分内容

  - [查看有关为 Lync Server 2013 启用的用户帐户的信息](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [为 Lync Server 2013 启用和禁用用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [在 Lync Server 2013 中管理用户的企业语音语音](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [在 Lync Server 2013 中修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)

  - [在 Lync Server 2013 中管理外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中分配每用户策略](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的用户管理 cmdlet](lync-server-2013-user-management-cmdlets.md)  


[在 Lync Server 2013 中管理用户](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

