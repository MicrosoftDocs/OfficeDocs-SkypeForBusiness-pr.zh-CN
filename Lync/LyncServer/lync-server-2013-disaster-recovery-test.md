---
title: Lync Server 2013：灾难恢复测试
TOCTitle: 灾难恢复测试
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn747887(v=OCS.15)
ms:contentKeyID: 62293593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的灾难恢复测试

 

_**上一次修改主题：** 2015-01-26_

为 Lync Server 2013 池服务器执行系统恢复以测试您记录的灾难恢复过程。此测试将模拟一台服务器的完整硬件故障并帮助确保资源、规划和数据都可用于恢复。请尝试每月轮转测试焦点，以便您的组织每次测试不同服务器或其他设备的故障。

请注意，组织执行灾难恢复测试时所遵循的计划将有所不同。非常重要的是，不得忽略灾难恢复测试。


将您的 Lync Server 2013 拓扑、策略和配置设置导出至文件。在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。

将您的 Lync Server 2013 拓扑、策略和配置设置导入到中央管理存储或本地计算机中，如以下命令所示：

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

要备份生产 Lync Server 2013 数据，请执行以下操作：

  - 使用标准的 SQL Server 备份过程将数据库转储到文件或磁带转储设备来备份 RTC 和 LCSLog 数据库。

  - 使用第三方备份应用程序将数据备份到文件或磁带。

  - 使用 Export-CsUserData cmdlet 创建整个 RTC 数据库的 XML 导出。

  - 使用文件系统备份或第三方来备份会议内容和合规性日志。

  - 使用 Export-CsConfiguration 命令行工具备份 Lync Server 2013 设置。

故障转移过程的第一个步骤包括强制性地将用户从生产池移动到灾难恢复池。

之所以称为强制性移动是因为生产池并不接受用户重新定位。

除了是 RTC SQL 数据库上的记录更新之外，Lync Server 2013 移动用户过程也是对用户帐户对象上的属性所做的一个有效更改。

此数据可通过以下两个过程还原：

  - 可以使用标准 SQL Server 还原过程或使用第三方备份/还原实用程序从生产 SQL Server 中的原始备份转储设备还原 RTC 数据库。

  - 可以使用根据生产 SQL Server 导出创建的 XML 文件通过 DBIMPEXP.exe 实用程序还原用户联系人数据。

在还原此数据后，用户可以有效地连接到灾难恢复 Lync Server 2013 池并照常操作。

要使用户能够连接到灾难恢复 Lync Server 2013 池，需要 DNS 记录更改。

生产 Lync Server 2013 池将由客户端使用自动配置和以下 DNS SRV 记录引用：

  - SRV：\_sip.\_tls.\<域\> /CNAME: SIP.\<域\>

  - CNAME：SIP.\<域\> /cvc-pool-1.\<域\>

为促进故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：

  - CNAME：SIP.\<域\> /DROCSPool.\<域\>

  - Sip.\<域\>

  - AV.\<域\>

  - webconf.\<域\>

  - OCSServices.\<域\>

> [!IMPORTANT]
> 有关详细的管理过程，请参阅<a href="lync-server-2013-backing-up-and-restoring-lync-server.md">备份和还原 Lync Server 2013</a>。


## 另请参阅

#### 概念

[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[备份和高可用性 Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps)  

#### 其他资源

[Import-CsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsConfiguration)  
[备份和还原 Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[管理 Lync Server 2013 灾难恢复、高可用性和备份服务](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)

