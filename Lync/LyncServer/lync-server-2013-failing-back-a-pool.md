---
title: Lync Server 2013：对池进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="f8fec-102">在 Lync Server 2013 中对池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="f8fec-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8fec-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f8fec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f8fec-104">在发生灾难的池重新联机后 (即在此示例中为 Pool1), 请执行以下步骤将你的部署还原到正常的工作状态。</span><span class="sxs-lookup"><span data-stu-id="f8fec-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="f8fec-105">请注意, 故障回复过程需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="f8fec-105">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="f8fec-106">作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="f8fec-106">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="f8fec-107">通过键入以下 cmdlet 对最初驻留在 Pool1 中的用户进行故障回复, 并已故障转移到 Pool2:</span><span class="sxs-lookup"><span data-stu-id="f8fec-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="f8fec-108">无需执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="f8fec-108">No other steps are necessary.</span></span> <span data-ttu-id="f8fec-109">如果您通过中央管理服务器进行了故障转移, 您可以将其保留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="f8fec-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

