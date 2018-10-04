---
title: 准备部署的 Microsoft 团队云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用入职培训清单团队准备 Office 365 和配置团队的核心功能，网络，和云语音工作负荷。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 335d5baac6f13d899b8d6f9875a419d86da1b6af
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374314"
---
# <a name="prepare-my-service"></a><span data-ttu-id="4ae0a-103">准备我的服务</span><span class="sxs-lookup"><span data-stu-id="4ae0a-103">Prepare my service</span></span>

<span data-ttu-id="4ae0a-104">本文概述了准备云的组织的语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="4ae0a-105">通过正确准备，您可以确保您已准备好提供语音功能延伸到您的组织的云。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="4ae0a-106">Microsoft 团队入职培训清单语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="4ae0a-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="4ae0a-107">以下清单可指导您完成 Microsoft 团队中实现音频会议，调用计划 （"调用计划"），与电话系统直接路由 （"直接路由"） 的功能电话系统的步骤。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="4ae0a-108">Office 365 准备团队</span><span class="sxs-lookup"><span data-stu-id="4ae0a-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="4ae0a-109">配置团队的核心功能</span><span class="sxs-lookup"><span data-stu-id="4ae0a-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="4ae0a-110">配置网络</span><span class="sxs-lookup"><span data-stu-id="4ae0a-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="4ae0a-111">在工作组中配置云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="4ae0a-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="4ae0a-112">配置直接路由团队</span><span class="sxs-lookup"><span data-stu-id="4ae0a-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="4ae0a-113">任务和这些清单中的活动是"核心待办事项"适用于云与团队的语音功能的每个部署。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="4ae0a-114">您可以自定义要包含的活动和特定于您自己团队旅程的任务的清单。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="4ae0a-115">本指南重点在于调用计划、 音频会议和直接路由。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="4ae0a-116">如果您熟悉向工作组，请查看[Microsoft 团队概述](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="4ae0a-117">规划团队部署的一般指导，请参阅[Microsoft 团队规划指南](quick-start-enable-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-117">For general guidance for planning your Teams deployment, see the [Microsoft Teams Planning Guide](quick-start-enable-teams.md).</span></span>

<span data-ttu-id="4ae0a-118">使用提供的清单来跟踪的每个单独的活动和任务，状态，以确保您没有跳过任何关键的步骤。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="4ae0a-119">每个活动包括所需的操作和可用于完成了该活动的其他信息的引用的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="4ae0a-120">虽然我们建议您按照顺序清单，准确的顺序将取决于您的部署和配置的范围和您的环境的复杂性。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="4ae0a-121">它们组织以支持"全新"工作组 （一个业务联机状态的任何以前 Skype） 部署或从 Skype 业务 online 迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="4ae0a-122">如果您正在从 Skype 业务 online 迁移内容，您可能已经完成一些这些活动，并可以忽略它们现在。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="4ae0a-123">按每个站点的入职培训用户时，我们强烈建议[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)使用这些清单的补充指南作为。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="4ae0a-124">常见团队和 Skype 业务 online 之间了大部分的配置设置。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="4ae0a-125">使用 Office 365 管理中心和团队和业务管理中心的 Skype 配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-125">You use the Office 365 Admin Center and Teams & Skype for Business Admin Center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="4ae0a-126">决策点</span><span class="sxs-lookup"><span data-stu-id="4ae0a-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="4ae0a-127">谁将负责监督入职培训清单完成？</span><span class="sxs-lookup"><span data-stu-id="4ae0a-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="4ae0a-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4ae0a-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="4ae0a-129">下载入职培训清单。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="4ae0a-130">通过按照贵组织的部署计划分步入职培训清单项目工作。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="4ae0a-131">继续入职培训</span><span class="sxs-lookup"><span data-stu-id="4ae0a-131">Continue onboarding</span></span>

<span data-ttu-id="4ae0a-132">完成这些清单后，将已成功添加语音功能延伸到您的团队部署。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="4ae0a-133">在下一步，使用[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)可帮助您加载您的用户在每个站点，并帮助确保您规划和执行特定于网站的重要活动。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="4ae0a-134">准备网站由网站推出计划</span><span class="sxs-lookup"><span data-stu-id="4ae0a-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="4ae0a-135">建立服务管理流程</span><span class="sxs-lookup"><span data-stu-id="4ae0a-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="4ae0a-136">执行测试和修正</span><span class="sxs-lookup"><span data-stu-id="4ae0a-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="4ae0a-137">团队中的测试云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="4ae0a-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="4ae0a-138">已定义和作为构想阶段的一部分中记录您的团队云语音业务成功和技术实现规划和执行所需在管理中心的配置后下, 一步是验证您的组织通过功能、 功能和可用性满足期望和要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="4ae0a-139">在生产环境中部署的试验或最终部署之前，应执行以下验证步骤。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="4ae0a-140">您可以利用您定义的阶段构想用作确定活动、 期望、 功能/功能测试用例和总体范围测试阶段进行求值的基础业务成功计划。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="4ae0a-141">定义您的测试方法</span><span class="sxs-lookup"><span data-stu-id="4ae0a-141">Define your testing approach</span></span>

<span data-ttu-id="4ae0a-142">简单的形式，测试方法根据您查看的音频会议，调用计划的功能或直接路由服务和开发测试计划验证功能要求满足范围中的用户。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="4ae0a-143">下面是针对音频会议实现的板载阶段的示例测试计划。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="4ae0a-144">要测试的音频会议功能</span><span class="sxs-lookup"><span data-stu-id="4ae0a-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="4ae0a-145">结果摘要</span><span class="sxs-lookup"><span data-stu-id="4ae0a-145">Results summary</span></span> | <span data-ttu-id="4ae0a-146">其他注释</span><span class="sxs-lookup"><span data-stu-id="4ae0a-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="4ae0a-147">包含信息电话拨入式音频会议的安排即席团队会议</span><span class="sxs-lookup"><span data-stu-id="4ae0a-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="4ae0a-148">通过/失败</span><span class="sxs-lookup"><span data-stu-id="4ae0a-148">Pass/Fail</span></span>   | <span data-ttu-id="4ae0a-149">TBD</span><span class="sxs-lookup"><span data-stu-id="4ae0a-149">TBD</span></span> |
| <span data-ttu-id="4ae0a-150">用于电话拨入从 PSTN 会议音频会议提供的电话拨入式信息</span><span class="sxs-lookup"><span data-stu-id="4ae0a-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="4ae0a-151">通过/失败</span><span class="sxs-lookup"><span data-stu-id="4ae0a-151">Pass/Fail</span></span> | <span data-ttu-id="4ae0a-152">TBD</span><span class="sxs-lookup"><span data-stu-id="4ae0a-152">TBD</span></span> |
| <span data-ttu-id="4ae0a-153">通过 PSTN 拨出其他人加入现有会议</span><span class="sxs-lookup"><span data-stu-id="4ae0a-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="4ae0a-154">通过/失败</span><span class="sxs-lookup"><span data-stu-id="4ae0a-154">Pass/Fail</span></span> | <span data-ttu-id="4ae0a-155">TBD</span><span class="sxs-lookup"><span data-stu-id="4ae0a-155">TBD</span></span> |



| <span data-ttu-id="4ae0a-156">呼叫计划或直接路由功能测试</span><span class="sxs-lookup"><span data-stu-id="4ae0a-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="4ae0a-157">结果摘要</span><span class="sxs-lookup"><span data-stu-id="4ae0a-157">Results summary</span></span> | <span data-ttu-id="4ae0a-158">其他注释</span><span class="sxs-lookup"><span data-stu-id="4ae0a-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="4ae0a-159">拨入 PSTN 号码发起 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4ae0a-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="4ae0a-160">通过/失败</span><span class="sxs-lookup"><span data-stu-id="4ae0a-160">Pass/Fail</span></span>       | <span data-ttu-id="4ae0a-161">TBD</span><span class="sxs-lookup"><span data-stu-id="4ae0a-161">TBD</span></span> |
| <span data-ttu-id="4ae0a-162">通过拨打您从外部行 （移动固定电话） 的 PSTN 号码收到 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4ae0a-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="4ae0a-163">通过/失败</span><span class="sxs-lookup"><span data-stu-id="4ae0a-163">Pass/Fail</span></span> | <span data-ttu-id="4ae0a-164">TBD</span><span class="sxs-lookup"><span data-stu-id="4ae0a-164">TBD</span></span>|
| <span data-ttu-id="4ae0a-165">转接到另一个团队用户从 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4ae0a-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="4ae0a-166">通过/失败</span><span class="sxs-lookup"><span data-stu-id="4ae0a-166">Pass/Fail</span></span> | <span data-ttu-id="4ae0a-167">TBD</span><span class="sxs-lookup"><span data-stu-id="4ae0a-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="4ae0a-168">为了帮助作为起点的测试用例创建，请参阅的用户指南 》[团队会议和呼叫](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)列表。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="4ae0a-169">设置团队云语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="4ae0a-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="4ae0a-170">既然已定义测试方法下, 一步配置您的服务环境和用户团队云语音功能的范围内。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="4ae0a-171">有关其他信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="4ae0a-171">For additional information, see:</span></span>

- [<span data-ttu-id="4ae0a-172">音频会议技术规划</span><span class="sxs-lookup"><span data-stu-id="4ae0a-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="4ae0a-173">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="4ae0a-173">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [<span data-ttu-id="4ae0a-174">技术规划调用计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="4ae0a-174">Technical Planning for Phone System with Calling Plans</span></span>](phone-system-with-calling-plans.md#technical-planning-for-phone-system-with-calling-plans)

- [<span data-ttu-id="4ae0a-175">调用计划为设置 Skype 业务和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="4ae0a-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="4ae0a-176">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="4ae0a-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="4ae0a-177">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="4ae0a-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="4ae0a-178">执行测试计划</span><span class="sxs-lookup"><span data-stu-id="4ae0a-178">Execute the test plan</span></span>

[//]: # (好了编辑？"User"看起来有点不明确给我。)
<span data-ttu-id="4ae0a-180">已配置的用户环境和服务后，测试的最后一步将包括具有焦点的功能及功能验证测试计划执行。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="4ae0a-181">**测试先决条件和假设条件的用户和网站范围内的音频会议：**</span><span class="sxs-lookup"><span data-stu-id="4ae0a-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="4ae0a-182">业务案例定义用于音频会议服务已完成。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="4ae0a-183">许可音频会议所需的可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="4ae0a-184">已发现的组织的站点和用户组列表。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="4ae0a-185">已标识并配置专用和共享的音频会议电话拨入式号码语言首选项的列表。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="4ae0a-186">[Communications 字幕式](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已为组织设置。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-186">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="4ae0a-187">音频会议的会议桥设置已标识和配置 （PIN 长度、 条目/退出通知启用通知首选项）。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="4ae0a-188">租户会议策略和拨号计划支持音频会议拨出方案具有标识、 配置和应用的设置。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="4ae0a-189">已标识和配置音频会议合规性要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="4ae0a-190">**调用测试先决条件和假设条件的用户和网站范围内的计划：**</span><span class="sxs-lookup"><span data-stu-id="4ae0a-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="4ae0a-191">商业调用计划已完成服务的使用案例定义。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="4ae0a-192">许可所需的调用计划可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="4ae0a-193">已发现的组织的站点和用户组列表。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="4ae0a-194">已获得或移植到 Microsoft 和租户门户中提供有要分配给用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="4ae0a-195">[Communications 字幕式](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已为组织设置。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-195">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="4ae0a-196">租户用户策略和拨号计划设置支持调用计划方案具有已标识、 配置，并应用。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="4ae0a-197">调用计划已标识和配置合规性要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="4ae0a-198">**测试先决条件和假设条件的用户和网站范围内的直接路由：**</span><span class="sxs-lookup"><span data-stu-id="4ae0a-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="4ae0a-199">业务直接路由服务已完成的使用案例定义。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="4ae0a-200">许可所需的直接路由中可用，并已分配。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="4ae0a-201">已发现的组织的站点和用户组列表。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="4ae0a-202">[认证的会话边界控制器 (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)已部署、 配置并与电话系统配对。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="4ae0a-203">已启用企业语音，且已分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="4ae0a-204">语音路由策略已标识、 配置和分配。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="4ae0a-205">在范围内，Microsoft 团队已被设为首选调用客户端的用户。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="4ae0a-206">已标识和配置直接路由合规性要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="4ae0a-207">决策点</span><span class="sxs-lookup"><span data-stu-id="4ae0a-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="4ae0a-208">决定将部署的音频会议功能 （服务决策）。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="4ae0a-209">确定用户音频会议功能要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="4ae0a-210">确定要进行音频会议服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="4ae0a-211">决定是否将部署并配置了直接路由或调用计划。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="4ae0a-212">决定将部署哪些电话系统的功能 （服务决策）。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="4ae0a-213">确定用户调用计划或直接路由的功能要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="4ae0a-214">标识调用计划或直接路由服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="4ae0a-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4ae0a-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="4ae0a-216">开发和测试计划方法的文档。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="4ae0a-217">准备您的服务环境和音频会议功能的范围内的用户。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="4ae0a-218">准备您的服务环境和调用计划或直接路由功能范围中的用户。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="4ae0a-219">执行测试验证您想要启用的音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="4ae0a-220">执行测试验证您想要启用的调用计划或直接路由功能。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="4ae0a-221">出于测试故障，确认您的配置是否正确，请查看社区文章和 — 如果需要 — 引发支持案例。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="4ae0a-222">有关如何执行测试团队中的音频会议的其他详细指导信息，请参阅[详细测试音频会议的指南](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="4ae0a-223">有关如何执行测试呼叫的团队中计划的其他详细指导信息，请参阅[详细测试的电话系统的指南](onboarding-test-plan-for-enterprises-Phone-System.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae0a-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
