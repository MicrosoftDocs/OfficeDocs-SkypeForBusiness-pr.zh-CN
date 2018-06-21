---
title: 高可用性 （规划工具）
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype 业务服务器中的大多数服务器角色的主高可用性方案基于通过池服务器冗余性。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
ms.openlocfilehash: 9948fbc4f1daff73afa020b83357a26c185d7785
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19977262"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="3a5d7-104">高可用性 （规划工具）</span><span class="sxs-lookup"><span data-stu-id="3a5d7-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="3a5d7-105">Skype 业务服务器中的大多数服务器角色的主高可用性方案基于通过池服务器冗余性。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="3a5d7-106">如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="3a5d7-107">Skype 业务服务器以实现高可用性要求至少两个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="3a5d7-108">规划工具使用下列条件确定是否才能支持高可用性，它将添加额外的服务器：</span><span class="sxs-lookup"><span data-stu-id="3a5d7-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="3a5d7-109">如果部署包含两个或多个前端服务器，规划工具不添加额外的服务器。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="3a5d7-110">如果部署包含边缘服务器，添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="3a5d7-111">如果部署包含持久聊天，规划工具将添加额外的服务器，但会增加池数。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="3a5d7-112">例如，如果已部署包含四台服务器，规划工具将建议添加其他服务器 （总共五台服务器），但将保持单个池。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="3a5d7-113">规划工具还添加镜像 SQL 数据库的所有数据库。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="3a5d7-114">例如，如果没有前端 SQL 服务器数据库，规划工具将作为此镜像数据库中添加其他数据库并将其命名为"前端镜像 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="3a5d7-115">有关准备您的环境的高可用性的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="3a5d7-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

