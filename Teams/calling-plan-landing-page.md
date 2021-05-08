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
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 确定哪个Microsoft 电话呼叫计划最适合在云语音中为组织Teams。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102728"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="9bba9-103">哪种通话套餐适合你？</span><span class="sxs-lookup"><span data-stu-id="9bba9-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="9bba9-104">你已完成入门[。](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="9bba9-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9bba9-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="9bba9-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9bba9-106">也许你已部署会议[&会议。](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="9bba9-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="9bba9-107">现在，你已准备好添加云语音工作负荷，并且你已决定使用 Microsoft 电话 System 和呼叫计划连接到公共电话交换网 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="9bba9-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="9bba9-108">本文介绍呼叫计划的核心部署决策，以及可能需要根据组织需求配置的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="9bba9-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="9bba9-109">还应阅读[云语音Microsoft Teams](cloud-voice-landing-page.md)了解有关 Microsoft 云语音产品/服务的信息。</span><span class="sxs-lookup"><span data-stu-id="9bba9-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="9bba9-110">详细了解通话套餐</span><span class="sxs-lookup"><span data-stu-id="9bba9-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="9bba9-111">以下文章提供有关部署和使用 Microsoft 呼叫计划的信息：</span><span class="sxs-lookup"><span data-stu-id="9bba9-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="9bba9-112">电话系统Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="9bba9-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="9bba9-113">呼叫套餐或Microsoft 365套餐Office 365</span><span class="sxs-lookup"><span data-stu-id="9bba9-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="9bba9-114">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="9bba9-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="9bba9-115">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="9bba9-115">Core deployment decisions</span></span>

<span data-ttu-id="9bba9-116">若要将 Microsoft 用作电话运营商，需要获取呼叫计划许可证并将其分配给电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="9bba9-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="9bba9-117">有两种类型的通话套餐可用：</span><span class="sxs-lookup"><span data-stu-id="9bba9-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="9bba9-118">国内呼叫计划</span><span class="sxs-lookup"><span data-stu-id="9bba9-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="9bba9-119">国内和国际呼叫计划</span><span class="sxs-lookup"><span data-stu-id="9bba9-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="9bba9-120">询问你自己</span><span class="sxs-lookup"><span data-stu-id="9bba9-120">Ask yourself</span></span>|<span data-ttu-id="9bba9-121">操作</span><span class="sxs-lookup"><span data-stu-id="9bba9-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="9bba9-122">"通话套餐"在我的区域中是否可用？</span><span class="sxs-lookup"><span data-stu-id="9bba9-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="9bba9-123">哪些用户位置将具有呼叫计划服务？</span><span class="sxs-lookup"><span data-stu-id="9bba9-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="9bba9-124">有关详细信息，请参阅音频会议和通话计划的"国家/地区["和"区域可用性"。](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="9bba9-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="9bba9-125">我的用户是否需要国际呼叫？</span><span class="sxs-lookup"><span data-stu-id="9bba9-125">Do my users need international calling?</span></span> | <span data-ttu-id="9bba9-126">有关详细信息，请参阅为用户[或Microsoft 365 Office 365](calling-plans-for-office-365.md)计划。</span><span class="sxs-lookup"><span data-stu-id="9bba9-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="9bba9-127">我的用户是否拥有通话套餐许可证？</span><span class="sxs-lookup"><span data-stu-id="9bba9-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="9bba9-128">若要购买和分配许可证，请参阅 [步骤 2：购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="9bba9-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="9bba9-129">我的用户是否都有直接拨入 (电话号码) 电话号码？</span><span class="sxs-lookup"><span data-stu-id="9bba9-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="9bba9-130">若要获取电话号码，请参阅 [步骤 3：获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="9bba9-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="9bba9-131">将电话号码转移到Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="9bba9-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="9bba9-132">可以轻松将电话号码从当前服务提供商转移到Teams。</span><span class="sxs-lookup"><span data-stu-id="9bba9-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="9bba9-133">将电话号码移植到Teams，Microsoft 将成为服务提供商，并针对这些电话号码计费。</span><span class="sxs-lookup"><span data-stu-id="9bba9-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="9bba9-134">有关详细信息，请参阅[将电话号码转移到 Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9bba9-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="9bba9-135">电话号码和紧急位置</span><span class="sxs-lookup"><span data-stu-id="9bba9-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="9bba9-136">使用 Microsoft 365 或 Office 365 中的呼叫计划，您的组织中的每个用户都需要具有唯一的直接拨入 (DID) 电话号码和相应的已验证紧急地址。</span><span class="sxs-lookup"><span data-stu-id="9bba9-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="9bba9-137">还可以在紧急地址内指定紧急 (，例如办公室号码或楼层) 。</span><span class="sxs-lookup"><span data-stu-id="9bba9-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="9bba9-138">询问你自己</span><span class="sxs-lookup"><span data-stu-id="9bba9-138">Ask yourself</span></span>|<span data-ttu-id="9bba9-139">操作</span><span class="sxs-lookup"><span data-stu-id="9bba9-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9bba9-140">希望紧急地址和位置信息有多详细？</span><span class="sxs-lookup"><span data-stu-id="9bba9-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="9bba9-141">有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？。](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="9bba9-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="9bba9-142">调用标识</span><span class="sxs-lookup"><span data-stu-id="9bba9-142">Calling identity</span></span>

<span data-ttu-id="9bba9-143">默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫者 ID) 。</span><span class="sxs-lookup"><span data-stu-id="9bba9-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="9bba9-144">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="9bba9-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="9bba9-145">询问你自己</span><span class="sxs-lookup"><span data-stu-id="9bba9-145">Ask yourself</span></span>|<span data-ttu-id="9bba9-146">操作</span><span class="sxs-lookup"><span data-stu-id="9bba9-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9bba9-147">是否要屏蔽或禁用来电显示？</span><span class="sxs-lookup"><span data-stu-id="9bba9-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="9bba9-148">若要更改或阻止来电显示，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9bba9-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||