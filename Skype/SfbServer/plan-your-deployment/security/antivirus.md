---
title: 防病毒扫描排除项Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 防病毒扫描程序与 Skype for Business Server 的互操作概述。
ms.openlocfilehash: 8a4ffae692704755753fbdaa2c84207af796d75d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858989"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>防病毒扫描排除项Skype for Business Server

防病毒扫描程序与 Skype for Business Server 的互操作概述。

若要确保防病毒扫描程序不会干扰 Skype for Business Server 的操作，必须排除运行防病毒扫描程序的每个 Skype for Business Server 服务器或服务器角色的特定进程和目录。 应排除以下进程和目录：

> [!NOTE]
> 下面列出的文件夹和文件位置是用户的默认Skype for Business Server。 对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。

> [!IMPORTANT]
> 请注意，某些防病毒程序可能需要其排除列表的绝对路径而非相对路径。

- Skype for Business Server过程：

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
  
  - LyncBackupService.exe

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

- Windows Fabric主机服务进程：

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- IIS 进程：

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End过程：

    > [!NOTE]
    > 请注意，这些路径特定于SQL Server版本。

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End过程：

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition安装 RTC 实例

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- 目录和文件：

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > 请注意，这些路径特定于Skype for Business Server版本。

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - 文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。

  - SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。可以在拓扑生成器中指定数据库和日志文件。有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中的 [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。

  - SQL Server数据和日志文件，包括前端数据库、Skype for Business和 RtcDatabase 存储的日志文件。 它们通常在 %localdrive%\CSData 下。