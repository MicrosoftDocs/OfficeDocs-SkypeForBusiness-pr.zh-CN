---
title: 直接路由配置媒体绕过
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 阅读本主题可了解如何配置媒体绕过与电话系统直接路由。
ms.openlocfilehash: 405f71fd0a1e0ea3e8fec6ee1061786c93fabf1b
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631018"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="a3e45-103">直接路由配置媒体绕过</span><span class="sxs-lookup"><span data-stu-id="a3e45-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="a3e45-104">配置媒体绕过直接路由之前，请确保您已阅读[规划媒体绕过直接路由](direct-routing-plan-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e45-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="a3e45-105">若要启用媒体绕过，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="a3e45-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="a3e45-106">请确保您选择的会话边界控制器 (SBC) 供应商支持媒体绕过功能，并提供有关如何配置说明上 SBC 绕过。</span><span class="sxs-lookup"><span data-stu-id="a3e45-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="a3e45-107">请参阅证书页上，若要了解有关 SBCs，哪些与支持媒体绕过，以及有关说明。</span><span class="sxs-lookup"><span data-stu-id="a3e45-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="a3e45-108">您需要使用以下命令中继上的媒体绕过打开：**集 CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="a3e45-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="a3e45-109">请确保，打开所需的端口。</span><span class="sxs-lookup"><span data-stu-id="a3e45-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="a3e45-110">从非绕过中继迁移到启用绕过功能的中继</span><span class="sxs-lookup"><span data-stu-id="a3e45-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="a3e45-111">您可以同时切换所有用户，也可以实现分阶段接近 （推荐）。</span><span class="sxs-lookup"><span data-stu-id="a3e45-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="a3e45-112">**同时切换所有用户。**</span><span class="sxs-lookup"><span data-stu-id="a3e45-112">**Switch all users at once.**</span></span> <span data-ttu-id="a3e45-113">如果满足所有条件，您可以打开绕过模式。</span><span class="sxs-lookup"><span data-stu-id="a3e45-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="a3e45-114">但是，将同时切换所有生产用户。</span><span class="sxs-lookup"><span data-stu-id="a3e45-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="a3e45-115">因为最初配置中继和端口时，可能会遇到的一些问题，可能会影响您的生产用户体验。</span><span class="sxs-lookup"><span data-stu-id="a3e45-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="a3e45-116">**分阶段方法。（推荐）**。</span><span class="sxs-lookup"><span data-stu-id="a3e45-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="a3e45-117">创建新的中继 （具有不同的端口） 相同的 SBC、 测试，并更改为指向新的中继的用户的联机语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="a3e45-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="a3e45-118">这是建议的方法，因为它允许更平稳转换和不间断的用户体验。</span><span class="sxs-lookup"><span data-stu-id="a3e45-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="a3e45-119">此方法需要配置的 SBC、 新的 FQDN 名称和防火墙的配置。</span><span class="sxs-lookup"><span data-stu-id="a3e45-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="a3e45-120">请注意，您将需要确保您的证书支持两个中继。</span><span class="sxs-lookup"><span data-stu-id="a3e45-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="a3e45-121">在 SAN，您需要有两个名称 （**sbc1.contoso.com**和**sbc2.contoso.com**） 或拥有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="a3e45-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![从非绕过中继迁移到启用绕过功能的中继）](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="a3e45-123">有关如何配置中继和执行迁移的说明，请参阅从您的 SBC 供应商的文档：</span><span class="sxs-lookup"><span data-stu-id="a3e45-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="a3e45-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a3e45-124">AudioCodes</span></span>
- <span data-ttu-id="a3e45-125">功能区</span><span class="sxs-lookup"><span data-stu-id="a3e45-125">Ribbon</span></span>
- <span data-ttu-id="a3e45-126">TE 系统 (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="a3e45-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="a3e45-127">此时该通知后，以下 SBCs 经全面测试和认证能够处理媒体绕过功能：</span><span class="sxs-lookup"><span data-stu-id="a3e45-127">At the moment of this announcement, the following SBCs are fully tested and certified to work with media bypass:</span></span>

- <span data-ttu-id="a3e45-128">AudioCodes 9000 V7.20A.204.222，AudioCodes M800B SBC / V7.20A.250.003</span><span class="sxs-lookup"><span data-stu-id="a3e45-128">AudioCodes 9000 V7.20A.204.222, AudioCodes M800B-SBC/ V7.20A.250.003</span></span>

-   <span data-ttu-id="a3e45-129">功能区</span><span class="sxs-lookup"><span data-stu-id="a3e45-129">Ribbon</span></span>
    - <span data-ttu-id="a3e45-130">™ 5210 v06.02.xx xxx</span><span class="sxs-lookup"><span data-stu-id="a3e45-130">5210 v06.02.xx-xxx</span></span> 
    - <span data-ttu-id="a3e45-131">5400，v06.02.xx xxx</span><span class="sxs-lookup"><span data-stu-id="a3e45-131">5400, v06.02.xx-xxx</span></span>
    - <span data-ttu-id="a3e45-132">5110，v06.02.xx xxx</span><span class="sxs-lookup"><span data-stu-id="a3e45-132">5110, v06.02.xx-xxx</span></span>

-   <span data-ttu-id="a3e45-133">TE 系统 AnyNode v 3.16.2</span><span class="sxs-lookup"><span data-stu-id="a3e45-133">TE-System AnyNode v 3.16.2</span></span> 


## <a name="see-also"></a><span data-ttu-id="a3e45-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e45-134">See also</span></span>

[<span data-ttu-id="a3e45-135">规划媒体绕过直接路由</span><span class="sxs-lookup"><span data-stu-id="a3e45-135">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



