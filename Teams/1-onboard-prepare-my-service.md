---
title: 准备部署 Microsoft 小组云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 使用板载清单为小组准备 Office 365 和配置团队核心功能，网络，和云语音工作负载。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2b3d68d63661c988116f3b6729656eb3f34cf37
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="prepare-my-service"></a><span data-ttu-id="35d43-103">准备我的服务</span><span class="sxs-lookup"><span data-stu-id="35d43-103">Prepare my service</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="35d43-104">针对 Microsoft 小组语音工作负载的服务清单</span><span class="sxs-lookup"><span data-stu-id="35d43-104">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="35d43-105">下列清单将逐步实现与 Microsoft 小组中调用计划功能的音频会议和电话系统的步骤。</span><span class="sxs-lookup"><span data-stu-id="35d43-105">The following checklists walk you through the steps for implementing Audio Conferencing and Phone System with Calling Plans capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="35d43-106">Office 365 准备团队</span><span class="sxs-lookup"><span data-stu-id="35d43-106">Prepare Office 365 for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [<span data-ttu-id="35d43-107">配置团队核心能力</span><span class="sxs-lookup"><span data-stu-id="35d43-107">Configure Teams core capabilities</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [<span data-ttu-id="35d43-108">配置网络</span><span class="sxs-lookup"><span data-stu-id="35d43-108">Configure networking</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [<span data-ttu-id="35d43-109">在团队中配置云语音工作负载</span><span class="sxs-lookup"><span data-stu-id="35d43-109">Configure cloud voice workloads in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

<span data-ttu-id="35d43-110">任务和这些检查表中的活动是应用于每个部署的云语音功能与团队的核心"待办事项"项目。</span><span class="sxs-lookup"><span data-stu-id="35d43-110">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="35d43-111">您可以自定义要包含的活动和特定于自己团队之旅的任务的清单。</span><span class="sxs-lookup"><span data-stu-id="35d43-111">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="35d43-112">本指南重点介绍仅调用计划和音频会议电话系统。</span><span class="sxs-lookup"><span data-stu-id="35d43-112">This guidance focuses solely on Phone System with Calling Plans and Audio Conferencing.</span></span> <span data-ttu-id="35d43-113">如果您是初次接触小组，检查[Microsoft 小组概述](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。</span><span class="sxs-lookup"><span data-stu-id="35d43-113">If you’re new to Teams, review [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> <span data-ttu-id="35d43-114">规划团队部署的一般准则，请参见[Microsoft 小组规划指南](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams)。</span><span class="sxs-lookup"><span data-stu-id="35d43-114">For general guidance for planning your Teams deployment, see the [Microsoft Teams Planning Guide](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams).</span></span>

<span data-ttu-id="35d43-115">使用提供的检查表来跟踪状态的每个单独的活动和任务，并确保没有跳过任何重要的步骤。</span><span class="sxs-lookup"><span data-stu-id="35d43-115">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="35d43-116">每个活动都包括所需的操作，并参考其他信息可用来完成该活动的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="35d43-116">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="35d43-117">但我们建议您按照顺序清单，准确的顺序将取决于您的部署和配置的范围和复杂环境中。</span><span class="sxs-lookup"><span data-stu-id="35d43-117">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="35d43-118">他们正在组织以支持"全新"团队部署 （一个没有以前 Skype 业务联机状态） 或从 Skype 的在线业务迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="35d43-118">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="35d43-119">如果您正在从 Skype 的在线业务迁移内容，您可能已经完成一些这样的活动，并可以忽略它们现在。</span><span class="sxs-lookup"><span data-stu-id="35d43-119">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="35d43-120">后服务用户在每个站点的基础上，我们强烈建议您为这些检查表的补充指南使用[站点支持行动手册 （手册） 的声音](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="35d43-120">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="35d43-121">大多数配置设置共有之间团队和 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="35d43-121">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="35d43-122">Office 365 Skype 业务管理中心的用于配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="35d43-122">You use Office 365 Skype for Business Administration Center to configure those settings.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="35d43-123">决策点</span><span class="sxs-lookup"><span data-stu-id="35d43-123">Decision points</span></span></td><td><ul><li><span data-ttu-id="35d43-124">谁将负责监督服务清单的完成？</span><span class="sxs-lookup"><span data-stu-id="35d43-124">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="35d43-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35d43-125">Next steps</span></span></td><td><ul><li><span data-ttu-id="35d43-126">下载的服务清单。</span><span class="sxs-lookup"><span data-stu-id="35d43-126">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="35d43-127">通过板载的核对清单项逐步根据您的组织部署计划而工作。</span><span class="sxs-lookup"><span data-stu-id="35d43-127">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="35d43-128">继续服务</span><span class="sxs-lookup"><span data-stu-id="35d43-128">Continue onboarding</span></span>

<span data-ttu-id="35d43-129">在完成此清单后，将成功添加语音功能为您的团队部署。</span><span class="sxs-lookup"><span data-stu-id="35d43-129">After you complete this checklist, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="35d43-130">作为下一步，使用[语音 （手册） 的网站支持行动手册](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)帮助您板载在每个站点上，您的用户，并帮助确保您规划和执行特定于站点的重要活动。</span><span class="sxs-lookup"><span data-stu-id="35d43-130">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="35d43-131">可以通过在站点首展计划</span><span class="sxs-lookup"><span data-stu-id="35d43-131">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="35d43-132">建立服务管理流程</span><span class="sxs-lookup"><span data-stu-id="35d43-132">Establish Service Management Process</span></span>

-   <span data-ttu-id="35d43-133">执行测试和修正</span><span class="sxs-lookup"><span data-stu-id="35d43-133">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="35d43-134">在团队中测试云语音工作负载</span><span class="sxs-lookup"><span data-stu-id="35d43-134">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="35d43-135">已经定义和记录您的团队云语音业务成功和技术实施计划构想阶段的一部分，并采取在管理中心所需的配置后下, 一步是验证您的组织通过特征、 功能性和易用性满足的期望和要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-135">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="35d43-136">试验或最终部署在生产环境中部署之前，您应该执行此验证步骤。</span><span class="sxs-lookup"><span data-stu-id="35d43-136">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="35d43-137">您可以利用业务成功计划构想阶段，作为确定活动、 期望、 特性/功能的测试用例和总体范围的测试阶段进行评估的基础定义。</span><span class="sxs-lookup"><span data-stu-id="35d43-137">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="35d43-138">定义测试方法</span><span class="sxs-lookup"><span data-stu-id="35d43-138">Define your testing approach</span></span>

<span data-ttu-id="35d43-139">在最简单的形式，测试方法基于作用域中的用户在满足音频会议或电话系统的功能功能调用计划服务和开发测试计划，验证功能要求您审阅。</span><span class="sxs-lookup"><span data-stu-id="35d43-139">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing or Phone System with Calling Plans service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="35d43-140">以下是一个示例测试计划板载音频会议实施的阶段。</span><span class="sxs-lookup"><span data-stu-id="35d43-140">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>

| <span data-ttu-id="35d43-141">音频会议功能测试</span><span class="sxs-lookup"><span data-stu-id="35d43-141">Audio Conferencing feature to test</span></span> | <span data-ttu-id="35d43-142">结果摘要</span><span class="sxs-lookup"><span data-stu-id="35d43-142">Results summary</span></span> | <span data-ttu-id="35d43-143">附加注释</span><span class="sxs-lookup"><span data-stu-id="35d43-143">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="35d43-144">计划特别小组会议，包含音频会议拨入信息</span><span class="sxs-lookup"><span data-stu-id="35d43-144">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="35d43-145">通过/失败</span><span class="sxs-lookup"><span data-stu-id="35d43-145">Pass/Fail</span></span>   | <span data-ttu-id="35d43-146">待定</span><span class="sxs-lookup"><span data-stu-id="35d43-146">TBD</span></span> |
| <span data-ttu-id="35d43-147">用于电话拨入从 PSTN 会议音频会议提供的拨号信息</span><span class="sxs-lookup"><span data-stu-id="35d43-147">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="35d43-148">通过/失败</span><span class="sxs-lookup"><span data-stu-id="35d43-148">Pass/Fail</span></span> | <span data-ttu-id="35d43-149">待定</span><span class="sxs-lookup"><span data-stu-id="35d43-149">TBD</span></span> |
| <span data-ttu-id="35d43-150">通过 PSTN 拨出其他人加入现有会议</span><span class="sxs-lookup"><span data-stu-id="35d43-150">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="35d43-151">通过/失败</span><span class="sxs-lookup"><span data-stu-id="35d43-151">Pass/Fail</span></span> | <span data-ttu-id="35d43-152">待定</span><span class="sxs-lookup"><span data-stu-id="35d43-152">TBD</span></span> |


| <span data-ttu-id="35d43-153">通过调用计划功能的电话系统可供测试</span><span class="sxs-lookup"><span data-stu-id="35d43-153">Phone System with Calling Plans feature to test</span></span> | <span data-ttu-id="35d43-154">结果摘要</span><span class="sxs-lookup"><span data-stu-id="35d43-154">Results summary</span></span> | <span data-ttu-id="35d43-155">附加注释</span><span class="sxs-lookup"><span data-stu-id="35d43-155">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="35d43-156">进行到 PSTN 呼叫 PSTN 拨号</span><span class="sxs-lookup"><span data-stu-id="35d43-156">Make a PSTN call to by dialing a PSTN number</span></span>       | <span data-ttu-id="35d43-157">通过/失败</span><span class="sxs-lookup"><span data-stu-id="35d43-157">Pass/Fail</span></span>       | <span data-ttu-id="35d43-158">待定</span><span class="sxs-lookup"><span data-stu-id="35d43-158">TBD</span></span> |
| <span data-ttu-id="35d43-159">拨入您从外部行 （移动，固定） 的 PSTN 号码接收 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="35d43-159">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="35d43-160">通过/失败</span><span class="sxs-lookup"><span data-stu-id="35d43-160">Pass/Fail</span></span> | <span data-ttu-id="35d43-161">待定</span><span class="sxs-lookup"><span data-stu-id="35d43-161">TBD</span></span>|
|<span data-ttu-id="35d43-162">将从一组用户 PSTN 呼叫转接到另一个</span><span class="sxs-lookup"><span data-stu-id="35d43-162">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="35d43-163">通过/失败</span><span class="sxs-lookup"><span data-stu-id="35d43-163">Pass/Fail</span></span> | <span data-ttu-id="35d43-164">待定</span><span class="sxs-lookup"><span data-stu-id="35d43-164">TBD</span></span> |


>[!TIP]
><span data-ttu-id="35d43-165">为了帮助作为起始点的测试用例创建，请参阅音频会议用户指南可在[团队会议和调用](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings)的列表。</span><span class="sxs-lookup"><span data-stu-id="35d43-165">To assist with test-case creation as a starting point, see the list of audio conferencing user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="35d43-166">为团队设置了云语音工作负载</span><span class="sxs-lookup"><span data-stu-id="35d43-166">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="35d43-167">现在，您已经定义了测试方法下, 一步配置您的服务环境和用户小组云语音功能的范围内。</span><span class="sxs-lookup"><span data-stu-id="35d43-167">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span> <span data-ttu-id="35d43-168">有关其他信息，请参阅[音频会议技术规划](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing)和[设置音频会议的 Skype 业务和 Microsoft 小组](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)以及[技术系统规划的电话与调用计划](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans)和[集Skype 的通话方案，为业务和 Microsoft 小组](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="35d43-168">For additional information, see [Technical Planning for Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing) and [Set up Audio Conferencing for Skype for Business and Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) in addition to [Technical Planning for Phone System with Calling Plans](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans) and [Set up Calling Plans for Skype for Business and Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)</span></span>

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a><span data-ttu-id="35d43-169">执行测试计划</span><span class="sxs-lookup"><span data-stu-id="35d43-169">Execute the test plan</span></span>

<span data-ttu-id="35d43-170">在配置用户和音频会议服务环境后，测试的最后一步包括重点放在功能验证执行的测试计划。</span><span class="sxs-lookup"><span data-stu-id="35d43-170">After the user and audio conferencing service environments have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="35d43-171">**音频会议系统必备组件和用户和站点的假设测试范围内：**</span><span class="sxs-lookup"><span data-stu-id="35d43-171">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="35d43-172">业务案例定义用于音频会议服务已完成。</span><span class="sxs-lookup"><span data-stu-id="35d43-172">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="35d43-173">授权所需的音频会议可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="35d43-173">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="35d43-174">已标识组织站点和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="35d43-174">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="35d43-175">已标识和配置的专用和共享音频会议拨入号码与语言首选项的列表。</span><span class="sxs-lookup"><span data-stu-id="35d43-175">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="35d43-176">[通信片尾](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已经为您的组织设置。</span><span class="sxs-lookup"><span data-stu-id="35d43-176">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="35d43-177">音频会议会议网桥的设置已被标识和配置 （PIN 长度、 入口/出口通知，启用通知首选项）。</span><span class="sxs-lookup"><span data-stu-id="35d43-177">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="35d43-178">租户会议策略，拨号计划设置支持音频会议拨出方案已确定，配置，和应用。</span><span class="sxs-lookup"><span data-stu-id="35d43-178">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="35d43-179">已标识和配置音频会议法规遵从性要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-179">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="35d43-180">**电话系统调用计划测试在作用域中的系统必备组件和用户和站点的假设：**</span><span class="sxs-lookup"><span data-stu-id="35d43-180">**Phone System with Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="35d43-181">与调用计划服务的电话系统的业务使用案例定义已完成。</span><span class="sxs-lookup"><span data-stu-id="35d43-181">Business use case definition for the Phone System with Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="35d43-182">授权与调用计划的电话系统所需要的是可用且已分配。</span><span class="sxs-lookup"><span data-stu-id="35d43-182">Licensing required for Phone System with Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="35d43-183">已标识组织站点和用户组的列表。</span><span class="sxs-lookup"><span data-stu-id="35d43-183">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="35d43-184">要分配给用户的电话号码已获得或移植到 Microsoft 和租户门户中可用。</span><span class="sxs-lookup"><span data-stu-id="35d43-184">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="35d43-185">[通信片尾](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已经为您的组织设置。</span><span class="sxs-lookup"><span data-stu-id="35d43-185">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="35d43-186">租户用户策略和拨号计划与调用计划方案支持电话系统的设置有标识，配置，和应用。</span><span class="sxs-lookup"><span data-stu-id="35d43-186">Tenant user policies and dial plan settings that support Phone System with Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="35d43-187">已标识和配置电话系统调用计划法规遵从性要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-187">Phone System with Calling Plans compliance requirements have been identified and configured.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="35d43-188">决策点</span><span class="sxs-lookup"><span data-stu-id="35d43-188">Decision points</span></span></td><td><ul><li><span data-ttu-id="35d43-189">确定要部署的音频会议功能功能 （服务决策）。</span><span class="sxs-lookup"><span data-stu-id="35d43-189">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="35d43-190">确定用户的音频会议的功能要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-190">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="35d43-191">确定音频会议服务配置要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-191">Identify service configuration requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="35d43-192">决定哪些调用计划功能功能的电话系统将部署 （服务决策）。</span><span class="sxs-lookup"><span data-stu-id="35d43-192">Decide which Phone System with Calling Plans feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="35d43-193">确定用户调用计划与电话系统的功能要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-193">Identify user functionality requirements for Phone System with Calling Plans.</span></span></li><li><span data-ttu-id="35d43-194">标识服务调用计划与电话系统的配置要求。</span><span class="sxs-lookup"><span data-stu-id="35d43-194">Identify service configuration requirement for Phone System with Calling Plans.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="35d43-195">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35d43-195">Next steps</span></span></td><td><ul><li><span data-ttu-id="35d43-196">开发并记录您的测试计划方法。</span><span class="sxs-lookup"><span data-stu-id="35d43-196">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="35d43-197">准备您的服务环境和音频会议功能的作用域中的用户。</span><span class="sxs-lookup"><span data-stu-id="35d43-197">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="35d43-198">准备您的服务环境和调用计划功能的电话系统范围内的用户。</span><span class="sxs-lookup"><span data-stu-id="35d43-198">Prepare your service environment and users in scope for Phone System with Calling Plans features.</span></span></li><li><span data-ttu-id="35d43-199">执行您想要启用音频会议功能的测试验证。</span><span class="sxs-lookup"><span data-stu-id="35d43-199">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="35d43-200">执行测试验证您想要启用的调用计划功能的电话系统。</span><span class="sxs-lookup"><span data-stu-id="35d43-200">Execute test validation for the Phone System with Calling Plans features that you want to enable.</span></span></li><li><span data-ttu-id="35d43-201">任何测试失败，确认您的配置是否正确，检查社区的文章，以及 — — 如果需要 — — 引发支持案例。</span><span class="sxs-lookup"><span data-stu-id="35d43-201">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="35d43-202">有关如何执行测试的团队中的音频会议的更多详细的指南，请参阅 [详细测试指南对于音频会议] (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing)。</span><span class="sxs-lookup"><span data-stu-id="35d43-202">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing]  (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing).</span></span>

<span data-ttu-id="35d43-203">有关如何执行测试的电话系统调用计划在团队中的其他详细指导，请参阅[详细测试电话系统指南](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System)。</span><span class="sxs-lookup"><span data-stu-id="35d43-203">For additional detailed guidance on how to perform testing for Phone System with Calling Plans in Teams, see the [detailed testing guide for Phone System](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System).</span></span>

<!--ENDOFSECTION-->