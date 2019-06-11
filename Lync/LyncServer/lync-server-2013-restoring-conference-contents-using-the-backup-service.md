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

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="38839-102">在 Lync Server 2013 中使用备份服务还原会议内容</span><span class="sxs-lookup"><span data-stu-id="38839-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38839-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38839-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38839-104">如果在前端池的文件存储中存储的会议信息不可用。</span><span class="sxs-lookup"><span data-stu-id="38839-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="38839-105">您必须还原此信息, 以便驻留在该池中的用户保留其会议数据。</span><span class="sxs-lookup"><span data-stu-id="38839-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="38839-106">如果已丢失会议数据的前端池与另一个前端池配对, 则可以使用备份服务还原数据。</span><span class="sxs-lookup"><span data-stu-id="38839-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="38839-107">如果整个池出现故障, 并且你必须将其用户故障转移到备份池, 还必须执行此任务。</span><span class="sxs-lookup"><span data-stu-id="38839-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="38839-108">当这些用户故障恢复到其原始池时, 必须使用此过程将其会议内容复制回其原始池。</span><span class="sxs-lookup"><span data-stu-id="38839-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="38839-109">假设 Pool1 与 Pool2 配对, 并且 Pool1 中的会议数据丢失。</span><span class="sxs-lookup"><span data-stu-id="38839-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="38839-110">你可以使用以下 cmdlet 调用备份服务来还原内容:</span><span class="sxs-lookup"><span data-stu-id="38839-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="38839-111">还原会议内容可能需要一些时间, 具体取决于它们的大小。</span><span class="sxs-lookup"><span data-stu-id="38839-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="38839-112">你可以使用以下 cmdlet 检查进程状态:</span><span class="sxs-lookup"><span data-stu-id="38839-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="38839-113">当此 cmdlet 为数据会议模块返回稳定状态的值时, 将执行此过程。</span><span class="sxs-lookup"><span data-stu-id="38839-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

