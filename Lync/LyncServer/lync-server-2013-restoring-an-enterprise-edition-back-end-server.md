---
title: Lync Server 2013：还原企业版后端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429bf681e157beece170b9fe10e64fa8dea749ef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中还原企业版后端服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-18_

在以下两种情况下，请使用本主题中介绍的过程：

  - 镜像企业版后端服务器的主数据库和镜像数据库都将失败。

  - 未镜像的企业版后端服务器失败。

如果您有一个镜像的企业版后端，并且只有镜像或主数据库出现故障，请参阅在 lync server [2013-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)用于还原主数据库，并[在 Lync server 2013 中还原镜像的企业版后端服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)（用于还原镜像的镜像）中的镜像企业版后端服务器。

如果中央管理存储失败，请参阅[在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是后端服务器的企业版成员服务器出现故障，请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

<div>


> [!TIP]  
> 我们建议您先获取系统的图像副本，然后再开始还原。 您可以将此图像用作回滚点，以防还原过程中出现问题。 您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>还原 Enterprise Edition 后端服务器

1.  从具有与故障计算机相同的完全限定域名（FQDN）的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照您组织的服务器部署过程来执行该步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。

3.  安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与失败前相同。
    
    <div>
    

    > [!NOTE]  
    > 根据您的部署，后端服务器可能包含多个并置或独立数据库。按照先前部署服务器时使用的过程来安装 SQL Server，包括 SQL Server 权限和登录名。

    
    </div>

4.  安装 SQL Server 后，执行以下操作：
    
    1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
    2.  单击“从现有部署下载拓扑”****，然后单击“确定”****。
    
    3.  选择拓扑，然后单击“保存”****。单击“是”**** 确认您的选择。
    
    4.  右键单击 " **Lync Server 2013** " 节点，然后单击 "**发布拓扑**"。
    
    5.  按照“发布拓扑”**** 向导操作。 在 "**创建数据库**" 页上，选择要重新创建的数据库。
        
        <div>
        

        > [!NOTE]  
        > 只有独立数据库会显示在“创建数据库”<STRONG></STRONG>页上。

        
        </div>
    
    6.  如果要还原已镜像的后端，请继续遵循向导的其余部分，直到出现提示**创建镜像数据库**。 选择要安装的数据库，并完成此过程。
    
    7.  按照向导的其余部分操作，然后单击“完成”****。
    
    <div>
    

    > [!TIP]  
    > 除了运行拓扑生成器之外，您还可以使用<STRONG>CsDatabase</STRONG> cmdlet 来创建每个数据库，并使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 来配置镜像。 有关详细信息，请参阅 Lync Server 命令行管理程序文档。

    
    </div>

5.  执行以下操作以还原用户数据：
    
    1.  将 ExportedUserData 从 $Backup\\复制到本地目录。
    
    2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。
    
    3.  在还原用户数据之前，必须停止 Lync 服务。 为此，请键入：
        
            Stop-CsWindowsService
    
    4.  若要还原用户数据，请在命令行中键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  通过键入以下命令重新启动 Lync 服务：
        
            Start-CsWindowsService

6.  如果您在此池上部署了响应组，请还原响应组配置数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

7.  如果要还原的后端服务器包含存档或监控数据库，请使用 SQL Server 工具（如 SQL Server Management Studio）还原存档或监控数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原监视或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

