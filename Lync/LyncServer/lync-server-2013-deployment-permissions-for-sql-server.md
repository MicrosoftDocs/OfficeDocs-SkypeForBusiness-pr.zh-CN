---
title: Lync Server 2013：SQL Server 的部署权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Lync Server 2013 中 SQL Server 的部署权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

Microsoft SQL Server 2012 在安装和部署 Lync Server 2013 时有特定要求。 由于 Windows 和 SQL Server 以不同的方式定义其安全性, 因此以 Active Directory 域中的管理员身份登录不会为 SQL Server 隐式授予权限。 你还必须是你正在配置的基于 SQL Server 的服务器上 sysadmin 实体的成员。

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>数据库和 Lync Server 安装所需的权限

以下选项详细介绍了安装 Lync Server 2013 文件和 SQL Server 数据库时的三个权限和组成员身份关联。 选择最符合组织要求的方案。

### <a name="permissions-and-group-membership-associations"></a>权限和组成员身份关联

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server 或 Lync Server 2013 角色</th>
<th>角色-典型的 SQL Server 权限和组成员身份</th>
<th>角色-典型的 Lync Server 2013 权限和组成员身份</th>
<th>权限结果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 管理员</p></td>
<td><p>必须授予 sysadmin SQL Server 安全组和 SQL Server 本地管理员组成员的成员身份</p></td>
<td><p>必须是 RTCUniversalServerAdmins 组的成员</p></td>
<td><p>Lync Server 2013 管理员拥有安装 Lync Server 2013 和 SQL Server 数据库的相应权限。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 管理员</p></td>
<td><p>Sql Server sysadmin 组成员 (或同等身份) 和 SQL Server 本地管理员组的成员</p></td>
<td><p>必须是 RTCUniversalServerReadOnly 组的成员</p></td>
<td><p>SQL Server 管理员拥有安装 Lync Server 2013 和 SQL Server 数据库的相应权限。</p></td>
</tr>
<tr class="odd">
<td><p>共享安装职责的两个管理员</p></td>
<td><p>SQL Server 管理员是 sysadmin 组 (或同等) 的成员, 以及 SQL Server 本地管理员组的成员</p></td>
<td><p>Lync Server 2013 管理员是 RTCUniversalServerAdmins 的成员</p></td>
<td><p>Lync Server 2013 管理员可以安装 Lync Server 2013, 但无法安装数据库。 SQL Server 管理员使用 lync Server Management Shell 和由 Lync Server 2013 管理员提供的 Windows PowerShell cmdlet 来安装数据库。 SQL Server 管理员使用的 Lync Server 2013 管理外壳程序已安装在前端服务器上。 这样便无需在基于 SQL Server 的服务器上安装 Lync Server 2013 管理工具。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

