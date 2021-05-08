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
description: 了解如何通过一次切换所有用户电话系统 Microsoft Teams或实施分阶段的按建议方法 (媒体旁路) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416892"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="b63bc-103">使用直接路由配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b63bc-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="b63bc-104">使用直接路由配置媒体旁路之前，请确保已阅读使用直接路由 [规划媒体旁路](direct-routing-plan-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="b63bc-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="b63bc-105">若要启用媒体旁路，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="b63bc-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="b63bc-106">请确保选择的 SBC (会话) 控制器支持媒体旁路，并说明如何在 SBC 上配置旁路。</span><span class="sxs-lookup"><span data-stu-id="b63bc-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="b63bc-107">请参阅认证页面，了解支持媒体绕过的 SDC，以及说明。</span><span class="sxs-lookup"><span data-stu-id="b63bc-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="b63bc-108">需使用以下命令在中继上打开媒体旁路 **：Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true。**</span><span class="sxs-lookup"><span data-stu-id="b63bc-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="b63bc-109">确保打开所需的端口。</span><span class="sxs-lookup"><span data-stu-id="b63bc-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="b63bc-110">从未绕过的中继迁移到已启用绕过的中继</span><span class="sxs-lookup"><span data-stu-id="b63bc-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="b63bc-111">可以一次切换所有用户，也可以实施分阶段的 (建议) 。</span><span class="sxs-lookup"><span data-stu-id="b63bc-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="b63bc-112">**一次切换所有用户。**</span><span class="sxs-lookup"><span data-stu-id="b63bc-112">**Switch all users at once.**</span></span> <span data-ttu-id="b63bc-113">如果满足所有条件，可以打开绕过模式。</span><span class="sxs-lookup"><span data-stu-id="b63bc-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="b63bc-114">但是，将同时切换所有生产用户。</span><span class="sxs-lookup"><span data-stu-id="b63bc-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="b63bc-115">由于在配置中继和端口时，最初可能会遇到一些问题，因此生产用户体验可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="b63bc-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="b63bc-116">**分阶段方法。 (建议) 。**</span><span class="sxs-lookup"><span data-stu-id="b63bc-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="b63bc-117">为同一 SBC (使用不同的端口) ，测试它，并更改用户的联机语音路由策略以指向新的中继。</span><span class="sxs-lookup"><span data-stu-id="b63bc-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="b63bc-118">这是建议的方法，因为它可实现更流畅的过渡和不间断的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b63bc-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="b63bc-119">此方法需要配置 SBC、新的 FQDN 名称和防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="b63bc-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="b63bc-120">请注意，需要确保证书支持这两个中继。</span><span class="sxs-lookup"><span data-stu-id="b63bc-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="b63bc-121">在 SAN 中，需要具有两个名称 (sbc1.contoso.com **和** **sbc2.contoso.com)** 或具有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="b63bc-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![从非绕过的中继迁移到已启用旁路的中继) ](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="b63bc-123">有关如何配置中继和执行迁移的说明，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="b63bc-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="b63bc-124">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="b63bc-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="b63bc-125">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="b63bc-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="b63bc-126">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="b63bc-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="b63bc-127">TE-Systems (anynode) 部署文档</span><span class="sxs-lookup"><span data-stu-id="b63bc-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="b63bc-128">有关已通过直接路由认证的 (SDC 的会话边界控制器) 列表，请参阅通过直接路由 认证的会话 [Broder](direct-routing-border-controllers.md)控制器列表。</span><span class="sxs-lookup"><span data-stu-id="b63bc-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="b63bc-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="b63bc-129">Related topics</span></span>

[<span data-ttu-id="b63bc-130">使用直接路由规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b63bc-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



