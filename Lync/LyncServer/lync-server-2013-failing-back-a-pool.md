---
title: Lync Server 2013：对池进行故障回复
description: Lync Server 2013：对池进行故障回复。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567738"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="431c1-103">在 Lync Server 2013 中对池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="431c1-103">Failing back a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="431c1-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="431c1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="431c1-105">在经历灾难的池恢复联机（即此示例中的 Pool1）后，执行以下步骤来使部署恢复常规工作状态。</span><span class="sxs-lookup"><span data-stu-id="431c1-105">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="431c1-p101">请注意，故障回复过程需要几分钟时间才能完成。一个 20,000 个用户的池需要占用 60 分钟的时间，可以此为参考。</span><span class="sxs-lookup"><span data-stu-id="431c1-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="431c1-108">通过键入以下 cmdlet 返回到最初驻留在 Pool1 中并已故障转移到 Pool2 的用户：</span><span class="sxs-lookup"><span data-stu-id="431c1-108">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="431c1-109">无需执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="431c1-109">No other steps are necessary.</span></span> <span data-ttu-id="431c1-110">如果对中央管理服务器进行了故障转移，则可以将其保留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="431c1-110">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

