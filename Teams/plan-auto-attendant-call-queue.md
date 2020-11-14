---
title: 规划团队自动助理和通话队列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 了解自动助理和通话队列以及如何使用它们帮助呼叫者在菜单系统中移动以联系组织中的人员或部门。
ms.openlocfilehash: 4eaad11841007176a1840ea0d789fa1496f10df4
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031558"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a><span data-ttu-id="738d6-103">规划团队自动助理和通话队列</span><span class="sxs-lookup"><span data-stu-id="738d6-103">Plan for Teams auto attendants and call queues</span></span>

<span data-ttu-id="738d6-104">自动助理允许你设置菜单选项，以根据呼叫方输入路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-104">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="738d6-105">菜单选项，如 "用于销售额"，请按1。</span><span class="sxs-lookup"><span data-stu-id="738d6-105">Menu options, such as "For Sales, press 1.</span></span>  <span data-ttu-id="738d6-106">对于服务，请按 "2"，对于自动助理，允许组织提供一系列可指导呼叫者快速到达其目的地的选项，而无需依靠人工接线员处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-106">For Services press 2", for an auto attendant let an organization provide a series of choices that guide callers to their destination quickly, without relying on a human operator to handle incoming calls.</span></span>

<span data-ttu-id="738d6-107">通话队列是呼叫方的等待区域。</span><span class="sxs-lookup"><span data-stu-id="738d6-107">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="738d6-108">对于呼叫者需要联系特定专业人员（如销售或服务-而不是特定人员）的情况，您可以使用呼叫队列将呼叫者连接到可以帮助他们的工程师组。</span><span class="sxs-lookup"><span data-stu-id="738d6-108">For situations where callers need to reach someone with a particular specialty - such as sales or service - rather than a specific person, you can use call queues to connect callers to the group of agents who can assist them.</span></span> <span data-ttu-id="738d6-109">将呼叫者置于保留状态，直到分配给该队列的代理可以进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-109">Callers are put on hold until an agent assigned to the queue is available to take their call.</span></span>

<span data-ttu-id="738d6-110">"自动助理" 和 "呼叫队列" 一起使用，可以轻松地将呼叫者路由到组织中的相应人员或部门。</span><span class="sxs-lookup"><span data-stu-id="738d6-110">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

## <a name="auto-attendants"></a><span data-ttu-id="738d6-111">自动助理</span><span class="sxs-lookup"><span data-stu-id="738d6-111">Auto attendants</span></span>

<span data-ttu-id="738d6-112">自动助理的主要用途是根据呼叫者的输入将呼叫者定向到所提供的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="738d6-112">The primary purpose of an auto attendant is to direct a caller to an appropriate person or department based on the caller's input to the provided menu options.</span></span> <span data-ttu-id="738d6-113">呼叫者可定向到您组织内的特定人员，以便呼叫队列，在该队列中等待与下一个可用的代理或语音邮件通话。</span><span class="sxs-lookup"><span data-stu-id="738d6-113">Callers can be directed to specific people within your organization, to call queues where they wait to talk to the next available agent, or to voicemail.</span></span> <span data-ttu-id="738d6-114">可以为 "营业时间"、"休息时间" 和 "假日" 指定不同的通话传送选项。</span><span class="sxs-lookup"><span data-stu-id="738d6-114">Different call routing options can be specified for business hours, off hours, and holidays.</span></span>

<span data-ttu-id="738d6-115">可通过使用文本到语音 (系统生成的提示) 或上载录制的音频文件来创建菜单提示。</span><span class="sxs-lookup"><span data-stu-id="738d6-115">Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading a recorded audio file.</span></span> <span data-ttu-id="738d6-116">语音识别接受用于无人参与导航的语音命令，但呼叫的人员也可以使用电话键盘导航菜单。</span><span class="sxs-lookup"><span data-stu-id="738d6-116">Speech recognition accepts voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.</span></span>

<span data-ttu-id="738d6-117">每个自动助理都具有特定的语言和时区。</span><span class="sxs-lookup"><span data-stu-id="738d6-117">Each auto attendant has a specific language and time zone.</span></span> <span data-ttu-id="738d6-118">如果您在多个语言或世界各地的多个部分进行业务，则可以根据需要创建任意数量的自动助理，以适应您的呼叫者。</span><span class="sxs-lookup"><span data-stu-id="738d6-118">If you do business in multiple languages or multiple parts of the world, you can create as many different auto attendants as you need to accommodate your callers.</span></span>

<span data-ttu-id="738d6-119">对于每个自动助理，您可以配置一个操作员。</span><span class="sxs-lookup"><span data-stu-id="738d6-119">For each auto attendant, you can configure an operator.</span></span> <span data-ttu-id="738d6-120">虽然你可以配置操作员呼叫以转到各种目标，但运营商功能旨在允许呼叫者与你组织中的特定人员交谈，这些人员可以帮助他们。</span><span class="sxs-lookup"><span data-stu-id="738d6-120">While you can configure operator calls to go to a variety of destinations, the operator feature is designed to allow callers to talk to a specific person in your organization who can help them.</span></span>

<span data-ttu-id="738d6-121">自动助理可以配置为允许呼叫者按姓名或分机号码搜索组织的目录。</span><span class="sxs-lookup"><span data-stu-id="738d6-121">Auto attendants can be configured to allow callers to search your organization's directory, either by name or by extension number.</span></span> <span data-ttu-id="738d6-122">在自动助理中，可以通过选择要包含或排除的用户组来指定哪些人可以使用目录搜索。</span><span class="sxs-lookup"><span data-stu-id="738d6-122">Within an auto attendant, you can specify who is available for the directory search by choosing groups of users to include or exclude.</span></span> <span data-ttu-id="738d6-123"> (这称为 " *拨号作用域* "。 ) </span><span class="sxs-lookup"><span data-stu-id="738d6-123">(This is known as *dial scope*.)</span></span>

<span data-ttu-id="738d6-124">呼叫者可以通过直接电话号码（如果已配置）或通过其他自动助理或呼叫队列重定向的方式到达自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-124">Callers can reach an auto attendant either by direct phone number, if configured, or by being redirected from another auto attendant or a call queue.</span></span>

## <a name="call-queues"></a><span data-ttu-id="738d6-125">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="738d6-125">Call queues</span></span>

<span data-ttu-id="738d6-126">通话队列类似于物理建筑物中的等待会议室。</span><span class="sxs-lookup"><span data-stu-id="738d6-126">A call queue is analogous to a waiting room in a physical building.</span></span> <span data-ttu-id="738d6-127">呼叫者等待保持时，呼叫将路由到队列中的代理，因为它们变为可用。</span><span class="sxs-lookup"><span data-stu-id="738d6-127">Callers wait on hold while calls are routed to the agents in the queue as they become available.</span></span> <span data-ttu-id="738d6-128">通话队列通常用于销售和服务功能。</span><span class="sxs-lookup"><span data-stu-id="738d6-128">Call queues are commonly used for sales and service functions.</span></span> <span data-ttu-id="738d6-129">但是，通话队列可用于任何通话次数超过内部容量的情况，如繁忙设备的接待员。</span><span class="sxs-lookup"><span data-stu-id="738d6-129">However, call queues can be used for any situation where the number of calls exceeds your internal capacity, such as a receptionist in a busy facility.</span></span>

<span data-ttu-id="738d6-130">当队列中的呼叫方总数或等待时间超过指定的限制时，呼叫队列允许特定的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="738d6-130">Call queues allow for specific routing of calls in cases where the total number of callers in the queue or the wait time exceeds the limits that you specify.</span></span> <span data-ttu-id="738d6-131">通话可以路由到特定人员、语音邮件、其他通话队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-131">Calls can be routed to specific people, voicemail, other call queues, or auto attendants.</span></span>

<span data-ttu-id="738d6-132">与自动助理一样，通话队列都有一种语言设置。</span><span class="sxs-lookup"><span data-stu-id="738d6-132">Like auto attendants, call queues each have a language setting.</span></span> <span data-ttu-id="738d6-133">如果您有多种语言的业务，则可以使用不同的通话队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-133">You can use different call queues if you do business in multiple languages.</span></span> <span data-ttu-id="738d6-134">如果代理是多语言的，则它可以是多个队列的成员。</span><span class="sxs-lookup"><span data-stu-id="738d6-134">Agents can be members of more than one queue if they're multi-lingual.</span></span>

<span data-ttu-id="738d6-135">对于每个呼叫队列，你可以指定队列中的代理是否可以选择退出呼叫，以及是否应根据其在团队中的状态指示将呼叫路由到这些呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-135">For each call queue, you can specify if agents in the queue can opt out of taking calls and if calls should be routed to them based on their presence indication in Teams.</span></span>

<span data-ttu-id="738d6-136">您可以将电话号码分配给呼叫队列，但通话队列不会提供单独的呼叫路由，而不是休息时间和假期。</span><span class="sxs-lookup"><span data-stu-id="738d6-136">You can assign a phone number to a call queue, however call queues do not provide separate call routing for off hours and holidays.</span></span> <span data-ttu-id="738d6-137">除非您的呼叫队列是个人版24/7，否则建议将电话号码分配给在工作时间内重定向到呼叫队列的自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-137">Unless your call queue is staffed 24/7, we recommend assigning the phone number to an auto attendant that redirects to the call queue during business hours.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="738d6-138">先决条件</span><span class="sxs-lookup"><span data-stu-id="738d6-138">Prerequisites</span></span>

<span data-ttu-id="738d6-139">若要配置自动助理和呼叫队列，需要以下资源：</span><span class="sxs-lookup"><span data-stu-id="738d6-139">To configure auto attendants and call queues, you need the following resources:</span></span>

- <span data-ttu-id="738d6-140">每个自动助理和每个通话队列的资源帐户</span><span class="sxs-lookup"><span data-stu-id="738d6-140">A resource account for each auto attendant and each call queue</span></span>
- <span data-ttu-id="738d6-141">免费电话系统-每个资源帐户的虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="738d6-141">A free Phone System - Virtual User license for each resource account</span></span>
- <span data-ttu-id="738d6-142">您希望直接拨出的每个资源帐户至少有一个 [Microsoft 服务号码](getting-service-phone-numbers.md)、直接路由号码或混合号码</span><span class="sxs-lookup"><span data-stu-id="738d6-142">At least one [Microsoft service number](getting-service-phone-numbers.md), direct routing number, or a hybrid number for each resource account that you want to be directly dialable</span></span>
 - <span data-ttu-id="738d6-143">服务号码可能是收费或免费电话号码</span><span class="sxs-lookup"><span data-stu-id="738d6-143">The service number may be a toll or toll-free number</span></span>

<span data-ttu-id="738d6-144">从通话队列接收呼叫的工程师必须是联机或本地用户启用的企业语音。</span><span class="sxs-lookup"><span data-stu-id="738d6-144">Agents who receive calls from the call queues must be Enterprise Voice enabled online or on-premise users.</span></span> 

<span data-ttu-id="738d6-145">如果你的代理正在使用 Microsoft 团队应用进行呼叫队列呼叫，则他们必须处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="738d6-145">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="738d6-146">将呼叫转移到外部电话号码时，执行传输 (（即与自动助理或呼叫) 队列关联的资源帐户）必须具有电话号码和 Microsoft 365 电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="738d6-146">When transferring calls to an external phone number, the resource account performing the transfer (that is, the one associated with the auto attendant or call queue) must have a phone number and a Microsoft 365 Phone System Virtual User license.</span></span> <span data-ttu-id="738d6-147">进一步</span><span class="sxs-lookup"><span data-stu-id="738d6-147">Additionally:</span></span>

- <span data-ttu-id="738d6-148">对于带有呼叫计划编号的资源帐户，请分配 [呼叫计划](calling-plans-for-office-365.md) 许可证。</span><span class="sxs-lookup"><span data-stu-id="738d6-148">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="738d6-149">对于具有直接路由号码的资源帐户，请分配 [联机语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="738d6-149">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="738d6-150">只有 Microsoft 团队用户和呼叫代理才支持自动助理和呼叫队列的直接路由服务号码。</span><span class="sxs-lookup"><span data-stu-id="738d6-150">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and call agents only.</span></span><br>
> <span data-ttu-id="738d6-151">不支持在通话计划中继和直接路由中继之间转移。</span><span class="sxs-lookup"><span data-stu-id="738d6-151">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

## <a name="business-decisions"></a><span data-ttu-id="738d6-152">业务决策</span><span class="sxs-lookup"><span data-stu-id="738d6-152">Business decisions</span></span>

<span data-ttu-id="738d6-153">在设置自动助理和呼叫队列之前，应考虑如何在您的企业中使用这些功能的一些决策。</span><span class="sxs-lookup"><span data-stu-id="738d6-153">Before you set up your auto attendants and call queues, there are some decisions that you should make about how to use these features in your business.</span></span> <span data-ttu-id="738d6-154">这些决策将确定在配置自动助理和呼叫队列时选择的设置。</span><span class="sxs-lookup"><span data-stu-id="738d6-154">These decisions will determine the settings that you choose when you configure your auto attendants and call queues.</span></span>

<span data-ttu-id="738d6-155">记录这些问题的答案，并向执行配置的管理员提供信息。</span><span class="sxs-lookup"><span data-stu-id="738d6-155">Document your answers to these questions and provide the information to the administrator doing the configuration.</span></span>

- <span data-ttu-id="738d6-156">您需要哪些语言？</span><span class="sxs-lookup"><span data-stu-id="738d6-156">What languages do you need?</span></span> <span data-ttu-id="738d6-157">需要这些语言的位置-哪个部门或组？</span><span class="sxs-lookup"><span data-stu-id="738d6-157">Where are these languages needed - which department or group?</span></span>
- <span data-ttu-id="738d6-158">你希望允许来自呼叫者的语音输入还是仅允许拨号输入？</span><span class="sxs-lookup"><span data-stu-id="738d6-158">Do you want to allow voice inputs from callers or only dialing inputs?</span></span>
- <span data-ttu-id="738d6-159">您是否需要单独的通话路由来表示下班时间或假期？</span><span class="sxs-lookup"><span data-stu-id="738d6-159">Do you need separate call routing for off hours or holidays?</span></span> <span data-ttu-id="738d6-160">工时和假日是多少？</span><span class="sxs-lookup"><span data-stu-id="738d6-160">What are the hours and holidays?</span></span>
- <span data-ttu-id="738d6-161">是否要允许呼叫队列中的代理选择退出通话？</span><span class="sxs-lookup"><span data-stu-id="738d6-161">Do you want to allow agents in a call queue to opt out of taking calls?</span></span>
- <span data-ttu-id="738d6-162">是否希望呼叫队列中的代理或操作员在拨出时有特定的呼叫者 ID？</span><span class="sxs-lookup"><span data-stu-id="738d6-162">Do you want agents in your call queues or your operator to have a specific caller ID if they dial out?</span></span>
- <span data-ttu-id="738d6-163">您是否希望在您的组织中启用 [呼叫停车和检索](call-park-and-retrieve.md) 来协助呼叫交付人员或部门？</span><span class="sxs-lookup"><span data-stu-id="738d6-163">Do you want to enable [call parking and retrieval](call-park-and-retrieve.md) in your organization to assist in call handoffs between people or departments?</span></span>
- <span data-ttu-id="738d6-164">对于语音提示，是要录制自己的还是使用系统生成的语音？</span><span class="sxs-lookup"><span data-stu-id="738d6-164">For the voice prompts, do you want to record your own or use the system-generated voice?</span></span> <span data-ttu-id="738d6-165"> (可轻松更新系统生成的语音。 ) </span><span class="sxs-lookup"><span data-stu-id="738d6-165">(The system-generated voice is easy to update.)</span></span>

## <a name="technical-decisions"></a><span data-ttu-id="738d6-166">技术决策</span><span class="sxs-lookup"><span data-stu-id="738d6-166">Technical decisions</span></span>

<span data-ttu-id="738d6-167">使用自动助理和呼叫队列将呼叫者连接到组织中的人员时，在开始配置之前，需要进行一些技术决策。</span><span class="sxs-lookup"><span data-stu-id="738d6-167">When using auto attendants and call queues to connect callers to people in your organization, there are some technical decisions to make before you start the configuration.</span></span>

<span data-ttu-id="738d6-168">可通过以下方式将代理添加到呼叫队列：</span><span class="sxs-lookup"><span data-stu-id="738d6-168">Agents can be added to call queues in the following ways:</span></span>

- <span data-ttu-id="738d6-169">单个用户</span><span class="sxs-lookup"><span data-stu-id="738d6-169">Individual users</span></span>
- <span data-ttu-id="738d6-170">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="738d6-170">Distribution lists</span></span>
- <span data-ttu-id="738d6-171">安全组，包括已启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="738d6-171">Security groups, including mail-enabled security groups</span></span>
- <span data-ttu-id="738d6-172">Microsoft 365 组或团队</span><span class="sxs-lookup"><span data-stu-id="738d6-172">Microsoft 365 Groups or Teams</span></span>

<span data-ttu-id="738d6-173">如果需要，你可以为每个队列使用这些选项的组合。</span><span class="sxs-lookup"><span data-stu-id="738d6-173">You can use a combination of these options for each queue if needed.</span></span> <span data-ttu-id="738d6-174">具有电子邮件地址的组可用于语音邮件。</span><span class="sxs-lookup"><span data-stu-id="738d6-174">Groups that have an email address can be used for voicemail.</span></span> <span data-ttu-id="738d6-175">使用团队提供许多优点，包括共享文件存储和在代理之间进行聊天、可接收语音邮件的常见邮箱以及可包含与业务线应用程序或 Power 应用集成的可扩展平台。</span><span class="sxs-lookup"><span data-stu-id="738d6-175">Using Teams offers a number of advantages, including shared file storage and chat between agents, a common mailbox where voicemails can be received, and an extensible platform that can include integration with your line of business applications or Power Apps.</span></span>

<span data-ttu-id="738d6-176">在开始配置之前，我们建议选择将呼叫代理添加到队列的策略。</span><span class="sxs-lookup"><span data-stu-id="738d6-176">We recommend choosing a strategy for adding call agents to queues before you start your configuration.</span></span>

<span data-ttu-id="738d6-177">如果您有一个现有的自动助理和呼叫队列基础结构，并且您正在迁移到团队，您需要将现有电话号码转移到新的自动助理和呼叫队列的计划。</span><span class="sxs-lookup"><span data-stu-id="738d6-177">If you have an existing auto attendant and call queue infrastructure and you're migrating to Teams, you'll need a plan to transfer your existing phone numbers to the new auto attendants and call queues.</span></span> <span data-ttu-id="738d6-178">您可能需要创建一个 [端口顺序](phone-number-calling-plans/port-order-overview.md) 才能从其他提供商处移动您的号码。</span><span class="sxs-lookup"><span data-stu-id="738d6-178">You might need to create a [port order](phone-number-calling-plans/port-order-overview.md) to move your numbers from another providers.</span></span> <span data-ttu-id="738d6-179">我们建议你暂时获取一个或多个新电话号码，并测试您的自动助理和通话队列流，然后再将它们切换到您当前拥有的服务号码。</span><span class="sxs-lookup"><span data-stu-id="738d6-179">We recommend that you temporarily acquire one or more new phone numbers and test your auto attendant and call queue flows before switching them over the numbers you currently have in service.</span></span>

<span data-ttu-id="738d6-180">*会议模式* 是通话队列中的一个选项，可显著减少将团队 VOIP 呼叫和 PSTN 呼叫连接到代理所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="738d6-180">*Conference mode* is an option in call queues that significantly reduces the amount of time it takes to connect Teams VOIP calls and PSTN calls to an agent.</span></span> <span data-ttu-id="738d6-181">若要使会议模式正常工作，呼叫队列中的代理必须使用下列客户端之一：</span><span class="sxs-lookup"><span data-stu-id="738d6-181">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

- <span data-ttu-id="738d6-182">Microsoft 团队桌面客户端、Android 应用或 iOS 应用的最新版本</span><span class="sxs-lookup"><span data-stu-id="738d6-182">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="738d6-183">Microsoft 团队手机版本 1449/1.0.94.2020051601 或更高版本</span><span class="sxs-lookup"><span data-stu-id="738d6-183">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="738d6-184">将代理的团队帐户设置为仅限团队模式。</span><span class="sxs-lookup"><span data-stu-id="738d6-184">Set Agents' Teams accounts to Teams-only mode.</span></span> <span data-ttu-id="738d6-185">不满足要求的工程师不会包含在 "呼叫" 传送列表中。</span><span class="sxs-lookup"><span data-stu-id="738d6-185">Agents who don't meet the requirements aren't included in the call routing list.</span></span>

<span data-ttu-id="738d6-186">如果你的代理全部使用兼容的客户端，我们建议你为通话队列启用会议模式。</span><span class="sxs-lookup"><span data-stu-id="738d6-186">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="738d6-187">会议模式不支持忙闲。</span><span class="sxs-lookup"><span data-stu-id="738d6-187">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="738d6-188">如果未启用基于状态的路由，则非呼叫队列呼叫中的代理仍会显示呼叫队列呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-188">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

## <a name="plan-your-call-routing-flow"></a><span data-ttu-id="738d6-189">规划您的呼叫路由流程</span><span class="sxs-lookup"><span data-stu-id="738d6-189">Plan your call routing flow</span></span>

<span data-ttu-id="738d6-190">作为规划过程的一部分，我们建议您在图表中为您的组织处理呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="738d6-190">As part of the planning process, we recommend that you work out the call routing for your organization in a diagram.</span></span> <span data-ttu-id="738d6-191">此图有助于确定与组织通话的用户最高效的路由。</span><span class="sxs-lookup"><span data-stu-id="738d6-191">The diagram helps determine the most efficient routing for people calling in to your organization.</span></span> <span data-ttu-id="738d6-192">你还可以使用图表确定你需要创建的自动助理和呼叫队列，以及相关要求（如服务号码、许可证和资源帐户）。</span><span class="sxs-lookup"><span data-stu-id="738d6-192">You can also use the diagram to determine the auto attendants and call queues that you need to create, along with related requirements such as service numbers, licenses, and resource accounts.</span></span>

<span data-ttu-id="738d6-193">让我们来看看自动助理和呼叫队列路由呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="738d6-193">Let's look at how auto attendants and call queues route calls.</span></span>

<span data-ttu-id="738d6-194">自动助理通过以下方式之一路由所有呼叫：</span><span class="sxs-lookup"><span data-stu-id="738d6-194">Auto attendants route all calls in one of the following ways:</span></span>

- <span data-ttu-id="738d6-195">**立即重定向** -呼叫可被重定向到 "呼叫路由" (之一，) 在接听或初始问候语后立即显示。</span><span class="sxs-lookup"><span data-stu-id="738d6-195">**Redirect immediately** - calls can be redirected to one of the call routing destinations (listed below) immediately upon answering or after an initial greeting.</span></span>
- <span data-ttu-id="738d6-196">**根据拨号选项重定向** -呼叫者可定向到分配给其电话键盘上的号码的选项（0-9）。</span><span class="sxs-lookup"><span data-stu-id="738d6-196">**Redirect based on dial options** - callers can be directed to choose between options that are assigned to the numbers on their telephone keypad, 0-9.</span></span> <span data-ttu-id="738d6-197">可以为每个拨号键分配一个呼叫传送目的地。</span><span class="sxs-lookup"><span data-stu-id="738d6-197">Each dial key can be assigned a call routing destinations.</span></span>
- <span data-ttu-id="738d6-198">**通过姓名或分机号码拨打电话** —呼叫者可以被定向到在您的组织的目录中拨打他们正在尝试访问的人员的分机号码，或通过拼写该人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="738d6-198">**Dial people by name or extension** - callers can be directed to dial the extension number of the person they're trying to reach in your organization's directory, or by spelling the person's name.</span></span>
- <span data-ttu-id="738d6-199">**断开** -自动助理可以挂断通话。</span><span class="sxs-lookup"><span data-stu-id="738d6-199">**Disconnect** - an auto attendant can hang up the call.</span></span>

> [!NOTE]
> <span data-ttu-id="738d6-200">单个自动助理只能支持单个 "拨号方式" 方法。</span><span class="sxs-lookup"><span data-stu-id="738d6-200">A single Auto attendant can only support a single "dial by" method.</span></span>  <span data-ttu-id="738d6-201">若要允许呼叫者按姓名和按号码拨号，您需要创建一个自动助理，该助理具有按名称拨号的选项，另一种是通过分机号码拨入。</span><span class="sxs-lookup"><span data-stu-id="738d6-201">To allow callers to dial by name and by number, you will need to create an auto attendant that has an option for dial by name and the another for dial by extension.</span></span>  <span data-ttu-id="738d6-202">这些选项中的每一个都将路由到为这些 "拨号方式" 方案配置的单独的自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-202">Each of these options will route to separate auto attendants configured for these "dial by" scenarios.</span></span>

<span data-ttu-id="738d6-203">当呼叫由自动助理或呼叫队列重定向时，您可以从下列呼叫路由目标中进行选择：</span><span class="sxs-lookup"><span data-stu-id="738d6-203">When calls are redirected by an auto attendant or call queue, you can choose from the following call routing destinations:</span></span>

- <span data-ttu-id="738d6-204">**组织中的人员** -您的组织中能够接收语音呼叫的人员。</span><span class="sxs-lookup"><span data-stu-id="738d6-204">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="738d6-205">这可以是联机用户，也可以是使用 Skype for Business 服务器内部托管的用户。</span><span class="sxs-lookup"><span data-stu-id="738d6-205">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="738d6-206">**语音应用** -另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-206">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="738d6-207">选择与目标相关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="738d6-207">Choose the resource account associated with the destination.</span></span>
- <span data-ttu-id="738d6-208">**外部电话号码** -任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="738d6-208">**External phone number** - any phone number.</span></span> <span data-ttu-id="738d6-209"> (参阅 [外部转接技术详细信息](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)) 。</span><span class="sxs-lookup"><span data-stu-id="738d6-209">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="738d6-210">**语音邮件** -与你指定的 Microsoft 365 组相关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="738d6-210">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="738d6-211">**运算符** (仅限自动助理) -为自动助理定义的操作员。</span><span class="sxs-lookup"><span data-stu-id="738d6-211">**Operator** (auto attendant only) - the operator defined for the auto attendant.</span></span> <span data-ttu-id="738d6-212">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="738d6-212">Defining an operator is optional.</span></span> <span data-ttu-id="738d6-213">操作员可以是此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="738d6-213">An operator can be any of the other destinations in this list.</span></span>

<span data-ttu-id="738d6-214">自动助理提供单独的呼叫传送选项，用于在工作时间之外和假期内接收的呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-214">Auto attendants offer separate call routing options for calls received outside of business hours and on holidays.</span></span> <span data-ttu-id="738d6-215">下班后呼叫路由允许以上列出的所有选项，而假日呼叫路由只允许重定向或断开呼叫，但不允许拨号键选项。</span><span class="sxs-lookup"><span data-stu-id="738d6-215">After-hours call routing allows all the options listed above, while holiday call routing allows only redirecting or disconnecting a call, but no dial key options.</span></span>

<span data-ttu-id="738d6-216">通话队列将呼叫者置于保持状态，直到分配给该队列的代理可以进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="738d6-216">Call queues place the caller on hold until an agent assigned to the queue is available to take their call.</span></span> <span data-ttu-id="738d6-217">在以下两种情况下，呼叫方可能会定向到队列：</span><span class="sxs-lookup"><span data-stu-id="738d6-217">There are two situations where a caller might be directed out of the queue:</span></span>

- <span data-ttu-id="738d6-218">**呼叫溢出** -如果队列中的呼叫数超过您设置的限制，则会将新的呼叫者重定向到队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-218">**Call overflow** - if the number of calls in the queue exceeds the limit that you set, then new callers are redirected out of the queue.</span></span>
- <span data-ttu-id="738d6-219">**呼叫超时** -如果呼叫者在队列中的时间长于配置的超时设置，则会将其重定向到队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-219">**Call timeout** - if a caller has been in the queue longer than the configured timeout setting, they're redirected out of the queue.</span></span>

<span data-ttu-id="738d6-220">除了操作员之外，可以将呼叫从队列中重定向的电话发送到上述任意呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="738d6-220">Calls redirected out of a queue can be sent to any of the call routing destinations listed above except for an operator.</span></span> <span data-ttu-id="738d6-221"> (通话队列没有操作员，但您可以将呼叫者重定向到与您为自动助理配置的操作员相同的目标。 ) </span><span class="sxs-lookup"><span data-stu-id="738d6-221">(Call queues don't have operators, but you can redirect callers to the same destination as an operator that you've configured for an auto attendant.)</span></span>

<span data-ttu-id="738d6-222">下面的示例显示了使用自动助理和通话队列呼叫路由的示例。</span><span class="sxs-lookup"><span data-stu-id="738d6-222">The example below shows an example of call routing using auto attendants and call queues.</span></span>

![使用自动助理和呼叫队列的呼叫路由的图表](media/attendant-and-queue-call-routing.png)

<span data-ttu-id="738d6-224">在上面的示例中：</span><span class="sxs-lookup"><span data-stu-id="738d6-224">In the example above:</span></span>

- <span data-ttu-id="738d6-225">零 (0) 键将调用方重定向到操作员。</span><span class="sxs-lookup"><span data-stu-id="738d6-225">The zero (0) key redirects callers to an operator.</span></span> <span data-ttu-id="738d6-226">该自动助理的操作员已配置为 **组织中的人员** 。</span><span class="sxs-lookup"><span data-stu-id="738d6-226">The operator for that auto attendant has been configured as a **Person in the organization**.</span></span>
- <span data-ttu-id="738d6-227"> (1) 密钥将呼叫者重定向到销售呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-227">The one (1) key redirects callers to the sales call queue.</span></span> <span data-ttu-id="738d6-228">此通话队列已连接到包含分配给该队列的销售团队的团队。</span><span class="sxs-lookup"><span data-stu-id="738d6-228">This call queue is connected to a team that contains the sales team assigned to the queue.</span></span>
- <span data-ttu-id="738d6-229">两个 (2) 密钥将呼叫者重定向到支持呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-229">The two (2) key redirects callers to the support call queue.</span></span> <span data-ttu-id="738d6-230">此通话队列已连接到包含分配给团队的支持团队的团队。</span><span class="sxs-lookup"><span data-stu-id="738d6-230">This call queue is connected to a team that contains the support team assigned to the team.</span></span>
- <span data-ttu-id="738d6-231">支持呼叫队列具有通过插入的自动助理的直接电话号码。</span><span class="sxs-lookup"><span data-stu-id="738d6-231">The support call queue has a direct phone number via an intervening auto attendant.</span></span> <span data-ttu-id="738d6-232">让自动助理回答 "支持" 行将允许单独的下班时间和假期呼叫路线。</span><span class="sxs-lookup"><span data-stu-id="738d6-232">Having an auto attendant answer the support line allows for separate off hours and holiday call routing.</span></span>
- <span data-ttu-id="738d6-233">三个 (3) 密钥将用户重定向到公司目录的其他自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-233">The three (3) key redirects users to another auto attendant for the company directory.</span></span> <span data-ttu-id="738d6-234">公司目录自动助理允许呼叫者通过拨叫其姓名或分机号码来呼叫组织中的个人。</span><span class="sxs-lookup"><span data-stu-id="738d6-234">The company directory auto attendant allows callers to call individuals in the organization by dialing their name or extension.</span></span>

<span data-ttu-id="738d6-235">我们建议你创建一个或多个类似于上述图表的图表来映射你的呼叫路线。</span><span class="sxs-lookup"><span data-stu-id="738d6-235">We recommend that you create one or more diagrams similar to the one above to map out your call routing.</span></span> <span data-ttu-id="738d6-236">请确保你的图表或随附文档中包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="738d6-236">Be sure to include the following in your diagram or accompanying documentation:</span></span>

- <span data-ttu-id="738d6-237">哪些自动助理将通过电话号码直接访问？</span><span class="sxs-lookup"><span data-stu-id="738d6-237">Which auto attendants will have direct access via phone numbers?</span></span>
- <span data-ttu-id="738d6-238">每个自动助理的工作时间和假日路由要求是多少？</span><span class="sxs-lookup"><span data-stu-id="738d6-238">What are the off-hours and holiday routing requirements for each auto attendants?</span></span>
- <span data-ttu-id="738d6-239">每个通话队列的成员身份。</span><span class="sxs-lookup"><span data-stu-id="738d6-239">The membership for each call queue.</span></span> <span data-ttu-id="738d6-240"> (您可以单独添加用户或将队列映射到不同类型的组。</span><span class="sxs-lookup"><span data-stu-id="738d6-240">(You can add users individually or map the queue to different kinds of groups.</span></span> <span data-ttu-id="738d6-241">将队列映射到团队可提供最丰富的体验。 ) </span><span class="sxs-lookup"><span data-stu-id="738d6-241">Mapping a queue to a team provides the most versatile experience.)</span></span>

<span data-ttu-id="738d6-242">下面是一些呼叫路由最佳做法：</span><span class="sxs-lookup"><span data-stu-id="738d6-242">Here are some call routing best practices:</span></span>

- <span data-ttu-id="738d6-243">查看您的现有呼叫系统并分析传入呼叫的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="738d6-243">Look at your existing calling system and analyze the types and frequency of incoming calls.</span></span> <span data-ttu-id="738d6-244">使用此信息有助于通知您的自动助理和呼叫队列结构。</span><span class="sxs-lookup"><span data-stu-id="738d6-244">Use this information to help inform your auto attendant and call queue structure.</span></span>
- <span data-ttu-id="738d6-245">将最常用的选项放到最早的菜单中，以便尽快路由通话。</span><span class="sxs-lookup"><span data-stu-id="738d6-245">Put the most common options earliest in the menu to route calls as quickly as possible.</span></span>
- <span data-ttu-id="738d6-246">避免将服务号码直接连接到呼叫队列，除非队列可用24/7。</span><span class="sxs-lookup"><span data-stu-id="738d6-246">Avoid connecting service numbers directly to call queues unless the queues are available 24/7.</span></span> <span data-ttu-id="738d6-247">通话队列不允许单独拨打的通话处理时间或假期。</span><span class="sxs-lookup"><span data-stu-id="738d6-247">Call queues don't allow for separate call handling for off hours or holidays.</span></span> <span data-ttu-id="738d6-248">如果您希望具有直接号码的队列，请将该号码分配给在工作时间自动重定向到该队列的自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-248">If you want to have a queue with a direct number, assign the number to an auto attendant that automatically redirects to the queue during business hours.</span></span>
- <span data-ttu-id="738d6-249">如果您收到大量请求，请求有关您的公司的基本信息（如工作时间、位置或网站地址），请考虑创建自动助理以使用录制的邮件回答这些问题。</span><span class="sxs-lookup"><span data-stu-id="738d6-249">If you receive numerous calls requesting basic information about your company, such as business hours, location, or web site address, consider creating an auto attendant to answer these questions with recorded messages.</span></span>
- <span data-ttu-id="738d6-250">将菜单项列表保留5个或更少。</span><span class="sxs-lookup"><span data-stu-id="738d6-250">Keep the list of menu items to five or fewer.</span></span> <span data-ttu-id="738d6-251">呼叫者在记忆五个以上的选项时可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="738d6-251">Callers can have trouble remembering more than five options.</span></span> <span data-ttu-id="738d6-252">如果需要更多选项才能正确路由呼叫，请使用嵌套的自动助理。</span><span class="sxs-lookup"><span data-stu-id="738d6-252">Use nested auto attendants if more options are needed to properly route a call.</span></span>
- <span data-ttu-id="738d6-253">首先描述服务，然后选择按 (的选项：对于销售额按 1) ，而不是 (例如的其他方式。</span><span class="sxs-lookup"><span data-stu-id="738d6-253">Describe the service first, followed by the option to press (eg: For Sales press 1) rather than the other way around (eg.</span></span> <span data-ttu-id="738d6-254">按1查看销售) 。</span><span class="sxs-lookup"><span data-stu-id="738d6-254">Press 1 for Sales).</span></span>
- <span data-ttu-id="738d6-255">您的呼叫方将理解的用户术语，而不是您内部可能使用的内容。</span><span class="sxs-lookup"><span data-stu-id="738d6-255">User terminology your callers will understand rather than what you may use internally.</span></span>
- <span data-ttu-id="738d6-256">避免频繁更新呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="738d6-256">Avoid frequent updates to call routing.</span></span> <span data-ttu-id="738d6-257">如果将来更改自动助理的菜单选项，请在 "语音提示" 中拨出前30天。</span><span class="sxs-lookup"><span data-stu-id="738d6-257">If you change your menu options for an auto attendant in the future, call that out in the voice prompts for the first 30 days.</span></span>

## <a name="getting-started"></a><span data-ttu-id="738d6-258">入门</span><span class="sxs-lookup"><span data-stu-id="738d6-258">Getting started</span></span>

<span data-ttu-id="738d6-259">完成本文中的规划任务后，请按照以下步骤操作，以获取自动助理和通话队列设置：</span><span class="sxs-lookup"><span data-stu-id="738d6-259">Once you've completed the planning tasks in this article, follow these steps to get your auto attendants and call queues set up:</span></span>

1. <span data-ttu-id="738d6-260">获取您需要用于自动助理和呼叫队列的服务号码，您希望通过直接拨号从组织外部进行访问。</span><span class="sxs-lookup"><span data-stu-id="738d6-260">Get the service numbers that you need for the auto attendants and call queues that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="738d6-261">这可能包括 [从另一个提供商转移号码](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [申请新的服务号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="738d6-261">This might include [transferring numbers from another provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](getting-service-phone-numbers.md).</span></span>

2. <span data-ttu-id="738d6-262">为计划创建的每个资源帐户获取一个 [电话系统-虚拟用户许可证](teams-add-on-licensing/virtual-user.md) 。</span><span class="sxs-lookup"><span data-stu-id="738d6-262">Get a [Phone System - Virtual User license](teams-add-on-licensing/virtual-user.md) for each resource account that you plan to create.</span></span> <span data-ttu-id="738d6-263">这些许可证是免费的，因此我们建议你在将来决定对资源帐户进行更改时使用一些额外的许可证。</span><span class="sxs-lookup"><span data-stu-id="738d6-263">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your resource accounts in the future.</span></span>

3. <span data-ttu-id="738d6-264">为要创建的每个自动助理和通话队列[创建一个资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="738d6-264">[Create a resource account](manage-resource-accounts.md) for each auto attendant and call queue that you want to create.</span></span> <span data-ttu-id="738d6-265">为每个帐户分配一个电话系统-虚拟用户许可证和一个服务号码（可选）。</span><span class="sxs-lookup"><span data-stu-id="738d6-265">Assign each account a Phone System - Virtual User license and, optionally, a service number.</span></span>

4. <span data-ttu-id="738d6-266">在自动助理中创建要为其提供单独呼叫传送的[假日](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="738d6-266">[Create the holidays](set-up-holidays-in-teams.md) for which you want to have separate call routing in your auto attendants.</span></span>

5. <span data-ttu-id="738d6-267">（可选）如果要使用此功能来帮助进行呼叫转接，请 [设置呼叫停车和检索](call-park-and-retrieve.md) 。</span><span class="sxs-lookup"><span data-stu-id="738d6-267">Optionally, [set up call parking and retrieval](call-park-and-retrieve.md) if you want to use this feature to help with call transfers.</span></span>

6. <span data-ttu-id="738d6-268">创建要用于包含通话队列的呼叫代理的组。</span><span class="sxs-lookup"><span data-stu-id="738d6-268">Create the groups that you want to use to contain the call agents for the call queues.</span></span>

7. <span data-ttu-id="738d6-269">如果你计划允许通过分机拨，请确保你已将用户的分机号码添加到其 Azure Active Directory 配置文件。</span><span class="sxs-lookup"><span data-stu-id="738d6-269">If you plan to allow dial by extension, ensure that you've added your users' extension number to their Azure Active Directory profile.</span></span>

<span data-ttu-id="738d6-270">完成上述步骤后，您就可以创建自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-270">Once you've completed the steps above, you're ready to create your auto attendants and call queues.</span></span> <span data-ttu-id="738d6-271">由于自动助理和呼叫队列可以互相重定向呼叫，因此请参阅您创建的工作流程图，以确定应首先创建的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-271">Because auto attendants and call queues can redirect calls to each other, refer to the workflow diagram that you created to determine which auto attendant or call queue should be created first.</span></span> <span data-ttu-id="738d6-272">在上述图表的示例中，你将在创建 Contoso 主自动助理之前创建销售和支持呼叫队列，因为主自动助理需要将呼叫者定向到销售和支持呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="738d6-272">In the example in the diagram above, you would create the sales and support call queues before you create the Contoso main auto attendant because the main auto attendant needs to direct callers to the sales and support call queues.</span></span>

<span data-ttu-id="738d6-273">有关如何创建自动助理和呼叫队列的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="738d6-273">See the following articles for information on how to create auto attendants and call queues:</span></span>

- [<span data-ttu-id="738d6-274">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="738d6-274">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="738d6-275">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="738d6-275">Create a call queue</span></span>](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a><span data-ttu-id="738d6-276">相关主题</span><span class="sxs-lookup"><span data-stu-id="738d6-276">Related topics</span></span>

[<span data-ttu-id="738d6-277">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="738d6-277">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="738d6-278">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="738d6-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="738d6-279">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="738d6-279">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)
