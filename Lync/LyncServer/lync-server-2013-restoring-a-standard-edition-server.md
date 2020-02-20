---
title: Lync Server 2013：还原 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bffde0a5b6047aeb2eabe38ee10c6b313ff1f01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中还原 Standard Edition 服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

如果未承载中央管理存储的 Standard Edition 服务器出现故障，请按照本节中的过程操作。 如果中央管理存储失败，请参阅[在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。

<div>


> [!TIP]  
> 我们建议您先获取系统的图像副本，然后再开始还原。 您可以将此图像用作回滚点，以防还原过程中出现问题。 您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>还原 Standard Edition 服务器

1.  从具有与故障计算机相同的完全限定域名（FQDN）的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照您组织的服务器部署过程来执行该步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组成员和本地 Administrators 组成员的用户帐户，登录到要还原的服务器。

3.  通过将相应的文件存储从 $Backup 复制到服务器上的文件存储位置并共享该文件夹来还原文件存储。
    
    <div>
    

    > [!IMPORTANT]  
    > 已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。

    
    </div>

4.  运行拓扑生成器：
    
    1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
    2.  单击“从现有部署下载拓扑”****，然后单击“确定”****。
    
    3.  选择拓扑，然后单击“保存”****。单击“是”**** 确认您的选择。

5.  浏览到 Lync Server 安装文件夹或媒体，然后启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。 使用 Lync Server 部署向导执行以下操作：
    
    1.  运行“步骤 1: 安装本地配置存储”**** 以安装本地配置文件。
    
    2.  运行**步骤2：安装或删除 Lync Server 组件**以安装 lync server 服务器角色。
    
    3.  运行“步骤 3: 请求、安装或分配证书”**** 以分配证书。
    
    4.  运行“步骤 4: 启动服务”**** 以在服务器上启动服务。
    
    有关运行部署向导的详细信息，请参阅适用于您要还原的服务器角色的部署文档。

6.  执行以下操作以还原用户数据：
    
    1.  将 ExportedUserData 从 $Backup\\复制到本地目录。
    
    2.  在还原用户数据之前，必须停止 Lync 服务。 为此，请键入：
        
            Stop-CsWindowsService
    
    3.  若要还原用户数据，请在命令行中键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  通过键入以下命令重新启动 Lync 服务：
        
            Start-CsWindowsService

7.  如果您在此 Standard Edition 服务器上部署了响应组，请还原响应组配置数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

8.  如果已在此 Standard Edition 服务器上部署持久聊天，请还原持久聊天数据库（mgc）。
    
    如果您使用 SQL Server 备份来备份持久聊天数据库，请使用 SQL Server 还原过程将其还原。
    
    如果使用 Export-cspersistentchatdata cmdlet 对其进行备份，请使用 Export-cspersistentchatdata 将其还原。

</div>

</div>

<span> </span>

</div>

</div>

</div>

