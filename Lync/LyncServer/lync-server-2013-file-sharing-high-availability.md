---
title: 'Lync Server 2013: 文件共享高可用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="6c73b-102">Lync Server 2013 中的文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="6c73b-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c73b-103">_**主题上次修改时间:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="6c73b-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="6c73b-104">为确保在单个数据中心内 Lync Server 文件共享的高可用性, 您可以使用分布式文件系统 (DFS)。</span><span class="sxs-lookup"><span data-stu-id="6c73b-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="6c73b-105">DFS 支持从一台文件服务器故障转移到相同数据中心内的其他文件服务器。</span><span class="sxs-lookup"><span data-stu-id="6c73b-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="6c73b-106">对于大规模部署，我们建议您使用通过 DFS 配对的专用文件服务器。</span><span class="sxs-lookup"><span data-stu-id="6c73b-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="6c73b-107">根据你的网络大小以及所需的复原量, 你可以使用一对服务器来托管网站中的所有文件共享, 或者对每个前端池使用一对。</span><span class="sxs-lookup"><span data-stu-id="6c73b-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="6c73b-108">DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。</span><span class="sxs-lookup"><span data-stu-id="6c73b-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="6c73b-109">应快速完成 DFS 服务器之间的故障转移, 但数据复制延迟可能会阻止用户在发生故障转移时继续进行工作。</span><span class="sxs-lookup"><span data-stu-id="6c73b-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="6c73b-110">如果你在文件共享上使用 DFS 和数据存储非常重要, 应经常备份文件共享, 例如每4到8小时。</span><span class="sxs-lookup"><span data-stu-id="6c73b-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="6c73b-111">如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="6c73b-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

