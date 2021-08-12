---
title: 配置和监控备份服务
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 可以使用命令行Skype for Business Server命令行管理程序命令配置和监视备份服务。
ms.openlocfilehash: ea4dd6bba87b06cb9c51320be9c040869c17204619656dfc4291054fcb6c214a
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849537"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>配置和监视备份服务Skype for Business Server

可以使用以下命令行管理Skype for Business Server命令行管理程序命令来配置和监视备份服务。 若要还原存储在前端池的文件存储中的会议信息，请参阅下面的使用 [备份](#restore-conference-contents-using-the-backup-service)服务还原会议内容。

> [!NOTE]  
> 默认情况下，RTCUniversalServerAdmins 组是唯一具有运行 **Get-CsBackupServiceStatus** 的权限的组。要使用此 cmdlet，请以该组的成员身份登录。或者，可通过使用 **Set-CsBackupServiceConfiguration** cmdlet 向其他组（如 CSAdministrator）授予对此命令的访问权。

## <a name="to-see-the-backup-service-configuration"></a>查看备份服务配置

运行以下 cmdlet：<br/><br/>Get-CsBackupServiceConfiguration

SyncInterval 的默认值为 2 分钟。

## <a name="to-set-the-backup-service-sync-interval"></a>设置备份服务同步间隔

运行以下 cmdlet：<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 间隔

例如，下面将此间隔设置为 3 分钟。<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00：03：00


> [!IMPORTANT]  
> 尽管可使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对有必要，否则您不应这样做，因为同步间隔对备份服务的性能和恢复点目标 (RPO) 有很大的影响。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>获取特殊池的备份服务状态

运行以下 cmdlet：<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> 备份服务的同步状态是从一个池 (P1) 到其备份池 (P2) 进行单向定义的。从 P1 到 P2 的同步状态与从 P2 到 P1 的同步状态不同。对于 P1 到 P2，如果在同步间隔内将 P1 中所做的所有更改完全复制到 P2，则备份服务将处于“稳定”状态。如果不再将更改从 P1 同步到 P2，则备份服务处于“最终”状态。这两个状态均指示执行 cmdlet 时备份服务的快照。它不表示返回的状态之后将继续保持下去。特别是，仅在执行 cmdlet 后 P1 未生成任何更改的情况下，才一直保持“最终”状态。当作为 **Invoke-CsPoolfailover** 执行逻辑的一部分将 P1 置于只读模式后，P1 到 P2 的同步失败时才会出现此种情况。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>获取有关特定池的备份关系的信息

运行以下 cmdlet：<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>强制备份服务同步

运行以下 cmdlet：<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>使用备份服务还原会议内容 

如果存储在前端池的文件存储中的会议信息变得不可用，则必须还原此信息，以便池中的用户可以保留其会议数据。 如果丢失会议数据的前端池与另一个前端池配对，您可以使用备份服务还原数据。

此外，如果整个池已失败并且您必须将其用户故障转移到备份池，则也必须执行此任务。在将这些用户故障转移回其原始池时，您也必须使用此过程将其会议内容复制回其原始池。

假定将 Pool1 与 Pool2 配对且 Pool1 中的会议数据已丢失。 可以使用以下 cmdlet 调用备份服务来还原内容：<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

还原会议内容可能需要一些时间，具体取决于该内容的大小。您可以使用以下 cmdlet 检查过程状态：<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

当此 cmdlet 为数据会议模块返回值“稳定状态”时，表示此过程已完成。
