---
title: Lync Server 2013：文件共享高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf27a7316494d24127f65309bdef347b558fade5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="3135c-102">Lync Server 2013 中的文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="3135c-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3135c-103">_**上次修改的主题：** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="3135c-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="3135c-104">为确保单个数据中心内的 Lync Server 文件共享具有高可用性，您可以使用分布式文件系统（DFS）。</span><span class="sxs-lookup"><span data-stu-id="3135c-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="3135c-105">DFS 支持同一个数据中心内从一个文件服务器到另一个文件服务器的故障转移。</span><span class="sxs-lookup"><span data-stu-id="3135c-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="3135c-106">对于大型部署，建议您使用通过 DFS 配对的专用文件服务器。</span><span class="sxs-lookup"><span data-stu-id="3135c-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="3135c-107">根据您的网络规模和所需的恢复工作量，可以使用一对服务器来承载一个站点中的所有文件共享，也可以为每个前端池使用一对服务器。</span><span class="sxs-lookup"><span data-stu-id="3135c-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="3135c-p102">DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。DFS 服务器之间的故障转移应快速完成，但在出现故障转移时，数据复制延迟可能会阻止用户继续工作。</span><span class="sxs-lookup"><span data-stu-id="3135c-p102">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment. The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="3135c-p103">如果需要在文件共享上使用 DFS 和数据存储，则应经常备份文件共享，如每 4 小时到 8 小时备份一次。如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="3135c-p103">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

