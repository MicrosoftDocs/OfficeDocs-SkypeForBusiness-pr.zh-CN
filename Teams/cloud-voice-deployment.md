---
title: 云语音部署
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: Rowille
description: 在 Microsoft Teams 中部署云语音功能实践指导
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 476d65ee927fedf285cf66377c58c9f09698b046
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236763"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="6ee0a-103">云语音部署</span><span class="sxs-lookup"><span data-stu-id="6ee0a-103">Cloud voice deployment</span></span>

<span data-ttu-id="6ee0a-104">作为 Office 365 中团队合作和沟通的中心的 Microsoft Teams 现在通过扩展 Teams 会议和通话体验以包含通过公用电话交换网 (PSTN) 连接的外部各方，提供了音频会议、具有通话套餐的电话系统以及电话系统直接路由功能，从而满足额外的业务需求。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing, Phone System with Calling Plans, and Phone System Direct Routing capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>


> [!Tip] 
> <span data-ttu-id="6ee0a-105">观看以下会话了解电话系统简介: [Microsoft 团队中的电话系统简介](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="6ee0a-105">Watch the following session for an introduction to Phone Systems: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>
 
<span data-ttu-id="6ee0a-106">我们将更新此页面, 因为随着时间的推移, 团队的其他云语音功能将随时间发布。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-106">We’ll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="6ee0a-107">Microsoft Teams 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="6ee0a-107">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="6ee0a-108">Office 365 中的音频会议允许参与者从任何电话加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-108">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="6ee0a-109">下面是 Office 365 中的[音频会议](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)所获得的功能。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-109">Here’s what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="6ee0a-110">Microsoft 团队中包含通话计划 ("通话计划") 的电话系统</span><span class="sxs-lookup"><span data-stu-id="6ee0a-110">Phone System with Calling Plans (“Calling Plans”) in Microsoft Teams</span></span>

<span data-ttu-id="6ee0a-111">电话系统是一种 Office 365 功能, 可提供管理呼叫路由、策略和用户预配的功能。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-111">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="6ee0a-112">这包括电话呼叫管理系统、呼叫路由和呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-112">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="6ee0a-113">通话计划是电话系统功能的附加服务, 通过团队和 Skype for business Online 提供。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-113">Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="6ee0a-114">通话计划要求有问题的用户托管在 Skype for business Online 中, 以便在 Microsoft 团队中工作。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-114">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="6ee0a-115">通话计划向企业中的人员提供主要电话号码, 并让他们通过 PSTN 拨打和接听您的组织外部的电话。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-115">Calling Plans provide the people in your business with a primary phone number, and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="6ee0a-116">若要了解详细信息, 请参阅在 Office 365 和[电话系统和通话计划](calling-plan-landing-page.md)[中使用手机系统获取的功能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)</span><span class="sxs-lookup"><span data-stu-id="6ee0a-116">To learn more, read [Here’s what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [Phone System and Calling Plans](calling-plan-landing-page.md)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="6ee0a-117">电话系统直接路由 ("直接路由")</span><span class="sxs-lookup"><span data-stu-id="6ee0a-117">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="6ee0a-118">直接路由可与电话系统功能配合使用, 以向组织中的人员提供通过 PSTN 建立和接收来自组织外部的电话呼叫, 其中 PSTN 连接是通过第三方服务提供商提供的。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-118">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="6ee0a-119">若要了解详细信息, 请阅读[计划直接路由](direct-routing-plan.md)和[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-119">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="6ee0a-120">适用于 Microsoft 团队的音频会议、通话计划和直接路由的实用指南</span><span class="sxs-lookup"><span data-stu-id="6ee0a-120">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="6ee0a-121">通过使用 Office 365 FastTrack 客户版旅行框架及其三个阶段&mdash;"构想"、"板载" 和 "驱动器" 值, 可对此实用指南进行组织。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-121">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="6ee0a-122">它旨在帮助你规划、交付和操作成功的音频会议、通话计划或直接路由实施。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-122">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="6ee0a-123">展望</span><span class="sxs-lookup"><span data-stu-id="6ee0a-123">Envision</span></span>  |<span data-ttu-id="6ee0a-124">上线</span><span class="sxs-lookup"><span data-stu-id="6ee0a-124">Onboard</span></span>  |<span data-ttu-id="6ee0a-125">推动价值</span><span class="sxs-lookup"><span data-stu-id="6ee0a-125">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="6ee0a-126">定义成功</span><span class="sxs-lookup"><span data-stu-id="6ee0a-126">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="6ee0a-127">提出我的服务决策</span><span class="sxs-lookup"><span data-stu-id="6ee0a-127">Make my service decisions for</span></span> <br><span data-ttu-id="6ee0a-128">&nbsp;&nbsp;[音频会议](2-envision-make-my-service-decisions-audio-conferencing.md),</span><span class="sxs-lookup"><span data-stu-id="6ee0a-128">&nbsp;&nbsp;[Audio Conferencing](2-envision-make-my-service-decisions-audio-conferencing.md),</span></span><br><span data-ttu-id="6ee0a-129">&nbsp;&nbsp;[通话计划](2-envision-make-my-service-decisions-phone-system.md)或[直接路由](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="6ee0a-129">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="6ee0a-130">评估环境</span><span class="sxs-lookup"><span data-stu-id="6ee0a-130">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="6ee0a-131">规划服务管理</span><span class="sxs-lookup"><span data-stu-id="6ee0a-131">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="6ee0a-132">规划我的用户体验</span><span class="sxs-lookup"><span data-stu-id="6ee0a-132">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="6ee0a-133">记录成功计划</span><span class="sxs-lookup"><span data-stu-id="6ee0a-133">Document my success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="6ee0a-134">准备服务</span><span class="sxs-lookup"><span data-stu-id="6ee0a-134">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="6ee0a-135">准备用户</span><span class="sxs-lookup"><span data-stu-id="6ee0a-135">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="6ee0a-136">部署服务</span><span class="sxs-lookup"><span data-stu-id="6ee0a-136">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="6ee0a-137">操作服务</span><span class="sxs-lookup"><span data-stu-id="6ee0a-137">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="6ee0a-138">增强服务</span><span class="sxs-lookup"><span data-stu-id="6ee0a-138">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="6ee0a-139">内容以有序的形式呈现, 旨在让你通过从开始到结束的端到端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-139">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="6ee0a-140">如果您已在主动部署, 我们仍鼓励您参考适用的内容区域。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-140">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="6ee0a-141">在此实用指南中, 我们为每个活动和关键讨论提供示例输出。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-141">In this practical guidance, we provide example outputs for each activity and key discussion.</span></span> <span data-ttu-id="6ee0a-142">本文档中的示例包含在 Tip 标注中, 它们作为可重复使用的模板。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-142">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="6ee0a-143">您将看到 "TBA" (要添加) 作为规划过程的一部分需要完成的信息。</span><span class="sxs-lookup"><span data-stu-id="6ee0a-143">You’ll see “TBA” (to be added) for information that you need to complete as part of your planning process.</span></span>
