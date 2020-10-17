---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 528dcfd975616d213b8a9fbd2499dc5d798708b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533579"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="1992e-103">从 Skype for Business 升级到 &mdash; IT 管理员的团队</span><span class="sxs-lookup"><span data-stu-id="1992e-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="1992e-104">概述</span><span class="sxs-lookup"><span data-stu-id="1992e-104">Overview</span></span>

<span data-ttu-id="1992e-105">从 Skype for Business 升级到团队时，某些组织需要由其 IT 部门计划和管理的渐进式推出。</span><span class="sxs-lookup"><span data-stu-id="1992e-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="1992e-106">本部分中的文章主要适用于大型组织中的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="1992e-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="1992e-107">这些组织通常位于本地，但它们也可能是大型 Skype for Business Online 组织。</span><span class="sxs-lookup"><span data-stu-id="1992e-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="1992e-108">阅读这些文章之前，请务必阅读 [团队升级](upgrade-start-here.md) 和 [升级框架](upgrade-framework.md)入门。</span><span class="sxs-lookup"><span data-stu-id="1992e-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="1992e-109">以下文章将指导你完成组织的升级过程：</span><span class="sxs-lookup"><span data-stu-id="1992e-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="1992e-110">升级方法</span><span class="sxs-lookup"><span data-stu-id="1992e-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="1992e-111">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="1992e-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="1992e-112">具有 Skype for business 内部部署的组织的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="1992e-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="1992e-113">实现升级</span><span class="sxs-lookup"><span data-stu-id="1992e-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="1992e-114"> (PSTN) 注意事项的公共交换电话网络</span><span class="sxs-lookup"><span data-stu-id="1992e-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="1992e-115">此外，以下文章介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="1992e-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1992e-116">团队和 Skype for business 的共存</span><span class="sxs-lookup"><span data-stu-id="1992e-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="1992e-117">共存模式-参考</span><span class="sxs-lookup"><span data-stu-id="1992e-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1992e-118">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="1992e-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="1992e-119">这些文章使用 "Skype for business Online"、"本地 Skype for business 服务器" 和 "Skype for business" 术语。</span><span class="sxs-lookup"><span data-stu-id="1992e-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="1992e-120">后一术语既指联机版本，也是本地版本。</span><span class="sxs-lookup"><span data-stu-id="1992e-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="1992e-121">开始之前，请注意，已迁移到团队的用户不再使用 Skype for business 客户端，除非加入 Skype for business 中托管的会议。</span><span class="sxs-lookup"><span data-stu-id="1992e-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="1992e-122">所有传入聊天和呼叫用户团队客户端中的土地，无论发件人是使用团队还是 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="1992e-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="1992e-123">由迁移用户组织的任何新会议将计划为团队会议。</span><span class="sxs-lookup"><span data-stu-id="1992e-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="1992e-124">如果用户尝试使用 Skype for Business 客户端，将阻止启动聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="1992e-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="1992e-125">但是，用户可以 (，并且必须) 仍使用 Skype for Business 客户端加入受邀的 Skype for business 会议。</span><span class="sxs-lookup"><span data-stu-id="1992e-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="1992e-126"> (在2017之前发运的旧版 Skype for business 客户端不接受 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="1992e-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="1992e-127">请确保您使用的是最新的 Skype for Business 客户端。 ) </span><span class="sxs-lookup"><span data-stu-id="1992e-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="1992e-128">使用 [模式](migration-interop-guidance-for-teams-with-skype.md)概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的属性）管理用户对团队的过渡。</span><span class="sxs-lookup"><span data-stu-id="1992e-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="1992e-129">按照上述说明迁移到团队的用户处于 "TeamsOnly" 模式。</span><span class="sxs-lookup"><span data-stu-id="1992e-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="1992e-130">对于迁移到团队的组织，最终目标是将所有用户移到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="1992e-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="1992e-131">拥有 Skype for business 本地帐户的用户不能 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="1992e-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="1992e-132">虽然这些用户可以 [在孤岛模式下使用团队](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)，但这不会提供可在 TeamsOnly 模式下使用的整套团队功能。</span><span class="sxs-lookup"><span data-stu-id="1992e-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="1992e-133">若要使这些用户 TeamsOnly，必须使用本地 Skype for business Server 工具将其移动到云 `Move-CsUser` 。</span><span class="sxs-lookup"><span data-stu-id="1992e-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="1992e-134">还行。</span><span class="sxs-lookup"><span data-stu-id="1992e-134">OK.</span></span> <span data-ttu-id="1992e-135">让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="1992e-135">Let's get started.</span></span>  <span data-ttu-id="1992e-136">第一步是了解 [可用的升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="1992e-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="1992e-137">相关链接</span><span class="sxs-lookup"><span data-stu-id="1992e-137">Related links</span></span>

[<span data-ttu-id="1992e-138">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="1992e-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1992e-139">配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="1992e-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1992e-140">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="1992e-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1992e-141">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="1992e-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1992e-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1992e-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1992e-143">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="1992e-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

