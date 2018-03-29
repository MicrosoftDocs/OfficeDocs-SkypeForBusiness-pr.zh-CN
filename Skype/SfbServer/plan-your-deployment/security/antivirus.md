---
title: Skype for Business Server 2015 防病毒扫描排除项
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 与业务服务器 2015 Skype 防病毒扫描程序的概述。
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 防病毒扫描排除项
 
与业务服务器 2015 Skype 防病毒扫描程序的概述。 
  
若要确保防病毒扫描程序不会干扰业务服务器 2015年的 Skype 的操作，必须为每个 Skype 业务服务器 2015年服务器或服务器角色在其上运行的防病毒扫描排除特定的流程和目录。 应排除以下进程和目录：
  
> [!NOTE]
> 下面列出的文件夹和文件位置是业务服务器 2015 Skype 的默认位置。 对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。 
  
> [!IMPORTANT]
> 请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。 
  
- Skype 的业务服务器 2015年进程：
    
  - ABServer.exe
    
  - ASMCUSvc.exe
    
  - AVMCUSvc.exe
    
  - ChannelService.exe
    
  - ClsAgent.exe
    
  - ComplianceService.exe
    
  - DataMCUSvc.exe
    
  - DataProxy.exe
    
  - FileTransferAgent.exe
    
  - HealthAgent.exe
    
  - IMMCUSvc.exe
    
  - LysSvc.exe
    
  - MasterReplicatorAgent.exe
    
  - MediaRelaySvc.exe
    
  - MediationServerSvc.exe
    
  - MRASSvc.exe
    
  - OcsAppServerHost.exe
    
  - ReplicaReplicatorAgent.exe
    
  - ReplicationApp.exe
    
  - RtcHost.exe
    
  - RTCSrv.exe
    
  - XmppProxy.exe
    
  - XmppTGW.exe
    
- Windows Fabric Host Service 进程：
    
  - Fabric.exe
    
  - FabricDCA.exe
    
  - FabricHost.exe
    
- IIS 进程：
    
  - %systemroot%\system32\inetsrv\w3wp.exe
    
  - %systemroot%\SysWOW64\inetsrv\w3wp.exe
    
- SQL Server 后端进程：
    
    > [!NOTE]
    > 请注意，这些路径特定于 SQL Server 版本。 
  
  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe
    
- SQL Server 前端进程：
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - Standard Edition 安装 RTC 实例 
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe
    
- 目录和文件：
    
  - %systemroot%\System32\LogFiles
    
  - %systemroot%\SysWow64\LogFiles
    
  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL
    
  - Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - 文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。
    
  - SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。 可以在拓扑生成器中指定数据库和日志文件。 有关每个数据库的数据和日志文件的详细信息，包括默认名称，请参阅[SQL Server 数据和日志文件位置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)中部署文档。
    
  - SQL Server 数据文件和日志文件，包括前端数据库，Skype 业务存储和 RtcDatabase 存储。 它们通常位于 %localdrive%\CSData 下。
    

