---
title: 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-25_

从 Lync Server 2010 迁移到 Lync Server 2013 后，您需要将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013 前端服务器或池，然后才能删除旧版 Lync Server 2010 服务器。

中央管理服务器是单个主/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在安装期间，在计算机上安装了 SQL Server 数据库中的中央管理存储数据的只读副本（默认情况下称为 RTCLOCAL）。部署. 本地数据库通过在所有计算机上作为服务运行的 Lync Server 副本复制程序代理来接收副本更新。 中央管理服务器和本地副本上的实际数据库的名称是 XDS，它由 XDS 和 XDS 文件组成。 Master 数据库位置由 Active Directory 域服务中的服务控制点（SCP）引用。 使用 "中央管理" 服务器管理和配置 Lync 服务器的所有工具均使用 SCP 查找中央管理存储。

成功移动中央管理服务器后，应从原始前端服务器中删除中央管理服务器数据库。 有关删除中央管理服务器数据库的信息，请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。

在 Lync Server Management Shell 中使用 Windows PowerShell cmdlet **Move CsManagementServer** ，将数据库从 lync SERVER 2010 sql server 数据库移动到 lync SERVER 2013 sql server 数据库，然后更新 SCP 以指向 lync Server 2013 中央管理服务器位置。

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>在移动中央管理服务器之前准备 Lync Server 2013 前端服务器

在移动 Lync Server 2010 中央管理服务器之前，请使用本部分中的步骤准备 Lync Server 2013 前端服务器。

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>准备企业版前端池

1.  在要重定位中央管理服务器的 Lync Server 2013 企业版前端池上：登录到安装了 Lync Server 管理外壳的计算机作为**RTCUniversalServerAdmins**组的成员。 你还必须在要安装中央管理存储的数据库上同时拥有 SQL Server 数据库 sysadmin 用户权限和权限。

2.  打开 Lync Server 命令行管理程序。

3.  若要在 Lync Server 2013 SQL Server 数据库中创建新的中央管理存储，请在 Lync Server 命令行管理程序中键入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  确认**Lync Server 前端**服务的状态为 "已**启动**"。

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>准备标准版前端服务器

1.  在要重定位中央管理服务器的 Lync Server 2013 标准版前端服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。

2.  打开 Lync Server 部署向导。

3.  在 Lync Server 部署向导中，单击 "**准备第一个标准版服务器**"。

4.  在 "**执行命令**" 页面上，将 SQL Server Express 作为中央管理服务器进行安装。 已创建必要的防火墙规则。 当数据库和必备软件的安装完成后，单击 "**完成**"。
    
    <div>
    

    > [!NOTE]  
    > 初始安装可能需要一些时间，但不显示命令输出摘要屏幕的更新。 这是由于 SQL Server Express 的安装所致。 如果需要监视数据库的安装，请使用 "任务管理器" 监视设置。

    
    </div>

5.  若要在 Lync Server 2013 标准版前端服务器上创建新的中心管理存储，请在 Lync Server 命令行管理程序中键入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  确认**Lync Server 前端**服务的状态为 "已**启动**"。

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013

1.  在将成为中央管理服务器的 Lync Server 2013 服务器上：登录到安装了 Lync Server Management Shell 的计算机作为**RTCUniversalServerAdmins**组的成员。 您还必须拥有 SQL Server 数据库管理员用户的权限。

2.  打开 Lync Server 命令行管理程序。

3.  在 Lync Server 命令行管理器中，键入：
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 如果<CODE>Enable-CsTopology</CODE>未成功，请解决阻止命令完成的问题，然后再继续。 如果<STRONG>Enable-CsTopology</STRONG>未成功，则移动将失败，并且可能会将拓扑置于没有中央管理存储的状态。

    
    </div>

4.  在 Lync Server 2013 前端服务器或前端池的 Lync Server 命令行管理程序中，键入：
    
        Move-CsManagementServer

5.  Lync Server Management Shell 显示当前状态和建议状态的服务器、文件存储、数据库存储和服务连接点。 请仔细阅读信息，确认这是预期的源和目标。 键入**Y**继续，或按**N**停止移动。

6.  查看由**CsManagementServer**命令生成并解决的任何警告或错误。

7.  在 Lync Server 2013 服务器上，打开 "Lync Server 部署向导"。

8.  在 Lync Server 部署向导中，单击 "**安装或更新 Lync Server 系统**"，单击 "**步骤2：设置" 或 "删除 Lync server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。

9.  在 Lync Server 2010 服务器上，打开 "Lync Server 部署向导"。

10. 在 Lync Server 部署向导中，单击 "**安装或更新 Lync Server 系统**"，单击 "**步骤2：设置" 或 "删除 Lync server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。

11. 重新启动 Lync Server 2013 服务器。 这是必需的，因为访问中央管理服务器数据库的组成员身份发生更改。

12. 若要确认与新的中央管理存储进行复制，请在 Lync Server 命令行管理程序中键入：
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > 复制可能需要一些时间来更新所有当前副本。

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>移动后删除 Lync Server 2010 中央管理存储文件

1.  在 Lync Server 2010 服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。 您还必须拥有 SQL Server 数据库管理员用户的权限。

2.  打开 Lync Server 命令行管理程序
    
    <div>
    

    > [!WARNING]  
    > 在复制完成且稳定之前，不要继续删除以前的数据库文件。 如果在完成复制之前删除文件，将中断复制过程，并使新移动的中央管理服务器处于未知状态。 使用 cmdlet <STRONG>CsManagementStoreReplicationStatus</STRONG>确认复制状态。

    
    </div>

3.  若要从 Lync Server 2010 中央管理服务器删除中央管理存储数据库文件，请键入：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    例如：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    SQL Server \<\>的 FQDN 是企业版部署中的 Lync Server 2010 后端服务器或标准版服务器的 fqdn。

</div>

</div>

<span> </span>

</div>

</div>

</div>

