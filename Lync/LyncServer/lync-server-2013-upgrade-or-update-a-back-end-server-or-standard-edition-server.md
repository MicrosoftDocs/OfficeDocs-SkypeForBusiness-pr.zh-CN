---
title: 升级或更新后端服务器或标准版服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中升级或更新后端服务器或标准版服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

本主题介绍如何在企业版后端服务器或标准版服务器上安装更新。

如果后端服务器在升级后至少30分钟, 则用户可能会进入恢复模式。 升级完成且后端服务器再次与池中的前端服务器连接时, 用户将返回到完整功能。 如果升级所用时间少于 30 分钟，则用户不会受到影响。

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或 Standard Edition Server

1.  以 CsAdministrator 角色的成员身份登录到要升级的服务器。

2.  下载更新并将其提取到本地硬盘。

3.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

4.  停止 Lync 服务器服务。 在命令行中键入：
    
        Stop-CsWindowsService

5.  停止万维网服务。 在命令行中键入：
    
        net stop w3svc

6.  关闭所有 Lync Server Management Shell 窗口。

7.  安装该更新。

8.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

9.  再次停止 Lync Server 服务以捕获全局程序集缓存 (GAC)-d 程序集。 在命令行中键入：
    
        Stop-CsWindowsService

10. 重新启动万维网服务。 在命令行中键入：
    
        net start w3svc

11. 通过执行下列操作之一将 LyncServerUpdateInstaller 所做的更改应用到 SQL Server 数据库:
    
      - 如果这是企业版后端服务器, 并且此服务器上没有 collocated 数据库 (如 "存档" 或 "监视数据库"), 请在命令行中键入以下内容:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - 如果这是企业版后端服务器, 并且此服务器上有 collocated 数据库, 请在命令行中键入以下内容:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 如果这是标准版服务器, 请在命令行键入以下命令:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

