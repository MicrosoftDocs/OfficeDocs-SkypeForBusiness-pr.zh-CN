---
title: Lync Server 2013：为 Lync Server 启用的用户帐户
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
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>为 Lync Server 2013 启用的用户帐户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-04-18_

本部分中的主题提供了配置用户设置的分步过程，这些设置可使用 Lync Server 2013 控制面板执行。

<div>


> [!IMPORTANT]  
> 无法使用 Lync Server 控制面板管理属于 Active Directory 域管理员组成员的用户。 对于域管理员用户，您只能使用 Lync Server "控制面板" 执行只读搜索操作。 若要对域管理员用户执行写操作（例如，启用或禁用 Lync Server 控制面板、更改池或策略分配、电话设置、SIP 地址），则必须在以域管理员用户身份登录时使用 Windows PowerShell cmdlet。 有关使用 Windows PowerShell cmdlet 管理用户的详细信息，请参阅<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 命令行管理</A>程序。



</div>

当你执行涉及搜索用户或筛选用户搜索结果的任何 Lync Server 2013 管理任务时，有一些用户属性作为属性存在于 Active Directory 域服务中，但未复制到全局编录在部署 Microsoft Exchange Server 之前。 Microsoft Exchange （而不是 Lync 服务器）在安装时标记用于复制到全局编录的以下属性：


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
<td><p>申请人</p></td>
<td><p>街道地址</p>
<p>国家/地区</p>
<p>导航</p>
<p>传入</p>
<p>移动</p></td>
<td><p>标题</p>
<p>子公司</p>
<p>部门</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本节内容

  - [查看有关为 Lync Server 2013 启用的用户帐户的信息](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [在 Lync Server 2013 中管理用户的企业语音语音](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [在 Lync Server 2013 中修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)

  - [在 Lync Server 2013 中管理组织的外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中分配每个用户的策略](lync-server-2013-assigning-per-user-policies.md)

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

