---
title: Lync Server 2013：防病毒扫描排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a67d7777017c004b0cfcc59a46cd27baf5c209
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013 的防病毒扫描排除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-11-02_

若要确保防病毒扫描程序不会干扰 Lync Server 2013 的操作，必须排除在其上运行防病毒扫描程序的每个 Lync Server 2013 服务器或服务器角色的特定进程和目录。 应排除以下进程和目录：

<div>


> [!NOTE]  
> 下面列出的文件夹和文件位置是 Lync Server 2013 的默认位置。 对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。



</div>

<div>


> [!IMPORTANT]  
> 请注意，某些防病毒程序可能需要其排除列表的绝对（而不是相对路径）。



</div>

  - Lync Server 2013 进程：
    
      - ABServer
    
      - AcpMcuSvc
    
      - ASMCUSvc
    
      - AVMCUSvc
    
      - ChannelService
    
      - ClsAgent
    
      - ComplianceService
    
      - DataMCUSvc
    
      - DataProxy
    
      - FileTransferAgent
    
      - IMMCUSvc
    
      - LysSvc
    
      - MasterReplicatorAgent
    
      - MediaRelaySvc
    
      - MediationServerSvc
    
      - MRASSvc
    
      - OcsAppServerHost
    
      - ReplicaReplicatorAgent
    
      - ReplicationApp
    
      - RtcHost
    
      - RTCSrv
    
      - XmppProxy
    
      - XmppTGW

  - Windows Fabric 主机服务进程：
    
      - Fabric .exe
    
      - FabricDCA
    
      - FabricHost

  - IIS 进程：
    
      - % systemroot%\\system32\\inetsrv\\w3wp
    
      - % systemroot%\\SysWOW64\\inetsrv\\w3wp

  - SQL Server 后端进程：
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\SQLServr
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\msmdsrv.ini

  - SQL Server 前端进程：
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\SQLServr
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\SQLServr

  - 目录和文件：
    
      - % systemroot%\\System32\\日志日志
    
      - % systemroot%\\SysWow64\\日志日志
    
      - % systemroot%\\Microsoft.NET\\程序\\集\_GAC MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - % programfiles%\\公共文件\\Microsoft Lync Server 2013\\观察程序节点
    
      - % programfiles%\\通用文件\\Microsoft Lync Server 2013
    
      - % 系统驱动器%\\RtcReplicaRoot
    
      - 文件共享存储（在拓扑生成器中指定）。 文件存储在拓扑生成器中指定。
    
      - SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。 可以在拓扑生成器中指定数据库和日志文件。 有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中[的适用于 Lync server 2013 的 SQL Server 数据和日志文件放置](lync-server-2013-sql-server-data-and-log-file-placement.md)。
    
      - SQL Server 数据和日志文件，包括用于前端数据库、Lync 存储和 RtcDatabase 存储的文件。 它们通常位于% localdrive%\\CSData。

</div>

<span> </span>

</div>

</div>

</div>

