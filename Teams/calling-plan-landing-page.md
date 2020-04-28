---
title: Microsoft Teams 中的通话套餐
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 确定哪种 Microsoft Phone 系统通话计划最适合你的组织在团队中的云语音服务。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1fb0abed3477039f4c19c0e2de0ea696626f35
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905024"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="aec2a-103">哪种通话套餐适合你？</span><span class="sxs-lookup"><span data-stu-id="aec2a-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="aec2a-104">您已完成 "[入门](get-started-with-teams-quick-start.md)"。</span><span class="sxs-lookup"><span data-stu-id="aec2a-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="aec2a-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="aec2a-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="aec2a-106">也许你已将[会议部署 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="aec2a-107">现在，你已准备好添加云语音工作负载，你已决定将 Microsoft Phone 系统与通话计划配合使用来连接到公共交换式电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="aec2a-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="aec2a-108">本文介绍调用计划的核心部署决策以及你可能希望根据组织的需求配置的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="aec2a-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="aec2a-109">您还应阅读[Microsoft 团队中的云语音](cloud-voice-landing-page.md)，了解有关 Microsoft 云语音服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aec2a-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="aec2a-110">了解有关通话计划的详细信息</span><span class="sxs-lookup"><span data-stu-id="aec2a-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="aec2a-111">以下文章提供了有关部署和使用 Microsoft 通话计划的详细信息：</span><span class="sxs-lookup"><span data-stu-id="aec2a-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="aec2a-112">Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="aec2a-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="aec2a-113">Office 365 通话套餐</span><span class="sxs-lookup"><span data-stu-id="aec2a-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="aec2a-114">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="aec2a-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="aec2a-115">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="aec2a-115">Core deployment decisions</span></span>

<span data-ttu-id="aec2a-116">若要将 Microsoft 用作电话运营商，你需要获取呼叫计划许可证并将其分配给你的电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="aec2a-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="aec2a-117">有两种类型的通话计划可用：</span><span class="sxs-lookup"><span data-stu-id="aec2a-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="aec2a-118">国内通话计划</span><span class="sxs-lookup"><span data-stu-id="aec2a-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="aec2a-119">国内和国际通话计划</span><span class="sxs-lookup"><span data-stu-id="aec2a-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="aec2a-120">询问你自己</span><span class="sxs-lookup"><span data-stu-id="aec2a-120">Ask yourself</span></span>|<span data-ttu-id="aec2a-121">操作</span><span class="sxs-lookup"><span data-stu-id="aec2a-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="aec2a-122">我所在区域是否有通话计划？</span><span class="sxs-lookup"><span data-stu-id="aec2a-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="aec2a-123">哪些用户位置将具有呼叫计划服务？</span><span class="sxs-lookup"><span data-stu-id="aec2a-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="aec2a-124">有关详细信息，请参阅[音频会议和通话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="aec2a-125">我的用户是否需要国际通话？</span><span class="sxs-lookup"><span data-stu-id="aec2a-125">Do my users need international calling?</span></span> | <span data-ttu-id="aec2a-126">有关详细信息，请参阅[Office 365 的呼叫计划](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="aec2a-127">我的用户是否有通话计划许可证？</span><span class="sxs-lookup"><span data-stu-id="aec2a-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="aec2a-128">要购买和分配许可证，请参阅[步骤2：购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="aec2a-129">我的用户是否每个都有直接拨入电话号码？</span><span class="sxs-lookup"><span data-stu-id="aec2a-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="aec2a-130">若要获取电话号码，请参阅[步骤3：获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="aec2a-131">将电话号码转接到 Office 365</span><span class="sxs-lookup"><span data-stu-id="aec2a-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="aec2a-132">将您的电话号码从当前服务提供商转移到团队非常简单。</span><span class="sxs-lookup"><span data-stu-id="aec2a-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="aec2a-133">将您的电话号码移植到团队后，Microsoft 将成为您的服务提供商，并向您收取这些电话号码。</span><span class="sxs-lookup"><span data-stu-id="aec2a-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="aec2a-134">有关详细信息，请参阅[将电话号码转移给团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="aec2a-135">电话号码和紧急位置</span><span class="sxs-lookup"><span data-stu-id="aec2a-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="aec2a-136">使用 Office 365 中的呼叫计划，您的组织中的每个用户都需要有一个唯一的直接向内拨号（已拨）电话号码和相应的已验证的紧急地址。</span><span class="sxs-lookup"><span data-stu-id="aec2a-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="aec2a-137">您还可以指定紧急地址内的紧急位置（例如，办公室号码或楼层号）。</span><span class="sxs-lookup"><span data-stu-id="aec2a-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="aec2a-138">询问你自己</span><span class="sxs-lookup"><span data-stu-id="aec2a-138">Ask yourself</span></span>|<span data-ttu-id="aec2a-139">操作</span><span class="sxs-lookup"><span data-stu-id="aec2a-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="aec2a-140">我需要有关紧急地址和位置信息的详细信息？</span><span class="sxs-lookup"><span data-stu-id="aec2a-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="aec2a-141">有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="aec2a-142">通话标识</span><span class="sxs-lookup"><span data-stu-id="aec2a-142">Calling identity</span></span>

<span data-ttu-id="aec2a-143">默认情况下，所有出站呼叫均使用分配的电话号码作为呼叫标识（呼叫者 ID）。</span><span class="sxs-lookup"><span data-stu-id="aec2a-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="aec2a-144">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="aec2a-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="aec2a-145">询问你自己</span><span class="sxs-lookup"><span data-stu-id="aec2a-145">Ask yourself</span></span>|<span data-ttu-id="aec2a-146">操作</span><span class="sxs-lookup"><span data-stu-id="aec2a-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="aec2a-147">我是否希望屏蔽或禁用来电显示？</span><span class="sxs-lookup"><span data-stu-id="aec2a-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="aec2a-148">若要更改或阻止呼叫方 ID，请参阅[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="aec2a-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




