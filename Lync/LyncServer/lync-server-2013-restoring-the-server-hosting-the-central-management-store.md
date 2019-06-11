---
title: 'Lync Server 2013: 还原托管中央管理存储的服务器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>在 Lync Server 2013 中还原托管中央管理存储的服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

Lync 服务器部署具有单个中央管理存储, 其副本将复制到运行 Lync Server 服务器角色的每台服务器。 本主题介绍如何还原托管中央管理存储的后端服务器或标准版服务器。

若要查找中央管理服务器所在的池, 请打开拓扑生成器, 单击 " **Lync Server**", 然后在右窗格中的 "**中央管理服务器**" 下查找。

如果托管中央管理存储的后端服务器位于镜像设置中, 并且镜像数据库仍正常运行, 我们建议你备份此仍运行的镜像, 然后在主数据库和数据库上执行完整还原。通过执行以下还原过程, 使用此备份镜像数据库。 这是必需的, 因为后端还原需要修改和发布拓扑, 并且只能在托管 CMS 的主数据库运行时执行此操作。 另请注意, 如果无法发布拓扑, 则无法交换主数据库角色和镜像数据库角色。

<div>


> [!NOTE]  
> 如果未托管中央管理存储的后端服务器或标准版服务器已失败, 请参阅<A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync server 2013 中还原企业版后端服务器</A>或<A href="lync-server-2013-restoring-a-standard-edition-server.md">在 lync Server 2013 中还原标准版服务器</A>。 如果托管中央管理存储的后端服务器位于镜像配置中且只有镜像失败, 请参阅<A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync server 2013-镜像中还原镜像的企业版后端服务器</A>。 如果任何其他服务器出现故障, 请参阅<A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync server 2013 中还原企业版成员服务器</A>。



</div>

<div>


> [!TIP]  
> 我们建议你先拍摄系统的映像副本, 然后再开始还原。 你可以将此映像用作回退点, 以防在还原过程中出现问题。 您可能希望在安装操作系统和 SQL Server 后获取图像副本, 并还原或重新注册证书。



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>还原中央管理存储

1.  从具有与故障计算机相同的完全限定的域名 (FQDN) 的全新或新服务器开始, 安装操作系统, 然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照组织的服务器部署过程执行此步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组和本地管理员组成员的用户帐户, 登录到要还原的服务器。

3.  如果要还原标准版服务器, 请还原文件存储, 方法是将相应的文件存储从 $Backup 复制到服务器上的文件存储位置, 然后共享该文件夹。
    
    <div>
    

    > [!IMPORTANT]  
    > 已还原文件存储的路径和文件名应与备份的文件存储完全相同, 以便使用这些文件的组件可以访问它们。

    
    </div>

4.  请执行下列操作之一：
    
      - 如果要安装标准版服务器, 请通过浏览找到 Lync Server 安装文件夹或媒体, 然后启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。 在部署向导中, 单击 "**准备第一个标准版服务器**", 然后按照向导安装中央管理存储。
    
      - 如果要安装企业后端服务器, 请安装 SQL Server 2012 或 SQL Server 2008 R2, 使实例名称保持与失败之前相同。
        
        <div>
        

        > [!NOTE]  
        > 服务器可能包含多个 collocated 或单独的数据库, 具体取决于你要还原的服务器和你的部署。 按照相同的步骤安装最初用于部署服务器的 SQL Server, 包括 SQL Server 权限和登录。

        
        </div>

5.  从前端服务器, 启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft lync server 2013**", 然后单击 " **Lync server Management Shell**"。

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
    > 如果您丢失了连接点, 则可以重新运行此 cmdlet。

    
    </div>

8.  从 $Backup 导入中央管理存储数据。 在命令行中键入：
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例如：
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  启用刚进行的更改。 在命令行中键入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 启用拓扑后, 您可以在数据库中找到拓扑文档。

    
    </div>

10. 如果您要还原同时托管 CMS 的企业版后端服务器, 或者需要重新创建 CMS 的镜像, 请执行此步骤。 否则, 请跳到步骤11。
    
    通过执行下列操作来安装独立数据库:
    
    1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。
    
    2.  单击 "**从现有部署下载拓扑**", 然后单击 **"确定"**。
    
    3.  选择拓扑, 然后单击 "**保存**"。 单击 **"是"** 以确认您的选择。
    
    4.  右键单击 " **Lync Server 2013** " 节点, 然后单击 "**安装数据库**"。
    
    5.  按照**安装数据库**向导操作。 如果你要还原的数据库不是此服务器上的中央管理存储, 请在 "**创建数据库**" 页面上, 选择要重新创建的数据库。
        
        <div>
        

        > [!NOTE]  
        > "<STRONG>创建数据库</STRONG>" 页面上仅显示独立数据库。 Collocated 数据库是在运行 Lync Server 部署向导时创建的。

        
        </div>
    
    6.  如果你要还原镜像后端服务器, 请继续按照向导的其余部分操作, 直到你转到创建镜像数据库的提示。 选择要安装的数据库, 然后完成此过程。
    
    7.  按照向导的其余部分, 然后单击 "**完成**"。
    
    <div>
    

    > [!TIP]  
    > 你可以使用<STRONG>CsDatabase</STRONG> cmdlet 创建每个数据库, 使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 来配置镜像, 而不是运行拓扑生成器。 有关详细信息, 请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">安装 CsDatabase</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">安装 CsMirrorDatabase</A>。

    
    </div>

11. 如果要还原标准版服务器, 请浏览到 Lync Server 安装文件夹或媒体, 然后启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。 使用 Lync Server 部署向导执行下列操作:
    
    1.  运行**步骤 1: 安装本地配置存储**以安装本地配置文件。
    
    2.  运行**步骤 2: 设置或删除 Lync Server 组件**以安装 lync server 服务器角色。
    
    3.  运行**步骤 3: 请求、安装或分配证书**以分配证书。
    
    4.  运行**步骤 4: 启动服务**以启动服务器上的服务。
    
    有关运行部署向导的详细信息, 请参阅要还原的服务器角色的部署文档。

12. 通过执行下列操作还原用户数据:
    
    1.  将 ExportedUserData 从 $Backup\\复制到本地目录。
    
    2.  还原用户数据之前, 必须停止 Lync 服务。 若要执行此操作, 请键入:
        
            Stop-CsWindowsService
    
    3.  若要还原用户数据, 请在命令行键入:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  通过键入以下内容重启 Lync 服务:
        
            Start-CsWindowsService

13. 将位置信息数据还原到中央管理存储。 在命令行中键入：
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例如：
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. 如果你已在此池或标准版服务器上部署了响应组, 请还原响应组配置数据。 有关详细信息, 请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

15. 如果要还原包括存档或监视数据库的后端服务器, 请使用 SQL Server 管理工具 (如 SQL Server Management Studio) 还原存档或监视数据。 有关详细信息, 请参阅[在 Lync Server 2013 中还原监视或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

