---
title: 开展用户试点，评估并测试Microsoft Teams在组织中如何工作
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 指导如何启动Microsoft Teams试点，探索Teams组织提供的所有功能，同时继续使用Skype for Business
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe1cf351bb5d3d4a950b818505a8e5d93fa7ab27
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282089"
---
# <a name="conduct-a-user-pilot"></a><span data-ttu-id="57aee-103">执行用户试点</span><span class="sxs-lookup"><span data-stu-id="57aee-103">Conduct a user pilot</span></span>

<span data-ttu-id="57aee-104">![升级过程图，突出显示"部署和实现"](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="57aee-104">![Upgrade journey diagram, highlighting Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="57aee-105">本文是升级旅程的部署和实施阶段的一部分，分享有关运行有效试点的见解。</span><span class="sxs-lookup"><span data-stu-id="57aee-105">This article is part of Deployment and Implementation stage of your upgrade journey, and shares insights for running an effective pilot.</span></span> <span data-ttu-id="57aee-106">在继续之前，请确认已经完成了以下活动:</span><span class="sxs-lookup"><span data-stu-id="57aee-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="57aee-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="57aee-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="57aee-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="57aee-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="57aee-109">了解两者共存Skype for Business互操作性Teams</span><span class="sxs-lookup"><span data-stu-id="57aee-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="57aee-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="57aee-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="57aee-111">准备环境</span><span class="sxs-lookup"><span data-stu-id="57aee-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="57aee-112">准备组织</span><span class="sxs-lookup"><span data-stu-id="57aee-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

<span data-ttu-id="57aee-113">通过部署新技术，组织可以实现成本节省、安全合规性、员工满意度和操作效率等业务价值，但也可能影响用户的工作效率和组织基础结构 (网络) 。</span><span class="sxs-lookup"><span data-stu-id="57aee-113">By deploying new technologies, your organization can realize business value such as cost savings, security compliance, employee satisfaction, and operational efficiencies, but it can also affect your users' productivity and organizational infrastructure (your network).</span></span> <span data-ttu-id="57aee-114">在整个组织中启用新技术之前，请进行正式用户试点。</span><span class="sxs-lookup"><span data-stu-id="57aee-114">Before enabling new technology across your organization, conduct a formal user pilot.</span></span> <span data-ttu-id="57aee-115">就像在绘制整个房间之前在墙壁上画一小片颜色一样，通过开展试点来验证技术和用户就绪性、识别和缓解问题，并帮助确保组织范围内的实施成功，从而在小规模上测试广泛推出。</span><span class="sxs-lookup"><span data-stu-id="57aee-115">Just like you'd paint a small patch of color on a wall before painting the whole room, you'd test a broad rollout on a smaller scale by conducting a pilot to validate technical and user readiness, identify and mitigate issues, and help ensure a successful organization-wide implementation.</span></span>

<span data-ttu-id="57aee-116">要实现最现实的结果，试点应涉及实际用户，模拟他们沟通和协作的方式，并验证技术和用户体验。</span><span class="sxs-lookup"><span data-stu-id="57aee-116">To achieve the most realistic results, the pilot should involve actual users, mimic how they communicate and collaborate, and verify both technical and user experiences.</span></span> <span data-ttu-id="57aee-117">无论组织考虑并行运行 Skype for Business 和 Teams、将来升级到 Teams，还是部署新功能（如呼叫或会议），试点都可以帮助确定组织的正确前进路径。</span><span class="sxs-lookup"><span data-stu-id="57aee-117">Whether your organization is considering running Skype for Business and Teams side by side, upgrading to Teams in the future, or deploying new functionality such a calling or conferencing, a pilot can help identify the right path forward for your organization.</span></span> <span data-ttu-id="57aee-118">有时被视为实施的第 1 阶段，理想的试点利用已启动的准备工作，通过目标用户组实施定义的计划。</span><span class="sxs-lookup"><span data-stu-id="57aee-118">Sometimes considered Phase 1 of a rollout, the ideal pilot leverages the preparation you've already started and implements your defined plan with a targeted group of users.</span></span>

| | |
|---|---|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="57aee-120">决策点</span><span class="sxs-lookup"><span data-stu-id="57aee-120">Decision point</span></span>|<ul><li><span data-ttu-id="57aee-121">如何使用试点来告知项目方向？</span><span class="sxs-lookup"><span data-stu-id="57aee-121">How will you use a pilot to inform project direction?</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="57aee-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="57aee-123">Next step</span></span>|<ul><li><span data-ttu-id="57aee-124">使用以下指南设计和执行正式试点。</span><span class="sxs-lookup"><span data-stu-id="57aee-124">Use the guidance below to design and execute your formal pilot.</span></span></li></ul>|

> [!Tip]
> <span data-ttu-id="57aee-125">使用示例 [试点资源](https://aka.ms/UpgradeSuccessKit) 来帮助设计通信、测试计划和反馈调查。</span><span class="sxs-lookup"><span data-stu-id="57aee-125">Use the sample [pilot resources](https://aka.ms/UpgradeSuccessKit) to help design your communications, test plan, and feedback survey.</span></span>

## <a name="1-outline-pilot-logistics"></a><span data-ttu-id="57aee-126">1. 概述试点物流</span><span class="sxs-lookup"><span data-stu-id="57aee-126">1. Outline pilot logistics</span></span>

<span data-ttu-id="57aee-127">成功的试点已定义开始日期和结束日期，以及 [用于衡量成功的](upgrade-define-project-scope.md#project-goals) 明确目标。</span><span class="sxs-lookup"><span data-stu-id="57aee-127">A successful pilot has defined start and end dates, and [clearly defined goals](upgrade-define-project-scope.md#project-goals) for measuring success.</span></span> <span data-ttu-id="57aee-128">这些目标应该与更广泛的项目范围保持一致，如定义项目范围时所记录，[](upgrade-define-project-scope.md)并且将用于在试点结束后通知你前进的路径。</span><span class="sxs-lookup"><span data-stu-id="57aee-128">These goals should align with the scope of your broader project, as you documented when you [defined your project scope](upgrade-define-project-scope.md), and will be used to inform your path forward after your pilot is over.</span></span> <span data-ttu-id="57aee-129">此外，应确保在项目持续期间包含适当的利益干系人。</span><span class="sxs-lookup"><span data-stu-id="57aee-129">You should also ensure that you've included the right stakeholders for the duration of the project.</span></span> <span data-ttu-id="57aee-130">你需要确保留出足够的时间来运行试点并评估其影响：我们建议至少 30 天。</span><span class="sxs-lookup"><span data-stu-id="57aee-130">You'll want to be sure to allow enough time to run the pilot and assess its impact: we recommend a minimum of 30 days.</span></span>

<span data-ttu-id="57aee-131">从小规模开始，并根据需要向试点添加内容（无论是通过添加工作负荷或功能，还是通过添加其他用户）来花时间评估结果，并调整试运行方式。</span><span class="sxs-lookup"><span data-stu-id="57aee-131">Start small, and add to your pilot as appropriate—whether by adding workloads or features, or additional users—making time to assess results and adjust your pilot as you iterate.</span></span> <span data-ttu-id="57aee-132">根据路线图发布新功能后，甚至可以选择Teams试点。</span><span class="sxs-lookup"><span data-stu-id="57aee-132">You might even opt to run subsequent pilots as new Teams features are released per the roadmap.</span></span>

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a><span data-ttu-id="57aee-133">2. 选择试点参与者和测试方案</span><span class="sxs-lookup"><span data-stu-id="57aee-133">2. Select your pilot participants and test scenarios</span></span>

<span data-ttu-id="57aee-134">试点计划最重要的任务之一是仔细选择参与者。</span><span class="sxs-lookup"><span data-stu-id="57aee-134">One of the most important tasks of pilot planning is thoughtful participant selection.</span></span> <span data-ttu-id="57aee-135">请记住，Teams团队协作进行了优化，因此请确保不仅基于角色或角色选择试点参与者，而且还要基于其项目和跨团队工作选择试点参与者。</span><span class="sxs-lookup"><span data-stu-id="57aee-135">Remember that Teams is optimized for teamwork, so be sure to select pilot participants not solely based on roles or personas but also based on their project and cross-team work.</span></span> <span data-ttu-id="57aee-136">一个很好的起点是要求利益干系人与部门经理提供可以在项目内验证Teams。</span><span class="sxs-lookup"><span data-stu-id="57aee-136">A great place to start is asking your stakeholders and department managers for real projects that you can validate in Teams.</span></span> <span data-ttu-id="57aee-137">基于角色的项目的一个示例可能是将 Teams 用于销售组织，以确保现场代表可以轻松访问所需的资源，并与其他现场成员共享见解。</span><span class="sxs-lookup"><span data-stu-id="57aee-137">An example of a role-based project might be to use Teams with your sales organization to ensure that field reps can easily access the resources they need and share insights with other field members.</span></span> <span data-ttu-id="57aee-138">基于项目的工作的一个示例可能是将产品发布活动与营销、培训、公共关系和事件规划团队协调。</span><span class="sxs-lookup"><span data-stu-id="57aee-138">An example of project-based work might be coordinating a product launch event with the marketing, training, public relations, and event planning teams.</span></span> <span data-ttu-id="57aee-139">无论选择哪种方案，试点都应扩展到 IT、培训和支持人员中的关键人员，以便你可以全面验证解决方案，同时完全优化项目管理资源。</span><span class="sxs-lookup"><span data-stu-id="57aee-139">Whichever scenarios you select, the pilot should extend to key people in IT, training, and your helpdesk, so you can thoroughly validate the solution while fully optimizing project management resources.</span></span>

> [!Tip]
> <span data-ttu-id="57aee-140">在选择Teams试点组参与者时，请确保包括最热门Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="57aee-140">When selecting your Teams pilot group participants, be sure to include top users of Skype for Business.</span></span> <span data-ttu-id="57aee-141">请与这些用户核实以了解他们当前Skype for Business，然后制定测试计划来验证Teams满足其当前需求。</span><span class="sxs-lookup"><span data-stu-id="57aee-141">Check with those users to understand how they use Skype for Business today, then build out a test plan to verify that Teams can meet their current needs.</span></span>

## <a name="3-design-your-test-plan-and-feedback-survey"></a><span data-ttu-id="57aee-142">3. 设计测试计划和反馈调查</span><span class="sxs-lookup"><span data-stu-id="57aee-142">3. Design your test plan and feedback survey</span></span>

<span data-ttu-id="57aee-143">若要获得成功的试点体验，请为参与者提供明确定义的任务来完成，并帮助他们分享反馈。</span><span class="sxs-lookup"><span data-stu-id="57aee-143">For a successful pilot experience, give your participants clearly defined tasks to complete along with a way for them to share their feedback.</span></span> <span data-ttu-id="57aee-144">将任务组合在一起，为用户提供实际方案，表明其日常活动的相关性。</span><span class="sxs-lookup"><span data-stu-id="57aee-144">Group tasks together to offer real-world scenarios to your users, demonstrating relevancy to their daily activities.</span></span> <span data-ttu-id="57aee-145">让在评估组织变更准备 [情况指南中定义的](./upgrade-org-change-readiness.md) 用例用于测试计划。</span><span class="sxs-lookup"><span data-stu-id="57aee-145">Let the use cases you defined in [Assess organizational change readiness](./upgrade-org-change-readiness.md) guide your test plan.</span></span>

<span data-ttu-id="57aee-146">组织可能选择一次试用所有功能，或者使用渐进式方法-例如，先试运行协作，然后进行会议，然后聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="57aee-146">Your organization might choose to pilot all functionality at once, or use a gradual approach—for example, pilot collaboration first, then meetings, then chat and calling.</span></span> <span data-ttu-id="57aee-147">确保你有一个开放的反馈渠道来跟踪进度和衡量结果。</span><span class="sxs-lookup"><span data-stu-id="57aee-147">Ensure that you have an open feedback channel to track progress and measure outcomes.</span></span> <span data-ttu-id="57aee-148">使用预定义的调查作为捕获和评估试点结果的简便方法;调查设计应基于测试计划中的方案和功能。</span><span class="sxs-lookup"><span data-stu-id="57aee-148">Use a predefined survey as an easy way to capture and assess pilot results; the survey design should be based on the scenarios and features in your test plan.</span></span>

## <a name="4-create-your-communications-plan"></a><span data-ttu-id="57aee-149">4. 创建通信计划</span><span class="sxs-lookup"><span data-stu-id="57aee-149">4. Create your communications plan</span></span>

<span data-ttu-id="57aee-150">让试点参与者了解情况、时间、原因以及预期结果，对试点的成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="57aee-150">It's crucial to the success of your pilot that you educate pilot participants on what's happening, when, and why, and what's expected of them.</span></span> <span data-ttu-id="57aee-151">若要促进兴奋和最大程度的参与，除了培训和支持的链接外，请确保包括用户价值消息，用户可以在试点进行时获取其他信息。</span><span class="sxs-lookup"><span data-stu-id="57aee-151">To drive excitement and maximum participation, be sure to include user value messaging in addition to links to training and support where users can get additional information as they progress through the pilot.</span></span> <span data-ttu-id="57aee-152">下面是一些示例资源，可让你开始使用试点通信计划：</span><span class="sxs-lookup"><span data-stu-id="57aee-152">Here are a few sample resources to get you started with your pilot communications plan:</span></span>

- <span data-ttu-id="57aee-153">[试点资源](https://aka.ms/UpgradeSuccessKit)，包括电子邮件模板和示例反馈调查问题</span><span class="sxs-lookup"><span data-stu-id="57aee-153">[Pilot resources](https://aka.ms/UpgradeSuccessKit), including email templates and sample feedback survey questions</span></span>
- <span data-ttu-id="57aee-154">[从 Teams 切换到 Skype for Business，](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)这是一个快速入门指南，旨在帮助Skype for Business用户开始使用Teams</span><span class="sxs-lookup"><span data-stu-id="57aee-154">[Switch to Teams from Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), a quick-start guide designed to help Skype for Business users get started with Teams</span></span>

## <a name="5-conduct-your-pilot"></a><span data-ttu-id="57aee-155">5. 开展试点</span><span class="sxs-lookup"><span data-stu-id="57aee-155">5. Conduct your pilot</span></span>

<span data-ttu-id="57aee-156">准备好所有物流后，即可开始试点。</span><span class="sxs-lookup"><span data-stu-id="57aee-156">With all the logistics in place, you're now ready to begin your pilot.</span></span> <span data-ttu-id="57aee-157">开展试点包括与用户通信、监视网络和使用情况以确保网络性能和呼叫质量保持正常、收集参与者的反馈，以及查看支持人员票证中与 Teams。</span><span class="sxs-lookup"><span data-stu-id="57aee-157">Conducting your pilot includes communicating with your users, monitoring your network and usage to ensure your network performance and call quality remain healthy, gathering feedback from participants, and reviewing helpdesk tickets for questions related to Teams.</span></span>

### <a name="tips-for-pilot-success"></a><span data-ttu-id="57aee-158">使用技巧试点成功的计划</span><span class="sxs-lookup"><span data-stu-id="57aee-158">Tips for pilot success</span></span>

<span data-ttu-id="57aee-159">以下提示有助于确保试点成功：</span><span class="sxs-lookup"><span data-stu-id="57aee-159">The following tips can help ensure the success of your pilot:</span></span>

- <span data-ttu-id="57aee-160">在开始试验之前，请确认所有试点参与者都启用了适当的 [共存模式]</span><span class="sxs-lookup"><span data-stu-id="57aee-160">Before beginning your pilot, confirm that all pilot participants are enabled for the appropriate [coexistence mode]</span></span>
- <span data-ttu-id="57aee-161"> (https://aka.ms/SkypeToTeams-SetCoexistence) 要验证的证书。</span><span class="sxs-lookup"><span data-stu-id="57aee-161">(https://aka.ms/SkypeToTeams-SetCoexistence) you want to validate.</span></span>
- <span data-ttu-id="57aee-162">每周在试点期间与项目利益干系人会面，查看用户反馈、使用情况数据、网络数据和支持票证，确保试点顺利运行。</span><span class="sxs-lookup"><span data-stu-id="57aee-162">Weekly, throughout your pilot, meet with your project stakeholders to review user feedback, usage data, network data, and helpdesk tickets to ensure your pilot is running smoothly.</span></span> <span data-ttu-id="57aee-163">根据需要做出任何调整。</span><span class="sxs-lookup"><span data-stu-id="57aee-163">Make any adjustments as needed.</span></span>

### <a name="suggested-timeline"></a><span data-ttu-id="57aee-164">建议的日程表</span><span class="sxs-lookup"><span data-stu-id="57aee-164">Suggested timeline</span></span>

<span data-ttu-id="57aee-165">下面是 30 天试点的建议时间线：</span><span class="sxs-lookup"><span data-stu-id="57aee-165">Here's a suggested timeline for a 30-day pilot:</span></span>

- <span data-ttu-id="57aee-166">试点启动前的一周：向试点用户发送初始通信。</span><span class="sxs-lookup"><span data-stu-id="57aee-166">One week before the pilot kickoff: Send initial communication to pilot users.</span></span>
- <span data-ttu-id="57aee-167">第 1 天：向试点用户发送启动通信。</span><span class="sxs-lookup"><span data-stu-id="57aee-167">Day 1: Send kickoff communication to pilot users.</span></span>
- <span data-ttu-id="57aee-168">第 7 天：召开第一次每周项目团队检查点会议。</span><span class="sxs-lookup"><span data-stu-id="57aee-168">Day 7: Hold the first weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="57aee-169">第 14 天：向试点用户发送中间点通信，召开每周项目团队检查点会议。</span><span class="sxs-lookup"><span data-stu-id="57aee-169">Day 14: Send mid-point communication to your pilot users, hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="57aee-170">第 21 天：召开每周项目团队检查点会议。</span><span class="sxs-lookup"><span data-stu-id="57aee-170">Day 21: Hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="57aee-171">第 30 天：向试点用户发送最终通信。</span><span class="sxs-lookup"><span data-stu-id="57aee-171">Day 30: Send final communication to your pilot users.</span></span>
- <span data-ttu-id="57aee-172">第 31-45 天：评估试点结果，并规划下一步。</span><span class="sxs-lookup"><span data-stu-id="57aee-172">Days 31–45: Assess pilot results, and plan for next steps.</span></span>

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a><span data-ttu-id="57aee-173">6. 评估学习和评估前进计划</span><span class="sxs-lookup"><span data-stu-id="57aee-173">6. Assess learnings and evaluate your go-forward plan</span></span>

<span data-ttu-id="57aee-174">试点完成后，可以收集所有反馈调查、最终网络统计信息和支持票证，以便针对目标进行分析，并确定是否实施前向计划。</span><span class="sxs-lookup"><span data-stu-id="57aee-174">After your pilot is complete, it's time to gather all feedback surveys, final network stats, and support tickets for analysis against your goals and determine whether you'll implement your go-forward plan.</span></span> <span data-ttu-id="57aee-175">你可能会发现，你的组织已准备好进行广泛部署，或者希望将试点扩展到更多用户，或者想要在发现的任何问题得到缓解后，在以后重新访问试点。</span><span class="sxs-lookup"><span data-stu-id="57aee-175">You might find that your organization is ready for a broad deployment, or you want to extend your pilot to more users, or you want to revisit the pilot at a later date after any concerns you've identified have been mitigated.</span></span> <span data-ttu-id="57aee-176">请记住，试点是在受控环境中预测技术和用户结果 _的一种好_ 方法;考虑过快地跳转。</span><span class="sxs-lookup"><span data-stu-id="57aee-176">Remember that your pilot is a great way to predict technical and user outcomes in a _controlled_ environment; be thoughtful about jumping ahead too quickly.</span></span>

<span data-ttu-id="57aee-177">如果结果指示：</span><span class="sxs-lookup"><span data-stu-id="57aee-177">If your results indicate:</span></span>

- <span data-ttu-id="57aee-178">**试点目标 (** 例如，用户满意度和网络质量) 已实现，应准备好继续进行下一阶段的推出。</span><span class="sxs-lookup"><span data-stu-id="57aee-178">**Your pilot goals (for example, user satisfaction and network quality) have been achieved**, you should be ready to proceed with the next phase of your rollout.</span></span> <span data-ttu-id="57aee-179">根据项目的目标，这可能是下列其中一项：</span><span class="sxs-lookup"><span data-stu-id="57aee-179">Depending on the goals of your project, this could be one of the following:</span></span>
  - <span data-ttu-id="57aee-180">将试点扩展到其他参与者</span><span class="sxs-lookup"><span data-stu-id="57aee-180">Extending the pilot to additional participants</span></span>
  - [<span data-ttu-id="57aee-181">为Teams或Skype for Business (组织启用) 群岛模式" </span><span class="sxs-lookup"><span data-stu-id="57aee-181">Enabling Teams alongside Skype for Business (**Islands** mode) for some or all of your organization</span></span>](./setting-your-coexistence-and-upgrade-settings.md)
  - [<span data-ttu-id="57aee-182">将用户从 Skype for Business 升级到 Teams (Teams **仅**) 部分或所有组织使用模式</span><span class="sxs-lookup"><span data-stu-id="57aee-182">Upgrading users from Skype for Business to Teams (**Teams only** mode) for some or all of your organization</span></span>](./setting-your-coexistence-and-upgrade-settings.md)
- <span data-ttu-id="57aee-183">**试运行未达到** 预期效果，例如 (满意度和网络质量) ，请花些时间对计划进行适当的调整，然后重新访问试点。</span><span class="sxs-lookup"><span data-stu-id="57aee-183">**Your pilot didn't achieve the outcomes you wanted (for example, user satisfaction and network quality)**, take time to make the appropriate adjustments to your plan and revisit your pilot.</span></span>

> [!Tip]
> <span data-ttu-id="57aee-184">将试点参与者登记为对等支持者，以帮助宣传新用户并加入Teams。</span><span class="sxs-lookup"><span data-stu-id="57aee-184">Enlist your pilot participants as peer champions to help evangelize and onboard new users to Teams.</span></span> <span data-ttu-id="57aee-185">对等支持者可以轻松地与其他用户关联、分享其自己的体验和知识，以及向同事提供支持和指导。</span><span class="sxs-lookup"><span data-stu-id="57aee-185">Peer champions can easily relate to other users, sharing their own experiences and learnings, and offering support and guidance to their colleagues.</span></span> <span data-ttu-id="57aee-186">详细了解冠军 [以及如何](https://go.microsoft.com/fwlink/?linkid=859068) 在你自己的推出中使用它们。</span><span class="sxs-lookup"><span data-stu-id="57aee-186">Learn more about [champions](https://go.microsoft.com/fwlink/?linkid=859068) and how you might use them within your own rollout.</span></span>