---
title: 在 Skype for Business Server 2015 中定义 E9-1-1 部署的范围
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 规划业务服务器企业语音在 Skype E9-1-1 部署所需的决策。
ms.openlocfilehash: f81a2c56642557bf92a965de025aecbdbcadadcd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="ce042-103">在 Skype for Business Server 2015 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="ce042-103">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ce042-104">规划业务服务器企业语音在 Skype E9-1-1 部署所需的决策。</span><span class="sxs-lookup"><span data-stu-id="ce042-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ce042-105">在 E9-1-1 的配置 Skype 业务之前，您需要规划部署 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="ce042-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="ce042-106">要考虑的一些问题包括：</span><span class="sxs-lookup"><span data-stu-id="ce042-106">Some of the questions to consider include:</span></span>
  
 <span data-ttu-id="ce042-107">**您的组织策略和 E9-1-1 的法律义务是什么？**</span><span class="sxs-lookup"><span data-stu-id="ce042-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>
  
 <span data-ttu-id="ce042-108">E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。</span><span class="sxs-lookup"><span data-stu-id="ce042-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="ce042-109">您应咨询法律团队了解适用于您的部署的业务相关的地区的 Skype 的义务。</span><span class="sxs-lookup"><span data-stu-id="ce042-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>
    
 <span data-ttu-id="ce042-110">**需要在企业内部的哪些区域启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="ce042-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>
  
 <span data-ttu-id="ce042-p103">可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。</span><span class="sxs-lookup"><span data-stu-id="ce042-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span> 
    
 <span data-ttu-id="ce042-113">**如何为分支站点部署 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="ce042-113">**How will you deploy E9-1-1 to branch sites?**</span></span>
  
 <span data-ttu-id="ce042-114">语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="ce042-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="ce042-115">如果您已集中了 E-9-1-1 的 SIP 中继和 WAN 故障发生，登录的客户端可能无法获取位置信息服务中的位置或连接到紧急服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ce042-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="ce042-116">Skype 业务提供几种策略，用于处理语音留存能力在分支机构，其中包括： 具有弹性数据网络、 部署在每个分支中，SIP 中继或推出紧急电话本地网关在停机期间。</span><span class="sxs-lookup"><span data-stu-id="ce042-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="ce042-117">有关详细信息，请参阅[规划分支站点语音留存能力](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ce042-117">For details, see [Planning for Branch-Site Voice Resiliency](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>
    
 <span data-ttu-id="ce042-118">**是否为在网络外部工作的用户启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="ce042-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>
  
 <span data-ttu-id="ce042-119">自动位置收购是仅用于客户端位于组织网络，使您的组织需要决定它是否将支持 E9-1-1 电话 Skype 业务时关闭部署的客户端。</span><span class="sxs-lookup"><span data-stu-id="ce042-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="ce042-120">例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？</span><span class="sxs-lookup"><span data-stu-id="ce042-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="ce042-121">如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="ce042-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="ce042-122">但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。</span><span class="sxs-lookup"><span data-stu-id="ce042-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ce042-123">业务客户端的用户通过 VPN 连接到组织网络的 Skype 可领取内部 IP 地址信息，但由于不能使用这些地址来标识用户的实际位置，是非常重要的排除 VPN 网从位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="ce042-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span> 
  
 <span data-ttu-id="ce042-124">**是否向美国之外的站点提供紧急呼叫路由？**</span><span class="sxs-lookup"><span data-stu-id="ce042-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>
  
 <span data-ttu-id="ce042-p106">您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="ce042-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>
    

