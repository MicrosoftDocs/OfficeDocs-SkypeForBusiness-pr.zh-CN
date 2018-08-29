---
title: 防病毒扫描排除的 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Overview of Business server 防病毒扫描程序与 Skype 的互操作。
ms.openlocfilehash: 1078b3c0a28573e84235cbd39a11a6aa84a58b47
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250022"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>防病毒扫描排除的 Skype 业务服务器

Overview of Business server 防病毒扫描程序与 Skype 的互操作。

本文包含可帮助管理员确定它与 Active Directory 域中的防病毒软件一起使用时正在运行受支持的版本的 Microsoft Windows 的计算机上的潜在不稳定的原因的建议环境或托管的业务环境中。

我们建议您暂时应用这些过程来评估系统。 如果您的系统性能或稳定性通过在本文中所做的建议得到了改善，与防病毒软件供应商联系的说明或更新版本的防病毒软件。

本文包含演示如何帮助低的安全设置或暂时关闭的计算机上的安全功能的信息。 您可以了解特定问题的性质这些更改。 进行这些更改之前，我们建议您对与您的特定环境中实现此变通解决方案相关联的风险评估。 如果实施此变通解决方案，采取任何适当的额外步骤来帮助保护的文件不再正在扫描的防病毒软件的计算机。

若要确保防病毒扫描程序不干扰业务服务器的 Skype 的操作，必须为每个 Skype 业务服务器或服务器角色在其上运行的防病毒扫描中排除特定过程和目录。 应排除以下进程和目录：

> [!NOTE]
> 下面列出的文件夹和文件位置是业务服务器 Skype 的默认位置。 对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。

> [!IMPORTANT]
> 请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。

- Skype Business Server 过程：

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

    > [!NOTE]
    > 请注意，这些路径特定于 Skype 业务服务器版本。

  - Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - 文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。

  - SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。 可以在拓扑生成器中指定数据库和日志文件。 有关每个数据库的数据和日志文件的详细信息，包括默认名称，请参阅[SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)部署文档中。

  - SQL Server 数据和日志文件，包括那些前端数据库 Skype 业务存储和 RtcDatabase 存储。 它们通常位于 %localdrive%\CSData 下。


