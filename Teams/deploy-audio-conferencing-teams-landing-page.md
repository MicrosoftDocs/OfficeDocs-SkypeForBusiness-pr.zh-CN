---
title: 配置音频会议设置 - Microsoft Teams
ms.reviewer: ''
description: 使用这些部署资源来帮助你部署作为 Microsoft Teams 中的会议工作负载一部分的音频会议。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 755a8499f62e39333b075519cc181dbd7c44e143
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521619"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="07172-103">了解如何在 Microsoft Teams 中部署音频会议</span><span class="sxs-lookup"><span data-stu-id="07172-103">Learn how to deploy audio conferencing in Microsoft Teams</span></span>

<span data-ttu-id="07172-104">音频会议是指通过普通电话加入 Teams 会议或从会议中拨出到某个电话号码的功能。</span><span class="sxs-lookup"><span data-stu-id="07172-104">Audio Conferencing is the ability to join a Teams meeting from a regular phone and dial out from a meeting to a phone number.</span></span> <span data-ttu-id="07172-105">确保在组织中部署音频会议的过程中已经查看了[会议部署](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-105">Be sure you've reviewed [Meetings rollout](deploy-meetings-microsoft-teams-landing-page.md) as part of rolling out Audio Conferencing in your organization.</span></span>

## <a name="audio-conferencing-deployment-decisions"></a><span data-ttu-id="07172-106">音频会议部署决策</span><span class="sxs-lookup"><span data-stu-id="07172-106">Audio Conferencing deployment decisions</span></span>

<span data-ttu-id="07172-107">本文根据组织的情况和业务需求来帮助你决定是否更改任何默认音频会议设置，然后引导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="07172-107">This article helps you decide whether to change any of the default Audio Conferencing settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="07172-108">我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="07172-108">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="07172-109">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="07172-109">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="07172-110">你只需为打算安排或主持会议的人设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="07172-110">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="07172-111">通过拨入方式参与的与会者无需任何分配的许可证或进行任何其他设置。</span><span class="sxs-lookup"><span data-stu-id="07172-111">Meeting attendees who dial in don't need any licenses assigned to them or any other setup.</span></span> <span data-ttu-id="07172-112">对于在旅途中并且无法使用其笔记本电脑或移动设备上的 Skype for Business 或 Teams 应用参与会议的用户来说，拨入（或呼入）会议非常有用。</span><span class="sxs-lookup"><span data-stu-id="07172-112">Dialing in (calling in) to meetings is very useful for users who are on the road and can't attend a meeting using the Skype for Business or Teams app on their laptops or mobile devices.</span></span> 


## <a name="audio-conferencing-prerequisites"></a><span data-ttu-id="07172-113">音频会议先决条件</span><span class="sxs-lookup"><span data-stu-id="07172-113">Audio Conferencing prerequisites</span></span> 

<span data-ttu-id="07172-114">在部署 Teams 的音频会议功能之前，请考虑以下各项：</span><span class="sxs-lookup"><span data-stu-id="07172-114">Before you can roll out Audio Conferencing for Teams, consider the following:</span></span>

|<span data-ttu-id="07172-115">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-115">Ask yourself</span></span>|<span data-ttu-id="07172-116">操作</span><span class="sxs-lookup"><span data-stu-id="07172-116">Action</span></span> |
|------------|-------|
|<span data-ttu-id="07172-117">我所在的国家/地区是否可以使用音频会议功能？</span><span class="sxs-lookup"><span data-stu-id="07172-117">Is Audio Conferencing available for my country/region?</span></span>|<span data-ttu-id="07172-118">若要了解你所在的国家/地区是否可使用音频会议功能，请参阅[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-118">To find out if Audio Conferencing is available for your country/region, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>|
|<span data-ttu-id="07172-119">我的用户是否有适当的 Teams 音频会议许可？</span><span class="sxs-lookup"><span data-stu-id="07172-119">Do my users have the proper licensing for Teams Audio Conferencing?</span></span>|<span data-ttu-id="07172-120">音频会议许可证作为 Microsoft 365 或 Office 365 E5 订阅的一部分提供，或作为 Microsoft 365 商业标准版 E1 或 E3 订阅的一项附加服务提供。</span><span class="sxs-lookup"><span data-stu-id="07172-120">Audio Conferencing licenses are available as part of a Microsoft 365 or Office 365 E5 subscription or as an add-on service for a Microsoft 365 Business Standard, E1, or E3 subscription.</span></span> <ul><li><span data-ttu-id="07172-121">若要获取和分配许可证，请参阅[在 Microsoft 365 或 Office 365 中试用或购买音频会议功能](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)以及[分配或移除 Microsoft 365 商业应用版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="07172-121">To get and assign licenses, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) and [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span></li><li> <span data-ttu-id="07172-122">若要了解详细信息，请阅读 [Microsoft Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="07172-122">To learn more, read [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span> </li><li><span data-ttu-id="07172-123">若要了解每种计划中包括哪些云功能，请参阅[基于计划的许可证选项](teams-add-on-licensing/office-365-business-premium.md)文章。</span><span class="sxs-lookup"><span data-stu-id="07172-123">To see what cloud features are included in each plan, see the [License options based on your plan](teams-add-on-licensing/office-365-business-premium.md) articles.</span></span></li></ul>|
|<span data-ttu-id="07172-124">是否需要为分配有音频会议许可证的用户购买通信点数？</span><span class="sxs-lookup"><span data-stu-id="07172-124">Do I need to purchase Communications Credits for the users who are assigned Audio Conferencing licenses?</span></span>|<span data-ttu-id="07172-125">若要了解详情，请阅读[什么是通信点数](what-are-communications-credits.md)，然后查看下面的[通信点数](#communications-credits)部分。</span><span class="sxs-lookup"><span data-stu-id="07172-125">To learn more, read [What are Communications Credits](what-are-communications-credits.md), then check out the [Communications Credits](#communications-credits) section below.</span></span>|
|||


## <a name="core-deployment-decisions"></a><span data-ttu-id="07172-126">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="07172-126">Core deployment decisions</span></span>

<span data-ttu-id="07172-127">满足了音频会议先决条件后，请完成以下任务来为用户配置音频会议。</span><span class="sxs-lookup"><span data-stu-id="07172-127">After you meet the Audio Conferencing prerequisites, complete the following tasks to configure Audio Conferencing for your users.</span></span>


### <a name="teams-administrators"></a><span data-ttu-id="07172-128">Teams 管理员</span><span class="sxs-lookup"><span data-stu-id="07172-128">Teams administrators</span></span>

<span data-ttu-id="07172-129">Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。</span><span class="sxs-lookup"><span data-stu-id="07172-129">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="07172-130">这些角色为管理员提供各种能力。</span><span class="sxs-lookup"><span data-stu-id="07172-130">The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="07172-131">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-131">Ask yourself</span></span> | <span data-ttu-id="07172-132">操作</span><span class="sxs-lookup"><span data-stu-id="07172-132">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="07172-133">将为谁分配 Teams 通信管理员角色？</span><span class="sxs-lookup"><span data-stu-id="07172-133">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="07172-134">若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-134">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="07172-135">将为谁分配 Teams 通信支持工程师角色？</span><span class="sxs-lookup"><span data-stu-id="07172-135">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="07172-136">若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="07172-136">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="07172-137">将为谁分配 Teams 通信支持专家角色？</span><span class="sxs-lookup"><span data-stu-id="07172-137">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a><span data-ttu-id="07172-138">会议网桥和电话号码</span><span class="sxs-lookup"><span data-stu-id="07172-138">Conferencing bridges and phone numbers</span></span>

<span data-ttu-id="07172-139">会议网桥使用户能够使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="07172-139">Conferencing bridges let people dial into meetings using a phone.</span></span> <span data-ttu-id="07172-140">可以使用会议网桥的默认设置，也可以更改电话号码（收费和免费）和其他设置（如 PIN 或使用的语言）。</span><span class="sxs-lookup"><span data-stu-id="07172-140">You can use the default settings for a conferencing bridge or change the phone numbers (toll and toll-free) and other settings, such as the PIN or the languages that are used.</span></span>

<span data-ttu-id="07172-141">请参阅[音频会议](audio-conferencing-in-office-365.md)了解详情。</span><span class="sxs-lookup"><span data-stu-id="07172-141">See [Audio Conferencing](audio-conferencing-in-office-365.md) to learn more.</span></span>

|<span data-ttu-id="07172-142">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-142">Ask yourself</span></span>|<span data-ttu-id="07172-143">操作</span><span class="sxs-lookup"><span data-stu-id="07172-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="07172-144">是否需要添加新的会议网桥号码？</span><span class="sxs-lookup"><span data-stu-id="07172-144">Do I need to add new conferencing bridge numbers?</span></span>| <span data-ttu-id="07172-145">若要添加新号码，请参阅[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="07172-145">To add new numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>|
|<span data-ttu-id="07172-146">是否需要修改网桥设置？</span><span class="sxs-lookup"><span data-stu-id="07172-146">Will I need to modify the bridge settings?</span></span>|<span data-ttu-id="07172-147">若要修改网桥设置，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-147">To modify the bridge settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="07172-148">是否需要移植号码以用于音频会议？</span><span class="sxs-lookup"><span data-stu-id="07172-148">Do I need to port numbers to use with audio conferencing?</span></span>|<span data-ttu-id="07172-149">若要了解移植电话号码，请阅读[将电话号码转移到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-149">To learn about porting phone numbers, read [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>|
|||


### <a name="default-and-alternate-languages"></a><span data-ttu-id="07172-150">默认语言和备用语言</span><span class="sxs-lookup"><span data-stu-id="07172-150">Default and alternate languages</span></span>

<span data-ttu-id="07172-151">Teams 音频会议允许你为会议网桥设置默认语言和备用语言。</span><span class="sxs-lookup"><span data-stu-id="07172-151">Teams Audio Conferencing lets you set up default and alternate languages for a conferencing bridge.</span></span>

|<span data-ttu-id="07172-152">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-152">Ask yourself</span></span>|<span data-ttu-id="07172-153">操作</span><span class="sxs-lookup"><span data-stu-id="07172-153">Action</span></span> |
|------------|-------|
| <span data-ttu-id="07172-154">我应为自动助理问候选择哪些语言？</span><span class="sxs-lookup"><span data-stu-id="07172-154">Which languages should I choose for auto attendant greetings?</span></span> | <span data-ttu-id="07172-155">若要选择语言，请参阅[为音频会议设置自动助理语言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="07172-155">To choose languages, see [Set auto attendant languages for Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="conferencing-bridge-settings"></a><span data-ttu-id="07172-156">会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="07172-156">Conferencing bridge settings</span></span> 

<span data-ttu-id="07172-157">设置了会议网桥（包括默认语言和备用语言）之后，你应验证诸如进入/退出通知和 PIN 长度等默认设置是否符合你的要求。</span><span class="sxs-lookup"><span data-stu-id="07172-157">After setting up your conferencing bridge, including default and alternate languages, you should verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use.</span></span> <span data-ttu-id="07172-158">如果不符合，你可以更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="07172-158">If they're not, you can change them.</span></span> 

|<span data-ttu-id="07172-159">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-159">Ask yourself</span></span>|<span data-ttu-id="07172-160">操作</span><span class="sxs-lookup"><span data-stu-id="07172-160">Action</span></span> |
|------------|-------|
| <span data-ttu-id="07172-161">当用户加入或退出会议时，与会者是否将听到一条通知？</span><span class="sxs-lookup"><span data-stu-id="07172-161">Will attendees hear a notification when a user joins or exits a meeting?</span></span> | <span data-ttu-id="07172-162">若要更改这些设置，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-162">To change these settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="07172-163">会议组织者用于开始会议的 PIN 必须设置为什么长度？</span><span class="sxs-lookup"><span data-stu-id="07172-163">What is the required length of the PIN that a meeting organizer uses to start the meeting?</span></span>||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a><span data-ttu-id="07172-164">主持会议的用户的拨入电话号码设置</span><span class="sxs-lookup"><span data-stu-id="07172-164">Dial-in phone number settings for users who lead meetings</span></span>

<span data-ttu-id="07172-165">创建音频会议网桥后，需要设置主持会议的用户将使用的收费和/或免费号码。</span><span class="sxs-lookup"><span data-stu-id="07172-165">After you create your Audio Conferencing bridge, you need to set the toll and/or toll-free numbers that users who lead meetings will use.</span></span>

|<span data-ttu-id="07172-166">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-166">Ask yourself</span></span>|<span data-ttu-id="07172-167">操作</span><span class="sxs-lookup"><span data-stu-id="07172-167">Action</span></span> |
|------------|-------|
| <span data-ttu-id="07172-168">为将主持会议的每名用户分配哪些会议网桥号码？</span><span class="sxs-lookup"><span data-stu-id="07172-168">Which conference bridge numbers will I assign to each user who leads meetings?</span></span> | <span data-ttu-id="07172-169">若要为用户分配拨入电话号码，请参阅[步骤 7：为主持会议的用户分配拨入电话号码](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)。</span><span class="sxs-lookup"><span data-stu-id="07172-169">To assign a dial-in phone number to a user, see [Step 7: Assign dial-in phone numbers for users who lead meetings](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings).</span></span> |
|||

### <a name="communications-credits"></a><span data-ttu-id="07172-170">通信点数</span><span class="sxs-lookup"><span data-stu-id="07172-170">Communications Credits</span></span>

<span data-ttu-id="07172-171">为了提供免费会议网桥电话号码以及支持会议向国际电话号码拨出，你需要贵组织设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="07172-171">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you must set up Communications Credits for your organization.</span></span> <span data-ttu-id="07172-172">若要详细了解通信点数，请参阅[什么是通信点数？](what-are-communications-credits.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-172">To learn more about Communications Credits, see [What are Communications Credits?](what-are-communications-credits.md).</span></span>

|<span data-ttu-id="07172-173">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-173">Ask yourself</span></span>|<span data-ttu-id="07172-174">操作</span><span class="sxs-lookup"><span data-stu-id="07172-174">Action</span></span> |
|------------|-------|
|<span data-ttu-id="07172-175">我的音频会议实现是否需要通信点数？</span><span class="sxs-lookup"><span data-stu-id="07172-175">Are Communications Credits required for my Audio Conferencing implementation?</span></span> |<span data-ttu-id="07172-176">若要了解你是否需要设置通信点数，请参阅[为你的组织设置通信点数](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-176">To find out if you need to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|<span data-ttu-id="07172-177">如果需要通信点数，我应该购买多少？</span><span class="sxs-lookup"><span data-stu-id="07172-177">If they're required, how much should I purchase?</span></span>|<span data-ttu-id="07172-178">若要确定通信点数数额，请参阅[推荐的资金金额](what-are-communications-credits.md#recommended-funding-amounts)。</span><span class="sxs-lookup"><span data-stu-id="07172-178">To determine the Communications Credits amount, see [Recommended funding amounts](what-are-communications-credits.md#recommended-funding-amounts).</span></span>|
|<span data-ttu-id="07172-179">是否要配置自动充值金额？</span><span class="sxs-lookup"><span data-stu-id="07172-179">Do I want to configure an auto-recharge amount?</span></span>|<span data-ttu-id="07172-180">若要配置自动充值金额，请参阅[为你的组织设置通信点数](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-180">To configure an auto-recharge amount, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|||



## <a name="additional-deployment-decisions"></a><span data-ttu-id="07172-181">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="07172-181">Additional deployment decisions</span></span>

<span data-ttu-id="07172-182">你可能需要根据组织的需求和配置更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="07172-182">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="outbound-calling-restriction-policies"></a><span data-ttu-id="07172-183">出站呼叫限制策略</span><span class="sxs-lookup"><span data-stu-id="07172-183">Outbound calling restriction policies</span></span> 

<span data-ttu-id="07172-184">作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="07172-184">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span>

|<span data-ttu-id="07172-185">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-185">Ask yourself</span></span>|<span data-ttu-id="07172-186">操作</span><span class="sxs-lookup"><span data-stu-id="07172-186">Action</span></span> |
|------------|-------|
| <span data-ttu-id="07172-187">是否将限制允许的出站通话类型？</span><span class="sxs-lookup"><span data-stu-id="07172-187">Will I limit the type of outbound calls that are allowed?</span></span> | <span data-ttu-id="07172-188">若要限制出站通话，请参阅[音频会议和用户 PSTN 通话的出站通话限制策略](outbound-calling-restriction-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-188">To restrict outbound calls, see [Outbound calling restriction policies for Audio Conferencing and user PSTN calls](outbound-calling-restriction-policies.md).</span></span>|
|||


### <a name="dial-plans"></a><span data-ttu-id="07172-189">拨号计划</span><span class="sxs-lookup"><span data-stu-id="07172-189">Dial plans</span></span>

<span data-ttu-id="07172-190">作为 Microsoft 365 或 Office 365 电话系统一部分的拨号计划是一组规范化规则，用于将拨打的电话号码转换为替代格式（通常为 E.164 格式）以便进行通话授权和通话路由。</span><span class="sxs-lookup"><span data-stu-id="07172-190">A dial plan, as part of Phone System in Microsoft 365 or Office 365, is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="07172-191">有关拨号计划的详细信息，请参阅[什么是拨号计划？](what-are-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="07172-191">For more information about dial plans, see [What are dial plans?](what-are-dial-plans.md)</span></span>

|<span data-ttu-id="07172-192">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-192">Ask yourself</span></span>|<span data-ttu-id="07172-193">操作</span><span class="sxs-lookup"><span data-stu-id="07172-193">Action</span></span> |
|------------|-------|
|<span data-ttu-id="07172-194">我的组织是否需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="07172-194">Does my organization need a customized dial plan?</span></span>|<span data-ttu-id="07172-195">为了帮助确定你是否需要自定义拨号计划，请参阅[规划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)。</span><span class="sxs-lookup"><span data-stu-id="07172-195">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans).</span></span> |
|<span data-ttu-id="07172-196">哪些用户需要自定义拨号计划，应为每个用户分配哪种租户拨号计划？</span><span class="sxs-lookup"><span data-stu-id="07172-196">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span>|<span data-ttu-id="07172-197">若要使用 PowerShell 将用户添加到自定义拨号计划，请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-197">To add users to a customized dial plan using PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="07172-198">会议和通话质量疑难解答</span><span class="sxs-lookup"><span data-stu-id="07172-198">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="07172-199">Teams 提供两种用于监视和排除通话质量问题的方法：[通话分析和通话质量仪表板](monitor-call-quality-qos.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-199">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](monitor-call-quality-qos.md).</span></span> <span data-ttu-id="07172-200">通话分析显示有关与每个用户的特定通话和会议相关的设备、网络和连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="07172-200">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="07172-201">通话分析旨在帮助管理员和技术支持人员解决特定通话的通话质量问题，而通话质量仪表板旨在帮助管理员和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="07172-201">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="07172-202">通话质量仪表板关注的不是特定用户，而是整个 Teams 组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="07172-202">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="07172-203">询问你自己</span><span class="sxs-lookup"><span data-stu-id="07172-203">Ask yourself</span></span>|<span data-ttu-id="07172-204">操作</span><span class="sxs-lookup"><span data-stu-id="07172-204">Action</span></span> |
|------------|-------|
| <span data-ttu-id="07172-205">谁将负责监视和排查通话质量问题？</span><span class="sxs-lookup"><span data-stu-id="07172-205">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="07172-206">请参阅[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)，了解排查通话质量问题所需的权限级别。</span><span class="sxs-lookup"><span data-stu-id="07172-206">See [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="07172-207">后续步骤</span><span class="sxs-lookup"><span data-stu-id="07172-207">Next steps</span></span>
- <span data-ttu-id="07172-208">在组织内[推动采用](adopt-microsoft-teams-landing-page.md)音频会议。</span><span class="sxs-lookup"><span data-stu-id="07172-208">[Drive adoption](adopt-microsoft-teams-landing-page.md) of audio conferencing in your organization.</span></span>
- [<span data-ttu-id="07172-209">部署云语音</span><span class="sxs-lookup"><span data-stu-id="07172-209">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="07172-210">在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="07172-210">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="07172-211">在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="07172-211">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
