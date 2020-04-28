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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft Phone 系统直接路由以将本地电话基础结构连接到 Microsoft 团队。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904824"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="04a34-103">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="04a34-103">Configure Direct Routing</span></span>

<span data-ttu-id="04a34-104">Microsoft 手机系统直接路由使你能够将本地电话基础结构连接到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="04a34-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="04a34-105">本文列出了将受支持的本地会话边界控制器（SBC）连接到直接路由以及如何将团队用户配置为使用直接路由连接到公共交换电话网络（PSTN）所需的高级别步骤。</span><span class="sxs-lookup"><span data-stu-id="04a34-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="04a34-106">本文将链接到相关文章以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="04a34-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="04a34-107">有关直接路由选择是否适合你的组织的信息，请参阅[手机系统直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="04a34-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="04a34-108">有关先决条件和规划部署的信息，请参阅[规划直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="04a34-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="04a34-109">你还可以观看以下会话，了解直接路由的好处、如何为其规划以及如何部署它：[在 Microsoft 团队中直接路由](https://aka.ms/teams-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="04a34-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="04a34-110">为了完成本文中介绍的步骤，管理员需要熟悉 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04a34-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="04a34-111">有关使用 PowerShell 的详细信息，请参阅[设置适用于 Windows powershell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="04a34-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="04a34-112">在执行这些文章中的步骤之前，Microsoft 建议你确认你的 SBC 已按照 SBC 供应商的建议进行配置：</span><span class="sxs-lookup"><span data-stu-id="04a34-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="04a34-113">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="04a34-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="04a34-114">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="04a34-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="04a34-115">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="04a34-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="04a34-116">TE-系统（anynode）部署文档</span><span class="sxs-lookup"><span data-stu-id="04a34-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="04a34-117">Metaswitch 部署文档</span><span class="sxs-lookup"><span data-stu-id="04a34-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="04a34-118">有关支持的 SBCs 的完整列表，请参阅为[直接路由认证的会话边框控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="04a34-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="04a34-119">若要配置 Microsoft Phone 系统并使用户能够使用直接路由，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="04a34-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="04a34-120">**第 1 步**</span><span class="sxs-lookup"><span data-stu-id="04a34-120">**Step 1.**</span></span> [<span data-ttu-id="04a34-121">将 SBC 连接到 Microsoft Phone 系统并验证连接</span><span class="sxs-lookup"><span data-stu-id="04a34-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="04a34-122">**第 2 步**</span><span class="sxs-lookup"><span data-stu-id="04a34-122">**Step 2.**</span></span> [<span data-ttu-id="04a34-123">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="04a34-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="04a34-124">**第 3 步**</span><span class="sxs-lookup"><span data-stu-id="04a34-124">**Step 3.**</span></span> [<span data-ttu-id="04a34-125">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="04a34-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="04a34-126">**第 4 步**</span><span class="sxs-lookup"><span data-stu-id="04a34-126">**Step 4.**</span></span> [<span data-ttu-id="04a34-127">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="04a34-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="04a34-128">如果你要为多个租户配置 SBC，你还需要阅读[为多个租户配置 sbc](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="04a34-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="04a34-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="04a34-129">Related topics</span></span>

[<span data-ttu-id="04a34-130">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="04a34-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="04a34-131">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="04a34-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

