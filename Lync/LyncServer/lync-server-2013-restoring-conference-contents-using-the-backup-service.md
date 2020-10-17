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
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="5d774-103">在 Lync Server 2013 中使用备份服务还原会议内容</span><span class="sxs-lookup"><span data-stu-id="5d774-103">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d774-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5d774-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5d774-p101">如果存储在前端池的文件存储中的会议信息变得不可用，则您必须还原此信息，以便驻留在池中的用户能够保留其会议数据。如果丢失了会议数据的前端池与另一个前端池配对，您可以使用备份服务还原数据。</span><span class="sxs-lookup"><span data-stu-id="5d774-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="5d774-p102">此外，如果整个池已失败并且您必须将其用户故障转移到备份池，则也必须执行此任务。在将这些用户故障转移回其原始池时，您也必须使用此过程将其会议内容复制回其原始池。</span><span class="sxs-lookup"><span data-stu-id="5d774-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="5d774-110">假定将 Pool1 与 Pool2 配对且 Pool1 中的会议数据已丢失。</span><span class="sxs-lookup"><span data-stu-id="5d774-110">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="5d774-111">您可以使用以下 cmdlet 调用备份服务以还原内容：</span><span class="sxs-lookup"><span data-stu-id="5d774-111">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="5d774-p104">还原会议内容可能需要一些时间，具体取决于该内容的大小。您可以使用以下 cmdlet 检查过程状态：</span><span class="sxs-lookup"><span data-stu-id="5d774-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="5d774-114">当此 cmdlet 为数据会议模块返回值“稳定状态”时，表示此过程已完成。</span><span class="sxs-lookup"><span data-stu-id="5d774-114">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

