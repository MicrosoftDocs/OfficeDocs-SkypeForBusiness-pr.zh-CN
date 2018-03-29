---
title: 高可用性 （规划工具）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: 大多数服务器角色中业务服务器 2015年的 Skype 的主要的高可用性方案基于通过池的服务器冗余。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
ms.openlocfilehash: 8441db5ee4a84c573ed6a1642473b827382e4654
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="d818e-104">高可用性 （规划工具）</span><span class="sxs-lookup"><span data-stu-id="d818e-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="d818e-105">大多数服务器角色中业务服务器 2015年的 Skype 的主要的高可用性方案基于通过池的服务器冗余。</span><span class="sxs-lookup"><span data-stu-id="d818e-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="d818e-106">如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="d818e-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="d818e-107">Skype 的业务服务器 2015年所需至少两个前端服务器实现高可用性。</span><span class="sxs-lookup"><span data-stu-id="d818e-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="d818e-108">规划工具使用以下条件来确定它将添加额外的服务器来支持高可用性：</span><span class="sxs-lookup"><span data-stu-id="d818e-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="d818e-109">如果部署中包含两个或多个前端服务器，规划工具将不会添加额外的服务器。</span><span class="sxs-lookup"><span data-stu-id="d818e-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="d818e-110">如果部署包含边缘服务器，添加额外的服务器。</span><span class="sxs-lookup"><span data-stu-id="d818e-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="d818e-111">如果部署中包含持久聊天，规划工具将添加额外的服务器，但不是增加池数。</span><span class="sxs-lookup"><span data-stu-id="d818e-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="d818e-112">例如，如果已部署包含四个服务器，规划工具将建议添加另一服务器 （总共五个服务器），但将保持单个共用池。</span><span class="sxs-lookup"><span data-stu-id="d818e-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="d818e-113">规划工具还会添加镜像 SQL 数据库的所有数据库。</span><span class="sxs-lookup"><span data-stu-id="d818e-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="d818e-114">例如，如果前结束 SQL Server 数据库，规划工具将其他数据库添加为镜像数据库中为此并将其命名为"前端镜像 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="d818e-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="d818e-115">准备您的环境以实现高可用性的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d818e-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

