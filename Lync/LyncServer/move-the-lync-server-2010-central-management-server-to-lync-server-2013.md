---
title: 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013
TOCTitle: 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49888353
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Server 2010 中央管理服务器移动到 Lync Server 2013

 

_**上一次修改主题：** 2013-11-25_

在从 Lync Server 2010 迁移到 Lync Server 2013 后，您需要将 Lync Server 2010中央管理服务器移动到 Lync Server 2013前端服务器或池中，然后才能移除旧 Lync Server 2010 服务器。

中央管理服务器是由一个主数据库和多个副本组成的系统，其中，数据库的读/写副本由包含 中央管理服务器的 前端服务器保存。拓扑中的每台计算机（包括包含 中央管理服务器的 前端服务器）都具有在安装和部署期间安装在该计算机上的 SQL Server 数据库中 中央管理存储数据的一个只读副本（默认情况下名为 RTCLOCAL）。本地数据库通过作为服务在所有计算机上运行的 Lync Server 副本复制程序代理接收副本更新。 中央管理服务器上的实际数据库和本地副本的名称是 XDS，它由 xds.mdf 和 xds.ldf 文件组成。主数据库位置由 Active Directory 域服务 中的服务控制点 (SCP) 引用。使用 中央管理服务器管理和配置 Lync Server 的所有工具都使用 SCP 查找 中央管理存储。

在成功移动 中央管理服务器后，您应该从原始 前端服务器中移除 中央管理服务器数据库。有关移除 中央管理服务器数据库的信息，请参阅 [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。

在 Lync Server 命令行管理程序中使用 Windows PowerShell cmdlet **Move-CsManagementServer** 将数据库从 Lync Server 2010 SQL Server 数据库移动到 Lync Server 2013 SQL Server 数据库，然后更新 SCP 以指向 Lync Server 2013中央管理服务器位置。

## 在移动 中央管理服务器之前准备 Lync Server 2013前端服务器

使用本节中的过程可在移动 Lync Server 2010中央管理服务器之前准备 Lync Server 2013前端服务器。

## 准备 Enterprise Edition 前端池

1.  在要重定位 中央管理服务器的 Lync Server 2013 Enterprise Edition 前端池中：以 **RTCUniversalServerAdmins** 组的成员身份登录到安装了 Lync Server 命令行管理程序的计算机。您还必须对要在其中安装 中央管理存储的数据库具有 SQL Server 数据库 sysadmin 用户权限。

2.  打开 Lync Server 命令行管理程序。

3.  若要在 Lync Server 2013 SQL Server 数据库中创建新的 中央管理存储，请在 Lync Server 命令行管理程序中键入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  确认“Lync Server 前端”服务的状态为“已启动”。

## 准备 Standard Edition 前端服务器

1.  在要重定位 中央管理服务器的 Lync Server 2013 Standard Edition 前端服务器上：以 **RTCUniversalServerAdmins** 组的成员身份登录到安装了 Lync Server 命令行管理程序的计算机。

2.  打开 Lync Server 部署向导。

3.  在 Lync Server 部署向导中，单击“准备第一个 Standard Edition Server”。

4.  在“正在执行命令”页上，将 SQL Server Express 作为中央管理服务器进行安装。创建必需的防火墙规则。安装数据库和必备软件后，单击“完成”。
    
    > [!NOTE]
    > 初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。这是由 SQL Server Express 安装所导致的。如果需要监视数据库安装，请使用任务管理器监视安装过程。


5.  若要在 Lync Server 2013 Standard Edition 前端服务器上创建新的 中央管理存储，请在 Lync Server 命令行管理程序中键入：
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  确认“Lync Server 前端”服务的状态为“已启动”。

## 将 Lync Server 2010中央管理服务器移动到 Lync Server 2013

1.  在将成为 中央管理服务器的 Lync Server 2013 服务器上：以 **RTCUniversalServerAdmins** 组的成员身份登录到安装了 Lync Server 命令行管理程序的计算机。您还必须具有 SQL Server 数据库管理员用户权限。

2.  打开 Lync Server 命令行管理程序。

3.  在 Lync Server 命令行管理程序中，键入：
    
        Enable-CsTopology
    
    > [!WARNING]
    > 如果 <code>Enable-CsTopology</code> 未成功，请首先解决妨碍该命令完成的问题，然后再继续。如果 <strong>Enable-CsTopology</strong> 未成功，移动将失败，这可能会使拓扑处于无 中央管理存储的状态。


4.  在 Lync Server 2013前端服务器或 前端池中，在 Lync Server 命令行管理程序中键入：
    
        Move-CsManagementServer

5.  Lync Server 命令行管理程序显示“当前状态”和“建议状态”的服务器、文件存储、数据库存储和服务连接点。请仔细查看这些信息，确认这是预期的源和目标。键入 **Y** 继续，或键入 **N** 停止移动。

6.  查看 **Move-CsManagementServer** 命令生成的所有警告或错误，并解决它们。

7.  在 Lync Server 2013 服务器上，打开 Lync Server 部署向导。

8.  在 Lync Server 部署向导中，依次单击“安装或更新 Lync Server 系统”、“步骤 2: 安装或删除 Lync Server 组件”和“下一步”，然后查看摘要并单击“完成”。

9.  在 Lync Server 2010 服务器上，打开 Lync Server 部署向导。

10. 在 Lync Server 部署向导中，依次单击“安装或更新 Lync Server 系统”、“步骤 2: 安装或删除 Lync Server 组件”和“下一步”，然后查看摘要并单击“完成”。

11. 重新启动 Lync Server 2013 服务器。由于组成员身份更改，这是访问 中央管理服务器 数据库所必需的。

12. 若要确认新 中央管理存储正在进行复制，请在 Lync Server 命令行管理程序中，键入：
    
        Get-CsManagementStoreReplicationStatus
    
    > [!NOTE]
    > 复制可能需要一段时间来更新当前所有副本。


## 在移动后移除 Lync Server 2010中央管理存储文件

1.  在 Lync Server 2010 服务器上：以 **RTCUniversalServerAdmins** 组的成员身份登录到安装了 Lync Server 命令行管理程序的计算机。您还必须具有 SQL Server 数据库管理员用户权限。

2.  打开 Lync Server 命令行管理程序
    
    > [!WARNING]
    > 在复制完成和系统稳定之前，不要继续删除以前的数据库文件。如果在完成复制之前删除这些文件，将会中断复制过程并导致新移动的 中央管理服务器处于未知状态。可使用 cmdlet <strong>Get-CsManagementStoreReplicationStatus</strong> 确认复制状态。


3.  若要从 Lync Server 2010中央管理服务器中移除 中央管理存储数据库文件，请键入：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    例如：
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    其中，*\<FQDN of SQL Server\>* 是 Enterprise Edition 部署中的 Lync Server 2010 后端服务器或 Standard Edition 服务器的 FQDN。

