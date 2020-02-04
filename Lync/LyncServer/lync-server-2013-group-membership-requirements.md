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
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="19bee-102">Lync Server 2013 的组成员身份要求</span><span class="sxs-lookup"><span data-stu-id="19bee-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19bee-103">_**主题上次修改时间：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="19bee-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="19bee-104">下表总结了人员应属于的组或组，以便成功安装、管理 Lync Server 2013 并对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="19bee-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19bee-105">Lync Server 2013 可执行文件</span><span class="sxs-lookup"><span data-stu-id="19bee-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="19bee-106">需要组成员身份</span><span class="sxs-lookup"><span data-stu-id="19bee-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19bee-107"><strong>Setup.exe-启动</strong>Lync Server 2013 管理工具安装的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="19bee-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="19bee-108">运行可执行文件的计算机上本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="19bee-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="19bee-109">"域用户" 组的成员以读取 Active Directory 域服务中的信息。</span><span class="sxs-lookup"><span data-stu-id="19bee-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="19bee-110">此级别的权限是必需的，因为本地计算机上必需的 MSI 程序包的自动安装需要允许读取和写入受保护的本地计算机资源（如程序文件目录和受保护）的权限。注册表，如本地计算机配置单元。</span><span class="sxs-lookup"><span data-stu-id="19bee-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="19bee-111">你还可以将设置权限委派给你不希望向其授予域管理员组成员身份的用户或组。</span><span class="sxs-lookup"><span data-stu-id="19bee-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="19bee-112">有关详细信息，请参阅部署文档中的<A href="lync-server-2013-granting-setup-permissions.md">在 Lync Server 2013 中授予设置权限</A>。</span><span class="sxs-lookup"><span data-stu-id="19bee-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bee-113">由 setup.exe 调用的<strong>.deploy</strong> -.deploy 负责为服务器角色部署软件组件的软件组件。</span><span class="sxs-lookup"><span data-stu-id="19bee-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="19bee-114">运行可执行文件的计算机上本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="19bee-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="19bee-115">"域用户" 组的成员以读取 AD DS 中的信息。</span><span class="sxs-lookup"><span data-stu-id="19bee-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="19bee-116">此级别的权限是必需的，因为本地计算机上必需的 MSI 程序包的自动安装需要允许读取和写入受保护的本地计算机资源（如程序文件目录和受保护）的权限。注册表，如本地计算机配置单元。</span><span class="sxs-lookup"><span data-stu-id="19bee-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="19bee-117">若要阅读中央管理存储，RtcUniversalReadOnlyAdmins 组中的成员身份是必需的。</span><span class="sxs-lookup"><span data-stu-id="19bee-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="19bee-118">如果您运行的是 Windows Vista 操作系统或 Windows 7 操作系统，系统将提示用户帐户控制（UAC）继续安装。</span><span class="sxs-lookup"><span data-stu-id="19bee-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="19bee-119">如果您使用标准用户帐户登录，则当系统提示您有权安装软件的帐户时，您将需要属于本地管理员组成员的人员才能提供凭据。</span><span class="sxs-lookup"><span data-stu-id="19bee-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bee-120">由 setup.exe 调用的<strong>setup.exe</strong>由 setup.exe 负责部署和配置服务器角色。</span><span class="sxs-lookup"><span data-stu-id="19bee-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="19bee-121">运行可执行文件的计算机上本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="19bee-121">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="19bee-122">RTCUniversalServerAdmins 组的成员以运行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="19bee-122">Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe.</span></span> <span data-ttu-id="19bee-123">"域用户" 组的成员以读取 AD DS 中的信息。</span><span class="sxs-lookup"><span data-stu-id="19bee-123">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="19bee-124">此级别的权限是必需的，因为本地计算机上必需的 MSI 程序包的自动安装需要允许读取和写入受保护的本地计算机资源（如程序文件目录和受保护）的权限。注册表，如本地计算机配置单元。</span><span class="sxs-lookup"><span data-stu-id="19bee-124">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bee-125"><strong>TopologyBuilder</strong> -由向导驱动的用户界面，用于创建、查看、调整和验证 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="19bee-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="19bee-126">运行可执行文件的计算机上本地管理员组的成员，以查看拓扑。</span><span class="sxs-lookup"><span data-stu-id="19bee-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="19bee-127">RTCUniversalServerAdmins 组的成员以更改配置设置。</span><span class="sxs-lookup"><span data-stu-id="19bee-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="19bee-128">RTCUniversalServerAdmins 组和域管理员组的成员或 RTCUniversalServerAdmins 组的成员（仅当该组已被授予委派设置权限时），才能发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="19bee-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="19bee-129">有关委派设置权限以允许 RTCUniversalServerAdmins 组的成员发布拓扑的详细信息，而不是域管理员组的成员，请参阅部署文档中<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的 "授予设置权限</a>"。</span><span class="sxs-lookup"><span data-stu-id="19bee-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bee-130"><strong>AdminUIHost</strong> –用于管理 Lync Server 2013 的基于 Web 的图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="19bee-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="19bee-131">分配了特定管理任务的其他基于角色的访问控制（RBAC）角色的 CsAdministrator 组或成员的成员。</span><span class="sxs-lookup"><span data-stu-id="19bee-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="19bee-132">Lync Server 2013 控制面板通过运行 Lync Server 2013 管理外壳 cmdlet 实现配置更改。</span><span class="sxs-lookup"><span data-stu-id="19bee-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="19bee-133">有关预定义角色和 cmdlet 成员的列表，请参阅规划文档中的在<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a>。</span><span class="sxs-lookup"><span data-stu-id="19bee-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bee-134"><strong>加载了 Lync server 2013 模块的 PowerShell</strong> -命令行管理工具，其 cmdlet 特定于管理 lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="19bee-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="19bee-135">已分配特定 cmdlet 的其他 RBAC 角色的 CsAdministrator 组成员或成员。</span><span class="sxs-lookup"><span data-stu-id="19bee-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="19bee-136">有关预定义角色和 cmdlet 成员的列表，请参阅规划文档中的在<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a>。</span><span class="sxs-lookup"><span data-stu-id="19bee-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="19bee-137">或者是以下一个或多个组的成员，具体取决于 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="19bee-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="19bee-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="19bee-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="19bee-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="19bee-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="19bee-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="19bee-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

