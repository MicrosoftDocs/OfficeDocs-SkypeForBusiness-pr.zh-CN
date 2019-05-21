---
title: Skype for business 服务器的防病毒扫描排除项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Skype for business Server 的防病毒扫描程序互操作概述。
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296971"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Skype for business 服务器的防病毒扫描排除项

Skype for business Server 的防病毒扫描程序互操作概述。

本文包含的建议可帮助管理员确定当运行受支持的 Microsoft Windows 版本的计算机与 Active Directory 域中的防病毒软件一起使用时, 该计算机可能不稳定的原因环境中或托管企业环境中。

我们建议你临时应用这些过程来评估系统。 如果你的系统性能或稳定性由本文所做的建议改进, 请与防病毒软件供应商联系, 了解有关的防病毒软件的更新版本。

本文包含的信息介绍了如何帮助降低安全设置或如何暂时关闭计算机上的安全功能。 你可以进行这些更改以了解特定问题的性质。 在进行这些更改之前, 我们建议你评估与在你的特定环境中实施此解决方法相关的风险。 如果你实现此解决方法, 请采取任何适当的附加步骤来帮助保护计算机, 以查找你的防病毒软件不再扫描的文件。

为确保防病毒扫描程序不会干扰 Skype for Business Server 的操作, 您必须为运行防病毒扫描程序的每个 Skype for business 服务器或服务器角色排除特定的流程和目录。 应排除以下进程和目录：

> [!NOTE]
> 以下列出的文件夹和文件位置是 Skype for business 服务器的默认位置。 对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。

> [!IMPORTANT]
> 请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。

- Skype for business 服务器流程:

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
  
  - LyncBackupService

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

    > [!NOTE]
    > 请注意, 这些路径特定于 Skype for business 服务器版本。

  - Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - 文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。

  - SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。可以在拓扑生成器中指定数据库和日志文件。有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中的 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。

  - SQL Server 数据和日志文件, 包括前端数据库、Skype for Business 应用商店和 RtcDatabase 应用商店的文件。 它们通常位于 %localdrive%\CSData 下。


