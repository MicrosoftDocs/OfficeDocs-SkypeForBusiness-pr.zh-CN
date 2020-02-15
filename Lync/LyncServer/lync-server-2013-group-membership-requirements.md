---
title: Lync Server 2013：组成员身份要求
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
ms.openlocfilehash: 2944b6f3feea6bfc4cadd3566abbdfe4918d9688
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="7478e-102">Lync Server 2013 的组成员身份要求</span><span class="sxs-lookup"><span data-stu-id="7478e-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7478e-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="7478e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="7478e-104">下表汇总了人员所属的组，以便成功安装、管理和排查 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="7478e-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7478e-105">Lync Server 2013 可执行文件</span><span class="sxs-lookup"><span data-stu-id="7478e-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="7478e-106">所需的组成员身份</span><span class="sxs-lookup"><span data-stu-id="7478e-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7478e-107"><strong>Setup.exe –启动</strong>安装 Lync Server 2013 管理工具的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="7478e-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="7478e-108">运行可执行文件的计算机上本地 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="7478e-109">"域用户" 组的成员，以读取 Active Directory 域服务中的信息。</span><span class="sxs-lookup"><span data-stu-id="7478e-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="7478e-110">需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</span><span class="sxs-lookup"><span data-stu-id="7478e-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="7478e-111">您还可以将安装权限委派给那些不会获得 Domain Admins 组成员身份的用户或组。</span><span class="sxs-lookup"><span data-stu-id="7478e-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="7478e-112">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中授予安装程序权限</A>。</span><span class="sxs-lookup"><span data-stu-id="7478e-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7478e-113"><strong>Deploy.exe</strong> – deploy.exe 由 setup.exe 调用，负责为服务器角色部署软件组件。</span><span class="sxs-lookup"><span data-stu-id="7478e-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="7478e-114">运行可执行文件的计算机上本地 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="7478e-115">用于读取 AD DS 中信息的 Domain Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="7478e-116">需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</span><span class="sxs-lookup"><span data-stu-id="7478e-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="7478e-117">若要读取中央管理存储，RtcUniversalReadOnlyAdmins 组中的成员身份是必需的。</span><span class="sxs-lookup"><span data-stu-id="7478e-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7478e-118">如果运行的是 Windows Vista 操作系统或 Windows 7 操作系统，则系统会提示用户帐户控制（UAC）以继续安装。</span><span class="sxs-lookup"><span data-stu-id="7478e-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="7478e-119">如果使用标准用户帐户登录，那么在提示要求您提供具有软件安装权限的帐户时，就需要具有本地 Administrators 组成员身份的用户来提供凭据。</span><span class="sxs-lookup"><span data-stu-id="7478e-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7478e-120"><strong>Bootstrapper.exe</strong> – bootstrapper.exe 由 setup.exe 调用，负责部署和配置服务器角色。</span><span class="sxs-lookup"><span data-stu-id="7478e-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="7478e-p105">运行可执行文件的计算机上本地 Administrators 组的成员。运行 Bootstrapper.exe 的 RTCUniversalServerAdmins 组的成员。读取 AD DS 中的信息的 Domain Users 组的成员。需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</span><span class="sxs-lookup"><span data-stu-id="7478e-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7478e-125"><strong>TopologyBuilder</strong> –用于创建、查看、调整和验证 Lync Server 2013 拓扑的向导驱动的用户界面。</span><span class="sxs-lookup"><span data-stu-id="7478e-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="7478e-126">能在运行可执行文件的计算机上查看拓扑的本地 Administrators 组成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="7478e-127">能更改配置设置的 RTCUniversalServerAdmins 组成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="7478e-128">能发布拓扑的 RTCUniversalServerAdmins 组和 Domain Admins 组成员或 RTCUniversalServerAdmins 组（仅限于该组已授予代理人安装权限的情况）成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="7478e-129">有关委派安装程序权限以允许 RTCUniversalServerAdmins 组的成员在不是 Domain Admins 组成员的情况下发布拓扑的详细信息，请参阅部署文档中的在<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中授予安装程序权限</a>。</span><span class="sxs-lookup"><span data-stu-id="7478e-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7478e-130"><strong>AdminUIHost</strong> –用于管理 Lync Server 2013 的基于 Web 的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="7478e-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="7478e-131">CsAdministrator 组成员或其他已分配特定管理任务的基于角色的访问控制 (RBAC) 角色成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="7478e-132">Lync Server 2013 "控制面板" 通过运行 Lync Server 2013 命令行管理程序 cmdlet 实现配置更改。</span><span class="sxs-lookup"><span data-stu-id="7478e-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="7478e-133">有关预定义角色和允许运行的 cmdlet 成员的列表，请参阅规划文档中的在<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a>。</span><span class="sxs-lookup"><span data-stu-id="7478e-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7478e-134"><strong>加载了 Lync server 2013 模块的 PowerShell</strong> –具有专用于管理 Lync Server 2013 的 cmdlet 的命令行管理工具。</span><span class="sxs-lookup"><span data-stu-id="7478e-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="7478e-135">CsAdministrator 组成员或其他已分配特定 cmdlet 的 RBAC 角色成员。</span><span class="sxs-lookup"><span data-stu-id="7478e-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="7478e-136">有关预定义角色和允许运行的 cmdlet 成员的列表，请参阅规划文档中的在<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a>。</span><span class="sxs-lookup"><span data-stu-id="7478e-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="7478e-137">或下列一组或多组中的成员，具体情况取决于 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7478e-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="7478e-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7478e-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="7478e-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7478e-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="7478e-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="7478e-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

