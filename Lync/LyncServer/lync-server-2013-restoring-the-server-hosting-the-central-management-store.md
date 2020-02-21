---
title: Lync Server 2013：还原承载中央管理存储的服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772646b8122e228aa43818aa5fe7fe2fb6689366
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>在 Lync Server 2013 中还原承载中央管理存储的服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

Lync Server 部署具有一个中央管理存储，该存储将复制到运行 Lync Server 服务器角色的每台服务器。 本主题介绍如何还原承载中央管理存储的后端服务器或 Standard Edition 服务器。

若要查找中央管理服务器所在的池，请打开拓扑生成器，单击 " **Lync Server**"，并在 "**中央管理服务器**" 下查找右侧窗格。

如果承载中央管理存储的后端服务器在镜像安装中，并且镜像数据库仍正常运行，我们建议您对此仍正常运行的镜像进行备份，然后在主数据库和服务器上执行完整还原。按照下面的还原步骤使用此备份镜像数据库。 这是必要的，因为后端还原需要修改和发布拓扑，并且只能在主数据库托管 CMS 运行时执行此操作。 另请注意，如果无法发布拓扑，主数据库角色和镜像数据库角色将无法互换。

<div>


> [!NOTE]  
> 如果未承载中央管理存储的后端服务器或 Standard Edition 服务器出现故障，请参阅<A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 lync server 2013 中还原企业版后端服务器</A>或<A href="lync-server-2013-restoring-a-standard-edition-server.md">在 lync Server 2013 中还原 Standard edition server</A>。 如果承载中央管理存储的后端服务器在镜像配置中，并且只有镜像失败，请参阅<A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013-镜像中还原镜像的企业版后端服务器</A>。 如果任何其他服务器发生故障，请参阅<A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync server 2013 中还原企业版成员服务器</A>。



</div>

<div>


> [!TIP]  
> 我们建议您先获取系统的图像副本，然后再开始还原。 您可以将此图像用作回滚点，以防还原过程中出现问题。 您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>还原中央管理存储

1.  从具有与故障计算机相同的完全限定域名（FQDN）的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照您组织的服务器部署过程来执行该步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组成员和本地 Administrators 组成员的用户帐户，登录到要还原的服务器。

3.  如果要还原 Standard Edition server，请通过将相应的文件存储从 $Backup 复制到服务器上的文件存储位置来还原文件存储，然后共享该文件夹。
    
    <div>
    

    > [!IMPORTANT]  
    > 已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。

    
    </div>

4.  执行下列操作之一：
    
      - 如果要安装 Standard Edition server，请浏览到 Lync Server 安装文件夹或媒体，然后启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。 在部署向导中，单击 "**准备第一个 Standard Edition server** "，然后按照向导安装中央管理存储。
    
      - 如果要安装企业后端服务器，请安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与故障前相同。
        
        <div>
        

        > [!NOTE]  
        > 根据要还原的服务器和部署，服务器可能包含多个并置或单独的数据库。 按照先前部署服务器时使用的过程来安装 SQL Server，包括 SQL Server 权限和登录名。

        
        </div>

5.  在前端服务器中，启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。

6.  重新创建中央管理存储。 在命令行中键入：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  为中央管理存储设置 Active Directory 域服务控制点。 在命令行中键入：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > 如果失去了连接点，可重新运行此 cmdlet。

    
    </div>

8.  从 $Backup 导入中央管理存储数据。 在命令行中键入：
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例如：
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  启用刚刚所做的更改。在命令行中键入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 启用拓扑后，可在数据库中找到拓扑文档。

    
    </div>

10. 如果要还原同时托管 CMS 的企业版后端服务器，或者如果需要重新创建 CMS 的镜像，请执行此步骤。 否则，请跳至步骤11。
    
    通过执行以下操作来安装独立数据库：
    
    1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
    2.  单击“从现有部署下载拓扑”****，然后单击“确定”****。
    
    3.  选择拓扑，然后单击“保存”****。单击“是”**** 确认您的选择。
    
    4.  右键单击 " **Lync Server 2013** " 节点，然后单击 "**安装数据库**"。
    
    5.  按照 "**安装数据库**" 向导操作。 如果要在此服务器上还原中央管理存储之外的数据库，请在 "**创建数据库**" 页上，选择要重新创建的数据库。
        
        <div>
        

        > [!NOTE]  
        > 只有独立数据库会显示在“创建数据库”<STRONG></STRONG>页上。 并置数据库是在运行 Lync Server 部署向导时创建的。

        
        </div>
    
    6.  如果要还原镜像后端服务器，请继续按照向导的其余部分操作，直到您进入创建镜像数据库的提示。 选择要安装的数据库，并完成此过程。
    
    7.  按照向导的其余部分操作，然后单击“完成”****。
    
    <div>
    

    > [!TIP]  
    > 除了运行拓扑生成器之外，您还可以使用<STRONG>CsDatabase</STRONG> cmdlet 来创建每个数据库，并使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 来配置镜像。 有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>。

    
    </div>

11. 如果要还原 Standard Edition server，请浏览到 Lync Server 安装文件夹或媒体，并启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。 使用 Lync Server 部署向导执行以下操作：
    
    1.  运行“步骤 1: 安装本地配置存储”**** 以安装本地配置文件。
    
    2.  运行**步骤2：安装或删除 Lync Server 组件**以安装 lync server 服务器角色。
    
    3.  运行“步骤 3: 请求、安装或分配证书”**** 以分配证书。
    
    4.  运行“步骤 4: 启动服务”**** 以在服务器上启动服务。
    
    有关运行部署向导的详细信息，请参阅部署文档以了解要还原的服务器角色。

12. 执行以下操作以还原用户数据：
    
    1.  将 ExportedUserData 从 $Backup\\复制到本地目录。
    
    2.  在还原用户数据之前，必须停止 Lync 服务。 为此，请键入：
        
            Stop-CsWindowsService
    
    3.  若要还原用户数据，请在命令行中键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  通过键入以下命令重新启动 Lync 服务：
        
            Start-CsWindowsService

13. 将位置信息数据还原到中央管理存储。 在命令行中键入：
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例如：
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. 如果已在此池或 Standard Edition server 上部署响应组，请还原响应组配置数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

15. 如果要还原包括存档或监控数据库的后端服务器，请使用 SQL Server 管理工具（如 SQL Server Management Studio）还原存档或监视数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原监视或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

