---
title: Lync Server 2013：备份核心数据和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4523dcaaee5931e6bf4df9dd79c09ec92636ec31
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>在 Lync Server 2013 中备份核心数据和设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-23_

以下过程使用 Lync Server 命令行管理程序 cmdlet 为核心服务的设置和数据创建备份文件。 有关此部分中使用的工具（包括它们位于何处）的详细信息，请参阅[Lync Server 2013 中的备份和还原要求：工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。 有关备份存档和监视数据的详细信息，请参阅[在 Lync Server 2013 中备份存档和监控数据库](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。

<div>


> [!NOTE]  
> 本部分中对中央管理存储进行备份的步骤包括用于存档和监视的设置和配置。



</div>

您可以在本地运行本节所述的 cmdlet，也可以远程运行它们。

<div>

## <a name="to-back-up-core-data-and-settings"></a>备份核心数据和设置

1.  通过 RTCUniversalServerAdmins 组成员的用户帐户，登录内部部署中的任意计算机。

2.  若要采用以下步骤存储创建的备份，请创建新的共享文件夹，并将 **$Backup** 引用的路径更新到该新共享文件夹。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

4.  备份中央管理存储配置文件。 在命令行中键入：
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > 此步骤将 Lync Server 拓扑、策略和配置设置导出到文件中。 无需使用其他步骤来备份拓扑数据。

    
    </div>

5.  将备份的中央管理存储配置文件复制到 $Backup\\。

6.  备份位置信息服务数据。在命令行中键入：
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  将备份的位置信息服务配置文件复制到 $Backup\\。

8.  备份前端池和每个 Standard Edition 服务器的每个后端数据库上的用户数据。 在命令行中键入：
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    例如：
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  将已备份的用户文件复制到\\$Backup。

10. 在运行响应组应用程序的每个池中，备份响应组配置。 请执行以下操作：
    
    1.  在命令行中键入：
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        例如：
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. 将已备份的响应组配置文件复制到\\$Backup。

</div>

</div>

<span> </span>

</div>

</div>

</div>

