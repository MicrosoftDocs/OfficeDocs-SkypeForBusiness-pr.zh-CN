---
title: 定义业务 Server 中 Skype E9-1-1 部署范围
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 规划业务 Server 企业语音中 Skype E9-1-1 部署所需的决策。
ms.openlocfilehash: 93cb665a17f7fc1be7c26efc1065377ab82cc482
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006543"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="31bb6-103">定义业务 Server 中 Skype E9-1-1 部署范围</span><span class="sxs-lookup"><span data-stu-id="31bb6-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="31bb6-104">规划业务 Server 企业语音中 Skype E9-1-1 部署所需的决策。</span><span class="sxs-lookup"><span data-stu-id="31bb6-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="31bb6-105">为 E9-1-1 配置 Skype for Business 之前，您需要规划 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="31bb6-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="31bb6-106">要考虑的一些问题包括：</span><span class="sxs-lookup"><span data-stu-id="31bb6-106">Some of the questions to consider include:</span></span>
  
 <span data-ttu-id="31bb6-107">**贵组织的策略和法律义务 E9-1-1 是什么？**</span><span class="sxs-lookup"><span data-stu-id="31bb6-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>
  
 <span data-ttu-id="31bb6-108">E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。</span><span class="sxs-lookup"><span data-stu-id="31bb6-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="31bb6-109">您应咨询法律团队了解可能适用于您相关的地理区域中的业务的 Skype 您部署义务。</span><span class="sxs-lookup"><span data-stu-id="31bb6-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>
    
 <span data-ttu-id="31bb6-110">**需要在企业内部的哪些区域启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="31bb6-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>
  
 <span data-ttu-id="31bb6-p103">可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。</span><span class="sxs-lookup"><span data-stu-id="31bb6-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span> 
    
 <span data-ttu-id="31bb6-113">**如何为分支站点部署 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="31bb6-113">**How will you deploy E9-1-1 to branch sites?**</span></span>
  
 <span data-ttu-id="31bb6-114">语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="31bb6-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="31bb6-115">如果您已集中 E-9-1-1 SIP 中继和 WAN 中断时，发生此事件，客户端登录可能不能用于从位置信息服务获取位置，或连接到紧急服务服务提供商。</span><span class="sxs-lookup"><span data-stu-id="31bb6-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="31bb6-116">Skype for Business 提供用于处理，包括为分支机构中的语音恢复能力的多个策略： 具有可恢复的数据网络、 部署在每个分支中，SIP 中继或推送紧急呼叫到本地网关在中断期间。</span><span class="sxs-lookup"><span data-stu-id="31bb6-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="31bb6-117">有关详细信息，请参阅[规划分支站点语音恢复能力](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。</span><span class="sxs-lookup"><span data-stu-id="31bb6-117">For details, see [Planning for Branch-Site Voice Resiliency](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>
    
 <span data-ttu-id="31bb6-118">**是否为在网络外部工作的用户启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="31bb6-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>
  
 <span data-ttu-id="31bb6-119">仅适用于位于组织网络内，所以您的组织需要决定是否将支持业务时关闭内部部署的客户端发出 Skype E9-1-1 呼叫的客户端自动位置获取。</span><span class="sxs-lookup"><span data-stu-id="31bb6-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="31bb6-120">例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？</span><span class="sxs-lookup"><span data-stu-id="31bb6-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="31bb6-121">如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="31bb6-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="31bb6-122">但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。</span><span class="sxs-lookup"><span data-stu-id="31bb6-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
> [!NOTE]
> <span data-ttu-id="31bb6-123">业务客户端的用户使用 VPN 连接到组织的网络的 Skype 可以拿起内部 IP 地址信息，但这些地址不能用于标识用户的实际位置，因为它非常重要的排除 VPN 子网从位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="31bb6-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span> 
  
 <span data-ttu-id="31bb6-124">**是否向美国之外的站点提供紧急呼叫路由？**</span><span class="sxs-lookup"><span data-stu-id="31bb6-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>
  
 <span data-ttu-id="31bb6-p106">您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="31bb6-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>
    

