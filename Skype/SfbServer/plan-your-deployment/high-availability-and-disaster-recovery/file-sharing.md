---
title: Skype for Business Server 中的文件共享高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 了解如何使用 DFS 确保 Skype for Business Server 中文件共享的高可用性。
ms.openlocfilehash: f47d8207969063472af23d898ef8a52c2383df0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093090"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="d487d-103">Skype for Business Server 中的文件共享高可用性</span><span class="sxs-lookup"><span data-stu-id="d487d-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="d487d-104">了解如何使用 DFS 确保 Skype for Business Server 中文件共享的高可用性。</span><span class="sxs-lookup"><span data-stu-id="d487d-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="d487d-105">为了确保文件共享在 Skype for Business Server 部署中的高可用性，可以使用分布式文件系统 (DFS) 。</span><span class="sxs-lookup"><span data-stu-id="d487d-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="d487d-106">DFS 支持同一个数据中心内从一个文件服务器到另一个文件服务器的故障转移。</span><span class="sxs-lookup"><span data-stu-id="d487d-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="d487d-107">对于大型部署，建议您使用通过 DFS 配对的专用文件服务器。</span><span class="sxs-lookup"><span data-stu-id="d487d-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="d487d-108">有关 DFS 中 DFS Windows Server 2012，请参阅 [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) 。</span><span class="sxs-lookup"><span data-stu-id="d487d-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).</span></span> <span data-ttu-id="d487d-109">有关 Windows Server 2008 上的 DFS 的信息，请参阅 [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) 。</span><span class="sxs-lookup"><span data-stu-id="d487d-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)).</span></span>
  
<span data-ttu-id="d487d-110">根据您的网络规模和所需的恢复工作量，可以使用一对服务器来承载一个站点中的所有文件共享，也可以为每个前端池使用一对服务器。</span><span class="sxs-lookup"><span data-stu-id="d487d-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="d487d-111">DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。</span><span class="sxs-lookup"><span data-stu-id="d487d-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="d487d-112">DFS 服务器之间的故障转移应快速完成，但数据复制延迟可能会阻止用户在故障转移发生时继续工作。</span><span class="sxs-lookup"><span data-stu-id="d487d-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="d487d-113">如果在文件共享上使用 DFS 和数据存储至关重要，应经常备份文件共享，如每 4 到 8 小时备份一次。</span><span class="sxs-lookup"><span data-stu-id="d487d-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="d487d-114">如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="d487d-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
