---
title: Lync Server 2013：配置和监控备份服务
TOCTitle: 配置和监控备份服务
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205252(v=OCS.15)
ms:contentKeyID: 49314202
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置和监控备份服务

 

_**上一次修改主题：** 2012-11-01_

可使用以下 Lync Server 命令行管理程序命令配置和监控备份服务。

> [!NOTE]  
> 默认情况下，RTCUniversalServerAdmins 组是唯一具有运行 <strong>Get-CsBackupServiceStatus</strong> 的权限的组。要使用此 cmdlet，请以该组的成员身份登录。或者，可通过使用 <strong>Set-CsBackupServiceConfiguration</strong> cmdlet 向其他组（如 CSAdministrator）授予对此命令的访问权。



## 查看备份服务配置

运行以下 cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的默认值为 2 分钟。

## 设置备份服务同步间隔

运行以下 cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，下面将此间隔设置为 3 分钟。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

> [!IMPORTANT]
> 尽管可使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对有必要，否则您不应这样做，因为同步间隔对备份服务的性能和恢复点目标 (RPO) 有很大的影响。


## 获取特殊池的备份服务状态

运行以下 cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> 备份服务的同步状态是从一个池 (P1) 到其备份池 (P2) 进行单向定义的。从 P1 到 P2 的同步状态与从 P2 到 P1 的同步状态不同。对于 P1 到 P2，如果在同步间隔内将 P1 中所做的所有更改完全复制到 P2，则备份服务将处于“稳定”状态。如果不再将更改从 P1 同步到 P2，则备份服务处于“最终”状态。这两个状态均指示执行 cmdlet 时备份服务的快照。它不表示返回的状态之后将继续保持下去。特别是，仅在执行 cmdlet 后 P1 未生成任何更改的情况下，才一直保持“最终”状态。当作为 <strong>Invoke-CsPoolfailover</strong> 执行逻辑的一部分将 P1 置于只读模式后，P1 到 P2 的同步失败时才会出现此种情况。



## 获取有关特定池的备份关系的信息

运行以下 cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## 强制备份服务同步

运行以下 cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

