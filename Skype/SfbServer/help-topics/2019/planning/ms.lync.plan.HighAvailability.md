---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 中大多数服务器角色的主高可用性方案基于服务器冗余 (通过池划分)。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
ms.openlocfilehash: 36869cedb2443d13774e8646b72a51a039683f16
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418610"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="f4b23-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="f4b23-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="f4b23-105">Skype for Business Server 中大多数服务器角色的主高可用性方案基于服务器冗余 (通过池划分)。</span><span class="sxs-lookup"><span data-stu-id="f4b23-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="f4b23-106">如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="f4b23-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="f4b23-107">Skype for business 服务器需要至少两个前端服务器才能启用高可用性。</span><span class="sxs-lookup"><span data-stu-id="f4b23-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="f4b23-108">规划工具使用以下条件来确定它是否将添加额外的服务器以支持高可用性:</span><span class="sxs-lookup"><span data-stu-id="f4b23-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="f4b23-109">如果部署包含两个或更多前端服务器, 则计划工具不会添加额外的服务器。</span><span class="sxs-lookup"><span data-stu-id="f4b23-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="f4b23-110">如果部署包含 Edge 服务器, 则会添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="f4b23-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="f4b23-111">如果部署包含持久聊天, 则计划工具将添加额外的服务器, 但不会增加池编号。</span><span class="sxs-lookup"><span data-stu-id="f4b23-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="f4b23-112">例如, 如果部署中已包含四台服务器, 则计划工具将建议添加其他服务器 (共5台服务器), 但将维护单个池。</span><span class="sxs-lookup"><span data-stu-id="f4b23-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="f4b23-113">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="f4b23-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f4b23-114">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="f4b23-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="f4b23-115">有关详细信息, 请参阅[Skype for business 到 Microsoft 团队升级](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="f4b23-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="f4b23-116">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="f4b23-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="f4b23-117">规划工具还为所有数据库添加镜像 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="f4b23-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="f4b23-118">例如, 如果有前端 SQL Server 数据库, 则计划工具将添加另一个数据库作为此数据库的镜像数据库, 并将其命名为 "前端镜像 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="f4b23-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="f4b23-119">有关为高可用性准备环境的更多详细信息, 请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b23-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

