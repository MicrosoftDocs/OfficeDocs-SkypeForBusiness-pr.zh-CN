---
title: 备份和还原过程概述
TOCTitle: 备份和还原过程概述
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202192(v=OCS.15)
ms:contentKeyID: 52061160
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份和还原过程概述

 

_**上一次修改主题：** 2013-03-26_

本节概述 Lync Server 2013 的备份和还原过程的工作方式。所有 Standard Edition Server 和 Enterprise Edition Server 的过程均相同，与其位置无关。

通常，备份过程的工作方式如下：

  - 您在不属于任何池的独立计算机上创建一个备份位置作为共享文件夹。备份的位置将在 **$Backup** 中引用。

  - 通过执行[备份 Lync Server](lync-server-2013-backing-up-lync-server.md) 中介绍的过程，定期按计划备份[备份和还原要求：数据](lync-server-2013-backup-and-restoration-requirements-data.md)中描述的所有 Lync Server 数据库和所有文件存储 中央管理存储包含所有服务器设置和配置。

  - 每次运行后续备份时，都会创建一个新共享文件夹并更改 **$Backup** 引用的路径。

通常，还原过程的工作方式如下：

  - 当出现故障或中断时，您需要将 **$Backup** 引用的位置中的数据还原到新的或干净的计算机。
    
    > [!IMPORTANT]  
	> 该还原过程不会将数据还原到现有服务器状态。即，该过程要求服务器是干净的或新的。


  - 要使您的用户和会议信息能够恢复到故障点，您可以实施具有已配对前端池的灾难恢复拓扑，如[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。除此选项之外，Lync Server 仅支持其数据库的简单恢复模式。使用简单恢复模式，数据库将恢复到上次完整备份点，这意味着您无法将数据库还原到故障点或特定时间点。对于许多组织而言，简单恢复模式是最佳选择，因为 Lync Server 后端数据库 (RTCXDS.mdf) 实际上小于事务日志文件，并且远远小于典型业务线数据库应用程序的日志文件。

  - 在还原时，所有域名系统 (DNS) 配置、动态主机配置协议 (DHCP) 配置、域名、计算机完全限定域名 (FQDN)、文件存储路径等必须与备份时相同。

如果运行 Lync Server 的服务器出现故障，恢复过程包括以下步骤：

  - 在新的或干净的计算机上安装操作系统，该计算机应与失败的计算机具有相同 FQDN。

  - 重新安装证书。

  - 如果服务器承载有数据库，则安装 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。

  - 通常，如果服务器承载有数据库，应运行拓扑生成器创建和安装数据库并设置访问控制列表 (ACL)。

  - 通常，如果服务器承载有服务器角色，则运行 Lync Server 部署向导的步骤 1 至步骤 4，以安装本地配置文件，安装服务器角色组件，分配证书，然后启动服务。
    
    > [!NOTE]  
    > 如果服务器承载有与服务器角色并置的数据库，则运行 Lync Server 部署向导的步骤 2 以重新创建数据库。
    


  - 如果服务器承载有数据库，则还原备份的数据。

