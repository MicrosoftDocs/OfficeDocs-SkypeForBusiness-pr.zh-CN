---
title: Lync Server 2013：组成员身份要求
description: Lync Server 2013：组成员身份要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f18fb6fbc782ecd41b7a782965f2cd6a82f6fd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554458"
---
# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="eb319-103">Lync Server 2013 的组成员身份要求</span><span class="sxs-lookup"><span data-stu-id="eb319-103">Group membership requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb319-104">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="eb319-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="eb319-105">下表汇总了人员所属的组，以便成功安装、管理和排查 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="eb319-105">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb319-106">Lync Server 2013 可执行文件</span><span class="sxs-lookup"><span data-stu-id="eb319-106">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="eb319-107">所需的组成员身份</span><span class="sxs-lookup"><span data-stu-id="eb319-107">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb319-108"><strong>Setup.exe</strong> –开始安装 Lync Server 2013 管理工具的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="eb319-108"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="eb319-109">运行可执行文件的计算机上本地 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-109">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="eb319-110">"域用户" 组的成员，以读取 Active Directory 域服务中的信息。</span><span class="sxs-lookup"><span data-stu-id="eb319-110">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="eb319-111">需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</span><span class="sxs-lookup"><span data-stu-id="eb319-111">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="eb319-112">您还可以将安装权限委派给那些不会获得 Domain Admins 组成员身份的用户或组。</span><span class="sxs-lookup"><span data-stu-id="eb319-112">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="eb319-113">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中授予安装程序权限</A> 。</span><span class="sxs-lookup"><span data-stu-id="eb319-113">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb319-114"><strong>Deploy.exe</strong> – deploy.exe 由 setup.exe 调用，负责为服务器角色部署软件组件。</span><span class="sxs-lookup"><span data-stu-id="eb319-114"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="eb319-115">运行可执行文件的计算机上本地 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-115">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="eb319-116">用于读取 AD DS 中信息的 Domain Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-116">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="eb319-117">需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</span><span class="sxs-lookup"><span data-stu-id="eb319-117">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="eb319-118">若要读取中央管理存储，RtcUniversalReadOnlyAdmins 组中的成员身份是必需的。</span><span class="sxs-lookup"><span data-stu-id="eb319-118">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="eb319-119">如果您运行的是 Windows Vista 操作系统或 Windows 7 操作系统，则用户帐户控制将提示您 (UAC) 继续安装。</span><span class="sxs-lookup"><span data-stu-id="eb319-119">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="eb319-120">如果使用标准用户帐户登录，那么在提示要求您提供具有软件安装权限的帐户时，就需要具有本地 Administrators 组成员身份的用户来提供凭据。</span><span class="sxs-lookup"><span data-stu-id="eb319-120">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb319-121"><strong>Bootstrapper.exe</strong> – bootstrapper.exe 由 setup.exe 调用，负责部署和配置服务器角色。</span><span class="sxs-lookup"><span data-stu-id="eb319-121"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="eb319-p105">运行可执行文件的计算机上本地 Administrators 组的成员。运行 Bootstrapper.exe 的 RTCUniversalServerAdmins 组的成员。读取 AD DS 中的信息的 Domain Users 组的成员。需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</span><span class="sxs-lookup"><span data-stu-id="eb319-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb319-126"><strong>TopologyBuilder</strong> –用于创建、查看、调整和验证 Lync Server 2013 拓扑的向导驱动的用户界面。</span><span class="sxs-lookup"><span data-stu-id="eb319-126"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="eb319-127">能在运行可执行文件的计算机上查看拓扑的本地 Administrators 组成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-127">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="eb319-128">能更改配置设置的 RTCUniversalServerAdmins 组成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-128">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="eb319-129">能发布拓扑的 RTCUniversalServerAdmins 组和 Domain Admins 组成员或 RTCUniversalServerAdmins 组（仅限于该组已授予代理人安装权限的情况）成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-129">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="eb319-130">有关委派安装程序权限以允许 RTCUniversalServerAdmins 组的成员在不是 Domain Admins 组成员的情况下发布拓扑的详细信息，请参阅部署文档中的在 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中授予安装程序权限</a> 。</span><span class="sxs-lookup"><span data-stu-id="eb319-130">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb319-131"><strong>AdminUIHost</strong> –用于管理 Lync Server 2013 的基于 Web 的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="eb319-131"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="eb319-132">CsAdministrator 组成员或其他已分配特定管理任务的基于角色的访问控制 (RBAC) 角色成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-132">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="eb319-133">Lync Server 2013 "控制面板" 通过运行 Lync Server 2013 命令行管理程序 cmdlet 实现配置更改。</span><span class="sxs-lookup"><span data-stu-id="eb319-133">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="eb319-134">有关预定义角色和允许运行的 cmdlet 成员的列表，请参阅规划文档中的在 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a> 。</span><span class="sxs-lookup"><span data-stu-id="eb319-134">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb319-135"><strong> 使用已加载 Lync server 2013 模块的PowerShell.exe</strong> （具有特定于 lync Server 2013 管理的 cmdlet 的命令行管理工具）。</span><span class="sxs-lookup"><span data-stu-id="eb319-135"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="eb319-136">CsAdministrator 组成员或其他已分配特定 cmdlet 的 RBAC 角色成员。</span><span class="sxs-lookup"><span data-stu-id="eb319-136">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="eb319-137">有关预定义角色和允许运行的 cmdlet 成员的列表，请参阅规划文档中的在 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a> 。</span><span class="sxs-lookup"><span data-stu-id="eb319-137">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="eb319-138">或下列一组或多组中的成员，具体情况取决于 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eb319-138">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb319-139">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="eb319-139">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="eb319-140">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="eb319-140">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="eb319-141">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="eb319-141">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

