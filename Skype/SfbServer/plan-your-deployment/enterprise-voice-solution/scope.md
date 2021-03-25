---
title: 在 Skype for Business Server 中定义 E9-1-1 部署的范围
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 在 Skype for Business Server 企业语音 中规划 E9-1-1 部署所必需的决策。
ms.openlocfilehash: 39397064fe525a2b1324b8ef0a0f0bb1df287653
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114568"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="c8a61-103">在 Skype for Business Server 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="c8a61-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="c8a61-104">在 Skype for Business Server 企业语音 中规划 E9-1-1 部署所必需的决策。</span><span class="sxs-lookup"><span data-stu-id="c8a61-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="c8a61-105">在配置 Skype for Business for E9-1-1 之前，你需要规划 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="c8a61-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="c8a61-106">要考虑的一些问题包括：</span><span class="sxs-lookup"><span data-stu-id="c8a61-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="c8a61-107">**贵组织关于 E9-1-1 的策略和义务是什么？**</span><span class="sxs-lookup"><span data-stu-id="c8a61-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="c8a61-108">E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。</span><span class="sxs-lookup"><span data-stu-id="c8a61-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="c8a61-109">您应咨询法律团队，以了解可能适用于在相关地理位置部署 Skype for Business 的义务。</span><span class="sxs-lookup"><span data-stu-id="c8a61-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="c8a61-110">**需要在企业内部的哪些区域启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="c8a61-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="c8a61-p103">可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。</span><span class="sxs-lookup"><span data-stu-id="c8a61-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="c8a61-113">**如何为分支站点部署 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="c8a61-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="c8a61-114">语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="c8a61-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="c8a61-115">如果您具有集中式 E-9-1-1 SIP 中继并且发生 WAN 中断，则登录的客户端可能无法从位置信息服务获取位置或无法连接到紧急服务服务提供商。</span><span class="sxs-lookup"><span data-stu-id="c8a61-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="c8a61-116">Skype for Business 提供了几个策略来处理分支机构中的语音恢复能力，包括：拥有可恢复的数据网络、在每个分支部署 SIP 中继或在中断期间将紧急呼叫推送到本地网关。</span><span class="sxs-lookup"><span data-stu-id="c8a61-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="c8a61-117">有关详细信息，请参阅[Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency)。</span><span class="sxs-lookup"><span data-stu-id="c8a61-117">For details, see [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span></span>

 <span data-ttu-id="c8a61-118">**是否为在网络外部工作的用户启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="c8a61-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="c8a61-119">自动位置获取仅适用于位于组织网络内部的客户端，因此组织需要决定是否支持在外部时从 Skype for Business 客户端拨打的 E9-1-1 呼叫。</span><span class="sxs-lookup"><span data-stu-id="c8a61-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="c8a61-120">例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？</span><span class="sxs-lookup"><span data-stu-id="c8a61-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="c8a61-121">如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="c8a61-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="c8a61-122">但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。</span><span class="sxs-lookup"><span data-stu-id="c8a61-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="c8a61-123">使用 VPN 连接到组织网络的用户的 Skype for Business 客户端可以获取内部 IP 地址信息，但由于这些地址不能用于标识用户的实际位置，因此有必要从位置信息服务中排除 VPN 子网。</span><span class="sxs-lookup"><span data-stu-id="c8a61-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="c8a61-124">**是否向美国之外的站点提供紧急呼叫路由？**</span><span class="sxs-lookup"><span data-stu-id="c8a61-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="c8a61-p106">您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="c8a61-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>