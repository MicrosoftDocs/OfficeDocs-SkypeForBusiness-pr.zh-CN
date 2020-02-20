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
ms.openlocfilehash: 0b344ff2fb9fb4ed123d864e219f64d9c1f04202
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-25_

从 Lync Server 2010 迁移到 Lync Server 2013 之后，您需要将 Lync Server 2010 中心管理服务器移动到 Lync Server 2013 前端服务器或池，然后才能删除旧版 Lync Server 2010 服务器。

中央管理服务器是单个主/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在安装过程中安装在计算机上的 SQL Server 数据库中的中央管理存储数据的只读副本（默认情况下称为 "RTCLOCAL"）。部署. 本地数据库通过作为所有计算机上的服务运行的 Lync Server 副本复制器代理来接收副本更新。 中央管理服务器和本地副本上的实际数据库的名称为 XDS，它由 XDS 和 XDS 文件组成。 主数据库位置由 Active Directory 域服务中的服务控制点（SCP）引用。 使用中央管理服务器来管理和配置 Lync Server 的所有工具都使用 SCP 查找中央管理存储。

成功移动中央管理服务器后，应从原始前端服务器中删除中央管理服务器数据库。 有关删除中央管理服务器数据库的信息，请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。

在 Lync Server 命令行管理**程序**中使用 Windows PowerShell cmdlet move-csmanagementserver 在 Lync Server 命令行管理程序中，将数据库从 lync SERVER 2010 sql server 数据库移动到 lync SERVER 2013 sql server 数据库，然后将 SCP 更新为指向 lync Server 2013 中央管理服务器位置。

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>在移动中央管理服务器之前准备 Lync Server 2013 前端服务器

使用本节中的过程准备 Lync Server 2013 前端服务器，然后再移动 Lync Server 2010 中央管理服务器。

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>准备企业版前端池

1.  在要重定位中央管理服务器的 Lync Server 2013 Enterprise Edition 前端池上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。 此外，还必须在要安装中央管理存储的数据库上具有 SQL Server 数据库 sysadmin 用户权限和权限。

2.  打开 Lync Server 命令行管理程序。

3.  若要在 Lync Server 2013 SQL Server 数据库中创建新的中央管理存储，请在 Lync Server 命令行管理程序中键入以下内容：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  确认“Lync Server 前端”**** 服务的状态为“已启动”****。

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>准备标准版前端服务器

1.  在要重新定位中央管理服务器的 Lync Server 2013 Standard Edition 前端服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。

2.  打开“Lync Server 部署向导”。

3.  在 "Lync Server 部署向导" 中，单击 "**准备第一个 Standard Edition Server**"。

4.  在 "**正在执行命令**" 页上，SQL Server Express 安装为中央管理服务器。 创建必需的防火墙规则。 安装数据库和必备软件后，单击“完成”****。
    
    <div>
    

    > [!NOTE]  
    > 初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。 这是因为安装了 SQL Server Express。 如果需要监视数据库安装，请使用任务管理器监视安装过程。

    
    </div>

5.  若要在 Lync Server 2013 Standard Edition 前端服务器上创建新的中央管理存储，请在 Lync Server 命令行管理程序中键入以下内容：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  确认“Lync Server 前端”**** 服务的状态为“已启动”****。

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013

1.  在将成为中央管理服务器的 Lync Server 2013 服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。 您还必须具有 SQL Server 数据库管理员用户权限。

2.  打开 Lync Server 命令行管理程序。

3.  在 Lync Server 命令行管理程序中，键入：
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 如果<CODE>Enable-CsTopology</CODE>未成功，请先解决阻止命令完成的问题，然后再继续。 如果<STRONG>enable-cstopology</STRONG>不成功，移动将会失败，并且可能会使拓扑处于没有中央管理存储的状态。

    
    </div>

4.  在 lync Server 2013 前端服务器或前端池上的 Lync Server 命令行管理程序中，键入：
    
        Move-CsManagementServer

5.  Lync Server 命令行管理程序显示服务器、文件存储、数据库存储以及当前状态和建议状态的服务连接点。 请仔细查看这些信息，确认这是预期的源和目标。 键入 **Y** 继续，或键入 **N** 停止移动。

6.  查看 **Move-CsManagementServer** 命令生成的所有警告或错误，并解决它们。

7.  在 Lync Server 2013 服务器上，打开 "Lync Server 部署向导"。

8.  在 "Lync Server 部署向导" 中，依次单击 "**安装或更新 Lync Server 系统**"、"**步骤2：设置" 或 "删除 Lync server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。

9.  在 Lync Server 2010 服务器上，打开 "Lync Server 部署向导"。

10. 在 "Lync Server 部署向导" 中，依次单击 "**安装或更新 Lync Server 系统**"、"**步骤2：设置" 或 "删除 Lync server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。

11. 重新启动 Lync Server 2013 服务器。 这是必需的，因为对 access 中央管理服务器数据库进行组成员资格更改。

12. 若要确认具有新的中央管理存储的复制正在发生，请在 Lync Server 命令行管理程序中键入以下内容：
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > 复制可能需要一段时间来更新当前所有副本。

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>移动后删除 Lync Server 2010 中央管理存储文件

1.  在 Lync Server 2010 服务器上：登录到安装了 Lync Server 命令行管理程序的计算机作为**RTCUniversalServerAdmins**组的成员。 您还必须具有 SQL Server 数据库管理员用户权限。

2.  打开 Lync Server 命令行管理程序
    
    <div>
    

    > [!WARNING]  
    > 在复制完成和系统稳定之前，不要继续删除以前的数据库文件。 如果在完成复制之前删除了文件，则会中断复制过程，并使新移动的中央管理服务器处于未知状态。 可使用 cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> 确认复制状态。

    
    </div>

3.  若要从 Lync Server 2010 中央管理服务器中删除中央管理存储数据库文件，请键入：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    例如：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    其中， \<SQL Server\>的 FQDN 是企业版部署中的 Lync Server 2010 后端服务器或 STANDARD edition 服务器的 fqdn。

</div>

</div>

<span> </span>

</div>

</div>

</div>

