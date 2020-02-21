---
title: 升级或更新后端服务器或 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中升级或更新后端服务器或 Standard Edition 服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

本主题介绍如何在企业版后端服务器或 Standard Edition server 上安装更新。

如果在您升级后端服务器时它至少要停机 30 分钟，则用户可能会进入恢复能力模式。升级完成，且后端服务器又与池中的前端服务器连接后，用户会返回到全部功能。如果升级所用时间少于 30 分钟，将不会对用户造成影响。

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或 Standard Edition server

1.  以 CsAdministrator 角色的成员身份登录到要升级的服务器。

2.  下载更新并将其提取到本地硬盘。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

4.  停止 Lync Server 服务。在命令行中键入：
    
        Stop-CsWindowsService

5.  停止万维网服务。在命令行中键入：
    
        net stop w3svc

6.  关闭所有 Lync Server 命令行管理程序窗口。

7.  安装该更新。

8.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

9.  再次停止 Lync Server 服务以缓存全局程序集缓存 (GAC) –d 程序集。在命令行中键入：
    
        Stop-CsWindowsService

10. 重新启动万维网服务。在命令行中键入：
    
        net start w3svc

11. 通过执行以下操作之一将 LyncServerUpdateInstaller.exe 进行的更改应用于 SQL Server 数据库：
    
      - 如果这是企业版后端服务器，并且此服务器上没有并置数据库（如存档或监控数据库），则在命令行中键入以下内容：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - 如果这是企业版后端服务器，并且此服务器上有并置数据库，请在命令行中键入以下内容：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 如果这是标准版服务器，请在命令行中键入以下命令：
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

