---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: 直接路由登陆页面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59f7cf4f1249956f3c763d12fcd96bf5c10a9fac
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298649"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="f8dc3-103">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="f8dc3-103">Phone System Direct Routing</span></span>

<span data-ttu-id="f8dc3-104">你已完成了[入门](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="f8dc3-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="f8dc3-106">也许您已经部署了[会议 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="f8dc3-107">现在已准备好添加云语音工作负荷，并已决定要使用电话系统直接路由电话运营商用于公共公用电话交换网 (PSTN) 连接。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="f8dc3-108">直接路由中，您可以使用电话系统与几乎任何电话运营商。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="f8dc3-109">本文介绍数据直接路由以及其他注意事项核心部署决策可能要考虑的事项，根据组织的需要。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="f8dc3-110">有关 Microsoft 云语音产品的详细信息，您还应阅读[Microsoft 团队中的云语音功能](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="f8dc3-111">了解有关直接路由的详细信息</span><span class="sxs-lookup"><span data-stu-id="f8dc3-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="f8dc3-112">下面的文章提供有关配置和使用电话系统直接路由的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="f8dc3-113">配置直接路由需要了解 PSTN 路由设计。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="f8dc3-114">您应阅读这些文章以了解如何规划和配置直接路由中的所有：</span><span class="sxs-lookup"><span data-stu-id="f8dc3-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="f8dc3-115">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="f8dc3-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="f8dc3-116">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="f8dc3-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="f8dc3-117">经认证可用于直接路由的会话边界控制器列表</span><span class="sxs-lookup"><span data-stu-id="f8dc3-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="f8dc3-118">对直接路由进行监视和故障排除</span><span class="sxs-lookup"><span data-stu-id="f8dc3-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="f8dc3-119">此外，您可能想要阅读以下文章根据您的要求：</span><span class="sxs-lookup"><span data-stu-id="f8dc3-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="f8dc3-120">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="f8dc3-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="f8dc3-121">迁移到直接路由</span><span class="sxs-lookup"><span data-stu-id="f8dc3-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="f8dc3-122">采用 PSTN 连接的混合环境中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="f8dc3-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="f8dc3-123">观看下面的会话，若要了解有关直接路由的详细信息： [Microsoft 团队中直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="f8dc3-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="f8dc3-124">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="f8dc3-124">Core deployment decisions</span></span>

<span data-ttu-id="f8dc3-125">这些是要考虑的直接路由中的核心决策。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="f8dc3-126">询问你自己</span><span class="sxs-lookup"><span data-stu-id="f8dc3-126">Ask yourself</span></span>|<span data-ttu-id="f8dc3-127">操作</span><span class="sxs-lookup"><span data-stu-id="f8dc3-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="f8dc3-128">哪些用户将启用直接路由？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="f8dc3-129">有关详细信息，请参阅[启用直接路由服务的用户](direct-routing-configure.md#enable-users-for-direct-routing-service)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="f8dc3-130">我的直接路由中有所需的许可证？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="f8dc3-131">有关详细信息，请参阅[授权和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="f8dc3-132">会话边界控制器 (SBC) 注意事项</span><span class="sxs-lookup"><span data-stu-id="f8dc3-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="f8dc3-133">使用直接路由时，您自己的会话边界控制器 (SBC) 直接连接到电话系统。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="f8dc3-134">认证的 Sbc 的列表，请参阅[支持的会话边界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="f8dc3-135">询问你自己</span><span class="sxs-lookup"><span data-stu-id="f8dc3-135">Ask yourself</span></span>|<span data-ttu-id="f8dc3-136">操作</span><span class="sxs-lookup"><span data-stu-id="f8dc3-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="f8dc3-137">在何处以及如何将部署 SBCs？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="f8dc3-138">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f8dc3-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="f8dc3-139">我有多个租户？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="f8dc3-140">有关详细信息，请参阅[配置多个租户的会话边界控制器](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="f8dc3-141">语音路由的注意事项</span><span class="sxs-lookup"><span data-stu-id="f8dc3-141">Voice routing considerations</span></span>

<span data-ttu-id="f8dc3-142">您需要配置电话系统，以将呼叫路由至特定的 Sbc。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="f8dc3-143">询问你自己</span><span class="sxs-lookup"><span data-stu-id="f8dc3-143">Ask yourself</span></span>|<span data-ttu-id="f8dc3-144">操作</span><span class="sxs-lookup"><span data-stu-id="f8dc3-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="f8dc3-145">我需要创建哪些语音路由策略、 PSTN 用法和语音路由？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="f8dc3-146">语音路由的信息，请参阅[配置语音路由](direct-routing-configure.md#configure-voice-routing)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="f8dc3-147">将分配给我定义语音路由策略的用户？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="f8dc3-148">请参阅[配置语音路由](direct-routing-configure.md#configure-voice-routing)中的示例。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="f8dc3-149">调用和互操作性策略</span><span class="sxs-lookup"><span data-stu-id="f8dc3-149">Calling and interop policies</span></span>

<span data-ttu-id="f8dc3-150">与 Microsoft 团队才支持直接路由。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="f8dc3-151">若要发起或接收直接路由通过 PSTN 呼叫，您需要配置所需的策略，以确保团队中收到传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="f8dc3-152">您可以配置用户设置为其首选的客户端的呼叫的团队通过配置用户仅团队模式或通过分配 TeamsCallingPolicy 和 TeamsInteropPolicy 配置为首选调用客户端的团队。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="f8dc3-153">询问你自己</span><span class="sxs-lookup"><span data-stu-id="f8dc3-153">Ask yourself</span></span>|<span data-ttu-id="f8dc3-154">操作</span><span class="sxs-lookup"><span data-stu-id="f8dc3-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="f8dc3-155">如何将设置为首选客户端的呼叫的团队？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="f8dc3-156">有关详细信息，请参阅[设置为首选的 Microsoft 团队呼叫的用户的客户端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="f8dc3-157">其他部署注意事项</span><span class="sxs-lookup"><span data-stu-id="f8dc3-157">Additional deployment considerations</span></span>

<span data-ttu-id="f8dc3-158">您可能要考虑以下内容，根据组织的需求和配置：</span><span class="sxs-lookup"><span data-stu-id="f8dc3-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="f8dc3-159">询问你自己</span><span class="sxs-lookup"><span data-stu-id="f8dc3-159">Ask yourself</span></span>| <span data-ttu-id="f8dc3-160">操作</span><span class="sxs-lookup"><span data-stu-id="f8dc3-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="f8dc3-161">您必须现有 Skype 业务服务器部署配置的混合连接？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="f8dc3-162">了解如何设置混合环境中的用户帐户和管理，请参阅[使用 PSTN 连接的混合环境中的用户帐户](direct-routing-user-accounts-in-a-hybrid-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="f8dc3-163">您即将迁移到直接路由从调用规划或从企业内部部署环境 Skype？</span><span class="sxs-lookup"><span data-stu-id="f8dc3-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="f8dc3-164">若要了解有关从现有环境迁移到直接路由的详细信息，请参阅[迁移到直接路由](direct-routing-migrating.md)。</span><span class="sxs-lookup"><span data-stu-id="f8dc3-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
