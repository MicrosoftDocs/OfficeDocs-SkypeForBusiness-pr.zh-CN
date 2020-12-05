---
title: 执行用户试验以评估和测试 Microsoft 团队在你的组织中的工作方式
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 有关启动 Microsoft 团队试点项目的指南，了解所有团队均可提供您的组织，同时继续使用 Skype for Business
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
ms.openlocfilehash: 4f74b3d59c226c3445fb317c22c29c67682d8107
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578315"
---
# <a name="conduct-a-user-pilot"></a><span data-ttu-id="a9976-103">执行用户试点</span><span class="sxs-lookup"><span data-stu-id="a9976-103">Conduct a user pilot</span></span>

<span data-ttu-id="a9976-104">![升级旅行图，突出显示部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="a9976-104">![Upgrade journey diagram, highlighting Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a9976-105">本文是升级过程的部署和实施阶段的一部分，并分享了运行有效试验的见解。</span><span class="sxs-lookup"><span data-stu-id="a9976-105">This article is part of Deployment and Implementation stage of your upgrade journey, and shares insights for running an effective pilot.</span></span> <span data-ttu-id="a9976-106">继续之前，请确认你已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="a9976-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="a9976-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="a9976-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a9976-108">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="a9976-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a9976-109">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="a9976-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a9976-110">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="a9976-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a9976-111">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="a9976-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a9976-112">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="a9976-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

<span data-ttu-id="a9976-113">通过部署新技术，你的组织可以实现成本节约、安全合规性、员工满意度和操作效率等业务价值，但它还会影响你的用户的工作效率和组织基础结构 (你的网络) 。</span><span class="sxs-lookup"><span data-stu-id="a9976-113">By deploying new technologies, your organization can realize business value such as cost savings, security compliance, employee satisfaction, and operational efficiencies, but it can also affect your users' productivity and organizational infrastructure (your network).</span></span> <span data-ttu-id="a9976-114">在您的组织中启用新技术之前，请进行正式的用户试验。</span><span class="sxs-lookup"><span data-stu-id="a9976-114">Before enabling new technology across your organization, conduct a formal user pilot.</span></span> <span data-ttu-id="a9976-115">就像在绘制整个聊天室之前在墙上绘制小的颜色片一样，你可以通过执行试验来验证技术和用户准备情况、确定和缓解问题，并帮助确保组织范围内成功实现，来在较小的范围内测试大量推出。</span><span class="sxs-lookup"><span data-stu-id="a9976-115">Just like you'd paint a small patch of color on a wall before painting the whole room, you'd test a broad rollout on a smaller scale by conducting a pilot to validate technical and user readiness, identify and mitigate issues, and help ensure a successful organization-wide implementation.</span></span>

<span data-ttu-id="a9976-116">为了实现最真实的结果，试验应包括实际用户、模仿其通信和协作的方式以及验证技术和用户体验。</span><span class="sxs-lookup"><span data-stu-id="a9976-116">To achieve the most realistic results, the pilot should involve actual users, mimic how they communicate and collaborate, and verify both technical and user experiences.</span></span> <span data-ttu-id="a9976-117">无论您的组织正在考虑并排运行 Skype for Business 和团队，升级到团队，还是部署新功能（如呼叫或会议），试验都可以帮助您为您的组织确定更合适的前进途径。</span><span class="sxs-lookup"><span data-stu-id="a9976-117">Whether your organization is considering running Skype for Business and Teams side by side, upgrading to Teams in the future, or deploying new functionality such a calling or conferencing, a pilot can help identify the right path forward for your organization.</span></span> <span data-ttu-id="a9976-118">有时考虑推出第1阶段，理想的测试版利用已启动的准备工作，并使用目标组用户实现定义的计划。</span><span class="sxs-lookup"><span data-stu-id="a9976-118">Sometimes considered Phase 1 of a rollout, the ideal pilot leverages the preparation you've already started and implements your defined plan with a targeted group of users.</span></span>

| | |
|---|---|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a9976-120">决策点</span><span class="sxs-lookup"><span data-stu-id="a9976-120">Decision point</span></span>|<ul><li><span data-ttu-id="a9976-121">如何使用试点通知项目方向？</span><span class="sxs-lookup"><span data-stu-id="a9976-121">How will you use a pilot to inform project direction?</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="a9976-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a9976-123">Next step</span></span>|<ul><li><span data-ttu-id="a9976-124">使用下面的指南设计和执行正式的试点。</span><span class="sxs-lookup"><span data-stu-id="a9976-124">Use the guidance below to design and execute your formal pilot.</span></span></li></ul>|

> [!Tip]
> <span data-ttu-id="a9976-125">使用示例 [试点资源](https://aka.ms/UpgradeSuccessKit) 帮助设计您的通信、测试计划和反馈调查。</span><span class="sxs-lookup"><span data-stu-id="a9976-125">Use the sample [pilot resources](https://aka.ms/UpgradeSuccessKit) to help design your communications, test plan, and feedback survey.</span></span>

## <a name="1-outline-pilot-logistics"></a><span data-ttu-id="a9976-126">1. 分级式试验物流</span><span class="sxs-lookup"><span data-stu-id="a9976-126">1. Outline pilot logistics</span></span>

<span data-ttu-id="a9976-127">成功的试生产已定义开始日期和结束日期，以及 [明确定义](upgrade-define-project-scope.md#project-goals) 的用于衡量成功的目标。</span><span class="sxs-lookup"><span data-stu-id="a9976-127">A successful pilot has defined start and end dates, and [clearly defined goals](upgrade-define-project-scope.md#project-goals) for measuring success.</span></span> <span data-ttu-id="a9976-128">这些目标应与您更广泛的项目的范围对齐，如您在 [定义项目范围](upgrade-define-project-scope.md)时进行了记录，并将用于在试运行后通知您的路径。</span><span class="sxs-lookup"><span data-stu-id="a9976-128">These goals should align with the scope of your broader project, as you documented when you [defined your project scope](upgrade-define-project-scope.md), and will be used to inform your path forward after your pilot is over.</span></span> <span data-ttu-id="a9976-129">你还应确保你已在项目工期内包含合适的利益干系人。</span><span class="sxs-lookup"><span data-stu-id="a9976-129">You should also ensure that you've included the right stakeholders for the duration of the project.</span></span> <span data-ttu-id="a9976-130">您需要确保有足够的时间来运行试验并评估其影响：我们建议最少30天。</span><span class="sxs-lookup"><span data-stu-id="a9976-130">You'll want to be sure to allow enough time to run the pilot and assess its impact: we recommend a minimum of 30 days.</span></span>

<span data-ttu-id="a9976-131">"从小" 开始，并根据需要添加到你的试点，无论是添加工作负载还是功能，还是其他用户-在进行迭代时需要时间来评估结果并调整你的试点。</span><span class="sxs-lookup"><span data-stu-id="a9976-131">Start small, and add to your pilot as appropriate—whether by adding workloads or features, or additional users—making time to assess results and adjust your pilot as you iterate.</span></span> <span data-ttu-id="a9976-132">您甚至还可以选择在按路线图发布新团队功能时运行后续试点。</span><span class="sxs-lookup"><span data-stu-id="a9976-132">You might even opt to run subsequent pilots as new Teams features are released per the roadmap.</span></span>

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a><span data-ttu-id="a9976-133">2. 选择你的试点参与者和测试方案</span><span class="sxs-lookup"><span data-stu-id="a9976-133">2. Select your pilot participants and test scenarios</span></span>

<span data-ttu-id="a9976-134">试点计划最重要的任务之一是仔细选择参与者。</span><span class="sxs-lookup"><span data-stu-id="a9976-134">One of the most important tasks of pilot planning is thoughtful participant selection.</span></span> <span data-ttu-id="a9976-135">请记住，团队已针对团队协作进行了优化，因此请确保仅根据角色或角色选择试验参与者，并且基于其项目和跨团队工作进行选择。</span><span class="sxs-lookup"><span data-stu-id="a9976-135">Remember that Teams is optimized for teamwork, so be sure to select pilot participants not solely based on roles or personas but also based on their project and cross-team work.</span></span> <span data-ttu-id="a9976-136">一个很好的开始位置是向你的利益干系人和部门经理询问你可以在团队中验证的真实项目。</span><span class="sxs-lookup"><span data-stu-id="a9976-136">A great place to start is asking your stakeholders and department managers for real projects that you can validate in Teams.</span></span> <span data-ttu-id="a9976-137">基于角色的项目的一个示例可能是将团队与您的销售组织配合使用，以确保现场代表可以轻松地访问所需的资源，并与其他域成员共享见解。</span><span class="sxs-lookup"><span data-stu-id="a9976-137">An example of a role-based project might be to use Teams with your sales organization to ensure that field reps can easily access the resources they need and share insights with other field members.</span></span> <span data-ttu-id="a9976-138">基于项目的工作示例可能是与市场营销、培训、公共关系和活动规划团队协调产品发布活动。</span><span class="sxs-lookup"><span data-stu-id="a9976-138">An example of project-based work might be coordinating a product launch event with the marketing, training, public relations, and event planning teams.</span></span> <span data-ttu-id="a9976-139">无论选择哪种方案，试点项目都应扩展到 IT、培训和帮助台中的关键人员，以便你可以在完全优化项目管理资源的同时全面验证解决方案。</span><span class="sxs-lookup"><span data-stu-id="a9976-139">Whichever scenarios you select, the pilot should extend to key people in IT, training, and your helpdesk, so you can thoroughly validate the solution while fully optimizing project management resources.</span></span>

> [!Tip]
> <span data-ttu-id="a9976-140">选择团队试点团队参与者时，请确保包括 Skype for business 的首要用户。</span><span class="sxs-lookup"><span data-stu-id="a9976-140">When selecting your Teams pilot group participants, be sure to include top users of Skype for Business.</span></span> <span data-ttu-id="a9976-141">请咨询这些用户以了解他们目前如何使用 Skype for Business，然后构建一个测试计划来验证团队是否可以满足其当前需求。</span><span class="sxs-lookup"><span data-stu-id="a9976-141">Check with those users to understand how they use Skype for Business today, then build out a test plan to verify that Teams can meet their current needs.</span></span>

## <a name="3-design-your-test-plan-and-feedback-survey"></a><span data-ttu-id="a9976-142">3. 设计测试计划和反馈调查</span><span class="sxs-lookup"><span data-stu-id="a9976-142">3. Design your test plan and feedback survey</span></span>

<span data-ttu-id="a9976-143">若要获得成功的试验体验，请为参与者提供明确定义的任务，以便与他们共享他们的反馈。</span><span class="sxs-lookup"><span data-stu-id="a9976-143">For a successful pilot experience, give your participants clearly defined tasks to complete along with a way for them to share their feedback.</span></span> <span data-ttu-id="a9976-144">将任务组合在一起以向用户提供真实的方案，演示其日常活动的相关性。</span><span class="sxs-lookup"><span data-stu-id="a9976-144">Group tasks together to offer real-world scenarios to your users, demonstrating relevancy to their daily activities.</span></span> <span data-ttu-id="a9976-145">让你在 [评估组织更改准备](https://aka.ms/OrgReadiness) 情况指南中定义的使用案例你的测试计划。</span><span class="sxs-lookup"><span data-stu-id="a9976-145">Let the use cases you defined in [Assess organizational change readiness](https://aka.ms/OrgReadiness) guide your test plan.</span></span>

<span data-ttu-id="a9976-146">您的组织可能会选择一次试点所有功能，或使用逐步式方法（例如，先进行试点协作，然后是会议，然后是聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="a9976-146">Your organization might choose to pilot all functionality at once, or use a gradual approach—for example, pilot collaboration first, then meetings, then chat and calling.</span></span> <span data-ttu-id="a9976-147">确保你有一个打开的反馈通道来跟踪进度和测量结果。</span><span class="sxs-lookup"><span data-stu-id="a9976-147">Ensure that you have an open feedback channel to track progress and measure outcomes.</span></span> <span data-ttu-id="a9976-148">将预定义的调查用作捕获和评估试验结果的简单方法;调查设计应基于测试计划中的方案和功能。</span><span class="sxs-lookup"><span data-stu-id="a9976-148">Use a predefined survey as an easy way to capture and assess pilot results; the survey design should be based on the scenarios and features in your test plan.</span></span>

## <a name="4-create-your-communications-plan"></a><span data-ttu-id="a9976-149">4. 创建通信计划</span><span class="sxs-lookup"><span data-stu-id="a9976-149">4. Create your communications plan</span></span>

<span data-ttu-id="a9976-150">对试点项目的成功非常重要，那就是让试点参与者了解所发生的情况、时间和原因以及它们的预期效果。</span><span class="sxs-lookup"><span data-stu-id="a9976-150">It's crucial to the success of your pilot that you educate pilot participants on what's happening, when, and why, and what's expected of them.</span></span> <span data-ttu-id="a9976-151">若要推动兴趣和最大程度的参与，请确保包括用户价值消息，以及用户在完成试验后可以获取其他信息的培训和支持的链接。</span><span class="sxs-lookup"><span data-stu-id="a9976-151">To drive excitement and maximum participation, be sure to include user value messaging in addition to links to training and support where users can get additional information as they progress through the pilot.</span></span> <span data-ttu-id="a9976-152">下面是一些示例资源，可帮助你开始使用试点通信计划：</span><span class="sxs-lookup"><span data-stu-id="a9976-152">Here are a few sample resources to get you started with your pilot communications plan:</span></span>

- <span data-ttu-id="a9976-153">[试点资源](https://aka.ms/UpgradeSuccessKit)，包括电子邮件模板和示例反馈调查问题</span><span class="sxs-lookup"><span data-stu-id="a9976-153">[Pilot resources](https://aka.ms/UpgradeSuccessKit), including email templates and sample feedback survey questions</span></span>
- <span data-ttu-id="a9976-154">[从 Skype For Business 切换到团队](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)，旨在帮助 Skype for business 用户开始使用团队的快速入门指南</span><span class="sxs-lookup"><span data-stu-id="a9976-154">[Switch to Teams from Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), a quick-start guide designed to help Skype for Business users get started with Teams</span></span>

## <a name="5-conduct-your-pilot"></a><span data-ttu-id="a9976-155">5. 开展试验</span><span class="sxs-lookup"><span data-stu-id="a9976-155">5. Conduct your pilot</span></span>

<span data-ttu-id="a9976-156">随着所有后勤工作，您现在已准备好开始试用。</span><span class="sxs-lookup"><span data-stu-id="a9976-156">With all the logistics in place, you're now ready to begin your pilot.</span></span> <span data-ttu-id="a9976-157">执行试验包括与用户进行通信、监视网络和使用情况以确保你的网络性能和通话质量保持正常运行、收集参与者的反馈和查看帮助者票证以获取与团队相关的问题。</span><span class="sxs-lookup"><span data-stu-id="a9976-157">Conducting your pilot includes communicating with your users, monitoring your network and usage to ensure your network performance and call quality remain healthy, gathering feedback from participants, and reviewing helpdesk tickets for questions related to Teams.</span></span>

### <a name="tips-for-pilot-success"></a><span data-ttu-id="a9976-158">有关试点成功的提示</span><span class="sxs-lookup"><span data-stu-id="a9976-158">Tips for pilot success</span></span>

<span data-ttu-id="a9976-159">以下提示可帮助确保试验成功：</span><span class="sxs-lookup"><span data-stu-id="a9976-159">The following tips can help ensure the success of your pilot:</span></span>

- <span data-ttu-id="a9976-160">在开始试用之前，请确认所有试点参与者均已启用相应的 [共存模式]</span><span class="sxs-lookup"><span data-stu-id="a9976-160">Before beginning your pilot, confirm that all pilot participants are enabled for the appropriate [coexistence mode]</span></span>
- <span data-ttu-id="a9976-161">https://aka.ms/SkypeToTeams-SetCoexistence)要验证的 (。</span><span class="sxs-lookup"><span data-stu-id="a9976-161">(https://aka.ms/SkypeToTeams-SetCoexistence) you want to validate.</span></span>
- <span data-ttu-id="a9976-162">每周，在您的整个试点中，与项目利益干系人会面，了解用户反馈、使用数据、网络数据和技术支持人员，确保您的试运行顺利运行。</span><span class="sxs-lookup"><span data-stu-id="a9976-162">Weekly, throughout your pilot, meet with your project stakeholders to review user feedback, usage data, network data, and helpdesk tickets to ensure your pilot is running smoothly.</span></span> <span data-ttu-id="a9976-163">根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="a9976-163">Make any adjustments as needed.</span></span>

### <a name="suggested-timeline"></a><span data-ttu-id="a9976-164">建议的日程表</span><span class="sxs-lookup"><span data-stu-id="a9976-164">Suggested timeline</span></span>

<span data-ttu-id="a9976-165">下面是 30 天试点的建议时间线：</span><span class="sxs-lookup"><span data-stu-id="a9976-165">Here's a suggested timeline for a 30-day pilot:</span></span>

- <span data-ttu-id="a9976-166">试点项目开始之前的一周：将初始通信发送到试点用户。</span><span class="sxs-lookup"><span data-stu-id="a9976-166">One week before the pilot kickoff: Send initial communication to pilot users.</span></span>
- <span data-ttu-id="a9976-167">第1天：向试点用户发送动员会通信。</span><span class="sxs-lookup"><span data-stu-id="a9976-167">Day 1: Send kickoff communication to pilot users.</span></span>
- <span data-ttu-id="a9976-168">第7天：保留第一周的项目团队检查点会议。</span><span class="sxs-lookup"><span data-stu-id="a9976-168">Day 7: Hold the first weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="a9976-169">第14天：向您的试点用户发送中间点通信，保持每周项目团队的检查点会议。</span><span class="sxs-lookup"><span data-stu-id="a9976-169">Day 14: Send mid-point communication to your pilot users, hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="a9976-170">第21天：保留每周项目团队检查点会议。</span><span class="sxs-lookup"><span data-stu-id="a9976-170">Day 21: Hold a weekly project team checkpoint meeting.</span></span>
- <span data-ttu-id="a9976-171">第30天：向您的试点用户发送最终通信。</span><span class="sxs-lookup"><span data-stu-id="a9976-171">Day 30: Send final communication to your pilot users.</span></span>
- <span data-ttu-id="a9976-172">第31至第45天：评估试验结果，并规划后续步骤。</span><span class="sxs-lookup"><span data-stu-id="a9976-172">Days 31–45: Assess pilot results, and plan for next steps.</span></span>

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a><span data-ttu-id="a9976-173">6. 评估发现并评估您的转至前计划</span><span class="sxs-lookup"><span data-stu-id="a9976-173">6. Assess learnings and evaluate your go-forward plan</span></span>

<span data-ttu-id="a9976-174">完成试验后，就可以根据你的目标收集所有反馈调查、最终网络统计信息和支持票证，确定是否将实施推进计划。</span><span class="sxs-lookup"><span data-stu-id="a9976-174">After your pilot is complete, it's time to gather all feedback surveys, final network stats, and support tickets for analysis against your goals and determine whether you'll implement your go-forward plan.</span></span> <span data-ttu-id="a9976-175">你可能会发现你的组织已准备好进行广泛的部署，或者你希望将试用扩展到更多用户，或者你希望在你确定的任何关注问题之后的更晚时间重新访问试用版。</span><span class="sxs-lookup"><span data-stu-id="a9976-175">You might find that your organization is ready for a broad deployment, or you want to extend your pilot to more users, or you want to revisit the pilot at a later date after any concerns you've identified have been mitigated.</span></span> <span data-ttu-id="a9976-176">请记住，你的试点是预测 _受控制_ 环境中的技术和用户成果的绝佳方式;非常仔细地跳转。</span><span class="sxs-lookup"><span data-stu-id="a9976-176">Remember that your pilot is a great way to predict technical and user outcomes in a _controlled_ environment; be thoughtful about jumping ahead too quickly.</span></span>

<span data-ttu-id="a9976-177">如果结果表明：</span><span class="sxs-lookup"><span data-stu-id="a9976-177">If your results indicate:</span></span>

- <span data-ttu-id="a9976-178">**你的试点目标 (例如，已实现用户满意度和网络质量)**，你应该准备好开始推出下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="a9976-178">**Your pilot goals (for example, user satisfaction and network quality) have been achieved**, you should be ready to proceed with the next phase of your rollout.</span></span> <span data-ttu-id="a9976-179">根据项目的目标，这可能是下列情况之一：</span><span class="sxs-lookup"><span data-stu-id="a9976-179">Depending on the goals of your project, this could be one of the following:</span></span>
  - <span data-ttu-id="a9976-180">将试点扩展到其他参与者</span><span class="sxs-lookup"><span data-stu-id="a9976-180">Extending the pilot to additional participants</span></span>
  - [<span data-ttu-id="a9976-181">为你的组织的部分或所有组织启用 Skype for business (**孤岛** 模式) 的团队</span><span class="sxs-lookup"><span data-stu-id="a9976-181">Enabling Teams alongside Skype for Business (**Islands** mode) for some or all of your organization</span></span>](https://aka.ms/SkypeToTeams-SetCoexistence)
  - [<span data-ttu-id="a9976-182">将用户从 Skype for Business 升级到团队 (**仅限团队** 的部分或所有组织的模式)</span><span class="sxs-lookup"><span data-stu-id="a9976-182">Upgrading users from Skype for Business to Teams (**Teams only** mode) for some or all of your organization</span></span>](https://aka.ms/SkypeToTeams-SetCoexistence)
- <span data-ttu-id="a9976-183">**你的示范未实现你希望的结果 (例如，用户满意度和网络质量)**，请花一些时间对你的计划进行适当调整并重新访问你的试点。</span><span class="sxs-lookup"><span data-stu-id="a9976-183">**Your pilot didn't achieve the outcomes you wanted (for example, user satisfaction and network quality)**, take time to make the appropriate adjustments to your plan and revisit your pilot.</span></span>

> [!Tip]
> <span data-ttu-id="a9976-184">将试点参与者登记为对等拥护者，以帮助布道和板载新用户加入团队。</span><span class="sxs-lookup"><span data-stu-id="a9976-184">Enlist your pilot participants as peer champions to help evangelize and onboard new users to Teams.</span></span> <span data-ttu-id="a9976-185">对等拥护者可以轻松地与其他用户、共享其自己的体验和发现以及为其同事提供支持和指导。</span><span class="sxs-lookup"><span data-stu-id="a9976-185">Peer champions can easily relate to other users, sharing their own experiences and learnings, and offering support and guidance to their colleagues.</span></span> <span data-ttu-id="a9976-186">了解有关 [拥护](https://go.microsoft.com/fwlink/?linkid=859068) 人员以及如何在自己的推出期间使用它们的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a9976-186">Learn more about [champions](https://go.microsoft.com/fwlink/?linkid=859068) and how you might use them within your own rollout.</span></span>
