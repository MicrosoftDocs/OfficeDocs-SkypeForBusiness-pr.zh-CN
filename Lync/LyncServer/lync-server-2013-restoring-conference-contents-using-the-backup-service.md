---
title: Lync Server 2013：使用备份服务还原会议内容
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用备份服务还原会议内容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

如果在前端池的文件存储中存储的会议信息不可用。 您必须还原此信息, 以便驻留在该池中的用户保留其会议数据。 如果已丢失会议数据的前端池与另一个前端池配对, 则可以使用备份服务还原数据。

如果整个池出现故障, 并且你必须将其用户故障转移到备份池, 还必须执行此任务。 当这些用户故障恢复到其原始池时, 必须使用此过程将其会议内容复制回其原始池。

假设 Pool1 与 Pool2 配对, 并且 Pool1 中的会议数据丢失。 你可以使用以下 cmdlet 调用备份服务来还原内容:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

还原会议内容可能需要一些时间, 具体取决于它们的大小。 你可以使用以下 cmdlet 检查进程状态:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

当此 cmdlet 为数据会议模块返回稳定状态的值时, 将执行此过程。

</div>

<span> </span>

</div>

</div>

</div>

