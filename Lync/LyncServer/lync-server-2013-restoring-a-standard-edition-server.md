---
title: Lync Server 2013：还原标准版服务器
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
ms.openlocfilehash: a0ecc58dc2683cd07b83a8c57385593961c3e985
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中还原标准版服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

如果未托管中央管理存储的标准版服务器出现故障，请按照本部分中的步骤操作。 如果中央管理存储失败，请参阅[在 Lync server 2013 中还原托管中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。

<div>


> [!TIP]  
> 我们建议你先拍摄系统的映像副本，然后再开始还原。 你可以将此映像用作回退点，以防在还原过程中出现问题。 您可能希望在安装操作系统和 SQL Server 后获取图像副本，并还原或重新注册证书。



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>还原标准版服务器

1.  从具有与故障计算机相同的完全限定的域名（FQDN）的全新或新服务器开始，安装操作系统，然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照组织的服务器部署过程执行此步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组和本地管理员组成员的用户帐户，登录到要还原的服务器。

3.  通过将相应的文件存储从 $Backup 复制到服务器上的文件存储位置并共享该文件夹，还原文件存储。
    
    <div>
    

    > [!IMPORTANT]  
    > 已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。

    
    </div>

4.  运行拓扑生成器：
    
    1.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
    2.  单击 "**从现有部署下载拓扑**"，然后单击 **"确定"**。
    
    3.  选择拓扑，然后单击 "**保存**"。 单击 **"是"** 以确认您的选择。

5.  通过浏览找到 Lync Server 安装文件夹或媒体，然后启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。 使用 Lync Server 部署向导执行下列操作：
    
    1.  运行**步骤1：安装本地配置存储**以安装本地配置文件。
    
    2.  运行**步骤2：设置或删除 Lync Server 组件**以安装 lync server 服务器角色。
    
    3.  运行**步骤3：请求、安装或分配证书**以分配证书。
    
    4.  运行**步骤4：启动服务**以启动服务器上的服务。
    
    有关运行部署向导的详细信息，请参阅要还原的服务器角色的部署文档。

6.  通过执行下列操作还原用户数据：
    
    1.  将 ExportedUserData 从 $Backup\\复制到本地目录。
    
    2.  还原用户数据之前，必须停止 Lync 服务。 若要执行此操作，请键入：
        
            Stop-CsWindowsService
    
    3.  若要还原用户数据，请在命令行键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  通过键入以下内容重启 Lync 服务：
        
            Start-CsWindowsService

7.  如果你在此标准版服务器上部署了响应组，请还原响应组配置数据。 有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

8.  如果在此标准版服务器上部署持久聊天，请还原持久聊天数据库（mgc）。
    
    如果使用 SQL Server 备份备份持久聊天数据库，请使用 SQL Server 还原过程还原它。
    
    如果你使用 CsPersistentChatData cmdlet 对其进行备份，请使用 Import-CsPersistentChatData 将其还原。

</div>

</div>

<span> </span>

</div>

</div>

</div>

