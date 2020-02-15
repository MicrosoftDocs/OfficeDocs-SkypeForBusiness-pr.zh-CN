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

# <a name="group-membership-requirements-for-lync-server-2013"></a>Lync Server 2013 的组成员身份要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

下表汇总了人员所属的组，以便成功安装、管理和排查 Lync Server 2013。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 可执行文件</th>
<th>所需的组成员身份</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe –启动</strong>安装 Lync Server 2013 管理工具的可执行文件。</p></td>
<td><p>运行可执行文件的计算机上本地 Administrators 组的成员。 "域用户" 组的成员，以读取 Active Directory 域服务中的信息。 需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</p>
<div>

> [!TIP]  
> 您还可以将安装权限委派给那些不会获得 Domain Admins 组成员身份的用户或组。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中授予安装程序权限</A>。


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> – deploy.exe 由 setup.exe 调用，负责为服务器角色部署软件组件。</p></td>
<td><p>运行可执行文件的计算机上本地 Administrators 组的成员。 用于读取 AD DS 中信息的 Domain Users 组的成员。 需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。 若要读取中央管理存储，RtcUniversalReadOnlyAdmins 组中的成员身份是必需的。</p>
<div>

> [!NOTE]  
> 如果运行的是 Windows Vista 操作系统或 Windows 7 操作系统，则系统会提示用户帐户控制（UAC）以继续安装。 如果使用标准用户帐户登录，那么在提示要求您提供具有软件安装权限的帐户时，就需要具有本地 Administrators 组成员身份的用户来提供凭据。


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> – bootstrapper.exe 由 setup.exe 调用，负责部署和配置服务器角色。</p></td>
<td><p>运行可执行文件的计算机上本地 Administrators 组的成员。运行 Bootstrapper.exe 的 RTCUniversalServerAdmins 组的成员。读取 AD DS 中的信息的 Domain Users 组的成员。需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> –用于创建、查看、调整和验证 Lync Server 2013 拓扑的向导驱动的用户界面。</p></td>
<td><p>能在运行可执行文件的计算机上查看拓扑的本地 Administrators 组成员。 能更改配置设置的 RTCUniversalServerAdmins 组成员。 能发布拓扑的 RTCUniversalServerAdmins 组和 Domain Admins 组成员或 RTCUniversalServerAdmins 组（仅限于该组已授予代理人安装权限的情况）成员。 有关委派安装程序权限以允许 RTCUniversalServerAdmins 组的成员在不是 Domain Admins 组成员的情况下发布拓扑的详细信息，请参阅部署文档中的在<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中授予安装程序权限</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> –用于管理 Lync Server 2013 的基于 Web 的图形用户界面。</p></td>
<td><p>CsAdministrator 组成员或其他已分配特定管理任务的基于角色的访问控制 (RBAC) 角色成员。 Lync Server 2013 "控制面板" 通过运行 Lync Server 2013 命令行管理程序 cmdlet 实现配置更改。 有关预定义角色和允许运行的 cmdlet 成员的列表，请参阅规划文档中的在<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>加载了 Lync server 2013 模块的 PowerShell</strong> –具有专用于管理 Lync Server 2013 的 cmdlet 的命令行管理工具。</p></td>
<td><p>CsAdministrator 组成员或其他已分配特定 cmdlet 的 RBAC 角色成员。 有关预定义角色和允许运行的 cmdlet 成员的列表，请参阅规划文档中的在<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</a>。</p>
<p>或下列一组或多组中的成员，具体情况取决于 cmdlet：</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

