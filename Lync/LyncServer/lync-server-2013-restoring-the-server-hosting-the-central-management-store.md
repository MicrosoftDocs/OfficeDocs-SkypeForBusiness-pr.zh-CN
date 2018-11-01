---
title: 还原承载中央管理存储的服务器
TOCTitle: 还原承载中央管理存储的服务器
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202172(v=OCS.15)
ms:contentKeyID: 52060992
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原承载中央管理存储的服务器

 

_**上一次修改主题：** 2013-02-21_

Lync Server 部署具有一个中央管理存储，它的副本会复制到运行 Lync Server 服务器角色的每台服务器上。本主题介绍如何还原托管中央管理存储的后端服务器或 Standard Edition Server。

若要查找中央管理服务器所在的池，请打开拓扑生成器，单击“Lync Server”，然后查看右窗格中“中央管理服务器”下显示的信息。

如果托管中央管理存储的后端服务器处于镜像设置状态且镜像数据库仍然正常运行，则我们建议对此仍在正常运行的镜像进行备份，然后按照以下还原过程使用此备份在主数据库和镜像数据库上执行完整的还原。这是必需的要求，因为后端服务器还原需要修改和发布拓扑，只有在托管 CMS 的主数据库处于正常运行状态的情况下，才能完成此操作。另请注意，如果无法发布拓扑，则主数据库和镜像数据库角色就无法交换。

> [!NOTE]  
> 如果未托管中央管理存储的后端服务器或 Standard Edition Server 出现故障，请参阅<a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">还原 Enterprise Edition 后端服务器</a>或<a href="lync-server-2013-restoring-a-standard-edition-server.md">还原 Standard Edition Server</a>。如果托管中央管理存储的后端服务器处于镜像配置状态并且只有镜像出现故障，请参阅<a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">还原镜像企业版后端服务器 - 镜像</a>。如果任何其他服务器出现故障，请参阅<a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">还原 Enterprise Edition 成员服务器</a>。



> [!TIP]
> 建议在开始还原之前制作系统的映像副本。在还原过程中出现问题时您可将该映像作为回滚点。您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。


## 还原中央管理存储

1.  首先准备与出现故障的计算机具有相同完全限定域名 (FQDN) 的干净或新服务器，接着安装操作系统，然后还原或重新注册证书。
    
    > [!NOTE]  
	> 按照您组织的服务器部署过程来执行该步骤。
    


2.  使用具有 RTCUniversalServerAdmins 组和本地 Administrators 组成员身份的用户帐户登录到要还原的服务器。

3.  如果要还原 Standard Edition Server，请通过将相应文件存储从 $Backup 复制到服务器上的文件存储位置来还原文件存储，然后共享该文件夹。
    
    > [!IMPORTANT]
    > 还原的文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。


4.  执行以下操作之一：
    
      - 如果要安装 Standard Edition Server，请浏览到 Lync Server 安装文件夹或介质，并启动位于 \\setup\\amd64\\Setup.exe 中的 Lync Server 部署向导。在部署向导中，单击“准备第一个 Standard Edition Server”，并按照向导中的说明操作，以安装中央管理存储。
    
      - 如果要安装 Enterprise 后端服务器，请安装 SQL Server 2012 或 SQL Server 2008 R2，使实例名称与出现故障前相同。
        
        > [!NOTE]  
		> 根据您要还原的服务器和您的部署，服务器可能包含多个并置或独立数据库。按照先前部署服务器时使用的过程来安装 SQL Server，包括 SQL Server 权限和登录名。
        


5.  从前端服务器，启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

6.  重新创建中央管理存储。在命令行中键入：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  设置中央管理存储的 Active Directory 域服务 控制点。在命令行中键入：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    > [!NOTE]  
	> 如果失去了连接点，可重新运行此 cmdlet。
    


8.  导入 $Backup 中的中央管理存储数据。在命令行中键入：
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例如：
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  启用刚刚所做的更改。在命令行中键入：
    
        Enable-CsTopology
    
    > [!NOTE]  
	> 启用拓扑后，可在数据库中找到拓扑文档。
    


10. 如果您要还原同时托管有 CMS 的 企业版后端服务器，或者您需要重新创建 CMS 的镜像，请按照此步骤进行操作。否则，请跳到步骤 11。
    
    通过执行以下操作安装独立数据库：
    
    1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
    2.  单击“从现有部署下载拓扑”，然后单击“确定”。
    
    3.  选择拓扑，然后单击“保存”。单击“是”确认您的选择。
    
    4.  右键单击“Lync Server 2013”节点，然后单击“安装数据库”。
    
    5.  按照“安装数据库”向导操作。如果要还原的数据库不是该服务器上的中央管理存储，请在“创建数据库”页上，选择要重新创建的数据库。
        
        > [!NOTE]  
		> 只有独立数据库会显示在“创建数据库”页上。并置数据库在运行 Lync Server 部署向导时创建。
        
    
    6.  如果您要还原镜像后端服务器，请继续向导的剩余部分，直到您得到一条“创建镜像数据库”的提示消息。选择您要安装的数据库，并完成该过程。
    
    7.  按照向导的其余部分操作，然后单击“完成”。
    
    > [!TIP]
    > 可使用 <strong>Install-CsDatabase</strong> cmdlet 创建每个数据库以及使用 <strong>Install-CsMirrorDatabase</strong> cmdlet 配置镜像，而不是运行拓扑生成器。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</a>。


11. 如果要还原 Standard Edition Server，请浏览到 Lync Server 安装文件夹或介质，并启动位于 \\setup\\amd64\\Setup.exe 中的 Lync Server 部署向导。使用 Lync Server 部署向导执行以下操作：
    
    1.  运行“步骤 1: 安装本地配置存储”以安装本地配置文件。
    
    2.  运行“步骤 2: 安装或删除 Lync Server 组件”以安装 Lync Server 服务器角色。
    
    3.  运行“步骤 3: 请求、安装或分配证书”以分配证书。
    
    4.  运行“步骤 4: 启动服务”以在服务器上启动服务。
    
    有关运行部署向导的详细信息，请参阅适用于您要还原的服务器角色的部署文档。

12. 执行以下操作以还原用户数据：
    
    1.  将 ExportedUserData.zip 从 $Backup\\ 复制到本地目录。
    
    2.  在还原用户数据之前，您必须停止 Lync 服务。为此，请键入：
        
            Stop-CsWindowsService
    
    3.  若要还原用户数据，请在命令行中键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  通过键入以下内容重新启动 Lync 服务：
        
            Start-CsWindowsService

13. 将位置信息数据还原到中央管理存储。在命令行中键入：
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例如：
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. 如果在该池或 Standard Edition Server 上部署了响应组，请还原响应组配置数据。有关详细信息，请参阅[还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

15. 如果要还原的后端服务器包含存档或监控数据库，请使用 SQL Server 管理工具（如 SQL Server Management Studio）还原存档或监控数据。有关详细信息，请参阅[还原监控或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

