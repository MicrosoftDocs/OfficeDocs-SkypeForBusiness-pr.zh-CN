---
title: Lync Server 2013：组成员身份要求
TOCTitle: 组成员身份要求
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204623(v=OCS.15)
ms:contentKeyID: 49311808
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的组成员身份要求

 

_**上一次修改主题：** 2015-03-09_

下表概述了相关人员成功地进行 Lync Server 2013 安装、管理和故障排除操作所需的组成员身份。


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
<td><p><strong>Setup.exe</strong> – 用于启动 Lync Server 2013 管理工具安装的可执行文件。</p></td>
<td><p>运行可执行文件的计算机上本地 Administrators 组的成员。用于读取 Active Directory 域服务 中信息的 Domain Users 组的成员。需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</p>
<div>

> [!TIP]
> 您还可以将安装权限委派给那些不会获得 Domain Admins 组成员身份的用户或组。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-granting-setup-permissions.md">在 Lync Server 2013 中授予安装权限</a>。

</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> – deploy.exe 由 setup.exe 调用，负责为服务器角色部署软件组件。</p></td>
<td><p>运行可执行文件的计算机上本地 Administrators 组的成员。用于读取 AD DS 中信息的 Domain Users 组的成员。需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。需要具有 RtcUniversalReadOnlyAdmins 组中的成员身份才能读取 中央管理存储。</p>
<div>

> [!NOTE]  
> 如果您运行的是 Windows Vista 操作系统或 Windows 7 操作系统，那么用户帐户控制 (UAC) 就会提示您继续安装。如果使用标准用户帐户登录，那么在提示要求您提供具有软件安装权限的帐户时，就需要具有本地 Administrators 组成员身份的用户来提供凭据。


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> – bootstrapper.exe 由 setup.exe 调用，负责部署和配置服务器角色。</p></td>
<td><p>运行可执行文件的计算机上本地 Administrators 组的成员。运行 Bootstrapper.exe 的 RTCUniversalServerAdmins 组的成员。读取 AD DS 中的信息的 Domain Users 组的成员。需要该级别的权限是因为，在本地计算机上自动安装所需的 MSI 软件包需要允许读取和写入受保护的本地计算机资源（如 Program Files 目录）和受保护注册表（如 Local Machine 配置单元）的权限。</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – 负责提供用于创建、查看、调整和验证 Lync Server 2013 拓扑的向导式用户界面。</p></td>
<td><p>能在运行可执行文件的计算机上查看拓扑的本地 Administrators 组成员。能更改配置设置的 RTCUniversalServerAdmins 组成员。能发布拓扑的 RTCUniversalServerAdmins 组和 Domain Admins 组成员或 RTCUniversalServerAdmins 组（仅限于该组已授予代理人安装权限的情况）成员。有关如何通过委派安装权限使 RTCUniversalServerAdmins 组成员在不具备 Domain Admins 组成员身份的情况下可以发布拓扑的详细信息，请参阅部署文档中的 <a href="lync-server-2013-granting-setup-permissions.md">在 Lync Server 2013 中授予安装权限</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> – 负责提供管理 Lync Server 2013 的基于 Web 的图形用户界面。</p></td>
<td><p>CsAdministrator 组成员或其他已分配特定管理任务的基于角色的访问控制 (RBAC) 角色成员。 Lync Server 2013 控制面板会通过运行 Lync Server 2013 命令行管理程序 cmdlet 实现配置更改。有关允许运行的预定义角色和 cmdlet 成员的列表，请参阅规划文档中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>加载 Lync Server 2013 模块的 PowerShell.exe</strong> – 负责提供具有 Lync Server 2013 管理专用 cmdlet 的命令行管理工具。</p></td>
<td><p>CsAdministrator 组成员或其他已分配特定 cmdlet 的 RBAC 角色成员。有关允许运行的预定义角色和 cmdlet 成员的列表，请参阅规划文档中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。</p>
<p>或下列一组或多组中的成员，具体情况取决于 cmdlet：</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>

