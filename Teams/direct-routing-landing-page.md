---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords: ms.teamsadmincenter.directrouting.overview
description: 直接路由的登陆页面
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc686f6e59eabedc405d0b6c517feb10908600a2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707247"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="941b3-103">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="941b3-103">Phone System Direct Routing</span></span>

<span data-ttu-id="941b3-104">你已完成了[入门](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="941b3-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="941b3-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="941b3-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="941b3-106">也许你已将[会议部署 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="941b3-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="941b3-107">现在，你已准备好添加云语音工作负载，并且你已决定通过使用电话系统直接路由将自己的电话运营商用于公共交换电话网络（PSTN）连接。</span><span class="sxs-lookup"><span data-stu-id="941b3-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="941b3-108">通过直接路由，您可以在任何电话运营商处使用电话系统。</span><span class="sxs-lookup"><span data-stu-id="941b3-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="941b3-109">本文介绍直接路由的核心部署决策，以及你可能希望考虑的基于组织需求的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="941b3-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="941b3-110">您还应阅读[Microsoft 团队中的云语音](cloud-voice-landing-page.md)，了解有关 Microsoft 云语音服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="941b3-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="941b3-111">了解有关直接路由的详细信息</span><span class="sxs-lookup"><span data-stu-id="941b3-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="941b3-112">以下文章提供了有关配置和使用 "电话系统直接路由" 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="941b3-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="941b3-113">配置直接路由需要了解 PSTN 路由设计。</span><span class="sxs-lookup"><span data-stu-id="941b3-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="941b3-114">您应阅读所有这些文章，以了解如何规划和配置直接路由：</span><span class="sxs-lookup"><span data-stu-id="941b3-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="941b3-115">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="941b3-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="941b3-116">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="941b3-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="941b3-117">经认证可用于直接路由的会话边界控制器列表</span><span class="sxs-lookup"><span data-stu-id="941b3-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="941b3-118">对直接路由进行监视和故障排除</span><span class="sxs-lookup"><span data-stu-id="941b3-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="941b3-119">此外，你可能需要根据你的要求阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="941b3-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="941b3-120">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="941b3-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="941b3-121">迁移到直接路由</span><span class="sxs-lookup"><span data-stu-id="941b3-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="941b3-122">采用 PSTN 连接的混合环境中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="941b3-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="941b3-123">观看以下会话以了解有关直接路由的详细信息：[在 Microsoft 团队中直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="941b3-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="941b3-124">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="941b3-124">Core deployment decisions</span></span>

<span data-ttu-id="941b3-125">以下是直接路由的核心决策。</span><span class="sxs-lookup"><span data-stu-id="941b3-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="941b3-126">询问你自己</span><span class="sxs-lookup"><span data-stu-id="941b3-126">Ask yourself</span></span>|<span data-ttu-id="941b3-127">Action</span><span class="sxs-lookup"><span data-stu-id="941b3-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="941b3-128">哪些用户将启用直接路由？</span><span class="sxs-lookup"><span data-stu-id="941b3-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="941b3-129">有关详细信息，请参阅[为直接路由服务启用用户](direct-routing-configure.md#enable-users-for-direct-routing-service)。</span><span class="sxs-lookup"><span data-stu-id="941b3-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="941b3-130">是否有直接路由所需的许可证？</span><span class="sxs-lookup"><span data-stu-id="941b3-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="941b3-131">有关详细信息，请参阅[许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="941b3-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="941b3-132">会话边框控制器（SBC）注意事项</span><span class="sxs-lookup"><span data-stu-id="941b3-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="941b3-133">通过直接路由，你可以将自己的会话边界控制器（SBC）直接连接到电话系统。</span><span class="sxs-lookup"><span data-stu-id="941b3-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="941b3-134">有关已验证的 SBCs 的列表，请参阅[支持的会话边界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="941b3-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="941b3-135">询问你自己</span><span class="sxs-lookup"><span data-stu-id="941b3-135">Ask yourself</span></span>|<span data-ttu-id="941b3-136">Action</span><span class="sxs-lookup"><span data-stu-id="941b3-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="941b3-137">我将在哪里以及如何部署 SBCs？</span><span class="sxs-lookup"><span data-stu-id="941b3-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="941b3-138">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="941b3-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="941b3-139">我有多个租户吗？</span><span class="sxs-lookup"><span data-stu-id="941b3-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="941b3-140">有关详细信息，请参阅[为多个租户配置会话边框控制器](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="941b3-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="941b3-141">语音路由注意事项</span><span class="sxs-lookup"><span data-stu-id="941b3-141">Voice routing considerations</span></span>

<span data-ttu-id="941b3-142">您需要配置电话系统以将呼叫路由到特定的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="941b3-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="941b3-143">询问你自己</span><span class="sxs-lookup"><span data-stu-id="941b3-143">Ask yourself</span></span>|<span data-ttu-id="941b3-144">Action</span><span class="sxs-lookup"><span data-stu-id="941b3-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="941b3-145">我需要创建哪些语音路由策略、PSTN 使用和语音路由？</span><span class="sxs-lookup"><span data-stu-id="941b3-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="941b3-146">有关语音路由信息，请参阅[配置语音路由](direct-routing-configure.md#configure-voice-routing)。</span><span class="sxs-lookup"><span data-stu-id="941b3-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="941b3-147">哪些用户将分配给我定义的语音路由策略？</span><span class="sxs-lookup"><span data-stu-id="941b3-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="941b3-148">请参阅[配置语音路由](direct-routing-configure.md#configure-voice-routing)中的示例。</span><span class="sxs-lookup"><span data-stu-id="941b3-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="941b3-149">使用 TeamsUpgradePolicy 在团队客户端中确保传入呼叫土地</span><span class="sxs-lookup"><span data-stu-id="941b3-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="941b3-150">直接路由仅受 Microsoft 团队支持。</span><span class="sxs-lookup"><span data-stu-id="941b3-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="941b3-151">要通过直接路由接收 PSTN 呼叫，您需要配置 TeamsUpgradePolicy 以确保在团队中接收传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="941b3-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="941b3-152">用户必须位于 "仅团队" 模式下，你可以通过为其分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="941b3-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="941b3-153">询问你自己</span><span class="sxs-lookup"><span data-stu-id="941b3-153">Ask yourself</span></span>|<span data-ttu-id="941b3-154">Action</span><span class="sxs-lookup"><span data-stu-id="941b3-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="941b3-155">团队的唯一模式意味着什么？</span><span class="sxs-lookup"><span data-stu-id="941b3-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="941b3-156">有关详细信息，请参阅[与 Skype For business 一起使用团队的组织的迁移和互操作指南](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="941b3-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="941b3-157">其他部署注意事项</span><span class="sxs-lookup"><span data-stu-id="941b3-157">Additional deployment considerations</span></span>

<span data-ttu-id="941b3-158">根据组织的需要和配置，您可能需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="941b3-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="941b3-159">询问你自己</span><span class="sxs-lookup"><span data-stu-id="941b3-159">Ask yourself</span></span>| <span data-ttu-id="941b3-160">Action</span><span class="sxs-lookup"><span data-stu-id="941b3-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="941b3-161">是否有配置了混合连接的现有 Skype for Business 服务器部署？</span><span class="sxs-lookup"><span data-stu-id="941b3-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="941b3-162">若要了解如何设置和管理混合环境中的用户帐户，请参阅[具有 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="941b3-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="941b3-163">您是否正在迁移以直接从呼叫计划或 Skype for business 内部部署环境中路由？</span><span class="sxs-lookup"><span data-stu-id="941b3-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="941b3-164">若要了解有关从现有环境迁移到直接路由的详细信息，请参阅[迁移到直接路由](direct-routing-migrating.md)。</span><span class="sxs-lookup"><span data-stu-id="941b3-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
