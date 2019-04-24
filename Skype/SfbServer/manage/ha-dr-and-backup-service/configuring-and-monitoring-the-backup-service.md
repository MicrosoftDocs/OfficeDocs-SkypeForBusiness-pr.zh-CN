---
title: 配置和监控备份服务
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务 Server 命令行管理程序命令可用于配置和监控备份服务。
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199875"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>配置和监控业务服务器中 Skype 的备份服务

以下 Skype 业务 Server 命令行管理程序命令可用于配置和监控备份服务。 若要还原存储在前端池的文件存储中的会议信息，请参阅下面的[还原备份服务使用的会议内容](#restore-conference-contents-using-the-backup-service)，。

> [!NOTE]  
> 以 RTCUniversalServerAdmins 组是唯一具有默认情况下运行**Get-csbackupservicestatus**权限的组。 若要使用此 cmdlet，此组的成员身份登录。 或者，您可以使用**Set-csbackupserviceconfiguration** cmdlet 授予到其他组 (例如，CSAdministrator) 访问此命令。

## <a name="to-see-the-backup-service-configuration"></a>若要查看的备份服务配置

运行以下 cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的默认值为两分钟。

## <a name="to-set-the-backup-service-sync-interval"></a>若要设置的备份服务同步间隔

运行以下 cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，以下为 3 分钟设置的间隔。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> 尽管可以使用此 cmdlet 的备份服务更改默认同步时间间隔，不应执行以便除非绝对需要时，为同步间隔具有对备份服务性能和恢复点目标 (RPO) 很大的影响。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>若要获取特定池的备份服务状态

运行以下 cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> 备份服务同步状态定义通信量从一个池 (P1) 到其备份池 (P2)。 从 P1 P2 到同步状态可以是不同于 p1 从 P2。 对于 P1 到 P2，备份服务位于"稳定"状态如果所有 P1 中所做的更改会完全都复制转移到 P2 内的同步间隔。 位于"最终"状态如果要从 P1 同步到 P2 没有更多更改。 两种状态指示在 cmdlet 执行的时间的备份服务的快照。 并不表示，按原样以后将保持返回的状态。 具体而言，将继续如果 P1 不会生成任何更改之后执行此 cmdlet 仅保留"最终"状态。 这是对于故障 P1 转移到 P2 之后 P1 **Invoke-cspoolfailover**执行逻辑的一部分置于只读模式,，则返回 true。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>若要获取特定池的备份关系的信息

运行以下 cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>若要强制备份服务同步

运行以下 cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>还原使用备份服务的会议内容 

如果在前端池的文件存储中存储的会议信息变得不可用，以便在池上驻留的用户，您必须还原此信息保留其会议数据。 如果与另一个前端池配对中断会议数据的前端池时，您可以使用备份服务还原数据。

如果整个池已失败，并且您需要进行故障转移到备份池其用户，则还必须执行此任务。 当这些用户都到其原始池将故障转移后时，您必须使用此过程将其会议内容复制到其原始的池。

假定 Pool1 配备 Pool2，并在 Pool1 会议数据都将丢失。 可以使用以下 cmdlet 以调用备份服务，要恢复的内容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

还原会议内容可能需要一些时间，具体取决于其大小。 您可以使用以下 cmdlet 检查进程状态：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

此 cmdlet 返回的数据会议模块的稳定状态的值时，此过程已完成。
