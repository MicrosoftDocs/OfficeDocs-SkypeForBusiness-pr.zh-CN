---
title: Lync Server 2013：病毒扫描排除
TOCTitle: Lync Server 2013 的病毒扫描排除
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn440138(v=OCS.15)
ms:contentKeyID: 59602824
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的病毒扫描排除

 

_**上一次修改主题：** 2015-11-02_

若要确保防病毒扫描程序不干扰 Lync Server 2013 的运行，您必须排除对其运行防病毒扫描程序的每个 Lync Server 2013 服务器或服务器角色的特定进程和目录。应排除以下进程和目录：

> [!NOTE]  
> 下面列出的文件夹和文件位置是 Lync Server 2013 的默认位置。对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。



  - Lync Server 2013 进程：
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
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
    
      - %systemroot%\\system32\\inetsrv\\w3wp.exe
    
      - %systemroot%\\SysWOW64\\inetsrv\\w3wp.exe

  - SQL Server 后端进程：
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe

  - SQL Server 前端进程：
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSMQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSMQL\\Binn\\SQLServr.exe

  - 目录和文件：
    
      - %systemroot%\\System32\\LogFiles
    
      - %systemroot%\\SysWow64\\LogFiles
    
      - %systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - %programfiles%\\Microsoft Lync Server 2013
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - %SystemDrive%\\RtcReplicaRoot
    
      - 文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。
    
      - SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。可以在拓扑生成器中指定数据库和日志文件。有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中的 [Lync Server 2013 的 SQL Server 数据和日志文件放置](lync-server-2013-sql-server-data-and-log-file-placement.md)。
    
      - SQL Server 数据和日志文件，包括前端数据库、Lync 存储、存档存储和 RtcDatabase 存储的这些文件。它们通常位于 %localdrive%\\CSData 下。

