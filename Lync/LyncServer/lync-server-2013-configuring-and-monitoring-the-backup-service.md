---
title: Lync Server 2013：配置和监控备份服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a14e7a451b6d28df2663498e64cf2fb85c818352
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中配置和监控备份服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

您可以使用以下 Lync Server 命令行管理程序命令来配置和监控备份服务。

<div>


> [!NOTE]  
> 默认情况下，RTCUniversalServerAdmins 组是唯一具有运行 <STRONG>Get-CsBackupServiceStatus</STRONG> 的权限的组。 要使用此 cmdlet，请以该组的成员身份登录。 或者，可通过使用 <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet 向其他组（如 CSAdministrator）授予对此命令的访问权。



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>查看备份服务配置

运行以下 cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的默认值为 2 分钟。

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>设置备份服务同步间隔

运行以下 cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，下面将此间隔设置为 3 分钟。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> 尽管可使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对有必要，否则您不应这样做，因为同步间隔对备份服务的性能和恢复点目标 (RPO) 有很大的影响。



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>获取特殊池的备份服务状态

运行以下 cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> 备份服务的同步状态是从一个池 (P1) 到其备份池 (P2) 进行单向定义的。 从 P1 到 P2 的同步状态与从 P2 到 P1 的同步状态不同。 对于 P1 到 P2，如果在同步间隔内将 P1 中所做的所有更改完全复制到 P2，则备份服务将处于“稳定”状态。 如果不再将更改从 P1 同步到 P2，则备份服务处于“最终”状态。 这两个状态均指示执行 cmdlet 时备份服务的快照。 它不表示返回的状态之后将继续保持下去。 特别是，仅在执行 cmdlet 后 P1 未生成任何更改的情况下，才一直保持“最终”状态。 当作为 <STRONG>Invoke-CsPoolfailover</STRONG> 执行逻辑的一部分将 P1 置于只读模式后，P1 到 P2 的同步失败时才会出现此种情况。



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

