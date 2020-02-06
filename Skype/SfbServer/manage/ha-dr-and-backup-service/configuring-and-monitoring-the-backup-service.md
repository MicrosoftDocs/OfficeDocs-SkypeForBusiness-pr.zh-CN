---
title: 配置和监控备份服务
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以使用 Skype for Business Server Management Shell 命令来配置和监视备份服务。
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818213"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置和监视备份服务

你可以使用以下 Skype for Business 服务器管理外壳命令来配置和监视备份服务。 若要还原存储在前端池的文件存储中的会议信息，请参阅下面[的使用备份服务还原会议内容](#restore-conference-contents-using-the-backup-service)。

> [!NOTE]  
> RTCUniversalServerAdmins 组是唯一具有运行**CsBackupServiceStatus**默认权限的组。 若要使用此 cmdlet，请以该组的成员身份登录。 或者，你可以使用**CsBackupServiceConfiguration** cmdlet 将对此命令的访问权限授予其他组（例如 CSAdministrator）。

## <a name="to-see-the-backup-service-configuration"></a>查看备份服务配置

运行以下 cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的默认值是2分钟。

## <a name="to-set-the-backup-service-sync-interval"></a>设置备份服务同步间隔

运行以下 cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，下面的时间间隔设置为3分钟。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> 虽然你可以使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对必要，否则不应执行此操作，因为同步间隔对备份服务性能和恢复点目标（RPO）有很高的影响。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>获取特定池的备份服务状态

运行以下 cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> 备份服务同步状态是从池（P1） unidirectionally 到其备份池（P2）定义的。 从 P1 到 P2 的同步状态可能与从 P2 到 P1 的同步状态不同。 对于 P2 到 P2，如果在 P1 中进行的所有更改都在同步间隔内完全复制到 P2，则备份服务处于 "稳定" 状态。 如果没有其他更改要从 P1 同步到 P2，它将处于 "最终状态" 状态。 这两种状态表示执行 cmdlet 时备份服务的快照。 这并不意味着返回的状态将保持为后的状态。 特别是，仅当在执行 cmdlet 后 P1 不会生成任何更改时，"最终" 状态才会继续保持。 在将 p1 置于只读模式（作为**CsPoolfailover**执行逻辑的一部分）之后，p1 被置于只读模式下时，此情况为 true。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>获取有关特定池的备份关系的信息

运行以下 cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>强制备份服务同步

运行以下 cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>使用备份服务还原会议内容 

如果在前端池的文件存储中存储的会议信息不可用，则必须还原此信息，以便驻留在该池中的用户保留其会议数据。 如果已丢失会议数据的前端池与另一个前端池配对，则可以使用备份服务还原数据。

如果整个池出现故障，并且你必须将其用户故障转移到备份池，还必须执行此任务。 当这些用户故障恢复到其原始池时，必须使用此过程将其会议内容复制回其原始池。

假设 Pool1 与 Pool2 配对，并且 Pool1 中的会议数据丢失。 你可以使用以下 cmdlet 调用备份服务来还原内容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

还原会议内容可能需要一些时间，具体取决于它们的大小。 你可以使用以下 cmdlet 检查进程状态：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

当此 cmdlet 为数据会议模块返回稳定状态的值时，将执行此过程。
