---
title: Lync Server 2013：使用备份服务还原会议内容
description: Lync Server 2013：使用备份服务还原会议内容。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a0037af711948c008e74c5444373ed995f0e6e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555178"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用备份服务还原会议内容

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

如果存储在前端池的文件存储中的会议信息变得不可用，则您必须还原此信息，以便驻留在池中的用户能够保留其会议数据。如果丢失了会议数据的前端池与另一个前端池配对，您可以使用备份服务还原数据。

此外，如果整个池已失败并且您必须将其用户故障转移到备份池，则也必须执行此任务。在将这些用户故障转移回其原始池时，您也必须使用此过程将其会议内容复制回其原始池。

假定将 Pool1 与 Pool2 配对且 Pool1 中的会议数据已丢失。 您可以使用以下 cmdlet 调用备份服务以还原内容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

还原会议内容可能需要一些时间，具体取决于该内容的大小。您可以使用以下 cmdlet 检查过程状态：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

当此 cmdlet 为数据会议模块返回值“稳定状态”时，表示此过程已完成。

</div>

<span> </span>

</div>

</div>

</div>

