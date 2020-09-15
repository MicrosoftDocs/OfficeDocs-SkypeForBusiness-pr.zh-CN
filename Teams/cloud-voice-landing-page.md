---
title: Microsoft Teams 中的云语音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: 了解有关云语音功能的详细信息，并了解你将面临的必要部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 851e14e934578b0da8853991e1bc993e8483f818
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814872"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="e946a-103">语音电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="e946a-103">Voice - Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="e946a-104">你已完成了[入门](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="e946a-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="e946a-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="e946a-106">也许你已将 [会议部署 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="e946a-107">现在，你已准备好为你的用户添加语音功能。</span><span class="sxs-lookup"><span data-stu-id="e946a-107">Now you're ready to add voice capabilities for your users.</span></span> 

<span data-ttu-id="e946a-108">语音提供专用分支 Exchange (PBX) 功能，以及用于连接到公共交换电话网络 (PSTN) 的选项。</span><span class="sxs-lookup"><span data-stu-id="e946a-108">Voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="e946a-109">本文将帮助你确定是否需要根据组织的配置文件和业务要求更改任何默认的语音设置，然后将指导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="e946a-109">This article helps you decide whether you need to change any of the default voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="e946a-110">我们已将设置拆分为两个组，从 [你更可能进行](#core-deployment-decisions)的一组核心更改开始。</span><span class="sxs-lookup"><span data-stu-id="e946a-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="e946a-111">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="e946a-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="e946a-112">我们建议所有组织通过核心决策，然后，如果您的组织有其他要求，请查看以下资料。</span><span class="sxs-lookup"><span data-stu-id="e946a-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>

 > [!Note]
 > <span data-ttu-id="e946a-113">有关详细信息，请参阅 [按平台的团队功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) 。</span><span class="sxs-lookup"><span data-stu-id="e946a-113">See [Team features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) for more information.</span></span>

## <a name="learn-more-about-voice"></a><span data-ttu-id="e946a-114">了解有关语音的详细信息</span><span class="sxs-lookup"><span data-stu-id="e946a-114">Learn more about voice</span></span>

<span data-ttu-id="e946a-115">以下文章提供了有关在团队中部署和使用语音功能的详细信息：</span><span class="sxs-lookup"><span data-stu-id="e946a-115">The following articles provide more information about deploying and using voice features in Teams:</span></span>

- [<span data-ttu-id="e946a-116">Microsoft 365 或 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="e946a-116">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="e946a-117">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="e946a-117">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="e946a-118">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="e946a-118">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="e946a-119">Microsoft 电话解决方案</span><span class="sxs-lookup"><span data-stu-id="e946a-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="e946a-120">观看以下会话以了解有关电话系统的详细信息： [Microsoft 团队中的电话系统简介](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="e946a-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="e946a-121">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="e946a-121">Core deployment decisions</span></span>

<span data-ttu-id="e946a-122">以下是大多数组织在默认设置不适合的情况下想要更改的设置。</span><span class="sxs-lookup"><span data-stu-id="e946a-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="e946a-123">电话系统 (Office 365) </span><span class="sxs-lookup"><span data-stu-id="e946a-123">Phone System (Office 365)</span></span>

<span data-ttu-id="e946a-124">电话系统是 Microsoft 365 或 Office 365 云中 (PBX) 功能的 Microsoft 技术，用于启用呼叫控制和专用分支 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e946a-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud.</span></span> <span data-ttu-id="e946a-125">通过电话系统，你可以使用从 Microsoft 365 或 Office 365 直接提供的一组功能将现有的专用分支 Exchange (PBX) 系统替换为公司的云生产效率体验。</span><span class="sxs-lookup"><span data-stu-id="e946a-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Microsoft 365 or Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="e946a-126">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-126">Ask yourself</span></span>|<span data-ttu-id="e946a-127">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="e946a-128">哪些用户位置或办公室将实施电话系统？</span><span class="sxs-lookup"><span data-stu-id="e946a-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="e946a-129">有关电话系统的详细信息，请参阅 [Microsoft 365 或 Office 365 中的什么是电话系统](what-is-phone-system-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-129">For more information about Phone System, see [What is Phone System in Microsoft 365 or Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="e946a-130">连接到公共交换电话网络 (PSTN) </span><span class="sxs-lookup"><span data-stu-id="e946a-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="e946a-131">若要将电话系统连接到公共交换电话网络 (PSTN) 以便用户可以拨打世界各地的电话，您可以根据自己的业务需求进行选择。</span><span class="sxs-lookup"><span data-stu-id="e946a-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="e946a-132">询问自己以下事项：</span><span class="sxs-lookup"><span data-stu-id="e946a-132">Ask yourself the following:</span></span>


|<span data-ttu-id="e946a-133">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-133">Ask yourself</span></span>|<span data-ttu-id="e946a-134">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="e946a-135">我是否希望使用 Microsoft 通话计划作为我的电话运营商？</span><span class="sxs-lookup"><span data-stu-id="e946a-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="e946a-136">有关详细信息，请参阅 [带有通话计划的电话系统](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="e946a-137">我是否需要使用自己的电话运营商？</span><span class="sxs-lookup"><span data-stu-id="e946a-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="e946a-138">有关详细信息，请参阅 [带有直接路由的电话系统](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="e946a-139">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="e946a-139">Additional deployment decisions</span></span>

<span data-ttu-id="e946a-140">你可能需要根据组织的需求和配置来更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="e946a-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="e946a-141">语音邮件</span><span class="sxs-lookup"><span data-stu-id="e946a-141">Voicemail</span></span>
- <span data-ttu-id="e946a-142">通话标识</span><span class="sxs-lookup"><span data-stu-id="e946a-142">Calling identity</span></span>
- <span data-ttu-id="e946a-143">Microsoft 的电话号码</span><span class="sxs-lookup"><span data-stu-id="e946a-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="e946a-144">拨号计划</span><span class="sxs-lookup"><span data-stu-id="e946a-144">Dial plans</span></span>
- <span data-ttu-id="e946a-145">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="e946a-145">Call queues</span></span>
- <span data-ttu-id="e946a-146">自动助理</span><span class="sxs-lookup"><span data-stu-id="e946a-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="e946a-147">语音邮件</span><span class="sxs-lookup"><span data-stu-id="e946a-147">Voicemail</span></span>

<span data-ttu-id="e946a-148">云语音邮件（由 Azure 语音邮件服务提供支持）仅支持 Exchange 邮箱的语音邮件存款，不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="e946a-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="e946a-149">云语音邮件包括语音邮件脚本，默认情况下为组织中的所有用户启用。</span><span class="sxs-lookup"><span data-stu-id="e946a-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="e946a-150">您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。</span><span class="sxs-lookup"><span data-stu-id="e946a-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="e946a-151">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-151">Ask yourself</span></span>|<span data-ttu-id="e946a-152">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e946a-153">是否要启用云语音邮件？</span><span class="sxs-lookup"><span data-stu-id="e946a-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="e946a-154">有关语音邮件设置过程，请参阅 [设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="e946a-155">我是否希望为部分或全部用户启用语音邮件功能？</span><span class="sxs-lookup"><span data-stu-id="e946a-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="e946a-156">要关闭语音邮件脚本，请参阅在 [组织中设置语音邮件策略](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="e946a-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="e946a-157">通话标识</span><span class="sxs-lookup"><span data-stu-id="e946a-157">Calling identity</span></span>

<span data-ttu-id="e946a-158">默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫方 ID) 。</span><span class="sxs-lookup"><span data-stu-id="e946a-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="e946a-159">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="e946a-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="e946a-160">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-160">Ask yourself</span></span>|<span data-ttu-id="e946a-161">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="e946a-162">我是否希望屏蔽或禁用来电显示？</span><span class="sxs-lookup"><span data-stu-id="e946a-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="e946a-163">若要更改或阻止呼叫方 ID，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="e946a-164">Microsoft 的电话号码</span><span class="sxs-lookup"><span data-stu-id="e946a-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="e946a-165">Microsoft 有两种类型的电话号码可供使用： *订户* (用户) 号码（可分配给您组织中的用户）和 *服务* 号码（如收费电话和免费服务号码），该号码具有比订户号码更高的并行通话能力，并且可以分配给诸如音频会议、自动助理或呼叫队列等服务。</span><span class="sxs-lookup"><span data-stu-id="e946a-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="e946a-166">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-166">Ask yourself</span></span>|<span data-ttu-id="e946a-167">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="e946a-168">哪些用户位置需要来自 Microsoft 的新电话号码？</span><span class="sxs-lookup"><span data-stu-id="e946a-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="e946a-169">有关获取电话号码的信息，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 和 [获取用户的电话号码](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="e946a-170">我需要 (订阅者或服务) 哪些类型的电话号码？</span><span class="sxs-lookup"><span data-stu-id="e946a-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="e946a-171">为帮助您选择所需的电话号码类型，请参阅 [用于通话计划的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="e946a-172">如何将现有电话号码移植到团队？</span><span class="sxs-lookup"><span data-stu-id="e946a-172">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="e946a-173">有关详细信息，请参阅 [将电话号码转移给 Microsoft 团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-173">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="e946a-174">拨号计划</span><span class="sxs-lookup"><span data-stu-id="e946a-174">Dial plans</span></span>

<span data-ttu-id="e946a-175">Microsoft 365 或 Office 365 的电话系统功能中的拨号计划是一组规范化规则，可将拨出的电话号码转换为备用格式 (通常为) 授权和呼叫路由的 E-164 格式的格式。</span><span class="sxs-lookup"><span data-stu-id="e946a-175">A dial plan in the Phone System feature of Microsoft 365 or Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="e946a-176">有关拨号计划的详细信息，请参阅[什么是拨号计划？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="e946a-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="e946a-177">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-177">Ask yourself</span></span>|<span data-ttu-id="e946a-178">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e946a-179">我的组织是否需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="e946a-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="e946a-180">若要帮助确定是否需要自定义拨号计划，请参阅 [计划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="e946a-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="e946a-181">哪些用户需要自定义拨号计划，应为每个用户分配哪种租户拨号计划？</span><span class="sxs-lookup"><span data-stu-id="e946a-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="e946a-182">若要将用户添加到 PowerShell 中的自定义拨号计划，请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="e946a-183">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="e946a-183">Call queues</span></span>

<span data-ttu-id="e946a-184">云呼叫队列包括当某人拨入到您的组织的电话号码时使用的问候语、自动将呼叫置于保持状态的功能，以及搜索下一个可用的呼叫代理以处理呼叫的功能，同时呼叫正在收听音乐的用户。</span><span class="sxs-lookup"><span data-stu-id="e946a-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="e946a-185">您可以为您的组织创建单个或多个通话队列。</span><span class="sxs-lookup"><span data-stu-id="e946a-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="e946a-186">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-186">Ask yourself</span></span>|<span data-ttu-id="e946a-187">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e946a-188">我的组织是否需要呼叫队列？</span><span class="sxs-lookup"><span data-stu-id="e946a-188">Does my organization need call queues?</span></span> | <span data-ttu-id="e946a-189">有关详细信息，请参阅 [创建云呼叫队列](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 和 [设置电话系统](setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="e946a-190">自动助理</span><span class="sxs-lookup"><span data-stu-id="e946a-190">Auto attendants</span></span>

<span data-ttu-id="e946a-191">云自动助理可用于为你的组织创建菜单系统，该系统允许外部和内部调用方在菜单系统中移动到你的组织中的公司用户或部门查找和放置或转移呼叫。</span><span class="sxs-lookup"><span data-stu-id="e946a-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="e946a-192">询问你自己</span><span class="sxs-lookup"><span data-stu-id="e946a-192">Ask yourself</span></span>|<span data-ttu-id="e946a-193">操作</span><span class="sxs-lookup"><span data-stu-id="e946a-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="e946a-194">我的组织是否需要自动助理？</span><span class="sxs-lookup"><span data-stu-id="e946a-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="e946a-195">有关详细信息，请参阅 [什么是云自动](what-are-phone-system-auto-attendants.md) 助理以及如何 [设置云自动助理](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="e946a-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="e946a-196">设备</span><span class="sxs-lookup"><span data-stu-id="e946a-196">Devices</span></span>

<span data-ttu-id="e946a-197">有关支持的设备的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="e946a-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="e946a-198">在 Microsoft Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="e946a-198">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="e946a-199">IP 电话</span><span class="sxs-lookup"><span data-stu-id="e946a-199">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="e946a-200">USB 音频和视频设备</span><span class="sxs-lookup"><span data-stu-id="e946a-200">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="e946a-201">适用于设备的智能通信</span><span class="sxs-lookup"><span data-stu-id="e946a-201">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


