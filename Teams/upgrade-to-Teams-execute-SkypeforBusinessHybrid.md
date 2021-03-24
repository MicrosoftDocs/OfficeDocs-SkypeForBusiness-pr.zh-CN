---
title: 将 Skype for Business 混合部署升级到 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business 混合部署将组织升级到 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104018"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="1ebf2-103">从 Skype for Business 混合部署升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="1ebf2-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="1ebf2-104">![升级旅程的阶段，着重强调部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="1ebf2-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1ebf2-105">本文是升级旅程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="1ebf2-106">在继续之前，请确认已经完成了以下活动:</span><span class="sxs-lookup"><span data-stu-id="1ebf2-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="1ebf2-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="1ebf2-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1ebf2-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="1ebf2-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="1ebf2-109">了解 Skype for Business 和 Teams 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="1ebf2-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="1ebf2-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="1ebf2-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1ebf2-111">准备环境</span><span class="sxs-lookup"><span data-stu-id="1ebf2-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="1ebf2-112">准备组织</span><span class="sxs-lookup"><span data-stu-id="1ebf2-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="1ebf2-113">开展试点</span><span class="sxs-lookup"><span data-stu-id="1ebf2-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="1ebf2-114">如果你已在本地部署 Skype for Business 或 Microsoft Lync，并且已将其配置为与 Microsoft 365 或 Office 365 组织的混合部署中，并且你的组织希望选择性地升级到 Teams（通过使用多种共存模式）或"全部"，请按照本文中的指导操作。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="1ebf2-115">对于任一升级过程，你需要将用户移动到 Skype for Business Online (如果他们还没有在线归居) 然后为其分配适当的共存和升级模式。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="1ebf2-116">步骤 1：将用户移动到 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1ebf2-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="1ebf2-117">此步骤适用于当前位于本地的用户。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="1ebf2-118">有关将这些用户移动到 Skype for Business Online 的信息，请参阅将用户从本地移动到[Skype for Business Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="1ebf2-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="1ebf2-119">步骤 2：分配共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="1ebf2-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="1ebf2-120">将用户移动到 Skype for Business Online 后，你可以根据组织选择的升级过程为其分配适当的共存模式。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="1ebf2-121">有关详细信息，请参阅 [设置共存和升级设置和](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ebf2-122">使用 Skype for Business Server 2019 和 Skype for Business Server 2015 的未来累积更新，你将能够执行步骤 1 (将用户移动到 Skype for Business Online) 和步骤 2 (将用户升级到 Teams) 一步。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="1ebf2-123">Skype for Business Server 2019 发布后，将提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="1ebf2-124">手机系统和 Teams 升级</span><span class="sxs-lookup"><span data-stu-id="1ebf2-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="1ebf2-125">如果你正在使用呼叫计划将 Skype for Business 混合部署转换到电话系统，并且 Microsoft 将成为你的公共电话交换网 (PSTN) 提供商，并且假定你已完成电话号码转网，将你的用户升级到 Teams 将自动将入站 PSTN 呼叫转换到 Teams。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="1ebf2-126">如果呼叫计划不可用，或者你打算使用现有的 PSTN 连接提供商，则需要将企业语音部署（或使用现有本地部署或 Cloud Connector Edition 的混合语音部署）转换为 Microsoft Phone 系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="1ebf2-127">若要将用户升级到 Teams，请参阅电话系统 [直接路由的其他注意事项](./direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="1ebf2-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>