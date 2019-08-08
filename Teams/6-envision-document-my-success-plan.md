---
title: 编制 Microsoft Teams 成功计划文档
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择部署模型, 开发有责任的、有责任的 (RACI) 矩阵, 创建执行和管理计划。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f324c703c71adbcabedc71d9a5fdb6a4ce63ca0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245157"
---
# <a name="document-my-success-plan"></a><span data-ttu-id="cd4ef-103">记录成功计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-103">Document my success plan</span></span>

<span data-ttu-id="cd4ef-104">本文概述了正确记录云语音部署的要求。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-104">This article gives an overview of the requirements for properly documenting your cloud voice deployment.</span></span> <span data-ttu-id="cd4ef-105">通过在规划云语音部署时定义和记录所有决策点和下一步操作, 您可以确保所有利益干系人和项目团队成员都在提供成功的结果中进行调整。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-105">By defining and documenting all decision points and next steps while planning your cloud voice deployment, you can make sure all stakeholders and project team members are aligned on delivering successful outcomes.</span></span> 

## <a name="execution-planning"></a><span data-ttu-id="cd4ef-106">执行计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-106">Execution planning</span></span> 

<span data-ttu-id="cd4ef-107">在定义了如何通过组织中的呼叫计划解决方案实现音频会议或电话系统后, 您需要规划实施项目的执行。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-107">After defining how you’ll implement the Audio Conferencing or Phone System with Calling Plan solution in your organization, you need to plan for the execution of the implementation project.</span></span>

<span data-ttu-id="cd4ef-108">如果你的组织只有一个或两个网站, 你可能不需要完成本文中提供的所有详细信息, 但你应该通读它以指导你的方法。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-108">If your organization has only one or two sites, you might not need to complete all the details provided in this article, but you should read through it to guide your approach.</span></span>

<!--ENDOFSECTION-->

## <a name="deployment-model"></a><span data-ttu-id="cd4ef-109">部署模型</span><span class="sxs-lookup"><span data-stu-id="cd4ef-109">Deployment model</span></span> 

<span data-ttu-id="cd4ef-110">与转换组织中人员工作方式的任何技术实现一样, 选择执行部署的正确方式将大大影响云语音实现的成功。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-110">As with any technology implementation that transforms the way people work in your organization, choosing the right way to undertake the deployment will greatly influence the success of your cloud voice implementation.</span></span>

<span data-ttu-id="cd4ef-111">潜在的部署模型包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="cd4ef-111">Potential deployment models include the following:</span></span>

-   <span data-ttu-id="cd4ef-112">**每个网站:** 此模型适用于组织地理位置分散的情况, 并且分支具有大量员工。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-112">**Per site:** This model is suitable for cases where your organization is geographically dispersed, and branches have significant numbers of employees.</span></span> <span data-ttu-id="cd4ef-113">但是, 此部署模型可能会中断部门员工在多个地点分布的部门内的通信。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-113">However, this deployment model can potentially disrupt communication within departments where department employees are spread across several locations.</span></span>

-   <span data-ttu-id="cd4ef-114">**每个部门**: 此模型通常是适用于中等规模公司的更佳选项, 可确保所涉及的部门具有相同的体验。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-114">**Per division**: This model is usually the better option for medium-size companies and ensures that departments involved have the same experience.</span></span>

-   <span data-ttu-id="cd4ef-115">**一次全公司:** 此模型通常是小型公司的最佳选择, 其中所有员工都可以从部署的第一天获得相同的体验。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-115">**Whole company at once:** This model is typically the best option for small companies, where all employees get the same experience from day one of the deployment.</span></span>


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="cd4ef-116">决策点</span><span class="sxs-lookup"><span data-stu-id="cd4ef-116">Decision points</span></span></td><td><ul><li><span data-ttu-id="cd4ef-117">确定适用于你的组织的团队部署执行模型。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-117">Decide the Teams deployment execution model that’s applicable to your organization.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="cd4ef-118">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd4ef-118">Next steps</span></span></td><td><ul><li><span data-ttu-id="cd4ef-119">记录你选择的团队部署执行模型, 并包括业务和技术论证。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-119">Document the Teams deployment execution model you’ve chosen, and include business and technical justifications.</span></span></li></ul></td></tr></table>

## <a name="raci-modeling"></a><span data-ttu-id="cd4ef-120">RACI 建模</span><span class="sxs-lookup"><span data-stu-id="cd4ef-120">RACI modeling</span></span>

<span data-ttu-id="cd4ef-121">若要确保对项目中的哪些人负责你对项目的负责, 请使用责任作业矩阵 (也称为 "RACI"), 即 "负责"、"有责任的"、"咨询" 和 "已通知"-矩阵。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-121">To ensure that you’ve got clarity for who is responsible for what in your project, use a responsibility assignment matrix (also known as a RACI—responsible, accountable, consulted, and informed—matrix).</span></span> <span data-ttu-id="cd4ef-122">列出负责每个任务的人员或组, 以及要在决策制定过程中咨询的利益干系人, 以及在整个项目执行过程中通知的风险承担者的每个决策和操作。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-122">List the person or group who is responsible and accountable for each task, along with stakeholders to be consulted in the decision-making process, and stakeholders to be informed of each decision and action throughout the project execution.</span></span>

<span data-ttu-id="cd4ef-123">以下是云语音实现的 RACI 矩阵的示例。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-123">The following is an example of a RACI matrix for a cloud voice implementation.</span></span>

| <span data-ttu-id="cd4ef-124">活动/角色</span><span class="sxs-lookup"><span data-stu-id="cd4ef-124">Activity/Role</span></span>                                         | <span data-ttu-id="cd4ef-125">项目主管</span><span class="sxs-lookup"><span data-stu-id="cd4ef-125">Project Lead</span></span> | <span data-ttu-id="cd4ef-126">协作主管/架构师</span><span class="sxs-lookup"><span data-stu-id="cd4ef-126">Collaboration Lead/Architect</span></span> | <span data-ttu-id="cd4ef-127">顾问</span><span class="sxs-lookup"><span data-stu-id="cd4ef-127">Consultant</span></span> | <span data-ttu-id="cd4ef-128">变更管理/采用专业人员</span><span class="sxs-lookup"><span data-stu-id="cd4ef-128">Change Management/Adoption Specialist</span></span> | <span data-ttu-id="cd4ef-129">业务单位代表</span><span class="sxs-lookup"><span data-stu-id="cd4ef-129">Business Unit Representatives</span></span> |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| <span data-ttu-id="cd4ef-130">计划演示动员会调用</span><span class="sxs-lookup"><span data-stu-id="cd4ef-130">Program presentation kickoff call</span></span>                     | <span data-ttu-id="cd4ef-131">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-131">R, A</span></span>         | <span data-ttu-id="cd4ef-132">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-132">C</span></span>                            |            |                                       |                               |
| <span data-ttu-id="cd4ef-133">设置通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="cd4ef-133">Set up Call Quality Dashboard</span></span>                         | <span data-ttu-id="cd4ef-134">如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-134">I</span></span>            | <span data-ttu-id="cd4ef-135">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-135">C</span></span>                            | <span data-ttu-id="cd4ef-136">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-136">R, A</span></span>       |                                       |                               |
| <span data-ttu-id="cd4ef-137">在动员通话期间共享发现问卷</span><span class="sxs-lookup"><span data-stu-id="cd4ef-137">Share the Discovery Questionnaire during kickoff call</span></span> | <span data-ttu-id="cd4ef-138">如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-138">I</span></span>            | <span data-ttu-id="cd4ef-139">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-139">C</span></span>                            | <span data-ttu-id="cd4ef-140">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-140">R, A</span></span>       |                                       |                               |
| <span data-ttu-id="cd4ef-141">构想阶段动员</span><span class="sxs-lookup"><span data-stu-id="cd4ef-141">Envision phase kickoff</span></span>                                | <span data-ttu-id="cd4ef-142">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-142">R, A</span></span>         | <span data-ttu-id="cd4ef-143">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-143">C</span></span>                            |            |                                       |                               |
| <span data-ttu-id="cd4ef-144">业务使用案例研讨会</span><span class="sxs-lookup"><span data-stu-id="cd4ef-144">Business use cases workshop</span></span>                           | <span data-ttu-id="cd4ef-145">A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-145">A</span></span>            |                              |            | <span data-ttu-id="cd4ef-146">R</span><span class="sxs-lookup"><span data-stu-id="cd4ef-146">R</span></span>                                     | <span data-ttu-id="cd4ef-147">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-147">C</span></span>                             |
| <span data-ttu-id="cd4ef-148">查看 "发现调查表"</span><span class="sxs-lookup"><span data-stu-id="cd4ef-148">Review the Discovery Questionnaire</span></span>                    |              | <span data-ttu-id="cd4ef-149">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-149">R, A</span></span>                         | <span data-ttu-id="cd4ef-150">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-150">C</span></span>          |                                       |                               |
| <span data-ttu-id="cd4ef-151">体系结构研讨会</span><span class="sxs-lookup"><span data-stu-id="cd4ef-151">Architecture workshop</span></span>                                 | <span data-ttu-id="cd4ef-152">如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-152">I</span></span>            | <span data-ttu-id="cd4ef-153">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-153">R, A</span></span>                         | <span data-ttu-id="cd4ef-154">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-154">C</span></span>          |                                       |                               |
| <span data-ttu-id="cd4ef-155">采纳用户方案构想阶段研讨会</span><span class="sxs-lookup"><span data-stu-id="cd4ef-155">Adoption user scenarios Envision phase workshop</span></span>       | <span data-ttu-id="cd4ef-156">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-156">C</span></span>            | <span data-ttu-id="cd4ef-157">如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-157">I</span></span>                            | <span data-ttu-id="cd4ef-158">A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-158">A</span></span>          | <span data-ttu-id="cd4ef-159">R</span><span class="sxs-lookup"><span data-stu-id="cd4ef-159">R</span></span>                                     |                               |
| <span data-ttu-id="cd4ef-160">采纳成功研讨会</span><span class="sxs-lookup"><span data-stu-id="cd4ef-160">Adoption success workshop</span></span>                             |              |                              | <span data-ttu-id="cd4ef-161">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-161">R, A</span></span>       | <span data-ttu-id="cd4ef-162">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-162">C</span></span>                                     |                               |
| <span data-ttu-id="cd4ef-163">客户端和设备准备情况研讨会</span><span class="sxs-lookup"><span data-stu-id="cd4ef-163">Client and device readiness workshop</span></span>                  | <span data-ttu-id="cd4ef-164">如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-164">I</span></span>            |                              | <span data-ttu-id="cd4ef-165">R、A</span><span class="sxs-lookup"><span data-stu-id="cd4ef-165">R, A</span></span>       | <span data-ttu-id="cd4ef-166">C</span><span class="sxs-lookup"><span data-stu-id="cd4ef-166">C</span></span>                                     |                               |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="cd4ef-167">决策点</span><span class="sxs-lookup"><span data-stu-id="cd4ef-167">Decision points</span></span></td><td><ul><li><span data-ttu-id="cd4ef-168">确定与云语音实现项目相关的活动/角色。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-168">Decide the activities/roles relevant to the cloud voice implementation project.</span></span></li><li><span data-ttu-id="cd4ef-169">确定要分配给云语音实现项目的责任分配矩阵 (RACI 矩阵) 的团队或人员。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-169">Decide the teams or people to be assigned to the responsibility assignment matrix (RACI matrix) of the cloud voice implementation project.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="cd4ef-170">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd4ef-170">Next steps</span></span></td><td><ul><li><span data-ttu-id="cd4ef-171">记录 RACI 矩阵。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-171">Document the RACI matrix.</span></span></li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a><span data-ttu-id="cd4ef-172">季度执行计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-172">Quarterly execution plan</span></span>

<span data-ttu-id="cd4ef-173">若要在可管理的工作块中执行云语音部署, 我们建议你根据目标密钥结果 (OKRs)、你选择的部署模型和你的组织的项目执行功能来创建季度语音部署。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-173">To execute the cloud voice deployment in manageable chunks of work, we recommend that you create a quarterly execution plan based on your objective key results (OKRs), the deployment model you’ve chosen, and the project execution capability of your organization.</span></span>

<span data-ttu-id="cd4ef-174">这样, 您就可以按季度跟踪进度, 根据需要修订计划, 并根据组织的执行容量部署云语音功能。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-174">This way you can track progress on a quarterly basis, revise the plan if needed, and deploy cloud voice capabilities based on your organization’s capacity to execute.</span></span>

<span data-ttu-id="cd4ef-175">如果你的组织只有一个或两个网站, 你可能不需要季度执行计划, 因为你希望在短时间内完全部署。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-175">If your organization has only one or two sites, you might not need a quarterly execution plan because you’d expect to be fully deployed in a short period of time.</span></span>

<span data-ttu-id="cd4ef-176">下面是云语音实现的 Envision 阶段的季度执行计划的示例。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-176">The following is an example of a quarterly execution plan for the Envision phase of a cloud voice implementation.</span></span>

| <span data-ttu-id="cd4ef-177">站点/部门</span><span class="sxs-lookup"><span data-stu-id="cd4ef-177">Site/division</span></span>                            | <span data-ttu-id="cd4ef-178">员工数</span><span class="sxs-lookup"><span data-stu-id="cd4ef-178">Number of employees</span></span> | <span data-ttu-id="cd4ef-179">音频会议</span><span class="sxs-lookup"><span data-stu-id="cd4ef-179">Audio Conferencing</span></span> | <span data-ttu-id="cd4ef-180">电话系统</span><span class="sxs-lookup"><span data-stu-id="cd4ef-180">Phone System</span></span>                    | <span data-ttu-id="cd4ef-181">要执行的季度</span><span class="sxs-lookup"><span data-stu-id="cd4ef-181">Quarter to execute</span></span> |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| <span data-ttu-id="cd4ef-182">美国: 纽约</span><span class="sxs-lookup"><span data-stu-id="cd4ef-182">US: New York</span></span>                             | <span data-ttu-id="cd4ef-183">2000</span><span class="sxs-lookup"><span data-stu-id="cd4ef-183">2000</span></span>                | <span data-ttu-id="cd4ef-184">是</span><span class="sxs-lookup"><span data-stu-id="cd4ef-184">Yes</span></span>                | <span data-ttu-id="cd4ef-185">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="cd4ef-185">Phone System with Calling Plans</span></span> | <span data-ttu-id="cd4ef-186">第1季度 CY2018</span><span class="sxs-lookup"><span data-stu-id="cd4ef-186">Q1 CY2018</span></span>          |
| <span data-ttu-id="cd4ef-187">爱尔兰: 都柏林</span><span class="sxs-lookup"><span data-stu-id="cd4ef-187">Ireland: Dublin</span></span>                          | <span data-ttu-id="cd4ef-188">300</span><span class="sxs-lookup"><span data-stu-id="cd4ef-188">300</span></span>                 | <span data-ttu-id="cd4ef-189">是</span><span class="sxs-lookup"><span data-stu-id="cd4ef-189">Yes</span></span>                | <span data-ttu-id="cd4ef-190">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="cd4ef-190">Phone System with Calling Plans</span></span> | <span data-ttu-id="cd4ef-191">第1季度 CY2018</span><span class="sxs-lookup"><span data-stu-id="cd4ef-191">Q1 CY2018</span></span>          |
| <span data-ttu-id="cd4ef-192">奥地利: 维也纳</span><span class="sxs-lookup"><span data-stu-id="cd4ef-192">Austria: Vienna</span></span>                          | <span data-ttu-id="cd4ef-193">500</span><span class="sxs-lookup"><span data-stu-id="cd4ef-193">500</span></span>                 | <span data-ttu-id="cd4ef-194">是</span><span class="sxs-lookup"><span data-stu-id="cd4ef-194">Yes</span></span>                | <span data-ttu-id="cd4ef-195">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="cd4ef-195">Phone System Direct Routing</span></span>     | <span data-ttu-id="cd4ef-196">第2季度 CY2018</span><span class="sxs-lookup"><span data-stu-id="cd4ef-196">Q2 CY2018</span></span>          |
| <span data-ttu-id="cd4ef-197">意大利: Milan</span><span class="sxs-lookup"><span data-stu-id="cd4ef-197">Italy: Milan</span></span>                             | <span data-ttu-id="cd4ef-198">200</span><span class="sxs-lookup"><span data-stu-id="cd4ef-198">200</span></span>                 | <span data-ttu-id="cd4ef-199">是</span><span class="sxs-lookup"><span data-stu-id="cd4ef-199">Yes</span></span>                | <span data-ttu-id="cd4ef-200">不适用</span><span class="sxs-lookup"><span data-stu-id="cd4ef-200">N/A</span></span>                             | <span data-ttu-id="cd4ef-201">第2季度 CY2018</span><span class="sxs-lookup"><span data-stu-id="cd4ef-201">Q2 CY2018</span></span>          |
| <span data-ttu-id="cd4ef-202">南美洲: 巴西</span><span class="sxs-lookup"><span data-stu-id="cd4ef-202">South America: Brazil</span></span>                    | <span data-ttu-id="cd4ef-203">1500</span><span class="sxs-lookup"><span data-stu-id="cd4ef-203">1500</span></span>                | <span data-ttu-id="cd4ef-204">是</span><span class="sxs-lookup"><span data-stu-id="cd4ef-204">Yes</span></span>                | <span data-ttu-id="cd4ef-205">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="cd4ef-205">Phone System Direct Routing</span></span>     | <span data-ttu-id="cd4ef-206">第2季度 CY2018</span><span class="sxs-lookup"><span data-stu-id="cd4ef-206">Q2 CY2018</span></span>          |
| <span data-ttu-id="cd4ef-207">印度: 新德里</span><span class="sxs-lookup"><span data-stu-id="cd4ef-207">India: Delhi</span></span>                             | <span data-ttu-id="cd4ef-208">7000</span><span class="sxs-lookup"><span data-stu-id="cd4ef-208">7000</span></span>                | <span data-ttu-id="cd4ef-209">是</span><span class="sxs-lookup"><span data-stu-id="cd4ef-209">Yes</span></span>                | <span data-ttu-id="cd4ef-210">不适用</span><span class="sxs-lookup"><span data-stu-id="cd4ef-210">N/A</span></span>                             | <span data-ttu-id="cd4ef-211">第3季度 CY2018</span><span class="sxs-lookup"><span data-stu-id="cd4ef-211">Q3 CY2018</span></span>          |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="cd4ef-212">决策点</span><span class="sxs-lookup"><span data-stu-id="cd4ef-212">Decision points</span></span></td><td><ul><li><span data-ttu-id="cd4ef-213">确定 "季度执行计划" 以实现目标键结果 (OKRs)。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-213">Decide the quarterly execution plan to achieve the objective key results (OKRs).</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="cd4ef-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd4ef-214">Next steps</span></span></td><td><ul><li><span data-ttu-id="cd4ef-215">记录季度执行计划。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-215">Document the quarterly execution plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a><span data-ttu-id="cd4ef-216">沟通和管理计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-216">Communications and governance plan</span></span>

<span data-ttu-id="cd4ef-217">若要让项目利益干系人与部署进度保持最新, 你需要制定一套计划, 了解如何在核心项目团队成员以及利益干系人讨论与项目状态相关的问题？针对已建立的 KSIs、操作指标和战略目标的项目里程碑、阻止和各种评价。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-217">To keep project stakeholders up to date with the progress of the deployment, you need to establish a plan for how communications will take place among the core project team members and with the stakeholders to discuss matters relating to status of the project, key milestones, blockers, and various reviews of the project against established KSIs, operational metrics, and strategic goals.</span></span>

<span data-ttu-id="cd4ef-218">下面是您可以在云语音实现项目中利用的通信和管理计划的示例。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-218">The following is an example of a communications and governance plan that you can leverage in your cloud voice implementation project.</span></span>

| <span data-ttu-id="cd4ef-219">类型</span><span class="sxs-lookup"><span data-stu-id="cd4ef-219">Type</span></span>                                        | <span data-ttu-id="cd4ef-220">目的</span><span class="sxs-lookup"><span data-stu-id="cd4ef-220">Goals</span></span>                                                                                                                                                      | <span data-ttu-id="cd4ef-221">者</span><span class="sxs-lookup"><span data-stu-id="cd4ef-221">Participants</span></span> | <span data-ttu-id="cd4ef-222">天/时间</span><span class="sxs-lookup"><span data-stu-id="cd4ef-222">Days/time</span></span>                                     | <span data-ttu-id="cd4ef-223">位置</span><span class="sxs-lookup"><span data-stu-id="cd4ef-223">Location</span></span>             | <span data-ttu-id="cd4ef-224">会议所有者</span><span class="sxs-lookup"><span data-stu-id="cd4ef-224">Meeting owner</span></span> |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| <span data-ttu-id="cd4ef-225">Project standup 通话</span><span class="sxs-lookup"><span data-stu-id="cd4ef-225">Project standup calls</span></span>                       | <span data-ttu-id="cd4ef-226">项目状态的同步, 跟踪关键里程碑和阻止程序</span><span class="sxs-lookup"><span data-stu-id="cd4ef-226">Sync on status of the project, track key milestones and blockers</span></span>                                                                                           | <span data-ttu-id="cd4ef-227">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-227">TBA</span></span>          | <span data-ttu-id="cd4ef-228">星期一、星期二、星期三、星期四下午5点 PST</span><span class="sxs-lookup"><span data-stu-id="cd4ef-228">Monday, Tuesday, Wednesday, Thursday 5 PM PST</span></span> | <span data-ttu-id="cd4ef-229">虚拟</span><span class="sxs-lookup"><span data-stu-id="cd4ef-229">Virtual</span></span>              | <span data-ttu-id="cd4ef-230">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-230">TBA</span></span>           |
| <span data-ttu-id="cd4ef-231">每周筹划指导委员会</span><span class="sxs-lookup"><span data-stu-id="cd4ef-231">Weekly steering committee</span></span>                   | <span data-ttu-id="cd4ef-232">查看云语音项目的状态, 向主管人员报告, 提出需要管理人员帮助解决的问题</span><span class="sxs-lookup"><span data-stu-id="cd4ef-232">Review status of the cloud voice project, report to executives, raise issues that require executive help to resolve</span></span>                                        | <span data-ttu-id="cd4ef-233">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-233">TBA</span></span>          | <span data-ttu-id="cd4ef-234">每个星期五上午11点 PST</span><span class="sxs-lookup"><span data-stu-id="cd4ef-234">Every Friday 11 AM PST</span></span>                        | <span data-ttu-id="cd4ef-235">虚拟</span><span class="sxs-lookup"><span data-stu-id="cd4ef-235">Virtual</span></span>              | <span data-ttu-id="cd4ef-236">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-236">TBA</span></span>           |
| <span data-ttu-id="cd4ef-237">每月项目业务/操作评审</span><span class="sxs-lookup"><span data-stu-id="cd4ef-237">Monthly project business/operational review</span></span> | <span data-ttu-id="cd4ef-238">通过扩展的利益干系人、主要联系点和执行发起人检查项目状态;查看部署计划、KSIs 和操作指标</span><span class="sxs-lookup"><span data-stu-id="cd4ef-238">Check project status with extended stakeholders, main points of contact, and executive sponsors; review the deployment plan, KSIs, and operational metrics</span></span> | <span data-ttu-id="cd4ef-239">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-239">TBA</span></span>          | <span data-ttu-id="cd4ef-240">每月的第二个星期二</span><span class="sxs-lookup"><span data-stu-id="cd4ef-240">Second Tuesday of month</span></span>                       | <span data-ttu-id="cd4ef-241">虚拟或个人</span><span class="sxs-lookup"><span data-stu-id="cd4ef-241">Virtual or in person</span></span> | <span data-ttu-id="cd4ef-242">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-242">TBA</span></span>           |
| <span data-ttu-id="cd4ef-243">季度商业考评 (QBR)</span><span class="sxs-lookup"><span data-stu-id="cd4ef-243">Quarterly business review (QBR)</span></span>             | <span data-ttu-id="cd4ef-244">检查项目状态并根据战略目标、KSIs 和运营指标查看进度;必要时重新访问计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-244">Check project status and review progress against strategic goals, KSIs, and operational metrics; revisit plans if required</span></span>                                 | <span data-ttu-id="cd4ef-245">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-245">TBA</span></span>          | <span data-ttu-id="cd4ef-246">每个季度的最后一个星期四</span><span class="sxs-lookup"><span data-stu-id="cd4ef-246">Last Thursday of every quarter</span></span>                | <span data-ttu-id="cd4ef-247">人</span><span class="sxs-lookup"><span data-stu-id="cd4ef-247">In person</span></span>            | <span data-ttu-id="cd4ef-248">TBA</span><span class="sxs-lookup"><span data-stu-id="cd4ef-248">TBA</span></span>           |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="cd4ef-249">决策点</span><span class="sxs-lookup"><span data-stu-id="cd4ef-249">Decision points</span></span></td><td><ul><li><span data-ttu-id="cd4ef-250">确定通信和监管计划, 包括定期状态更新 (每天、每周、每月或每季度) 的频率、用于实施状态更新会议的方法和每个会议的所有者。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-250">Decide the communications and governance plan, including the frequency of regular status updates (daily, weekly, monthly, or quarterly), methods for conducting the status update meetings, and the owner of each meeting.</span></span></li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="cd4ef-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd4ef-251">Next steps</span></span></td><td><ul><li><span data-ttu-id="cd4ef-252">记录通信和管理计划。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-252">Document the communications and governance plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a><span data-ttu-id="cd4ef-253">完成我的成功计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-253">Finalize my success plan</span></span>

<span data-ttu-id="cd4ef-254">成功计划是你在构想阶段创建的文档的摘要。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-254">A success plan is the summary of the documentation you created in the Envision phase.</span></span>

<span data-ttu-id="cd4ef-255">成功计划为项目团队提供了项目团队, 其中包括 FastTrack 或部署合作伙伴-通过使用呼叫计划服务实施音频会议或电话系统, 可实现组织的目标的充足信息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-255">The success plan gives the project team—which can include FastTrack or a deployment partner—sufficient information to realize your organization’s goals with implementing the Audio Conferencing or Phone System with Calling Plan service.</span></span>

<span data-ttu-id="cd4ef-256">通常情况下, 成功计划包含以下主要部分, 这些主要部分将通过构想阶段进行了处理:</span><span class="sxs-lookup"><span data-stu-id="cd4ef-256">In general, a success plan contains the following main sections, many which you will have worked on through the Envision phase:</span></span>

-   <span data-ttu-id="cd4ef-257">业务案例</span><span class="sxs-lookup"><span data-stu-id="cd4ef-257">Business case</span></span>

-   <span data-ttu-id="cd4ef-258">服务就绪</span><span class="sxs-lookup"><span data-stu-id="cd4ef-258">Service readiness</span></span>

-   <span data-ttu-id="cd4ef-259">服务决策</span><span class="sxs-lookup"><span data-stu-id="cd4ef-259">Service decisions</span></span>

-   <span data-ttu-id="cd4ef-260">执行计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-260">Execution plan</span></span>

-   <span data-ttu-id="cd4ef-261">采用计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-261">Adoption plan</span></span>

-   <span data-ttu-id="cd4ef-262">运营计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-262">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="cd4ef-263">业务案例</span><span class="sxs-lookup"><span data-stu-id="cd4ef-263">Business case</span></span>

<span data-ttu-id="cd4ef-264">业务使用案例、利益干系人、OKRs 和 KSIs、风险登记和项目日程表的列表通常构成了业务案例所需的大量信息。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-264">Business use cases, the list of stakeholders, OKRs and KSIs, risk registers, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="cd4ef-265">应将这些内容记录为成功计划的一部分。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-265">You should document these as part of your success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="cd4ef-266">服务就绪</span><span class="sxs-lookup"><span data-stu-id="cd4ef-266">Service readiness</span></span>

<span data-ttu-id="cd4ef-267">你的环境评估提供初始信息, 以确定你的组织的技术准备情况, 以便通过呼叫计划实现音频会议和/或电话系统。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-267">Your environmental assessment provides the initial information required to determine your organization’s technical readiness to implement Audio Conferencing and/or Phone System with Calling Plan.</span></span>

<span data-ttu-id="cd4ef-268">此处包括您的服务准备情况评估以及用于解决通过环境评估发现的需要补救的领域的计划。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-268">Included here is your service readiness assessment and the plan to address areas that need remediation that you discovered through environmental assessment.</span></span>

### <a name="service-decisions"></a><span data-ttu-id="cd4ef-269">服务决策</span><span class="sxs-lookup"><span data-stu-id="cd4ef-269">Service decisions</span></span>

<span data-ttu-id="cd4ef-270">记录如何为组织的通话计划服务技术实施计划音频会议或电话系统。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-270">Document how you planned the Audio Conferencing or Phone System with Calling Plan service technical implementation for your organization.</span></span>

### <a name="execution-plan"></a><span data-ttu-id="cd4ef-271">执行计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-271">Execution plan</span></span>

<span data-ttu-id="cd4ef-272">记录如何计划项目在整个组织中实现解决方案的执行。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-272">Document how you planned the execution of the project to implement the solution throughout your organization.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="cd4ef-273">采用计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-273">Adoption plan</span></span>

<span data-ttu-id="cd4ef-274">在执行采纳准备情况评估后, 项目团队需要提出一套全面的沟通计划、一个培训计划以及预启动、启动和启动后的采纳活动计划。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-274">After you perform your adoption readiness assessment, the project team needs to come up with a comprehensive set of communication plans, a training plan, and plans for pre-launch, launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="cd4ef-275">标识支持采纳活动 (如传单、欢迎电子邮件和培训资料) 的资源, 以及满足组织要求所需的自定义。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-275">Identify resources to support adoption activities such as flyers, welcome emails, and training materials, along with any customizations you’ll need to meet your organization’s requirements.</span></span>

<span data-ttu-id="cd4ef-276">从[Microsoft 团队客户成功工具包](https://www.microsoft.com/download/details.aspx?id=54244)下载采纳活动的模板。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-276">Download templates for adoption activities from the [Microsoft Teams Customer Success Kit](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="cd4ef-277">运营计划</span><span class="sxs-lookup"><span data-stu-id="cd4ef-277">Operational plan</span></span>

<span data-ttu-id="cd4ef-278">映射操作角色的操作将建立角色和职责, 以及分配给每个操作角色的团队, 您将需要支持音频会议的实现。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-278">The exercise of mapping operational roles will establish roles and responsibilities, and the teams assigned to each operational role, that you’ll need to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="cd4ef-279">您需要完成此操作并将运营计划作为成功计划的一部分包括在内, 以确保解决方案的操作准备就绪。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-279">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="cd4ef-280">决策点</span><span class="sxs-lookup"><span data-stu-id="cd4ef-280">Decision points</span></span></td><td><ul><li><span data-ttu-id="cd4ef-281">确定你将如何记录整个成功计划, 以便提供云语音工作负荷。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-281">Decide how you will document your entire success plan for delivering your cloud voice workloads.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="cd4ef-282">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd4ef-282">Next steps</span></span></td><td><ul><li><span data-ttu-id="cd4ef-283">确认成功计划的所有组件均已记录。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-283">Confirm all components of your success plan have been documented.</span></span></li><li><span data-ttu-id="cd4ef-284">将成功计划的单个组件聚合到单个摘要文档中 (可选)。</span><span class="sxs-lookup"><span data-stu-id="cd4ef-284">Aggregate individual components of your success plan into a single summary document (optional).</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
