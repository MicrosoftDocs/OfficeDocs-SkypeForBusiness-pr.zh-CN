---
title: 配置直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置Microsoft 电话直接路由，将本地电话基础结构连接到 Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122236"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="6ded6-103">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="6ded6-103">Configure Direct Routing</span></span>

<span data-ttu-id="6ded6-104">Microsoft 电话使用系统直接路由可将本地电话基础结构连接到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6ded6-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="6ded6-105">本文列出了将受支持的本地会话边界控制器 (SBC) 连接到直接路由所需的高级步骤，以及如何将 Teams 用户配置为使用直接路由连接到公共电话交换网 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="6ded6-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="6ded6-106">本文链接到相关文章，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ded6-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="6ded6-107">有关直接路由是否是适用于组织的解决方案的信息，请参阅直接电话系统[路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="6ded6-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="6ded6-108">有关先决条件和规划部署的信息，请参阅 [规划直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="6ded6-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="6ded6-109">还可以观看以下会话，了解直接路由的好处、如何规划它以及如何部署[它：直接](https://aka.ms/teams-direct-routing)路由在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6ded6-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="6ded6-110">若要完成本文中介绍的步骤，管理员需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ded6-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="6ded6-111">有关使用 PowerShell 的信息，请参阅为计算机设置[Windows PowerShell。](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="6ded6-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="6ded6-112">在执行这些文章中的步骤之前，Microsoft 建议确认 SBC 已根据 SBC 供应商的建议进行配置：</span><span class="sxs-lookup"><span data-stu-id="6ded6-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="6ded6-113">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="6ded6-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="6ded6-114">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="6ded6-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="6ded6-115">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="6ded6-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="6ded6-116">TE-Systems (anynode) 部署文档</span><span class="sxs-lookup"><span data-stu-id="6ded6-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="6ded6-117">Metaswitch 部署文档</span><span class="sxs-lookup"><span data-stu-id="6ded6-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="6ded6-118">有关受支持的 SDC 的完整列表，请参阅通过直接路由 认证的 [会话边界控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="6ded6-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="6ded6-119">若要配置Microsoft 电话系统并允许用户使用直接路由，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6ded6-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="6ded6-120">**第 1 步**</span><span class="sxs-lookup"><span data-stu-id="6ded6-120">**Step 1.**</span></span> [<span data-ttu-id="6ded6-121">连接系统Microsoft 电话 SBC 并验证连接</span><span class="sxs-lookup"><span data-stu-id="6ded6-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="6ded6-122">**第 2 步**</span><span class="sxs-lookup"><span data-stu-id="6ded6-122">**Step 2.**</span></span> [<span data-ttu-id="6ded6-123">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="6ded6-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="6ded6-124">**第 3 步**</span><span class="sxs-lookup"><span data-stu-id="6ded6-124">**Step 3.**</span></span> [<span data-ttu-id="6ded6-125">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="6ded6-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="6ded6-126">**第 4 步**</span><span class="sxs-lookup"><span data-stu-id="6ded6-126">**Step 4.**</span></span> [<span data-ttu-id="6ded6-127">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="6ded6-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="6ded6-128">如果要为多个租户配置 SBC，则还需要阅读为多个租户[配置 SBC。](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="6ded6-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="6ded6-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="6ded6-129">Related topics</span></span>

[<span data-ttu-id="6ded6-130">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="6ded6-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="6ded6-131">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="6ded6-131">Plan Direct Routing</span></span>](direct-routing-plan.md)