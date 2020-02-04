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
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中还原企业版后端服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-18_

在以下两种情况下使用本主题中介绍的过程：

  - 镜像企业版后端服务器的主数据库和镜像数据库均失败。

  - 不进行镜像的企业版后端服务器失败。

如果你有一个镜像的企业版后端，并且只有镜像或主数据库失败，请参阅[在 Lync server 2013 中还原镜像的企业版后端服务器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)用于还原主数据库，以及[在 lync Server 2013 中还原镜像的企业版后端服务器-镜像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)以还原镜像。

如果中央管理存储失败，请参阅[在 Lync server 2013 中还原托管中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是后端服务器的企业版成员服务器出现故障，请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

<div>


> [!TIP]  
> 我们建议你先拍摄系统的映像副本，然后再开始还原。 你可以将此映像用作回退点，以防在还原过程中出现问题。 您可能希望在安装操作系统和 SQL Server 后获取图像副本，并还原或重新注册证书。



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>还原企业版后端服务器

1.  从具有与故障计算机相同的完全限定的域名（FQDN）的全新或新服务器开始，安装操作系统，然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照组织的服务器部署过程执行此步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。

3.  安装 SQL Server 2012 或 SQL Server 2008 R2，使实例名称与失败之前保持相同。
    
    <div>
    

    > [!NOTE]  
    > 根据你的部署，后端服务器可能包含多个 collocated 或单独的数据库。 按照相同的步骤安装最初用于部署服务器的 SQL Server，包括 SQL Server 权限和登录。

    
    </div>

4.  安装 SQL Server 后，请执行以下操作：
    
    1.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
    2.  单击 "**从现有部署下载拓扑**"，然后单击 **"确定"**。
    
    3.  选择拓扑，然后单击 "**保存**"。 单击 **"是"** 以确认您的选择。
    
    4.  右键单击 " **Lync Server 2013** " 节点，然后单击 "**发布拓扑**"。
    
    5.  按照 "**发布拓扑**向导" 中的步骤操作。 在 "**创建数据库**" 页面上，选择要重新创建的数据库。
        
        <div>
        

        > [!NOTE]  
        > "<STRONG>创建数据库</STRONG>" 页面上仅显示独立数据库。

        
        </div>
    
    6.  如果要还原已镜像的后端，请继续按照向导的其余部分操作，直到出现 "提示**创建镜像数据库**"。 选择要安装的数据库，然后完成此过程。
    
    7.  按照向导的其余部分，然后单击 "**完成**"。
    
    <div>
    

    > [!TIP]  
    > 你可以使用<STRONG>CsDatabase</STRONG> cmdlet 创建每个数据库，使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 来配置镜像，而不是运行拓扑生成器。 有关详细信息，请参阅 Lync Server Management Shell 文档。

    
    </div>

5.  通过执行下列操作还原用户数据：
    
    1.  将 ExportedUserData 从 $Backup\\复制到本地目录。
    
    2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。
    
    3.  还原用户数据之前，必须停止 Lync 服务。 若要执行此操作，请键入：
        
            Stop-CsWindowsService
    
    4.  若要还原用户数据，请在命令行键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  通过键入以下内容重启 Lync 服务：
        
            Start-CsWindowsService

6.  如果你在此池中部署了响应组，请还原响应组配置数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

7.  如果要还原包含存档或监视数据库的后端服务器，请使用 SQL Server 工具（如 SQL Server Management Studio）还原存档或监视数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原监视或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

