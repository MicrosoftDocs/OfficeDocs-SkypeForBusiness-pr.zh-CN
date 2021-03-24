---
title: '高可用性 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 中大多数服务器角色的主要高可用性方案基于通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093310"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="edb47-104">高可用性 (规划工具) </span><span class="sxs-lookup"><span data-stu-id="edb47-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="edb47-105">Skype for Business Server 中大多数服务器角色的主要高可用性方案基于通过池实现的服务器冗余。</span><span class="sxs-lookup"><span data-stu-id="edb47-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="edb47-106">如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。</span><span class="sxs-lookup"><span data-stu-id="edb47-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="edb47-107">Skype for Business Server 需要至少两台前端服务器才能实现高可用性。</span><span class="sxs-lookup"><span data-stu-id="edb47-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="edb47-108">规划工具使用下列条件来确定它是否将添加额外的服务器以支持高可用性：</span><span class="sxs-lookup"><span data-stu-id="edb47-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="edb47-109">如果部署包含两台或多台前端服务器，则规划工具不会添加额外的服务器。</span><span class="sxs-lookup"><span data-stu-id="edb47-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="edb47-110">如果部署包含边缘服务器，则添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="edb47-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="edb47-111">如果部署包含持久聊天，则规划工具将添加一台额外的服务器，但不增加池数量。</span><span class="sxs-lookup"><span data-stu-id="edb47-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="edb47-112">例如，如果部署已包含四台服务器，规划工具将建议为总共 5 台服务器 (添加一个额外的服务器) 但会维护一个池。</span><span class="sxs-lookup"><span data-stu-id="edb47-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="edb47-113">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="edb47-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="edb47-114">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="edb47-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="edb47-115">有关详细信息，请参阅 [Skype for Business 到 Microsoft Teams 的升级](/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="edb47-115">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="edb47-116">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="edb47-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="edb47-117">规划工具还会添加一个SQL数据库的镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="edb47-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="edb47-118">例如，如果存在前端 SQL Server数据库，则规划工具将另一个数据库添加为此数据库的镜像数据库，并将其名称为"前端镜像SQL数据库。</span><span class="sxs-lookup"><span data-stu-id="edb47-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="edb47-119">有关为高可用性准备环境的详细信息，请参阅 Plan for [high availability and disaster recovery in Skype for Business Server。](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="edb47-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
