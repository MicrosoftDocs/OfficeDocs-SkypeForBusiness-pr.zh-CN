---
title: 在 Microsoft 团队中的云语音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 部署团队中的云语音登陆页面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 969bab316a39ec873fea802a9c257cf062891bb9
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351295"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="cf7fe-103">在 Microsoft 团队中的云语音</span><span class="sxs-lookup"><span data-stu-id="cf7fe-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="cf7fe-104">你已完成了[入门](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="cf7fe-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="cf7fe-106">也许您已经部署了[会议 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="cf7fe-107">现在您已准备好添加云为您的用户的语音功能。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="cf7fe-108">云语音提供专用交换机 (PBX) 功能，并连接到公共公用电话交换网 (PSTN) 的选项。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="cf7fe-109">本文帮助您确定是否需要更改任何默认云语音设置，根据您的组织配置文件和业务要求，则它引导您完成每次更改。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="cf7fe-110">我们已拆分成两个组，从开始进行[要更容易进行的更改](#core-deployment-decisions)的核心集的设置。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="cf7fe-111">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="cf7fe-112">我们建议所有组织的核心决策通过工作，然后，如果您的组织有其他要求，请查看以下材料。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="cf7fe-113">了解有关云语音</span><span class="sxs-lookup"><span data-stu-id="cf7fe-113">Learn more about cloud voice</span></span>

<span data-ttu-id="cf7fe-114">以下文章提供有关部署和使用团队中的云语音功能的详细信息：</span><span class="sxs-lookup"><span data-stu-id="cf7fe-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="cf7fe-115">Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="cf7fe-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="cf7fe-116">调用计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="cf7fe-116">Phone System with Calling Plan</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="cf7fe-117">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="cf7fe-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="cf7fe-118">云语音部署</span><span class="sxs-lookup"><span data-stu-id="cf7fe-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="cf7fe-119">Microsoft 电话服务解决方案</span><span class="sxs-lookup"><span data-stu-id="cf7fe-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="cf7fe-120">观看下面的会话，若要了解有关电话系统的详细信息：[简介中的 Microsoft 团队的电话系统](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="cf7fe-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="cf7fe-121">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="cf7fe-121">Core deployment decisions</span></span>

<span data-ttu-id="cf7fe-122">以下是大多数组织在默认设置不适合的情况下想要更改的设置。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="cf7fe-123">电话系统 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="cf7fe-123">Phone System (Office 365)</span></span>

<span data-ttu-id="cf7fe-124">电话系统是 Microsoft 的技术来启用呼叫控制和 Office 365 云中的专用交换机 (PBX) 功能。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="cf7fe-125">电话系统允许您直接从 Office 365 中发送和紧密集成到公司的云生产力体验的功能的一组替换现有专用交换机 (PBX) 系统的信息。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="cf7fe-126">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-126">Ask yourself</span></span>|<span data-ttu-id="cf7fe-127">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="cf7fe-128">哪些用户位置或办公室中我将实现电话系统？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="cf7fe-129">有关电话系统的详细信息，请参阅[什么是 Office 365 中的电话系统](what-is-phone-system-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="cf7fe-130">连接到公共公用电话交换网 (PSTN)</span><span class="sxs-lookup"><span data-stu-id="cf7fe-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="cf7fe-131">若要将电话系统连接到公共公用电话交换网 (PSTN)，以便用户可以在世界各地发出电话呼叫，您可以根据业务需要的选项。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="cf7fe-132">问自己以下：</span><span class="sxs-lookup"><span data-stu-id="cf7fe-132">Ask yourself the following:</span></span>


|<span data-ttu-id="cf7fe-133">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-133">Ask yourself</span></span>|<span data-ttu-id="cf7fe-134">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="cf7fe-135">是否要用作 Microsoft 调用规划我的电话运营商？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="cf7fe-136">有关详细信息，请参阅[电话系统与调用计划](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="cf7fe-137">是否需要使用我自己电话运营商？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="cf7fe-138">有关详细信息，请参阅[直接路由的电话系统](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="cf7fe-139">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="cf7fe-139">Additional deployment decisions</span></span>

<span data-ttu-id="cf7fe-140">您可能想要更改设置以下内容，根据组织的需求和配置：</span><span class="sxs-lookup"><span data-stu-id="cf7fe-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="cf7fe-141">语音邮件</span><span class="sxs-lookup"><span data-stu-id="cf7fe-141">Voicemail</span></span>
- <span data-ttu-id="cf7fe-142">呼叫标识</span><span class="sxs-lookup"><span data-stu-id="cf7fe-142">Calling identity</span></span>
- <span data-ttu-id="cf7fe-143">从 Microsoft 的电话号码</span><span class="sxs-lookup"><span data-stu-id="cf7fe-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="cf7fe-144">拨号计划</span><span class="sxs-lookup"><span data-stu-id="cf7fe-144">Dial plans</span></span>
- <span data-ttu-id="cf7fe-145">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="cf7fe-145">Call queues</span></span>
- <span data-ttu-id="cf7fe-146">自动助理</span><span class="sxs-lookup"><span data-stu-id="cf7fe-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="cf7fe-147">语音邮件</span><span class="sxs-lookup"><span data-stu-id="cf7fe-147">Voicemail</span></span>

<span data-ttu-id="cf7fe-148">电话系统的语音邮件，由 Azure 语音邮件服务，支持语音邮件存款仅 Exchange 邮箱和不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-148">Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="cf7fe-149">电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-149">Phone System voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="cf7fe-150">您的业务需求可能需要您禁用语音邮件转录的特定用户或整个组织中的每个人。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="cf7fe-151">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-151">Ask yourself</span></span>|<span data-ttu-id="cf7fe-152">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cf7fe-153">是否要启用电话系统的语音邮件？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-153">Do I want to enable Phone System voicemail?</span></span> | <span data-ttu-id="cf7fe-154">有关语音邮件设置过程，请参阅[设置电话系统的语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-154">For voicemail setup procedures, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="cf7fe-155">是否要启用的部分或所有用户的语音邮件转录？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="cf7fe-156">若要关闭语音邮件转录，请参阅[设置您的组织中的语音邮件策略](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="cf7fe-157">呼叫标识</span><span class="sxs-lookup"><span data-stu-id="cf7fe-157">Calling identity</span></span>

<span data-ttu-id="cf7fe-158">默认情况下，所有出站呼叫的分配的电话号码用作调用 identity (呼叫者 ID)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="cf7fe-159">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="cf7fe-160">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-160">Ask yourself</span></span>|<span data-ttu-id="cf7fe-161">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="cf7fe-162">我想要屏蔽或禁用呼叫者 ID 吗？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="cf7fe-163">若要更改或阻止呼叫者 ID，请参阅[设置用户的呼叫者 ID](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="cf7fe-164">从 Microsoft 的电话号码</span><span class="sxs-lookup"><span data-stu-id="cf7fe-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="cf7fe-165">Microsoft 有两种类型的电话号码：*订阅者*（用户） 号码，可以为其分配给您的组织中的用户，以及*服务*号码，可用作收费和免费电话服务号码，具有更高的并发呼叫容量比订户号且可分配给服务，如要进行音频会议、 自动助理或呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="cf7fe-166">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-166">Ask yourself</span></span>|<span data-ttu-id="cf7fe-167">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="cf7fe-168">哪些用户位置需要从 Microsoft 的新电话号码？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="cf7fe-169">有关获取电话号码的信息，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)和[您的用户获取电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="cf7fe-170">是否需要哪种类型的电话号码 （订户或服务）？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="cf7fe-171">若要帮助您选择所需的电话号码的类型，请参阅[不同种类的用于调用计划的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="cf7fe-172">如何实现到 Office 365 端口现有电话号码？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="cf7fe-173">有关详细信息，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="cf7fe-174">拨号计划</span><span class="sxs-lookup"><span data-stu-id="cf7fe-174">Dial plans</span></span>

<span data-ttu-id="cf7fe-175">Office 365 的电话系统功能中的拨号计划是翻译的规范化规则的一组呼叫授权和呼叫路由到的备用格式 （通常为 E.164 格式） 拨打的电话号码。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="cf7fe-176">有关拨号计划的详细信息，请参阅[什么是拨号计划？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="cf7fe-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="cf7fe-177">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-177">Ask yourself</span></span>|<span data-ttu-id="cf7fe-178">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cf7fe-179">我的组织是否需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="cf7fe-180">若要帮助确定您是否需要自定义的拨号计划，请参阅[Planning for 租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="cf7fe-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="cf7fe-181">哪些用户需要自定义拨号计划，应为每个用户分配哪种租户拨号计划？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="cf7fe-182">若要将用户添加到在 PowerShell 中的自定义的拨号计划，请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="cf7fe-183">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="cf7fe-183">Call queues</span></span>

<span data-ttu-id="cf7fe-184">队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-184">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="cf7fe-185">您可以为组织创建单个或多个呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="cf7fe-186">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-186">Ask yourself</span></span>|<span data-ttu-id="cf7fe-187">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cf7fe-188">我的组织是否需要调用队列？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-188">Does my organization need call queues?</span></span> | <span data-ttu-id="cf7fe-189">有关详细信息，请参阅[创建电话系统呼叫队列](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)和[电话系统的设置](setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-189">For more information, see [Create a Phone System call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="cf7fe-190">自动助理</span><span class="sxs-lookup"><span data-stu-id="cf7fe-190">Auto attendants</span></span>

<span data-ttu-id="cf7fe-191">通过菜单系统，以查找并放置或将呼叫转接到您的组织中的部门或公司用户移动电话系统自动助理可以用于创建您的组织允许外部和内部呼叫者菜单系统。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-191">Phone System auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="cf7fe-192">询问你自己</span><span class="sxs-lookup"><span data-stu-id="cf7fe-192">Ask yourself</span></span>|<span data-ttu-id="cf7fe-193">操作</span><span class="sxs-lookup"><span data-stu-id="cf7fe-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cf7fe-194">我的组织是否需要自动助理？</span><span class="sxs-lookup"><span data-stu-id="cf7fe-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="cf7fe-195">有关详细信息，请参阅[什么是电话系统自动助理](what-are-phone-system-auto-attendants.md)和[设置电话系统自动助理](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="cf7fe-195">For more information, see [What are Phone System auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Phone System auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="cf7fe-196">设备</span><span class="sxs-lookup"><span data-stu-id="cf7fe-196">Devices</span></span>

<span data-ttu-id="cf7fe-197">有关受支持设备的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="cf7fe-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="cf7fe-198">在 Microsoft Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="cf7fe-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="cf7fe-199">IP 电话</span><span class="sxs-lookup"><span data-stu-id="cf7fe-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="cf7fe-200">USB 音频和视频设备</span><span class="sxs-lookup"><span data-stu-id="cf7fe-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="cf7fe-201">智能通信设备</span><span class="sxs-lookup"><span data-stu-id="cf7fe-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


