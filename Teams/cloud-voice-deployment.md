---
title: 云语音部署
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: 在 Microsoft Teams 中部署云语音功能实践指导
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="dd9fe-103">云语音部署</span><span class="sxs-lookup"><span data-stu-id="dd9fe-103">Cloud voice deployment</span></span>

<span data-ttu-id="dd9fe-104">Microsoft 的团队，团队协作和 Office 365 中的通信的中心现在提供音频会议和电话系统调用计划功能，以满足通过扩展团队会议并调用体验，以包括其他业务需求，通过公用交换的电话网 (PSTN) 连接外部各方。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="dd9fe-105">当以后适用于 Teams 的其他云语音功能发布时，我们将更新此页面。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="dd9fe-106">Microsoft Teams 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="dd9fe-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="dd9fe-107">Office 365 中的音频会议允许参与者从任何电话加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="dd9fe-108">下面是使用 Office 365 中的[音频会议](https://go.microsoft.com/fwlink/?linkid=858992)完成的内容。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="dd9fe-109">与在 Microsoft 小组电话计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="dd9fe-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="dd9fe-110">电话系统是一项 Office 365 功能，用于管理呼叫路由、策略和用户预配。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="dd9fe-111">其中包括电话呼叫管理系统、呼叫路由和呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="dd9fe-112">Office 365 通话套餐是电话系统功能的附加项，通过 Teams 和 Skype for Business Online 交付。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="dd9fe-113">电话计划提供了主要的电话与您的业务的人编号，并可以拨打和接听电话您组织以外的 PSTN 上。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="dd9fe-114">要了解更多信息，请参阅 [Office 365 中的电话系统提供的功能](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c)和 [Office 365 中的通话套餐是什么？](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="dd9fe-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="dd9fe-115">音频会议和电话系统调用中 Microsoft 小组计划的实用指南</span><span class="sxs-lookup"><span data-stu-id="dd9fe-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="dd9fe-116">通过使用 Office 365 FastTrack 客户之旅框架分为本实用指南和三个阶段&mdash;构想，板载和推动价值。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="dd9fe-117">它具有用于帮助您规划、 提供和使用调用计划实施成功的音频会议或电话系统。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="dd9fe-118">展望</span><span class="sxs-lookup"><span data-stu-id="dd9fe-118">Envision</span></span>  |<span data-ttu-id="dd9fe-119">上线</span><span class="sxs-lookup"><span data-stu-id="dd9fe-119">Onboard</span></span>  |<span data-ttu-id="dd9fe-120">推动价值</span><span class="sxs-lookup"><span data-stu-id="dd9fe-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="dd9fe-121">我的成功定义</span><span class="sxs-lookup"><span data-stu-id="dd9fe-121">Define my success</span></span> <br> <span data-ttu-id="dd9fe-122">决定我的服务</span><span class="sxs-lookup"><span data-stu-id="dd9fe-122">Make my service decisions</span></span> <br> <span data-ttu-id="dd9fe-123">评估环境</span><span class="sxs-lookup"><span data-stu-id="dd9fe-123">Evaluate my environment</span></span> <br> <span data-ttu-id="dd9fe-124">我的服务管理计划</span><span class="sxs-lookup"><span data-stu-id="dd9fe-124">Plan my service management</span></span> <br> <span data-ttu-id="dd9fe-125">计划我的用户体验</span><span class="sxs-lookup"><span data-stu-id="dd9fe-125">Plan my users' experience</span></span> <br> <span data-ttu-id="dd9fe-126">我成功的计划的文档</span><span class="sxs-lookup"><span data-stu-id="dd9fe-126">Document my success plan</span></span>    | <span data-ttu-id="dd9fe-127">准备我的服务</span><span class="sxs-lookup"><span data-stu-id="dd9fe-127">Prepare my service</span></span> <br> <span data-ttu-id="dd9fe-128">准备我的用户</span><span class="sxs-lookup"><span data-stu-id="dd9fe-128">Prepare my users</span></span> <br> <span data-ttu-id="dd9fe-129">部署服务</span><span class="sxs-lookup"><span data-stu-id="dd9fe-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="dd9fe-130">使用我的服务</span><span class="sxs-lookup"><span data-stu-id="dd9fe-130">Operate my service</span></span> <br> <span data-ttu-id="dd9fe-131">增强我的服务</span><span class="sxs-lookup"><span data-stu-id="dd9fe-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="dd9fe-132">内容以有序方式呈现，旨在引导您完成端到端部署迁移的过程从开始到结束。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="dd9fe-133">如果已积极部署，我们仍建议您引用适用的内容区域。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="dd9fe-134">在本实用的指南，我们提供示例输出每个活动和主要的讨论。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="dd9fe-135">在本文档的示例括内提示注解，它们作为一个模板，您可以重复使用。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="dd9fe-136">对于需要你在规划过程中完成的信息，以“TBA”（待添加）表示。</span><span class="sxs-lookup"><span data-stu-id="dd9fe-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>