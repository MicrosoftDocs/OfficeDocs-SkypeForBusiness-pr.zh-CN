---
title: 规划 Teams 自动助理和呼叫队列
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
description: 了解自动助理和呼叫队列，以及如何使用它们来帮助呼叫者在菜单系统中移动以联系你组织的人或部门。
ms.openlocfilehash: 9ba8ccf08793e352e225340aeab33d7b95204cd9
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918888"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a><span data-ttu-id="3d53c-103">规划 Teams 自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3d53c-103">Plan for Teams auto attendants and call queues</span></span>

<span data-ttu-id="3d53c-104">自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-104">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="3d53c-105">菜单选项，例如"对于销售，请按 1。</span><span class="sxs-lookup"><span data-stu-id="3d53c-105">Menu options, such as "For Sales, press 1.</span></span>  <span data-ttu-id="3d53c-106">对于服务按 2"，对于自动助理，让组织提供一系列选项来引导呼叫者快速到达其目的地，而无需依赖人工接线员来处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-106">For Services press 2", for an auto attendant let an organization provide a series of choices that guide callers to their destination quickly, without relying on a human operator to handle incoming calls.</span></span>

<span data-ttu-id="3d53c-107">呼叫队列正在等待呼叫者的区域。</span><span class="sxs-lookup"><span data-stu-id="3d53c-107">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="3d53c-108">对于呼叫者需要联系具有特定特殊用途（如销售或服务）而不是特定人员的人的情况，可以使用呼叫队列将呼叫者连接到可以协助他们的代理组。</span><span class="sxs-lookup"><span data-stu-id="3d53c-108">For situations where callers need to reach someone with a particular specialty - such as sales or service - rather than a specific person, you can use call queues to connect callers to the group of agents who can assist them.</span></span> <span data-ttu-id="3d53c-109">调用方被置于保持状态，直到分配到队列的代理可以发起其呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-109">Callers are put on hold until an agent assigned to the queue is available to take their call.</span></span>

<span data-ttu-id="3d53c-110">自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。</span><span class="sxs-lookup"><span data-stu-id="3d53c-110">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

## <a name="auto-attendants"></a><span data-ttu-id="3d53c-111">自动助理</span><span class="sxs-lookup"><span data-stu-id="3d53c-111">Auto attendants</span></span>

<span data-ttu-id="3d53c-112">自动助理的主要用途是，根据呼叫者对提供的菜单选项的输入，将呼叫者引导至相应的人员或部门。</span><span class="sxs-lookup"><span data-stu-id="3d53c-112">The primary purpose of an auto attendant is to direct a caller to an appropriate person or department based on the caller's input to the provided menu options.</span></span> <span data-ttu-id="3d53c-113">呼叫者可以定向到组织内的特定人员，呼叫他们等待与下一个可用代理交谈的队列或语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3d53c-113">Callers can be directed to specific people within your organization, to call queues where they wait to talk to the next available agent, or to voicemail.</span></span> <span data-ttu-id="3d53c-114">可以针对营业时间、非工作时间和假日指定不同的呼叫路由选项。</span><span class="sxs-lookup"><span data-stu-id="3d53c-114">Different call routing options can be specified for business hours, off hours, and holidays.</span></span>

<span data-ttu-id="3d53c-115">菜单提示可以通过使用文本到语音 (系统生成的提示) 上传录制的音频文件。</span><span class="sxs-lookup"><span data-stu-id="3d53c-115">Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading a recorded audio file.</span></span> <span data-ttu-id="3d53c-116">语音识别接受用于免提导航的语音命令，但呼叫者也可使用电话键盘导航菜单。</span><span class="sxs-lookup"><span data-stu-id="3d53c-116">Speech recognition accepts voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.</span></span>

<span data-ttu-id="3d53c-117">每个自动助理都有特定的语言和时区。</span><span class="sxs-lookup"><span data-stu-id="3d53c-117">Each auto attendant has a specific language and time zone.</span></span> <span data-ttu-id="3d53c-118">如果你以多种语言或世界多个地区建立业务，你可以创建许多不同的自动助理，以满足呼叫者需求。</span><span class="sxs-lookup"><span data-stu-id="3d53c-118">If you do business in multiple languages or multiple parts of the world, you can create as many different auto attendants as you need to accommodate your callers.</span></span>

<span data-ttu-id="3d53c-119">对于每个自动助理，可以配置接线员。</span><span class="sxs-lookup"><span data-stu-id="3d53c-119">For each auto attendant, you can configure an operator.</span></span> <span data-ttu-id="3d53c-120">虽然可以将接线员呼叫配置为转到各种目的地，但接线员功能旨在允许呼叫者与组织中可以提供帮助的特定人员交谈。</span><span class="sxs-lookup"><span data-stu-id="3d53c-120">While you can configure operator calls to go to a variety of destinations, the operator feature is designed to allow callers to talk to a specific person in your organization who can help them.</span></span>

<span data-ttu-id="3d53c-121">可以将自动助理配置为允许呼叫者按姓名或分机号码搜索组织的目录。</span><span class="sxs-lookup"><span data-stu-id="3d53c-121">Auto attendants can be configured to allow callers to search your organization's directory, either by name or by extension number.</span></span> <span data-ttu-id="3d53c-122">在自动助理中，可以通过选择要包括或排除的用户组来指定哪些人可用于目录搜索。</span><span class="sxs-lookup"><span data-stu-id="3d53c-122">Within an auto attendant, you can specify who is available for the directory search by choosing groups of users to include or exclude.</span></span> <span data-ttu-id="3d53c-123"> (这称为拨号 *范围*.) </span><span class="sxs-lookup"><span data-stu-id="3d53c-123">(This is known as *dial scope*.)</span></span>

<span data-ttu-id="3d53c-124">呼叫者可以通过直接电话号码（如果已配置）或者通过从另一个自动助理或呼叫队列重定向来联系自动助理。</span><span class="sxs-lookup"><span data-stu-id="3d53c-124">Callers can reach an auto attendant either by direct phone number, if configured, or by being redirected from another auto attendant or a call queue.</span></span>

## <a name="call-queues"></a><span data-ttu-id="3d53c-125">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3d53c-125">Call queues</span></span>

<span data-ttu-id="3d53c-126">呼叫队列类似于物理大楼中的等待室。</span><span class="sxs-lookup"><span data-stu-id="3d53c-126">A call queue is analogous to a waiting room in a physical building.</span></span> <span data-ttu-id="3d53c-127">当呼叫路由到队列中的代理时，调用方将等待等待。</span><span class="sxs-lookup"><span data-stu-id="3d53c-127">Callers wait on hold while calls are routed to the agents in the queue.</span></span> <span data-ttu-id="3d53c-128">呼叫队列通常用于销售和服务功能。</span><span class="sxs-lookup"><span data-stu-id="3d53c-128">Call queues are commonly used for sales and service functions.</span></span> <span data-ttu-id="3d53c-129">但是，呼叫队列可用于通话次数超过内部容量的任何情况，例如忙碌设施中的接待员。</span><span class="sxs-lookup"><span data-stu-id="3d53c-129">However, call queues can be used for any situation where the number of calls exceeds your internal capacity, such as a receptionist in a busy facility.</span></span>

<span data-ttu-id="3d53c-130">当队列中的呼叫者总数或等待时间超过指定的限制时，呼叫队列允许特定的调用路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-130">Call queues allow for specific routing of calls in cases where the total number of callers in the queue or the wait time exceeds the limits that you specify.</span></span> <span data-ttu-id="3d53c-131">呼叫可以路由到特定人员、语音邮件、其他呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="3d53c-131">Calls can be routed to specific people, voicemail, other call queues, or auto attendants.</span></span>

<span data-ttu-id="3d53c-132">与自动助理一样，呼叫队列每个都有语言设置。</span><span class="sxs-lookup"><span data-stu-id="3d53c-132">Like auto attendants, call queues each have a language setting.</span></span> <span data-ttu-id="3d53c-133">如果以多种语言进行业务，可以使用不同的呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-133">You can use different call queues if you do business in multiple languages.</span></span> <span data-ttu-id="3d53c-134">如果代理是多语言代理，它们可以是多个队列的成员。</span><span class="sxs-lookup"><span data-stu-id="3d53c-134">Agents can be members of more than one queue if they're multi-lingual.</span></span>

<span data-ttu-id="3d53c-135">对于每个呼叫队列，可以指定队列中的代理能否选择不接听呼叫，以及是否应当根据 Teams 中的状态指示将呼叫路由给他们。</span><span class="sxs-lookup"><span data-stu-id="3d53c-135">For each call queue, you can specify if agents in the queue can opt out of taking calls and if calls should be routed to them based on their presence indication in Teams.</span></span>

<span data-ttu-id="3d53c-136">可以将电话号码分配给呼叫队列，但是呼叫队列不提供非工作时间和假日的单独呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-136">You can assign a phone number to a call queue, however call queues do not provide separate call routing for off hours and holidays.</span></span> <span data-ttu-id="3d53c-137">除非你的呼叫队列是 24/7 人员，否则我们建议将电话号码分配给在营业时间重定向到呼叫队列的自动助理。</span><span class="sxs-lookup"><span data-stu-id="3d53c-137">Unless your call queue is staffed 24/7, we recommend assigning the phone number to an auto attendant that redirects to the call queue during business hours.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d53c-138">先决条件</span><span class="sxs-lookup"><span data-stu-id="3d53c-138">Prerequisites</span></span>

<span data-ttu-id="3d53c-139">若要配置自动助理和呼叫队列，需要以下资源：</span><span class="sxs-lookup"><span data-stu-id="3d53c-139">To configure auto attendants and call queues, you need the following resources:</span></span>

- <span data-ttu-id="3d53c-140">每个自动助理和每个呼叫队列的资源帐户</span><span class="sxs-lookup"><span data-stu-id="3d53c-140">A resource account for each auto attendant and each call queue</span></span>
- <span data-ttu-id="3d53c-141">免费手机系统 - 每个资源帐户的虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="3d53c-141">A free Phone System - Virtual User license for each resource account</span></span>
- <span data-ttu-id="3d53c-142">要直接拨打的每个资源帐户至少有一个 [Microsoft](getting-service-phone-numbers.md)服务号码、直接路由号码或混合号码</span><span class="sxs-lookup"><span data-stu-id="3d53c-142">At least one [Microsoft service number](getting-service-phone-numbers.md), direct routing number, or a hybrid number for each resource account that you want to be directly dialable</span></span>
 - <span data-ttu-id="3d53c-143">服务号码可能是收费或免费电话号码</span><span class="sxs-lookup"><span data-stu-id="3d53c-143">The service number may be a toll or toll-free number</span></span>

<span data-ttu-id="3d53c-144">从呼叫队列接收呼叫的代理必须企业语音或本地用户启用。</span><span class="sxs-lookup"><span data-stu-id="3d53c-144">Agents who receive calls from the call queues must be Enterprise Voice enabled online or on-premise users.</span></span> <span data-ttu-id="3d53c-145">此外，如果呼叫队列使用直接路由号码，则需要电话会议或转接呼叫的代理还需要：</span><span class="sxs-lookup"><span data-stu-id="3d53c-145">In addition, if the call queues are using Direct Routing numbers, agents who need to conference or transfer calls also require:</span></span>

- <span data-ttu-id="3d53c-146">在呼叫队列使用转接模式时分配的联机语音路由策略</span><span class="sxs-lookup"><span data-stu-id="3d53c-146">An online voice routing policy assigned if the call queue uses transfer mode</span></span>
- <span data-ttu-id="3d53c-147">如果呼叫队列使用会议模式，则分配音频会议许可证或在线语音路由策略</span><span class="sxs-lookup"><span data-stu-id="3d53c-147">An Audio Conferencing license or online voice routing policy assigned if the call queue uses conference mode</span></span>

<span data-ttu-id="3d53c-148">如果你的代理使用 Microsoft Teams 应用进行呼叫队列呼叫，他们需要在 TeamsOnly 模式下。</span><span class="sxs-lookup"><span data-stu-id="3d53c-148">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="3d53c-149">将呼叫转接到外部电话号码时，执行转接 (的资源帐户，即与自动助理或呼叫队列) 关联的资源帐户必须具有电话号码和 Microsoft 365 电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="3d53c-149">When transferring calls to an external phone number, the resource account performing the transfer (that is, the one associated with the auto attendant or call queue) must have a phone number and a Microsoft 365 Phone System Virtual User license.</span></span> <span data-ttu-id="3d53c-150">此外：</span><span class="sxs-lookup"><span data-stu-id="3d53c-150">Additionally:</span></span>

- <span data-ttu-id="3d53c-151">对于具有呼叫计划号码的资源帐户，请分配 [呼叫计划](calling-plans-for-office-365.md) 许可证。</span><span class="sxs-lookup"><span data-stu-id="3d53c-151">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="3d53c-152">对于具有直接路由号码的资源帐户，请分配 [联机语音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3d53c-152">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3d53c-153">仅 Microsoft Teams 用户和呼叫代理支持自动助理和呼叫队列的直接路由服务号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-153">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and call agents only.</span></span><br>
> <span data-ttu-id="3d53c-154">不支持在呼叫计划中继和直接路由中继之间传输。</span><span class="sxs-lookup"><span data-stu-id="3d53c-154">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

## <a name="business-decisions"></a><span data-ttu-id="3d53c-155">业务决策</span><span class="sxs-lookup"><span data-stu-id="3d53c-155">Business decisions</span></span>

<span data-ttu-id="3d53c-156">在设置自动助理和呼叫队列之前，应做出一些决定，了解如何在企业中使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="3d53c-156">Before you set up your auto attendants and call queues, there are some decisions that you should make about how to use these features in your business.</span></span> <span data-ttu-id="3d53c-157">这些决策将决定配置自动助理和呼叫队列时选择的设置。</span><span class="sxs-lookup"><span data-stu-id="3d53c-157">These decisions will determine the settings that you choose when you configure your auto attendants and call queues.</span></span>

<span data-ttu-id="3d53c-158">记录这些问题的解答，并为执行配置的管理员提供相关信息。</span><span class="sxs-lookup"><span data-stu-id="3d53c-158">Document your answers to these questions and provide the information to the administrator doing the configuration.</span></span>

- <span data-ttu-id="3d53c-159">需要哪些语言？</span><span class="sxs-lookup"><span data-stu-id="3d53c-159">What languages do you need?</span></span> <span data-ttu-id="3d53c-160">这些语言需要在何处 - 哪个部门或组？</span><span class="sxs-lookup"><span data-stu-id="3d53c-160">Where are these languages needed - which department or group?</span></span>
- <span data-ttu-id="3d53c-161">你是希望允许来自呼叫者的语音输入还是仅允许拨号输入？</span><span class="sxs-lookup"><span data-stu-id="3d53c-161">Do you want to allow voice inputs from callers or only dialing inputs?</span></span>
- <span data-ttu-id="3d53c-162">非工作时间或假日是否需要单独的呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="3d53c-162">Do you need separate call routing for off hours or holidays?</span></span> <span data-ttu-id="3d53c-163">营业时间和假日是什么？</span><span class="sxs-lookup"><span data-stu-id="3d53c-163">What are the hours and holidays?</span></span>
- <span data-ttu-id="3d53c-164">是否允许呼叫队列中的代理选择不接听呼叫？</span><span class="sxs-lookup"><span data-stu-id="3d53c-164">Do you want to allow agents in a call queue to opt out of taking calls?</span></span>
- <span data-ttu-id="3d53c-165">希望呼叫队列中的代理或接线员在拨出时拥有特定的呼叫者 ID？</span><span class="sxs-lookup"><span data-stu-id="3d53c-165">Do you want agents in your call queues or your operator to have a specific caller ID if they dial out?</span></span>
- <span data-ttu-id="3d53c-166">是否 [希望在你的组织中](call-park-and-retrieve.md) 启用呼叫停放和检索，以帮助人员或部门之间的呼叫协调？</span><span class="sxs-lookup"><span data-stu-id="3d53c-166">Do you want to enable [call parking and retrieval](call-park-and-retrieve.md) in your organization to assist in call handoffs between people or departments?</span></span>
- <span data-ttu-id="3d53c-167">对于语音提示，是否要录制自己的语音或使用系统生成的语音？</span><span class="sxs-lookup"><span data-stu-id="3d53c-167">For the voice prompts, do you want to record your own or use the system-generated voice?</span></span> <span data-ttu-id="3d53c-168"> (系统生成的语音易于更新。) </span><span class="sxs-lookup"><span data-stu-id="3d53c-168">(The system-generated voice is easy to update.)</span></span>

## <a name="technical-decisions"></a><span data-ttu-id="3d53c-169">技术决策</span><span class="sxs-lookup"><span data-stu-id="3d53c-169">Technical decisions</span></span>

<span data-ttu-id="3d53c-170">使用自动助理和呼叫队列将呼叫者连接到组织人员时，在开始配置之前，需要做出一些技术决策。</span><span class="sxs-lookup"><span data-stu-id="3d53c-170">When using auto attendants and call queues to connect callers to people in your organization, there are some technical decisions to make before you start the configuration.</span></span>

<span data-ttu-id="3d53c-171">可以按照以下方式添加代理以调用队列：</span><span class="sxs-lookup"><span data-stu-id="3d53c-171">Agents can be added to call queues in the following ways:</span></span>

- <span data-ttu-id="3d53c-172">单个用户</span><span class="sxs-lookup"><span data-stu-id="3d53c-172">Individual users</span></span>
- <span data-ttu-id="3d53c-173">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="3d53c-173">Distribution lists</span></span>
- <span data-ttu-id="3d53c-174">安全组，包括启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="3d53c-174">Security groups, including mail-enabled security groups</span></span>
- <span data-ttu-id="3d53c-175">Microsoft 365 组或 Teams</span><span class="sxs-lookup"><span data-stu-id="3d53c-175">Microsoft 365 Groups or Teams</span></span>

<span data-ttu-id="3d53c-176">如果需要，可以针对每个队列使用这些选项的组合。</span><span class="sxs-lookup"><span data-stu-id="3d53c-176">You can use a combination of these options for each queue if needed.</span></span> <span data-ttu-id="3d53c-177">具有电子邮件地址的组可用于语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3d53c-177">Groups that have an email address can be used for voicemail.</span></span> <span data-ttu-id="3d53c-178">使用 Teams 提供许多优势，包括共享文件存储和代理之间的聊天、可接收语音邮件的公用邮箱，以及可包括与业务线应用程序或 Power Apps 集成的可扩展平台。</span><span class="sxs-lookup"><span data-stu-id="3d53c-178">Using Teams offers a number of advantages, including shared file storage and chat between agents, a common mailbox where voicemails can be received, and an extensible platform that can include integration with your line of business applications or Power Apps.</span></span>

<span data-ttu-id="3d53c-179">建议在开始配置之前选择一个策略，用于将呼叫代理添加到队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-179">We recommend choosing a strategy for adding call agents to queues before you start your configuration.</span></span>

<span data-ttu-id="3d53c-180">如果你有现有的自动助理和呼叫队列基础结构，并且要迁移到 Teams，则需要一个计划，将现有电话号码转移到新的自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-180">If you have an existing auto attendant and call queue infrastructure and you're migrating to Teams, you'll need a plan to transfer your existing phone numbers to the new auto attendants and call queues.</span></span> <span data-ttu-id="3d53c-181">可能需要创建转口 [订单，才能](phone-number-calling-plans/port-order-overview.md) 将号码从其他提供商移动。</span><span class="sxs-lookup"><span data-stu-id="3d53c-181">You might need to create a [port order](phone-number-calling-plans/port-order-overview.md) to move your numbers from another providers.</span></span> <span data-ttu-id="3d53c-182">建议临时获取一个或多个新电话号码，测试自动助理和呼叫队列流，然后再切换当前服务号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-182">We recommend that you temporarily acquire one or more new phone numbers and test your auto attendant and call queue flows before switching them over the numbers you currently have in service.</span></span>

<span data-ttu-id="3d53c-183">*会议模式* 是呼叫队列中的一个选项，可显著减少将 Teams VOIP 呼叫和 PSTN 呼叫连接到代理所花的时间。</span><span class="sxs-lookup"><span data-stu-id="3d53c-183">*Conference mode* is an option in call queues that significantly reduces the amount of time it takes to connect Teams VOIP calls and PSTN calls to an agent.</span></span> <span data-ttu-id="3d53c-184">若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：</span><span class="sxs-lookup"><span data-stu-id="3d53c-184">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

- <span data-ttu-id="3d53c-185">最新版本的 Microsoft Teams 桌面客户端、Android 应用或 iOS 应用</span><span class="sxs-lookup"><span data-stu-id="3d53c-185">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="3d53c-186">Microsoft Teams 手机版本 1449/1.0.94.2020051601 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3d53c-186">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="3d53c-187">将代理的 Teams 帐户设置为仅 Teams 模式。</span><span class="sxs-lookup"><span data-stu-id="3d53c-187">Set Agents' Teams accounts to Teams-only mode.</span></span> <span data-ttu-id="3d53c-188">不符合要求的代理不包括在呼叫路由列表中。</span><span class="sxs-lookup"><span data-stu-id="3d53c-188">Agents who don't meet the requirements aren't included in the call routing list.</span></span>

<span data-ttu-id="3d53c-189">如果代理都使用兼容的客户端，我们建议为呼叫队列启用会议模式。</span><span class="sxs-lookup"><span data-stu-id="3d53c-189">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="3d53c-190">会议模式不支持忙碌。</span><span class="sxs-lookup"><span data-stu-id="3d53c-190">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="3d53c-191">如果未启用基于状态的路由，则非呼叫队列呼叫上的代理仍可能显示呼叫队列呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-191">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

## <a name="plan-your-call-routing-flow"></a><span data-ttu-id="3d53c-192">规划呼叫路由流</span><span class="sxs-lookup"><span data-stu-id="3d53c-192">Plan your call routing flow</span></span>

<span data-ttu-id="3d53c-193">在规划过程中，我们建议在图表中为组织制定呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-193">As part of the planning process, we recommend that you work out the call routing for your organization in a diagram.</span></span> <span data-ttu-id="3d53c-194">该图可帮助确定呼叫组织人员的最高效路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-194">The diagram helps determine the most efficient routing for people calling in to your organization.</span></span> <span data-ttu-id="3d53c-195">还可使用图表来确定需要创建的自动助理和呼叫队列，以及服务号码、许可证和资源帐户等相关要求。</span><span class="sxs-lookup"><span data-stu-id="3d53c-195">You can also use the diagram to determine the auto attendants and call queues that you need to create, along with related requirements such as service numbers, licenses, and resource accounts.</span></span>

<span data-ttu-id="3d53c-196">让我们看看自动助理和呼叫队列如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-196">Let's look at how auto attendants and call queues route calls.</span></span>

<span data-ttu-id="3d53c-197">自动助理通过以下方式之一路由所有呼叫：</span><span class="sxs-lookup"><span data-stu-id="3d53c-197">Auto attendants route all calls in one of the following ways:</span></span>

- <span data-ttu-id="3d53c-198">**立即重定向** - 呼叫可以重定向到下面列出的呼叫路由目标 (在) 或初始问候后立即列出。</span><span class="sxs-lookup"><span data-stu-id="3d53c-198">**Redirect immediately** - calls can be redirected to one of the call routing destinations (listed below) immediately upon answering or after an initial greeting.</span></span>
- <span data-ttu-id="3d53c-199">**基于拨号选项重定向** - 可以指示呼叫者在分配给其电话键盘上的号码的选项（0-9）之间选择。</span><span class="sxs-lookup"><span data-stu-id="3d53c-199">**Redirect based on dial options** - callers can be directed to choose between options that are assigned to the numbers on their telephone keypad, 0-9.</span></span> <span data-ttu-id="3d53c-200">可以为每个拨号键分配一个呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="3d53c-200">Each dial key can be assigned a call routing destinations.</span></span>
- <span data-ttu-id="3d53c-201">**按姓名** 或分机呼叫人员 - 呼叫者可以定向到他们尝试在组织的目录中联系的联系人的分机号码，或者通过拼写人员的姓名来拨打分机号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-201">**Dial people by name or extension** - callers can be directed to dial the extension number of the person they're trying to reach in your organization's directory, or by spelling the person's name.</span></span>
- <span data-ttu-id="3d53c-202">**断开连接** - 自动助理可以挂断呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-202">**Disconnect** - an auto attendant can hang up the call.</span></span>

> [!NOTE]
> <span data-ttu-id="3d53c-203">单个自动助理只能支持单个"拨号方式"方法。</span><span class="sxs-lookup"><span data-stu-id="3d53c-203">A single Auto attendant can only support a single "dial by" method.</span></span>  <span data-ttu-id="3d53c-204">若要允许呼叫者按姓名和号码进行拨号，你需要创建一个自动助理，该自动助理具有按名称进行拨号的选项，另一个选项用于按分机进行拨号。</span><span class="sxs-lookup"><span data-stu-id="3d53c-204">To allow callers to dial by name and by number, you will need to create an auto attendant that has an option for dial by name and the another for dial by extension.</span></span>  <span data-ttu-id="3d53c-205">其中每个选项将路由到为这些"拨号方式"方案配置的单独自动助理。</span><span class="sxs-lookup"><span data-stu-id="3d53c-205">Each of these options will route to separate auto attendants configured for these "dial by" scenarios.</span></span>

<span data-ttu-id="3d53c-206">当自动助理或呼叫队列重定向呼叫时，可以从以下呼叫路由目标中选择：</span><span class="sxs-lookup"><span data-stu-id="3d53c-206">When calls are redirected by an auto attendant or call queue, you can choose from the following call routing destinations:</span></span>

- <span data-ttu-id="3d53c-207">**组织中的人** - 组织中能够接收语音呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="3d53c-207">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="3d53c-208">这可以是联机用户，或者是使用 Skype for Business Server 在本地托管的用户。</span><span class="sxs-lookup"><span data-stu-id="3d53c-208">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="3d53c-209">**语音应用** - 另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-209">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="3d53c-210">选择与目标关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3d53c-210">Choose the resource account associated with the destination.</span></span>
- <span data-ttu-id="3d53c-211">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-211">**External phone number** - any phone number.</span></span> <span data-ttu-id="3d53c-212"> (外部[传输技术详细信息) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="3d53c-212">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="3d53c-213">**语音邮件** - 与指定的 Microsoft 365 组关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="3d53c-213">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="3d53c-214">**接线** 员 (自动助理) 自动助理定义的接线员。</span><span class="sxs-lookup"><span data-stu-id="3d53c-214">**Operator** (auto attendant only) - the operator defined for the auto attendant.</span></span> <span data-ttu-id="3d53c-215">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="3d53c-215">Defining an operator is optional.</span></span> <span data-ttu-id="3d53c-216">操作员可以是此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="3d53c-216">An operator can be any of the other destinations in this list.</span></span>

<span data-ttu-id="3d53c-217">自动助理为在营业时间外和假日收到的呼叫提供单独的呼叫路由选项。</span><span class="sxs-lookup"><span data-stu-id="3d53c-217">Auto attendants offer separate call routing options for calls received outside of business hours and on holidays.</span></span> <span data-ttu-id="3d53c-218">非营业时间呼叫路由允许上面列出的所有选项，而假日呼叫路由仅允许重定向或断开呼叫，但允许没有拨号键选项。</span><span class="sxs-lookup"><span data-stu-id="3d53c-218">After-hours call routing allows all the options listed above, while holiday call routing allows only redirecting or disconnecting a call, but no dial key options.</span></span>

<span data-ttu-id="3d53c-219">呼叫队列将调用方放在保持状态，直到分配到队列的代理可以发起其呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-219">Call queues place the caller on hold until an agent assigned to the queue is available to take their call.</span></span> <span data-ttu-id="3d53c-220">在两种情况下，调用方可能会被定向出队列：</span><span class="sxs-lookup"><span data-stu-id="3d53c-220">There are two situations where a caller might be directed out of the queue:</span></span>

- <span data-ttu-id="3d53c-221">**调用溢出** - 如果队列中的调用数超过设置的限制，则新调用方会从队列中重定向。</span><span class="sxs-lookup"><span data-stu-id="3d53c-221">**Call overflow** - if the number of calls in the queue exceeds the limit that you set, then new callers are redirected out of the queue.</span></span>
- <span data-ttu-id="3d53c-222">**调用超时** - 如果调用方在队列中的时间超过配置的超时设置，则将其从队列中重定向。</span><span class="sxs-lookup"><span data-stu-id="3d53c-222">**Call timeout** - if a caller has been in the queue longer than the configured timeout setting, they're redirected out of the queue.</span></span>

<span data-ttu-id="3d53c-223">从队列重定向的呼叫可以发送到上面列出的任何呼叫路由目标，操作员除外。</span><span class="sxs-lookup"><span data-stu-id="3d53c-223">Calls redirected out of a queue can be sent to any of the call routing destinations listed above except for an operator.</span></span> <span data-ttu-id="3d53c-224"> (呼叫队列没有运算符，但可以将呼叫者重定向到与为自动助理.) </span><span class="sxs-lookup"><span data-stu-id="3d53c-224">(Call queues don't have operators, but you can redirect callers to the same destination as an operator that you've configured for an auto attendant.)</span></span>

<span data-ttu-id="3d53c-225">以下示例显示了使用自动助理和呼叫队列的呼叫路由示例。</span><span class="sxs-lookup"><span data-stu-id="3d53c-225">The example below shows an example of call routing using auto attendants and call queues.</span></span>

![使用自动助理和呼叫队列的呼叫路由图](media/attendant-and-queue-call-routing.png)

<span data-ttu-id="3d53c-227">在上例中：</span><span class="sxs-lookup"><span data-stu-id="3d53c-227">In the example above:</span></span>

- <span data-ttu-id="3d53c-228">0 (0) 键将调用方重定向到操作员。</span><span class="sxs-lookup"><span data-stu-id="3d53c-228">The zero (0) key redirects callers to an operator.</span></span> <span data-ttu-id="3d53c-229">该自动助理的接线员已配置为 **组织中的人**。</span><span class="sxs-lookup"><span data-stu-id="3d53c-229">The operator for that auto attendant has been configured as a **Person in the organization**.</span></span>
- <span data-ttu-id="3d53c-230">1 (键) 将调用方重定向到销售呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-230">The one (1) key redirects callers to the sales call queue.</span></span> <span data-ttu-id="3d53c-231">此呼叫队列连接到包含分配给队列的销售团队的团队。</span><span class="sxs-lookup"><span data-stu-id="3d53c-231">This call queue is connected to a team that contains the sales team assigned to the queue.</span></span>
- <span data-ttu-id="3d53c-232">这两 (2) 密钥将调用方重定向到支持呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-232">The two (2) key redirects callers to the support call queue.</span></span> <span data-ttu-id="3d53c-233">此呼叫队列连接到包含分配给该团队的支持团队的团队。</span><span class="sxs-lookup"><span data-stu-id="3d53c-233">This call queue is connected to a team that contains the support team assigned to the team.</span></span>
- <span data-ttu-id="3d53c-234">支持呼叫队列通过中间的自动助理提供直接电话号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-234">The support call queue has a direct phone number via an intervening auto attendant.</span></span> <span data-ttu-id="3d53c-235">让自动助理应答支持行允许单独的非工作时间和假日呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-235">Having an auto attendant answer the support line allows for separate off hours and holiday call routing.</span></span>
- <span data-ttu-id="3d53c-236">三 (3) 密钥将用户重定向到公司目录的另一个自动助理。</span><span class="sxs-lookup"><span data-stu-id="3d53c-236">The three (3) key redirects users to another auto attendant for the company directory.</span></span> <span data-ttu-id="3d53c-237">公司目录自动助理允许呼叫者通过拨打其姓名或分机呼叫组织的个人。</span><span class="sxs-lookup"><span data-stu-id="3d53c-237">The company directory auto attendant allows callers to call individuals in the organization by dialing their name or extension.</span></span>

<span data-ttu-id="3d53c-238">建议创建一个或多个类似于上面的图表来映射呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-238">We recommend that you create one or more diagrams similar to the one above to map out your call routing.</span></span> <span data-ttu-id="3d53c-239">请确保在图表或随附文档中包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="3d53c-239">Be sure to include the following in your diagram or accompanying documentation:</span></span>

- <span data-ttu-id="3d53c-240">哪些自动助理可通过电话号码直接访问？</span><span class="sxs-lookup"><span data-stu-id="3d53c-240">Which auto attendants will have direct access via phone numbers?</span></span>
- <span data-ttu-id="3d53c-241">每个自动助理的非工作时间和假日路线要求是什么？</span><span class="sxs-lookup"><span data-stu-id="3d53c-241">What are the off-hours and holiday routing requirements for each auto attendants?</span></span>
- <span data-ttu-id="3d53c-242">每个调用队列的成员身份。</span><span class="sxs-lookup"><span data-stu-id="3d53c-242">The membership for each call queue.</span></span> <span data-ttu-id="3d53c-243"> (可以单独添加用户，也可以将队列映射到不同类型的组。</span><span class="sxs-lookup"><span data-stu-id="3d53c-243">(You can add users individually or map the queue to different kinds of groups.</span></span> <span data-ttu-id="3d53c-244">将队列映射到团队可提供最通用的体验。) </span><span class="sxs-lookup"><span data-stu-id="3d53c-244">Mapping a queue to a team provides the most versatile experience.)</span></span>

<span data-ttu-id="3d53c-245">下面是一些呼叫路由最佳做法：</span><span class="sxs-lookup"><span data-stu-id="3d53c-245">Here are some call routing best practices:</span></span>

- <span data-ttu-id="3d53c-246">查看现有呼叫系统并分析传入呼叫的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="3d53c-246">Look at your existing calling system and analyze the types and frequency of incoming calls.</span></span> <span data-ttu-id="3d53c-247">使用此信息帮助通知自动助理和呼叫队列结构。</span><span class="sxs-lookup"><span data-stu-id="3d53c-247">Use this information to help inform your auto attendant and call queue structure.</span></span>
- <span data-ttu-id="3d53c-248">最早在菜单中放入最常用的选项，以尽快路由调用。</span><span class="sxs-lookup"><span data-stu-id="3d53c-248">Put the most common options earliest in the menu to route calls as quickly as possible.</span></span>
- <span data-ttu-id="3d53c-249">避免将服务号码直接连接到呼叫队列，除非队列24/7 可用。</span><span class="sxs-lookup"><span data-stu-id="3d53c-249">Avoid connecting service numbers directly to call queues unless the queues are available 24/7.</span></span> <span data-ttu-id="3d53c-250">呼叫队列不允许在非工作时间或假日单独处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-250">Call queues don't allow for separate call handling for off hours or holidays.</span></span> <span data-ttu-id="3d53c-251">如果要使用具有直接号码的队列，请为自动助理分配该号码，该自动助理会在营业时间自动重定向到队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-251">If you want to have a queue with a direct number, assign the number to an auto attendant that automatically redirects to the queue during business hours.</span></span>
- <span data-ttu-id="3d53c-252">如果您收到大量呼叫，请求有关您的公司的基本信息（如营业时间、位置或网站地址），请考虑创建自动助理以使用录制的消息回答这些问题。</span><span class="sxs-lookup"><span data-stu-id="3d53c-252">If you receive numerous calls requesting basic information about your company, such as business hours, location, or web site address, consider creating an auto attendant to answer these questions with recorded messages.</span></span>
- <span data-ttu-id="3d53c-253">将菜单项列表保留为五个或更少。</span><span class="sxs-lookup"><span data-stu-id="3d53c-253">Keep the list of menu items to five or fewer.</span></span> <span data-ttu-id="3d53c-254">呼叫者在记住超过五个选项时可能遇到问题。</span><span class="sxs-lookup"><span data-stu-id="3d53c-254">Callers can have trouble remembering more than five options.</span></span> <span data-ttu-id="3d53c-255">如果需要更多选项来正确路由呼叫，请使用嵌套式自动助理。</span><span class="sxs-lookup"><span data-stu-id="3d53c-255">Use nested auto attendants if more options are needed to properly route a call.</span></span>
- <span data-ttu-id="3d53c-256">先描述服务，然后按以下选项 (例如：对于"销售"，请按 1) 而不是按其他方式 (例如</span><span class="sxs-lookup"><span data-stu-id="3d53c-256">Describe the service first, followed by the option to press (eg: For Sales press 1) rather than the other way around (eg.</span></span> <span data-ttu-id="3d53c-257">按 1 进行销售) 。</span><span class="sxs-lookup"><span data-stu-id="3d53c-257">Press 1 for Sales).</span></span>
- <span data-ttu-id="3d53c-258">调用方将理解用户术语，而不是在内部使用哪些术语。</span><span class="sxs-lookup"><span data-stu-id="3d53c-258">User terminology your callers will understand rather than what you may use internally.</span></span>
- <span data-ttu-id="3d53c-259">避免频繁更新调用路由。</span><span class="sxs-lookup"><span data-stu-id="3d53c-259">Avoid frequent updates to call routing.</span></span> <span data-ttu-id="3d53c-260">如果将来更改自动助理的菜单选项，在前 30 天内，在语音提示中发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d53c-260">If you change your menu options for an auto attendant in the future, call that out in the voice prompts for the first 30 days.</span></span>

## <a name="getting-started"></a><span data-ttu-id="3d53c-261">入门</span><span class="sxs-lookup"><span data-stu-id="3d53c-261">Getting started</span></span>

<span data-ttu-id="3d53c-262">完成本文中的规划任务后，请按照以下步骤设置自动助理和呼叫队列：</span><span class="sxs-lookup"><span data-stu-id="3d53c-262">Once you've completed the planning tasks in this article, follow these steps to get your auto attendants and call queues set up:</span></span>

1. <span data-ttu-id="3d53c-263">从组织外部直接拨号，获取自动助理和呼叫队列所需的服务号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-263">Get the service numbers that you need for the auto attendants and call queues that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="3d53c-264">这可能包括[转移来自其他提供商的号码或](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)[请求新的服务号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="3d53c-264">This might include [transferring numbers from another provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](getting-service-phone-numbers.md).</span></span>

2. <span data-ttu-id="3d53c-265">获取 [计划创建的每个](teams-add-on-licensing/virtual-user.md) 资源帐户的电话系统 - 虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="3d53c-265">Get a [Phone System - Virtual User license](teams-add-on-licensing/virtual-user.md) for each resource account that you plan to create.</span></span> <span data-ttu-id="3d53c-266">这些许可证是免费的，因此我们建议额外获取一些许可证，以防你决定在将来对资源帐户进行更改。</span><span class="sxs-lookup"><span data-stu-id="3d53c-266">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your resource accounts in the future.</span></span>

3. <span data-ttu-id="3d53c-267">[为要创建的每个](manage-resource-accounts.md) 自动助理和呼叫队列创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3d53c-267">[Create a resource account](manage-resource-accounts.md) for each auto attendant and call queue that you want to create.</span></span> <span data-ttu-id="3d53c-268">为每个帐户分配电话系统 - 虚拟用户许可证，以及（可选）服务号码。</span><span class="sxs-lookup"><span data-stu-id="3d53c-268">Assign each account a Phone System - Virtual User license and, optionally, a service number.</span></span>

4. <span data-ttu-id="3d53c-269">[创建想要](set-up-holidays-in-teams.md) 在自动助理中设置单独呼叫路由的假日。</span><span class="sxs-lookup"><span data-stu-id="3d53c-269">[Create the holidays](set-up-holidays-in-teams.md) for which you want to have separate call routing in your auto attendants.</span></span>

5. <span data-ttu-id="3d53c-270">（可选 [）如果要使用](call-park-and-retrieve.md) 此功能来帮助转接呼叫，请设置呼叫停放和检索。</span><span class="sxs-lookup"><span data-stu-id="3d53c-270">Optionally, [set up call parking and retrieval](call-park-and-retrieve.md) if you want to use this feature to help with call transfers.</span></span>

6. <span data-ttu-id="3d53c-271">创建要用于包含呼叫队列的呼叫代理的组。</span><span class="sxs-lookup"><span data-stu-id="3d53c-271">Create the groups that you want to use to contain the call agents for the call queues.</span></span>

7. <span data-ttu-id="3d53c-272">如果计划允许按分机拨号，请确保已将用户的分机号码添加到其 Azure Active Directory 配置文件。</span><span class="sxs-lookup"><span data-stu-id="3d53c-272">If you plan to allow dial by extension, ensure that you've added your users' extension number to their Azure Active Directory profile.</span></span>

<span data-ttu-id="3d53c-273">完成上述步骤后，即可创建自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-273">Once you've completed the steps above, you're ready to create your auto attendants and call queues.</span></span> <span data-ttu-id="3d53c-274">由于自动助理和呼叫队列可以将呼叫重定向到彼此，因此请参考创建的工作流关系图，以确定应首先创建哪个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-274">Because auto attendants and call queues can redirect calls to each other, refer to the workflow diagram that you created to determine which auto attendant or call queue should be created first.</span></span> <span data-ttu-id="3d53c-275">在上图中的示例中，创建 Contoso 主自动助理之前，会创建销售和支持呼叫队列，因为主自动助理需要将呼叫者引导到销售和支持呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3d53c-275">In the example in the diagram above, you would create the sales and support call queues before you create the Contoso main auto attendant because the main auto attendant needs to direct callers to the sales and support call queues.</span></span>

<span data-ttu-id="3d53c-276">请参阅以下文章，了解如何创建自动助理和呼叫队列：</span><span class="sxs-lookup"><span data-stu-id="3d53c-276">See the following articles for information on how to create auto attendants and call queues:</span></span>

- [<span data-ttu-id="3d53c-277">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="3d53c-277">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="3d53c-278">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3d53c-278">Create a call queue</span></span>](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a><span data-ttu-id="3d53c-279">相关主题</span><span class="sxs-lookup"><span data-stu-id="3d53c-279">Related topics</span></span>

[<span data-ttu-id="3d53c-280">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="3d53c-280">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="3d53c-281">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="3d53c-281">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="3d53c-282">创建呼叫队列 - 小型企业教程</span><span class="sxs-lookup"><span data-stu-id="3d53c-282">Create a call queue - small business tutorial</span></span>](business-voice/create-a-phone-system-call-queue-smb.md)

[<span data-ttu-id="3d53c-283">设置自动助理 - 小型企业教程</span><span class="sxs-lookup"><span data-stu-id="3d53c-283">Set up an auto attendant - small business tutorial</span></span>](business-voice/create-a-phone-system-auto-attendant-smb.md)