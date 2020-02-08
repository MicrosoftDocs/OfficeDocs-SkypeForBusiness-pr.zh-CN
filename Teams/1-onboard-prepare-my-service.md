---
title: 准备部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用 "加入清单" 为团队准备 Office 365 并配置团队核心功能、网络和云语音工作负荷。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: efc7193549fac95a29a574f455576dec5ea35c58
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862822"
---
# <a name="prepare-my-service"></a><span data-ttu-id="10df6-103">准备服务</span><span class="sxs-lookup"><span data-stu-id="10df6-103">Prepare my service</span></span>

<span data-ttu-id="10df6-104">本文概述了为组织准备云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="10df6-105">通过正确准备，你可以确保你已准备好向你的组织提供云语音功能。</span><span class="sxs-lookup"><span data-stu-id="10df6-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="10df6-106">Microsoft 团队语音工作负荷的加入清单</span><span class="sxs-lookup"><span data-stu-id="10df6-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="10df6-107">以下清单将指导你完成以下步骤：使用呼叫计划（"呼叫计划"）实现音频会议、电话系统和 Microsoft 团队中的电话系统直接路由（"直接路由"）功能。</span><span class="sxs-lookup"><span data-stu-id="10df6-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="10df6-108">为团队准备 Office 365</span><span class="sxs-lookup"><span data-stu-id="10df6-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="10df6-109">配置团队核心功能</span><span class="sxs-lookup"><span data-stu-id="10df6-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="10df6-110">准备网络</span><span class="sxs-lookup"><span data-stu-id="10df6-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="10df6-111">在团队中配置云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="10df6-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="10df6-112">配置团队中的直接路由</span><span class="sxs-lookup"><span data-stu-id="10df6-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="10df6-113">这些清单中的任务和活动是应用于团队的每个云语音功能部署的核心 "待办事项" 项目。</span><span class="sxs-lookup"><span data-stu-id="10df6-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="10df6-114">你可以自定义清单，以包括特定于你自己的团队旅行的活动和任务。</span><span class="sxs-lookup"><span data-stu-id="10df6-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="10df6-115">本指南仅重点介绍通话计划、音频会议和直接路由。</span><span class="sxs-lookup"><span data-stu-id="10df6-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="10df6-116">如果您不熟悉团队，请查看[Microsoft 团队的概述](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="10df6-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="10df6-117">有关规划团队部署的一般指南，请从[Microsoft 团队中的 "部署聊天"、"团队"、"频道" 和 "应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)" 开始。</span><span class="sxs-lookup"><span data-stu-id="10df6-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="10df6-118">使用提供的清单跟踪每个单独的活动和任务的状态，并确保未跳过任何关键步骤。</span><span class="sxs-lookup"><span data-stu-id="10df6-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="10df6-119">每个活动都包括所需操作的详细说明和可用于完成该活动的其他信息的参考。</span><span class="sxs-lookup"><span data-stu-id="10df6-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="10df6-120">尽管我们建议按顺序跟踪检查表，但具体顺序将取决于你的部署的范围以及你的环境的配置和复杂程度。</span><span class="sxs-lookup"><span data-stu-id="10df6-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="10df6-121">它们被组织为支持 "全新" 团队部署（没有以前的 Skype for Business Online 状态）或从 Skype for business Online 迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="10df6-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="10df6-122">如果您是从 Skype for Business Online 迁移，您可能已经完成了这些活动中的一部分，并且现在可以忽略它们。</span><span class="sxs-lookup"><span data-stu-id="10df6-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="10df6-123">如果您是在每个网站的基础上加入用户，我们强烈建议您使用[网站支持行动手册（如 "行动手册"）](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)作为这些清单的辅助指南。</span><span class="sxs-lookup"><span data-stu-id="10df6-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="10df6-124">大多数配置设置在团队和 Skype for business Online 之间通用。</span><span class="sxs-lookup"><span data-stu-id="10df6-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="10df6-125">使用 Microsoft 365 管理中心和 Microsoft 团队管理中心配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="10df6-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="10df6-126">决策点</span><span class="sxs-lookup"><span data-stu-id="10df6-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="10df6-127">谁将负责监督加入核对清单的完成？</span><span class="sxs-lookup"><span data-stu-id="10df6-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="10df6-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="10df6-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="10df6-129">下载加入核对清单。</span><span class="sxs-lookup"><span data-stu-id="10df6-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="10df6-130">按照组织的部署计划逐步执行 "加入清单" 项目。</span><span class="sxs-lookup"><span data-stu-id="10df6-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="10df6-131">继续加入</span><span class="sxs-lookup"><span data-stu-id="10df6-131">Continue onboarding</span></span>

<span data-ttu-id="10df6-132">完成这些清单后，您将向团队部署成功添加了语音功能。</span><span class="sxs-lookup"><span data-stu-id="10df6-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="10df6-133">下一步，使用[网站支持行动手册 For 语音（行动手册）](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)帮助你在每个网站上为你的用户板载，并帮助确保你规划和执行重要的特定于网站的活动。</span><span class="sxs-lookup"><span data-stu-id="10df6-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="10df6-134">按网站推出计划准备的网站</span><span class="sxs-lookup"><span data-stu-id="10df6-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="10df6-135">建立服务管理过程</span><span class="sxs-lookup"><span data-stu-id="10df6-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="10df6-136">执行测试和修正</span><span class="sxs-lookup"><span data-stu-id="10df6-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="10df6-137">在团队中测试云语音工作负载</span><span class="sxs-lookup"><span data-stu-id="10df6-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="10df6-138">在构思阶段中定义并记录团队云语音业务成功和技术实现计划后，在管理中心执行所需的配置后，下一步是验证你的组织的通过功能、功能和可用性来满足预期和要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="10df6-139">在生产环境中部署试验或最终部署之前，应执行此验证步骤。</span><span class="sxs-lookup"><span data-stu-id="10df6-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="10df6-140">你可以利用在 Envision 阶段中定义的业务成功计划来充当确定活动、预期、功能/功能测试用例以及测试阶段中要评估的整体范围的基础。</span><span class="sxs-lookup"><span data-stu-id="10df6-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="10df6-141">定义测试方法</span><span class="sxs-lookup"><span data-stu-id="10df6-141">Define your testing approach</span></span>

<span data-ttu-id="10df6-142">在最简单的形式中，你的测试方法基于你查看音频会议、呼叫计划或直接路由服务的功能功能，并开发测试计划以验证你的功能要求是否满足范围内的用户。</span><span class="sxs-lookup"><span data-stu-id="10df6-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="10df6-143">下面是音频会议实现的板载阶段的示例测试计划。</span><span class="sxs-lookup"><span data-stu-id="10df6-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="10df6-144">要测试的音频会议功能</span><span class="sxs-lookup"><span data-stu-id="10df6-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="10df6-145">结果摘要</span><span class="sxs-lookup"><span data-stu-id="10df6-145">Results summary</span></span> | <span data-ttu-id="10df6-146">其他笔记</span><span class="sxs-lookup"><span data-stu-id="10df6-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="10df6-147">安排包含音频会议拨入信息的临时团队会议</span><span class="sxs-lookup"><span data-stu-id="10df6-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="10df6-148">通过/失败</span><span class="sxs-lookup"><span data-stu-id="10df6-148">Pass/Fail</span></span>   | <span data-ttu-id="10df6-149">TBD</span><span class="sxs-lookup"><span data-stu-id="10df6-149">TBD</span></span> |
| <span data-ttu-id="10df6-150">通过使用提供的拨入信息从 PSTN 拨入会议，使用手机进行会议音频</span><span class="sxs-lookup"><span data-stu-id="10df6-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="10df6-151">通过/失败</span><span class="sxs-lookup"><span data-stu-id="10df6-151">Pass/Fail</span></span> | <span data-ttu-id="10df6-152">TBD</span><span class="sxs-lookup"><span data-stu-id="10df6-152">TBD</span></span> |
| <span data-ttu-id="10df6-153">通过 PSTN 拨出，将其他人加入现有会议</span><span class="sxs-lookup"><span data-stu-id="10df6-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="10df6-154">通过/失败</span><span class="sxs-lookup"><span data-stu-id="10df6-154">Pass/Fail</span></span> | <span data-ttu-id="10df6-155">TBD</span><span class="sxs-lookup"><span data-stu-id="10df6-155">TBD</span></span> |



| <span data-ttu-id="10df6-156">通话计划或直接路由功能进行测试</span><span class="sxs-lookup"><span data-stu-id="10df6-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="10df6-157">结果摘要</span><span class="sxs-lookup"><span data-stu-id="10df6-157">Results summary</span></span> | <span data-ttu-id="10df6-158">其他笔记</span><span class="sxs-lookup"><span data-stu-id="10df6-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="10df6-159">通过拨打 PSTN 号码进行 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="10df6-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="10df6-160">通过/失败</span><span class="sxs-lookup"><span data-stu-id="10df6-160">Pass/Fail</span></span>       | <span data-ttu-id="10df6-161">TBD</span><span class="sxs-lookup"><span data-stu-id="10df6-161">TBD</span></span> |
| <span data-ttu-id="10df6-162">通过从外部线路（手机、座机）拨您的 PSTN 号码来接收 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="10df6-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="10df6-163">通过/失败</span><span class="sxs-lookup"><span data-stu-id="10df6-163">Pass/Fail</span></span> | <span data-ttu-id="10df6-164">TBD</span><span class="sxs-lookup"><span data-stu-id="10df6-164">TBD</span></span>|
| <span data-ttu-id="10df6-165">将 PSTN 呼叫从一个团队用户转移到另一个团队用户</span><span class="sxs-lookup"><span data-stu-id="10df6-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="10df6-166">通过/失败</span><span class="sxs-lookup"><span data-stu-id="10df6-166">Pass/Fail</span></span> | <span data-ttu-id="10df6-167">TBD</span><span class="sxs-lookup"><span data-stu-id="10df6-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="10df6-168">若要帮助测试案例创建作为起点，请参阅[团队会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)中可用的用户指南列表。</span><span class="sxs-lookup"><span data-stu-id="10df6-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="10df6-169">为团队设置云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="10df6-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="10df6-170">现在，你已定义测试方法，下一步是在团队云语音功能的范围内配置你的服务环境和用户。</span><span class="sxs-lookup"><span data-stu-id="10df6-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="10df6-171">有关其他信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="10df6-171">For additional information, see:</span></span>

- [<span data-ttu-id="10df6-172">音频会议的技术规划</span><span class="sxs-lookup"><span data-stu-id="10df6-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="10df6-173">设置 Microsoft Teams 的音频会议</span><span class="sxs-lookup"><span data-stu-id="10df6-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="10df6-174">带有呼叫计划的电话系统技术规划</span><span class="sxs-lookup"><span data-stu-id="10df6-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="10df6-175">为 Skype for business 和 Microsoft 团队设置呼叫计划</span><span class="sxs-lookup"><span data-stu-id="10df6-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="10df6-176">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="10df6-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="10df6-177">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="10df6-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="10df6-178">执行测试计划</span><span class="sxs-lookup"><span data-stu-id="10df6-178">Execute the test plan</span></span>

[//]: # (编辑？"用户" 似乎对我有点不明确。)
<span data-ttu-id="10df6-180">在用户环境和服务配置完成后，测试的最后一步包括测试计划执行，重点在于功能和功能验证。</span><span class="sxs-lookup"><span data-stu-id="10df6-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="10df6-181">**针对范围内的用户和网站的音频会议测试先决条件和假设：**</span><span class="sxs-lookup"><span data-stu-id="10df6-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="10df6-182">音频会议服务的业务使用案例定义已完成。</span><span class="sxs-lookup"><span data-stu-id="10df6-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="10df6-183">音频会议所需的许可可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="10df6-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="10df6-184">已标识组织网站和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="10df6-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="10df6-185">已确定并配置了具有语言首选项的专用和共享音频会议拨入号码的列表。</span><span class="sxs-lookup"><span data-stu-id="10df6-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="10df6-186">已为你的组织设置[通信信用点数](what-are-communications-credits.md)（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="10df6-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="10df6-187">已识别和配置音频会议网桥设置（PIN 长度、进入/退出通知、启用通知首选项）。</span><span class="sxs-lookup"><span data-stu-id="10df6-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="10df6-188">已识别、配置和应用支持音频会议拨出方案的租户会议策略和拨号计划设置。</span><span class="sxs-lookup"><span data-stu-id="10df6-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="10df6-189">已确定和配置音频会议合规性要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="10df6-190">**针对范围内的用户和网站的通话计划测试先决条件和假设：**</span><span class="sxs-lookup"><span data-stu-id="10df6-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="10df6-191">已完成通话计划服务的业务使用案例定义。</span><span class="sxs-lookup"><span data-stu-id="10df6-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="10df6-192">通话计划所需的许可可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="10df6-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="10df6-193">已标识组织网站和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="10df6-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="10df6-194">要分配给用户的电话号码已获取或移植到 Microsoft，并且在租户门户中可用。</span><span class="sxs-lookup"><span data-stu-id="10df6-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="10df6-195">已为你的组织设置[通信信用点数](what-are-communications-credits.md)（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="10df6-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="10df6-196">已识别、配置和应用支持呼叫计划方案的租户用户策略和拨号计划设置。</span><span class="sxs-lookup"><span data-stu-id="10df6-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="10df6-197">已确定并配置了通话计划合规性要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="10df6-198">**作用域中的用户和网站的直接路由测试先决条件和假设：**</span><span class="sxs-lookup"><span data-stu-id="10df6-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="10df6-199">直接路由服务的企业使用案例定义已完成。</span><span class="sxs-lookup"><span data-stu-id="10df6-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="10df6-200">直接路由所需的许可可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="10df6-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="10df6-201">已标识组织网站和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="10df6-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="10df6-202">已[验证的会话边界控制器（SBC）](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)已部署、配置并与电话系统配对。</span><span class="sxs-lookup"><span data-stu-id="10df6-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="10df6-203">已启用企业语音，并且已分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="10df6-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="10df6-204">已确定、配置和分配语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="10df6-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="10df6-205">Microsoft 团队已被设置为范围内用户的首选呼叫客户端。</span><span class="sxs-lookup"><span data-stu-id="10df6-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="10df6-206">已确定并配置直接路由合规性要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="10df6-207">决策点</span><span class="sxs-lookup"><span data-stu-id="10df6-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="10df6-208">确定将部署哪些音频会议功能（服务决策）。</span><span class="sxs-lookup"><span data-stu-id="10df6-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="10df6-209">确定音频会议的用户功能要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="10df6-210">确定音频会议的服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="10df6-211">确定是否将部署和配置直接路由或呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="10df6-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="10df6-212">确定将部署哪些电话系统功能功能（服务决策）。</span><span class="sxs-lookup"><span data-stu-id="10df6-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="10df6-213">确定呼叫计划或直接路由的用户功能要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="10df6-214">确定呼叫计划或直接路由的服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="10df6-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="10df6-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="10df6-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="10df6-216">开发并记录你的测试计划方法。</span><span class="sxs-lookup"><span data-stu-id="10df6-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="10df6-217">准备您的服务环境和音频会议功能范围内的用户。</span><span class="sxs-lookup"><span data-stu-id="10df6-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="10df6-218">在 "呼叫计划" 或 "直接路由" 功能的范围内准备服务环境和用户。</span><span class="sxs-lookup"><span data-stu-id="10df6-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="10df6-219">对要启用的音频会议功能执行测试验证。</span><span class="sxs-lookup"><span data-stu-id="10df6-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="10df6-220">为要启用的呼叫计划或直接路由功能执行测试验证。</span><span class="sxs-lookup"><span data-stu-id="10df6-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="10df6-221">对于任何测试失败，请确认您的配置正确，查看社区文章，如果需要，还可以提出支持案例。</span><span class="sxs-lookup"><span data-stu-id="10df6-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="10df6-222">有关如何在团队中执行音频会议测试的更多详细指导，请参阅[音频会议的详细测试指南](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="10df6-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="10df6-223">有关如何针对团队中的通话计划执行测试的更多详细指导，请参阅[电话系统的详细测试指南](onboarding-test-plan-for-enterprises-Phone-System.md)。</span><span class="sxs-lookup"><span data-stu-id="10df6-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
