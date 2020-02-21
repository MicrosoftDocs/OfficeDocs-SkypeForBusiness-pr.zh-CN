---
title: Lync Server 2013： ABC 池故障转移的备份先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd6bd22b29cd5031e83f0e8e8a09755c730be64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013 中的 ABC 池故障转移的备份先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-26_

若要获取使用 ABC 池故障转移过程的最大好处，必须在发生灾难和故障转移之前执行某些备份：

  - 您必须使用**CsLISConfiguration** cmdlet 定期备份池 A 中的位置信息服务（.lis）配置数据。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - 您必须使用**CsRgsConfiguration** cmdlet 定期备份 pool A 中的响应组配置数据。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    通常，建议您执行日常备份，但如果您要进行大量更改，那么您可能希望安排更为频繁的备份。 灾难发生时可以丢失的信息量取决于备份的频率，以及更改的频率和数量的情况。
    
    响应组应用程序只能为每个池存储一组应用程序级别的设置。 可以通过**CsRgsConfiguration** cmdlet 访问这些设置。 这些设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理的电话拨入式宽限期和呼叫上下文配置。 通过使用**ReplaceExistingSettings**参数，可以通过**CsRgsConfiguration** cmdlet 将这些设置从一个池传输到另一个池，但此操作将替代目标池中的任何应用程序级设置。
    
    <div>
    

    > [!TIP]  
    > 在一个单独的位置，保留已用于配置响应组应用程序的所有原始音频文件的备份副本（即任何录制或保留音乐的文件）。

    
    </div>
    
    如果已为池中的呼叫寄存上载了任何自定义的已保留音乐文件，则应在其他位置保留这些文件的副本。 这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或清除，这些文件将会丢失。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > 呼叫寄存应用程序只能为每个池存储一组设置和一个自定义的音乐保留音频文件。 可以通过<STRONG>CsCpsConfiguration</STRONG> cmdlet 访问这些设置。 由于呼叫寄存的灾难恢复机制依赖于备份池的呼叫寄存应用程序，因此在发生灾难时不会备份或保留主池的设置。 如果主池丢失，则无法恢复这些设置，并且在部署新池以替换主池时，将需要重新配置呼叫寄存设置和任何自定义的保持音乐音频文件。

    
    </div>

  - 如果将任何公告配置为 "未分配号码语音" 功能的一部分，我们建议您将在初始配置期间使用的任何原始音频文件的副本保留在另一个位置。 如果不执行此操作，则可以在导入音频文件的服务器或池的文件存储中获取已配置的音频文件的副本。 这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或清除，这些文件将会丢失。 若要从服务器或池的文件存储中复制用于配置未分配号码语音功能的所有音频文件，请使用：
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - 如果您已监视和存档池中的数据库，则应使用 SQL Server 管理工具对其进行备份。 在 ABC 故障转移过程中，如果监视和存档数据库在池 A 中并置，则不会保留这些数据库，因为这些数据库不是通过 Lync Server 备份服务备份的。

</div>

<span> </span>

</div>

</div>

</div>

