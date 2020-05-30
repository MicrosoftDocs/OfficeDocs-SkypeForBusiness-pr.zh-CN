---
title: 使用直接路由配置媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用电话系统直接路由为 Microsoft 团队配置媒体旁路，方法是同时切换所有用户或实施分阶段接近（推荐）。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416892"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="149a3-103">使用直接路由配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="149a3-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="149a3-104">在使用直接路由配置媒体旁路之前，请确保具有[直接路由的媒体旁路计划](direct-routing-plan-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="149a3-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="149a3-105">若要打开媒体绕过，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="149a3-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="149a3-106">确保你的会话边框控制器（SBC）供应商选择支持媒体旁路，并提供有关如何在 SBC 上配置旁路的说明。</span><span class="sxs-lookup"><span data-stu-id="149a3-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="149a3-107">请参阅证书页面，了解有关 SBCs、支持媒体旁路的信息以及相关说明。</span><span class="sxs-lookup"><span data-stu-id="149a3-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="149a3-108">您需要使用以下命令打开 trunk 上的媒体旁路： **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="149a3-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="149a3-109">请确保打开所需的端口。</span><span class="sxs-lookup"><span data-stu-id="149a3-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="149a3-110">从非绕过中继迁移到绕过启用中继</span><span class="sxs-lookup"><span data-stu-id="149a3-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="149a3-111">您可以一次切换所有用户，也可以实现分阶段的接近（推荐）。</span><span class="sxs-lookup"><span data-stu-id="149a3-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="149a3-112">**一次切换所有用户。**</span><span class="sxs-lookup"><span data-stu-id="149a3-112">**Switch all users at once.**</span></span> <span data-ttu-id="149a3-113">如果满足所有条件，则可以打开 "绕过" 模式。</span><span class="sxs-lookup"><span data-stu-id="149a3-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="149a3-114">但是，你的所有生产用户将同时进行切换。</span><span class="sxs-lookup"><span data-stu-id="149a3-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="149a3-115">由于最初配置中继和端口时可能会遇到某些问题，因此你的生产用户体验可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="149a3-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="149a3-116">**分阶段方法。（推荐）**。</span><span class="sxs-lookup"><span data-stu-id="149a3-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="149a3-117">为同一 SBC （具有不同端口）创建新的主干，对其进行测试，并更改用户的联机语音路由策略，以指向新的主干。</span><span class="sxs-lookup"><span data-stu-id="149a3-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="149a3-118">这是推荐的方法，因为它允许更平稳的切换和无中断的用户体验。</span><span class="sxs-lookup"><span data-stu-id="149a3-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="149a3-119">此方法需要使用 SBC、新的 FQDN 名称和防火墙的配置。</span><span class="sxs-lookup"><span data-stu-id="149a3-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="149a3-120">注意你需要确保你的证书支持这两个中继。</span><span class="sxs-lookup"><span data-stu-id="149a3-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="149a3-121">在 SAN 中，你需要具有两个名称（**sbc1.contoso.com**和**sbc2.contoso.com**）或具有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="149a3-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![从非绕过的中继迁移到绕过启用的中继）](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="149a3-123">有关如何配置中继和执行迁移的说明，请参阅来自 SBC 供应商的文档：</span><span class="sxs-lookup"><span data-stu-id="149a3-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="149a3-124">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="149a3-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="149a3-125">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="149a3-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="149a3-126">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="149a3-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="149a3-127">TE-系统（anynode）部署文档</span><span class="sxs-lookup"><span data-stu-id="149a3-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="149a3-128">有关直接路由认证的会话边框控制器（SBCs）的列表，请参阅为[直接路由认证的会话 Broder 控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="149a3-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="149a3-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="149a3-129">Related topics</span></span>

[<span data-ttu-id="149a3-130">使用直接路由规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="149a3-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



