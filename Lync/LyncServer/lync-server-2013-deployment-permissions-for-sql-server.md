---
title: Lync Server 2013： SQL Server 的部署权限
description: Lync Server 2013： SQL Server 的部署权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575718"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="39726-103">Lync Server 2013 中 SQL Server 的部署权限</span><span class="sxs-lookup"><span data-stu-id="39726-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39726-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="39726-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="39726-105">Microsoft SQL Server 2012 在安装和部署 Lync Server 2013 时有特定要求。</span><span class="sxs-lookup"><span data-stu-id="39726-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="39726-106">由于 Windows 和 SQL Server 以不同的方式定义其安全性，因此以 Active Directory 域中的管理员身份登录不会为 SQL Server 隐式授予权限。</span><span class="sxs-lookup"><span data-stu-id="39726-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="39726-107">您还必须是正配置的基于 SQL Server 的服务器上 sysadmin 实体的成员。</span><span class="sxs-lookup"><span data-stu-id="39726-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="39726-108">数据库和 Lync Server 安装所需的权限</span><span class="sxs-lookup"><span data-stu-id="39726-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="39726-109">以下选项详细介绍了安装 Lync Server 2013 文件和 SQL Server 数据库的三个权限和组成员身份关联。</span><span class="sxs-lookup"><span data-stu-id="39726-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="39726-110">选择最符合组织要求的方案。</span><span class="sxs-lookup"><span data-stu-id="39726-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="39726-111">权限和组成员身份关联</span><span class="sxs-lookup"><span data-stu-id="39726-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39726-112">SQL Server 或 Lync Server 2013 角色</span><span class="sxs-lookup"><span data-stu-id="39726-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="39726-113">典型角色的 SQL Server 权限和组成员身份</span><span class="sxs-lookup"><span data-stu-id="39726-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="39726-114">角色-典型的 Lync Server 2013 权限和组成员身份</span><span class="sxs-lookup"><span data-stu-id="39726-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="39726-115">权限结果</span><span class="sxs-lookup"><span data-stu-id="39726-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39726-116">Lync Server 2013 管理员</span><span class="sxs-lookup"><span data-stu-id="39726-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="39726-117">必须授予 sysadmin SQL Server 安全组和 SQL Server 本地 Administrators 组的成员身份</span><span class="sxs-lookup"><span data-stu-id="39726-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="39726-118">必须是 RTCUniversalServerAdmins 组的成员</span><span class="sxs-lookup"><span data-stu-id="39726-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="39726-119">Lync Server 2013 管理员拥有安装 Lync Server 2013 和 SQL Server 数据库的适当权限。</span><span class="sxs-lookup"><span data-stu-id="39726-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39726-120">SQL Server 管理员</span><span class="sxs-lookup"><span data-stu-id="39726-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="39726-121">SQL Server sysadmin 组成员（或等效身份）和 SQL Server 本地 Administrators 组的成员</span><span class="sxs-lookup"><span data-stu-id="39726-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="39726-122">必须是 RTCUniversalServerReadOnly 组的成员</span><span class="sxs-lookup"><span data-stu-id="39726-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="39726-123">SQL Server 管理员有适当的权限来安装这两个 Lync Server 2013 和 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="39726-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39726-124">两个管理员共同承担安装职责</span><span class="sxs-lookup"><span data-stu-id="39726-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="39726-125">SQL Server 管理员是 sysadmin 组的成员（或等效身份）和 SQL Server 本地 Administrators 组的成员</span><span class="sxs-lookup"><span data-stu-id="39726-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="39726-126">Lync Server 2013 管理员是 RTCUniversalServerAdmins 的成员</span><span class="sxs-lookup"><span data-stu-id="39726-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="39726-127">Lync Server 2013 管理员可以安装 Lync Server 2013，但无法安装数据库。</span><span class="sxs-lookup"><span data-stu-id="39726-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="39726-128">SQL Server 管理员使用 lync server 命令行管理程序和由 Lync Server 2013 管理员提供的 Windows PowerShell cmdlet 来安装数据库。</span><span class="sxs-lookup"><span data-stu-id="39726-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="39726-129">SQL Server 管理员使用的 Lync Server 2013 命令行管理程序安装在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="39726-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="39726-130">这样就无需在基于 SQL Server 的服务器上安装 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="39726-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

