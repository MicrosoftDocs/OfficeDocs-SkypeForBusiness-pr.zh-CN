---
title: 为业务 Server Skype 中文件共享高可用性
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 了解业务服务器，使用 DFS 确保您 Skype 中的文件共享的高可用性。
ms.openlocfilehash: 0b5d2f577775635b95add15dd7b7576ca24c883f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214066"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="e2ee4-103">为业务 Server Skype 中文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="e2ee4-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="e2ee4-104">了解业务服务器，使用 DFS 确保您 Skype 中的文件共享的高可用性。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="e2ee4-105">若要确保您 Skype 业务服务器部署中的文件共享的高可用性，您可以使用分布式文件系统 (DFS)。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="e2ee4-106">DFS 支持从一台文件服务器故障转移到相同数据中心内的其他文件服务器。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="e2ee4-107">对于大规模部署，我们建议您使用通过 DFS 配对的专用文件服务器。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="e2ee4-108">Windows Server 2012 中的 DFS 的详细信息，请参阅[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="e2ee4-109">Windows Server 2008 上的 DFS 的信息，请参阅[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="e2ee4-110">根据您的网络大小和所需的恢复能力量，可以使用一对服务器来承载网站中的所有文件共享或使用一对每个前端池。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="e2ee4-111">DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="e2ee4-112">DFS 服务器之间进行故障转移，应该完成快速，但数据复制延迟可能阻止用户能够在发生故障转移时继续正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="e2ee4-p103">如果需要在文件共享上使用 DFS 和数据存储，则应经常备份文件共享，如每 4 小时到 8 小时备份一次。如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="e2ee4-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

