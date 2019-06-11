---
title: Lync Server 2013：配置和监控备份服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中配置和监控备份服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

你可以使用以下 Lync Server Management Shell 命令来配置和监视备份服务。

<div>


> [!NOTE]  
> RTCUniversalServerAdmins 组是唯一具有运行<STRONG>CsBackupServiceStatus</STRONG>默认权限的组。 若要使用此 cmdlet, 请以该组的成员身份登录。 或者, 你可以使用<STRONG>CsBackupServiceConfiguration</STRONG> cmdlet 将对此命令的访问权限授予其他组 (例如 CSAdministrator)。



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>查看备份服务配置

运行以下 cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的默认值是2分钟。

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>设置备份服务同步间隔

运行以下 cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如, 下面的时间间隔设置为3分钟。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> 虽然你可以使用此 cmdlet 更改备份服务的默认同步间隔, 但除非绝对必要, 否则不应执行此操作, 因为同步间隔对备份服务性能和恢复点目标 (RPO) 有很高的影响。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>获取特定池的备份服务状态

运行以下 cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> 备份服务同步状态是从池 (P1) unidirectionally 到其备份池 (P2) 定义的。 从 P1 到 P2 的同步状态可能与从 P2 到 P1 的同步状态不同。 对于 P2 到 P2, 如果在 P1 中进行的所有更改都在同步间隔内完全复制到 P2, 则备份服务处于 "稳定" 状态。 如果没有其他更改要从 P1 同步到 P2, 它将处于 "最终状态" 状态。 这两种状态表示执行 cmdlet 时备份服务的快照。 这并不意味着返回的状态将保持为后的状态。 特别是, 仅当在执行 cmdlet 后 P1 不会生成任何更改时, "最终" 状态才会继续保持。 在将 p1 置于只读模式 (作为<STRONG>CsPoolfailover</STRONG>执行逻辑的一部分) 之后, p1 被置于只读模式下时, 此情况为 true。



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>获取有关特定池的备份关系的信息

运行以下 cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>强制备份服务同步

运行以下 cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

