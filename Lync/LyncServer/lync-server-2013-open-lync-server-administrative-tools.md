---
title: 打开 Lync Server 管理工具
TOCTitle: 打开 Lync Server 管理工具
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg195741(v=OCS.15)
ms:contentKeyID: 49313528
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 打开 Lync Server 管理工具

 

_**上一次修改主题：** 2012-06-28_

可以使用本主题中的过程来打开管理工具，以便部署、配置 Lync Server 2013 拓扑或对其进行疑难解答。

  - 部署向导

  - 拓扑生成器

  - Lync Server 控制面板

  - Lync Server 命令行管理程序

## 部署向导

可使用下面的过程本地启动部署向导来添加或删除 Lync Server 2013 组件文件。

## 启动 Lync Server 2013 部署向导

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了 Lync Server 部署向导的计算机。

2.  依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 部署向导”。

## 拓扑生成器

可使用下面的过程打开拓扑生成器以定义要在 Lync Server 2013 拓扑中部署的服务器。

## 打开 Lync Server 2013 拓扑生成器以设计拓扑

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
    > [!NOTE]  
	> 可以使用作为本地用户组成员的帐户来定义拓扑，但若要读取、发布或启用拓扑（这是在服务器上安装 Lync Server 2013 所必需的），您必须使用作为 Domain Admins 组和 RTCUniversalServerAdmins 组的成员的帐户（此类帐户应在要用于存档文件存储的文件共享上具有完全控制权限，即读取、写入和修改权限，以使拓扑生成器可以配置所需的随机访问控制列表 (DACL)），或具有同等用户权限的帐户。
    


2.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

## Lync Server 2013 控制面板

可以使用下面的过程打开 Lync Server 2013 控制面板以管理环境中服务器、用户、客户端和设备的配置。

> [!NOTE]  
> 可以使用分配给 CsAdministrator 角色的用户帐户来执行 Lync Server 2013 控制面板中的任何任务。可使用其他角色登录 Lync Server 2013 控制面板来执行特定的管理任务，具体取决于需执行的任务。例如，可使用 CSArchivingAdministrator 管理 Lync Server 2013 控制面板中的存档。有关角色的详细信息，请参阅规划文档中的<a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。有关可用于执行某项特定任务的角色的详细信息，请参阅该任务的文档。



## 从组织防火墙内的任何计算机中打开 Lync Server 2013 控制面板

1.  使用分配给 CsAdministrator 角色或其他角色，并且具有与要执行的任务对应的用户权限的用户帐户，登录到内部部署中最低屏幕分辨率为 1024 x 768 的任何计算机。
    
    > [!IMPORTANT]
    > 如果已配置管理简单统一资源定位器 (URL)，则可通过在组织防火墙内的计算机上运行的 Internet 浏览器访问 Lync Server 2013 控制面板。有关配置管理简单 URL 的详细信息，请参阅规划文档中的<a href="lync-server-2013-planning-for-simple-urls.md">在 Lync Server 2013 中规划简单 URL</a> 和部署文档中的<a href="lync-server-2013-edit-or-configure-simple-urls.md">在 Lync Server 2013 中编辑或配置简单 URL</a>。


2.  打开浏览器窗口，然后输入为组织配置的管理 URL。

## 在运行 Lync Server 2013 的计算机上打开 Lync Server 2013 控制面板

1.  使用作为 CsAdministrator 角色或其他角色的成员，并且具有与要执行的任务对应的用户权限的用户帐户，登录到安装了 Lync Server 2013 或至少安装了 Lync Server 2013 管理工具的计算机。若要配置设置，计算机的最低屏幕分辨率必须为 1024 x 768。

2.  启动 Lync Server 2013 控制面板：单击“开始”、再单击“所有程序”，指向“管理工具”、再指向“Microsoft Lync Server 2013”，然后单击“Lync Server 2013 控制面板”。

## Lync Server 2013 命令行管理程序

可使用下面的过程打开 Lync Server 2013 命令行管理程序，以通过使用命令行来管理环境中的服务器、用户、客户端和设备。

> [!NOTE]  
> 可以使用分配给 CsAdministrator 角色的用户帐户来执行 Lync Server 2013 命令行管理程序中的任何任务。可使用其他角色登录以执行特定的管理任务，具体取决于需执行的任务。例如，可以使用 CSArchivingAdministrator 运行与存档管理相关的 cmdlet。有关角色的详细信息，请参阅规划文档中的<a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。有关可用于运行某个特定 cmdlet 的角色的详细信息，请参阅该 cmdlet 的文档。<br />
还可以使用 RTCUniversalServerAdmins 组、RTCUniversalUserAdmins 组或 RTCUniversalReadOnlyAdmins 组中的用户帐户来运行某些 cmdlet，具体取决于该 cmdlet。



## 打开 Lync Server 2013 命令行管理程序

  - 如果您打开 Windows PowerShell 窗口而非 Lync Server 2013 命令行管理程序，则默认情况下，您无法运行 Lync Server 2013 cmdlet。若要从 Windows PowerShell 中运行 Lync Server 2013 cmdlet，请在 Windows PowerShell 命令提示符处键入：
    
    `Import-Module Lync`

  - 启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

## 另请参阅

#### 任务

[安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)  

#### 概念

[Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)

