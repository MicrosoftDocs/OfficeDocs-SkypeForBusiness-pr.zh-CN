---
title: Microsoft Teams 中的通话套餐
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 调用计划登录页
appliesto:
- Microsoft Teams
ms.openlocfilehash: 412797a52e82c03937670e895fea7b42a3ce7b4a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460753"
---
# <a name="phone-system-with-calling-plans"></a><span data-ttu-id="5818b-103">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="5818b-103">Phone System with Calling Plans</span></span> 

<span data-ttu-id="5818b-104">您已完成的[开始](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="5818b-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="5818b-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="5818b-106">也许您已经部署了[会议 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="5818b-107">现在已准备好添加云语音工作负荷，因而您已决定使用调用计划与 Microsoft 电话系统连接到公共公用电话交换网 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="5818b-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="5818b-108">本文介绍数据调用计划以及其他注意事项核心部署决策可能想要配置，根据组织的需要。</span><span class="sxs-lookup"><span data-stu-id="5818b-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="5818b-109">有关 Microsoft 云语音产品的详细信息，您还应阅读[Microsoft 团队中的云语音功能](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="5818b-110">了解有关调用计划</span><span class="sxs-lookup"><span data-stu-id="5818b-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="5818b-111">以下文章提供有关部署和使用 Microsoft 调用计划的详细信息：</span><span class="sxs-lookup"><span data-stu-id="5818b-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="5818b-112">Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="5818b-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="5818b-113">Office 365 通话套餐</span><span class="sxs-lookup"><span data-stu-id="5818b-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="5818b-114">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="5818b-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="5818b-115">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="5818b-115">Core deployment decisions</span></span>

<span data-ttu-id="5818b-116">若要使用 Microsoft 为您的电话运营商，您需要获得调用规划许可证并将其分配给您电话系统的用户。</span><span class="sxs-lookup"><span data-stu-id="5818b-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="5818b-117">有两种类型的调用计划：</span><span class="sxs-lookup"><span data-stu-id="5818b-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="5818b-118">国内呼叫计划</span><span class="sxs-lookup"><span data-stu-id="5818b-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="5818b-119">国内和国际呼叫计划</span><span class="sxs-lookup"><span data-stu-id="5818b-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="5818b-120">询问你自己</span><span class="sxs-lookup"><span data-stu-id="5818b-120">Ask yourself</span></span>|<span data-ttu-id="5818b-121">操作</span><span class="sxs-lookup"><span data-stu-id="5818b-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="5818b-122">有调用计划在我的区域中？</span><span class="sxs-lookup"><span data-stu-id="5818b-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="5818b-123">哪些用户位置会调用规划服务？</span><span class="sxs-lookup"><span data-stu-id="5818b-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="5818b-124">有关详细信息，请参阅[国家和地区音频会议和调用计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="5818b-125">我的用户是否需要国际呼叫？</span><span class="sxs-lookup"><span data-stu-id="5818b-125">Do my users need international calling?</span></span> | <span data-ttu-id="5818b-126">有关详细信息，请参阅[调用 Office 365 的计划](calling-plans-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="5818b-127">我的用户是否具有调用计划许可证？</span><span class="sxs-lookup"><span data-stu-id="5818b-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="5818b-128">若要购买并分配许可证时，请参阅[步骤 2： 购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="5818b-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="5818b-129">每个我用户是否有直接向内拨打 (DID) 电话号码？</span><span class="sxs-lookup"><span data-stu-id="5818b-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="5818b-130">若要获取电话号码，请参阅[步骤 3： 获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="5818b-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="5818b-131">将电话号码转接到 Office 365</span><span class="sxs-lookup"><span data-stu-id="5818b-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="5818b-132">很容易将您的电话号码从您当前的服务提供商转接到团队。</span><span class="sxs-lookup"><span data-stu-id="5818b-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="5818b-133">端口您向工作组的电话号码后，Microsoft 将成为服务提供商，将向您为这些电话号码。</span><span class="sxs-lookup"><span data-stu-id="5818b-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="5818b-134">有关详细信息，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="5818b-135">电话号码和紧急位置</span><span class="sxs-lookup"><span data-stu-id="5818b-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="5818b-136">与调用计划在 Office 365 中，每个用户在您的组织需要具有唯一直接拨入 (DID) 电话号码和相应的验证紧急地址。</span><span class="sxs-lookup"><span data-stu-id="5818b-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="5818b-137">您还可以指定紧急地址 （例如，办公室号码或楼层号） 中的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="5818b-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="5818b-138">询问你自己</span><span class="sxs-lookup"><span data-stu-id="5818b-138">Ask yourself</span></span>|<span data-ttu-id="5818b-139">操作</span><span class="sxs-lookup"><span data-stu-id="5818b-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="5818b-140">如何详细我是否需要为的紧急地址和位置信息？</span><span class="sxs-lookup"><span data-stu-id="5818b-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="5818b-141">有关详细信息，请参阅[紧急位置、 地址和呼叫路由是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。</span><span class="sxs-lookup"><span data-stu-id="5818b-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="5818b-142">呼叫标识</span><span class="sxs-lookup"><span data-stu-id="5818b-142">Calling identity</span></span>

<span data-ttu-id="5818b-143">默认情况下，所有出站呼叫的分配的电话号码用作调用 identity (呼叫者 ID)。</span><span class="sxs-lookup"><span data-stu-id="5818b-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="5818b-144">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="5818b-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="5818b-145">询问你自己</span><span class="sxs-lookup"><span data-stu-id="5818b-145">Ask yourself</span></span>|<span data-ttu-id="5818b-146">操作</span><span class="sxs-lookup"><span data-stu-id="5818b-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="5818b-147">我想要屏蔽或禁用呼叫者 ID 吗？</span><span class="sxs-lookup"><span data-stu-id="5818b-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="5818b-148">若要更改或阻止呼叫者 ID，请参阅[设置用户的呼叫者 ID](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="5818b-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




