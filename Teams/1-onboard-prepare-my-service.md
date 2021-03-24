---
title: 准备部署云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用载入清单准备 Microsoft 365 或 Office 365 for Teams 并配置 Teams 核心功能、网络和云语音工作负荷。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103968"
---
# <a name="prepare-my-service"></a><span data-ttu-id="435fe-103">准备服务</span><span class="sxs-lookup"><span data-stu-id="435fe-103">Prepare my service</span></span>

<span data-ttu-id="435fe-104">本文概述了为组织准备云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="435fe-105">通过正确准备，你可以确保已准备好向组织提供云语音功能。</span><span class="sxs-lookup"><span data-stu-id="435fe-105">By preparing properly, you can be sure you're ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="435fe-106">载入 Microsoft Teams 语音工作负荷的清单</span><span class="sxs-lookup"><span data-stu-id="435fe-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="435fe-107">以下清单将引导你完成在 Microsoft Teams 中实现音频会议、具有呼叫计划的电话系统 ("呼叫计划") 和电话系统直接路由 ("直接路由") 功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="435fe-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans ("Calling Plans"), and Phone System Direct Routing ("Direct Routing") capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="435fe-108">准备 Microsoft 365 或 Office 365 for Teams</span><span class="sxs-lookup"><span data-stu-id="435fe-108">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="435fe-109">配置 Teams 核心功能</span><span class="sxs-lookup"><span data-stu-id="435fe-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="435fe-110">准备网络</span><span class="sxs-lookup"><span data-stu-id="435fe-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="435fe-111">在 Teams 中配置云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="435fe-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="435fe-112">在 Teams 中配置直接路由</span><span class="sxs-lookup"><span data-stu-id="435fe-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="435fe-113">这些清单中的任务和活动是核心的"任务"项目，适用于使用 Teams 部署云语音功能的每一项。</span><span class="sxs-lookup"><span data-stu-id="435fe-113">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="435fe-114">你可以自定义清单，以包含特定于你自己的 Teams 旅程的活动和任务。</span><span class="sxs-lookup"><span data-stu-id="435fe-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="435fe-115">本指南仅侧重于通话计划、音频会议和直接路由。</span><span class="sxs-lookup"><span data-stu-id="435fe-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="435fe-116">如果你是 Teams 的新人，请查看 [Microsoft Teams 概述](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="435fe-116">If you're new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="435fe-117">有关规划 Teams 部署的一般指南，请从在 Microsoft Teams 中部署聊天、团队、频道 [和应用开始](deploy-chat-teams-channels-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="435fe-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="435fe-118">使用提供的清单跟踪每个单独活动和任务的状态，并确保未跳过任何关键步骤。</span><span class="sxs-lookup"><span data-stu-id="435fe-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="435fe-119">每个活动包含所需操作的详细说明，并引用可用于完成该活动的其他信息。</span><span class="sxs-lookup"><span data-stu-id="435fe-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="435fe-120">尽管我们建议按顺序遵循清单，但确切顺序取决于部署范围和环境的配置和复杂性。</span><span class="sxs-lookup"><span data-stu-id="435fe-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="435fe-121">它们组织起来支持"绿地"Teams 部署 (之前没有 Skype for Business Online 状态的团队部署) 或者从 Skype for Business Online 迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="435fe-121">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="435fe-122">如果你正在从 Skype for Business Online 迁移，你可能已完成其中一些活动，现在可以忽略这些活动。</span><span class="sxs-lookup"><span data-stu-id="435fe-122">If you're migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="435fe-123">当您按网站载入用户时，强烈建议使用 [适用于 Voice (Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 的站点启用 Playbook) 作为这些清单的补充指南。</span><span class="sxs-lookup"><span data-stu-id="435fe-123">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="435fe-124">大多数配置设置在 Teams 和 Skype for Business Online 之间很常见。</span><span class="sxs-lookup"><span data-stu-id="435fe-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="435fe-125">使用 Microsoft 365 管理中心和 Microsoft Teams 管理中心配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="435fe-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="435fe-126">决策点</span><span class="sxs-lookup"><span data-stu-id="435fe-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="435fe-127">谁负责监督登记清单的完成情况？</span><span class="sxs-lookup"><span data-stu-id="435fe-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="435fe-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="435fe-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="435fe-129">下载载入清单。</span><span class="sxs-lookup"><span data-stu-id="435fe-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="435fe-130">根据组织的部署计划逐步完成登记清单项。</span><span class="sxs-lookup"><span data-stu-id="435fe-130">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="435fe-131">继续载入</span><span class="sxs-lookup"><span data-stu-id="435fe-131">Continue onboarding</span></span>

<span data-ttu-id="435fe-132">完成这些清单后，你已成功将语音功能添加到 Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="435fe-132">After you complete these checklists, you'll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="435fe-133">下一步，使用 [Voice (Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 网站启用 Playbook 来帮助你在每个网站上载入用户，并帮助确保你计划和执行重要的特定于网站的活动。</span><span class="sxs-lookup"><span data-stu-id="435fe-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="435fe-134">就绪的站点按站点推出计划</span><span class="sxs-lookup"><span data-stu-id="435fe-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="435fe-135">建立服务管理流程</span><span class="sxs-lookup"><span data-stu-id="435fe-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="435fe-136">执行测试和修正</span><span class="sxs-lookup"><span data-stu-id="435fe-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="435fe-137">在 Teams 中测试云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="435fe-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="435fe-138">在"构想"阶段中定义并记录 Teams 云语音业务成功和技术实施计划并采用所需的配置后，下一步是验证通过功能、功能和可用性满足组织的期望和要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-138">After you've defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization's expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="435fe-139">在生产环境中部署试点或最终部署之前，应执行此验证步骤。</span><span class="sxs-lookup"><span data-stu-id="435fe-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="435fe-140">可以利用在"构想"阶段定义的业务成功计划，作为确定在测试阶段要评估的活动、预期、功能/功能测试用例和总体范围的基础。</span><span class="sxs-lookup"><span data-stu-id="435fe-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="435fe-141">定义测试方法</span><span class="sxs-lookup"><span data-stu-id="435fe-141">Define your testing approach</span></span>

<span data-ttu-id="435fe-142">最简单的测试方法基于你查看音频会议、呼叫计划或直接路由服务的功能，并开发一个测试计划来验证你的功能要求是否满足范围内用户的要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="435fe-143">下面是音频会议实现载入阶段的示例测试计划。</span><span class="sxs-lookup"><span data-stu-id="435fe-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="435fe-144">要测试的音频会议功能</span><span class="sxs-lookup"><span data-stu-id="435fe-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="435fe-145">结果摘要</span><span class="sxs-lookup"><span data-stu-id="435fe-145">Results summary</span></span> | <span data-ttu-id="435fe-146">其他说明</span><span class="sxs-lookup"><span data-stu-id="435fe-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="435fe-147">安排包含音频会议拨入信息临时 Teams 会议</span><span class="sxs-lookup"><span data-stu-id="435fe-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="435fe-148">通过/失败</span><span class="sxs-lookup"><span data-stu-id="435fe-148">Pass/Fail</span></span>   | <span data-ttu-id="435fe-149">TBD</span><span class="sxs-lookup"><span data-stu-id="435fe-149">TBD</span></span> |
| <span data-ttu-id="435fe-150">使用电话从 PSTN 拨入会议，并使用提供的拨入信息拨入音频</span><span class="sxs-lookup"><span data-stu-id="435fe-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="435fe-151">通过/失败</span><span class="sxs-lookup"><span data-stu-id="435fe-151">Pass/Fail</span></span> | <span data-ttu-id="435fe-152">TBD</span><span class="sxs-lookup"><span data-stu-id="435fe-152">TBD</span></span> |
| <span data-ttu-id="435fe-153">通过 PSTN 拨出将其他人加入现有会议</span><span class="sxs-lookup"><span data-stu-id="435fe-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="435fe-154">通过/失败</span><span class="sxs-lookup"><span data-stu-id="435fe-154">Pass/Fail</span></span> | <span data-ttu-id="435fe-155">TBD</span><span class="sxs-lookup"><span data-stu-id="435fe-155">TBD</span></span> |



| <span data-ttu-id="435fe-156">要测试的调用计划或直接路由功能</span><span class="sxs-lookup"><span data-stu-id="435fe-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="435fe-157">结果摘要</span><span class="sxs-lookup"><span data-stu-id="435fe-157">Results summary</span></span> | <span data-ttu-id="435fe-158">其他说明</span><span class="sxs-lookup"><span data-stu-id="435fe-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="435fe-159">通过拨打 PSTN 号码进行 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="435fe-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="435fe-160">通过/失败</span><span class="sxs-lookup"><span data-stu-id="435fe-160">Pass/Fail</span></span>       | <span data-ttu-id="435fe-161">TBD</span><span class="sxs-lookup"><span data-stu-id="435fe-161">TBD</span></span> |
| <span data-ttu-id="435fe-162">通过从外部线路拨打 PSTN 号码以接收 PSTN 呼叫 (移动、座机) </span><span class="sxs-lookup"><span data-stu-id="435fe-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="435fe-163">通过/失败</span><span class="sxs-lookup"><span data-stu-id="435fe-163">Pass/Fail</span></span> | <span data-ttu-id="435fe-164">TBD</span><span class="sxs-lookup"><span data-stu-id="435fe-164">TBD</span></span>|
| <span data-ttu-id="435fe-165">将 PSTN 呼叫从一个 Teams 用户转移到另一个 Teams 用户</span><span class="sxs-lookup"><span data-stu-id="435fe-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="435fe-166">通过/失败</span><span class="sxs-lookup"><span data-stu-id="435fe-166">Pass/Fail</span></span> | <span data-ttu-id="435fe-167">TBD</span><span class="sxs-lookup"><span data-stu-id="435fe-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="435fe-168">若要从创建测试用例开始，请参阅 Teams 会议和通话中提供的用户 [指南列表](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。</span><span class="sxs-lookup"><span data-stu-id="435fe-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="435fe-169">为 Teams 设置云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="435fe-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="435fe-170">定义测试方法后，下一步是在 Teams 云语音功能范围内配置服务环境和用户。</span><span class="sxs-lookup"><span data-stu-id="435fe-170">Now that you've defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="435fe-171">有关其他信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="435fe-171">For additional information, see:</span></span>

- [<span data-ttu-id="435fe-172">音频会议的技术规划</span><span class="sxs-lookup"><span data-stu-id="435fe-172">Technical Planning for Audio Conferencing</span></span>](./cloud-voice-landing-page.md)

- [<span data-ttu-id="435fe-173">设置 Microsoft Teams 的音频会议</span><span class="sxs-lookup"><span data-stu-id="435fe-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="435fe-174">使用呼叫计划对电话系统进行技术规划</span><span class="sxs-lookup"><span data-stu-id="435fe-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="435fe-175">为 Skype for Business 和 Microsoft Teams 设置通话计划</span><span class="sxs-lookup"><span data-stu-id="435fe-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="435fe-176">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="435fe-176">Plan Direct Routing</span></span>](./direct-routing-plan.md)

- [<span data-ttu-id="435fe-177">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="435fe-177">Configure Direct Routing</span></span>](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a><span data-ttu-id="435fe-178">执行测试计划</span><span class="sxs-lookup"><span data-stu-id="435fe-178">Execute the test plan</span></span>

[//]: # (编辑好吗？"用户"似乎有点不明确。)
<span data-ttu-id="435fe-180">配置用户环境和服务后，最后一个测试步骤包括测试计划执行，并侧重于特性和功能验证。</span><span class="sxs-lookup"><span data-stu-id="435fe-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="435fe-181">**音频会议测试针对范围中的用户和网站的先决条件和假设：**</span><span class="sxs-lookup"><span data-stu-id="435fe-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="435fe-182">音频会议服务的业务用例定义已完成。</span><span class="sxs-lookup"><span data-stu-id="435fe-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="435fe-183">音频会议所需的许可可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="435fe-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="435fe-184">已标识组织站点和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="435fe-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="435fe-185">已标识并配置具有语言首选项的专用和共享音频会议拨入号码列表。</span><span class="sxs-lookup"><span data-stu-id="435fe-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="435fe-186">[如果需要 (，) ](what-are-communications-credits.md) 为组织设置通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="435fe-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="435fe-187">音频会议会议网桥设置已识别并 (PIN 长度、进入/退出通知、启用通知首选项) 。</span><span class="sxs-lookup"><span data-stu-id="435fe-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="435fe-188">已标识、配置和应用支持音频会议拨出方案的租户会议策略和拨号计划设置。</span><span class="sxs-lookup"><span data-stu-id="435fe-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="435fe-189">已标识并配置音频会议符合性要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="435fe-190">**调用计划测试范围内用户和网站的先决条件和假设：**</span><span class="sxs-lookup"><span data-stu-id="435fe-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="435fe-191">呼叫计划服务的业务用例定义已完成。</span><span class="sxs-lookup"><span data-stu-id="435fe-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="435fe-192">呼叫计划所需的许可可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="435fe-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="435fe-193">已标识组织站点和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="435fe-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="435fe-194">要分配给用户的电话号码已获取或移植到 Microsoft，可在租户门户中获取。</span><span class="sxs-lookup"><span data-stu-id="435fe-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="435fe-195">[如果需要 (，) ](what-are-communications-credits.md) 为组织设置通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="435fe-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="435fe-196">已标识、配置和应用支持呼叫计划的租户用户策略和拨号计划设置。</span><span class="sxs-lookup"><span data-stu-id="435fe-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="435fe-197">已标识并配置调用计划符合性要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="435fe-198">**用户和站点在范围内直接路由测试先决条件和假设：**</span><span class="sxs-lookup"><span data-stu-id="435fe-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="435fe-199">已完成直接路由服务的业务用例定义。</span><span class="sxs-lookup"><span data-stu-id="435fe-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="435fe-200">直接路由所需的许可可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="435fe-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="435fe-201">已标识组织站点和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="435fe-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="435fe-202">已 [部署、配置 (SBC ](./direct-routing-plan.md#supported-session-border-controllers-sbcs)) 且已与电话系统配对的经认证的会话边界控制器。</span><span class="sxs-lookup"><span data-stu-id="435fe-202">A [certified session border controller (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="435fe-203">已启用企业语音，并且已分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="435fe-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="435fe-204">已标识、配置和分配语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="435fe-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="435fe-205">Microsoft Teams 已设置为范围内用户的首选呼叫客户端。</span><span class="sxs-lookup"><span data-stu-id="435fe-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="435fe-206">已标识并配置直接路由符合性要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="435fe-207">决策点</span><span class="sxs-lookup"><span data-stu-id="435fe-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="435fe-208">确定将部署哪些音频会议功能 (服务决策) 。</span><span class="sxs-lookup"><span data-stu-id="435fe-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="435fe-209">确定音频会议的用户功能要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="435fe-210">确定音频会议的服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="435fe-211">确定是否部署和配置直接路由或呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="435fe-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="435fe-212">决定在服务决策中部署哪些电话 (功能) 。</span><span class="sxs-lookup"><span data-stu-id="435fe-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="435fe-213">确定调用计划或直接路由的用户功能要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="435fe-214">确定调用计划或直接路由的服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="435fe-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="435fe-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="435fe-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="435fe-216">开发和记录测试计划方法。</span><span class="sxs-lookup"><span data-stu-id="435fe-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="435fe-217">在音频会议功能的范围内准备服务环境和用户。</span><span class="sxs-lookup"><span data-stu-id="435fe-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="435fe-218">在调用计划或直接路由功能的范围内准备服务环境和用户。</span><span class="sxs-lookup"><span data-stu-id="435fe-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="435fe-219">对要启用的音频会议功能执行测试验证。</span><span class="sxs-lookup"><span data-stu-id="435fe-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="435fe-220">对要启用的呼叫计划或直接路由功能执行测试验证。</span><span class="sxs-lookup"><span data-stu-id="435fe-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="435fe-221">对于任何测试失败，请确认配置是否正确，查看社区文章，并（如果需要）提出支持案例。</span><span class="sxs-lookup"><span data-stu-id="435fe-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="435fe-222">有关如何在 Teams 中执行音频会议测试的其他详细指南，请参阅 [音频会议的详细测试指南](./deploy-audio-conferencing-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="435fe-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](./deploy-audio-conferencing-teams-landing-page.md).</span></span>

<span data-ttu-id="435fe-223">有关如何在 Teams 中执行通话计划测试的其他详细指南，请参阅 [电话系统的详细测试指南](./cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="435fe-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](./cloud-voice-landing-page.md).</span></span>

<!--ENDOFSECTION-->