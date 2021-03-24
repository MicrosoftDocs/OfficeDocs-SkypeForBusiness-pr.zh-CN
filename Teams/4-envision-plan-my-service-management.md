---
title: 规划 Microsoft Teams 服务管理
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 通过规划运营角色并分配质量保证者，提供和维护高质量的部署。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b940ad9347e2a91a3816eb95817e59368692290
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094740"
---
# <a name="plan-my-service-management"></a><span data-ttu-id="9777a-103">规划服务管理</span><span class="sxs-lookup"><span data-stu-id="9777a-103">Plan my service management</span></span>

<span data-ttu-id="9777a-104">本文概述了交付和维护高质量的 Microsoft Teams 部署所需的要求。</span><span class="sxs-lookup"><span data-stu-id="9777a-104">This article gives an overview of the requirements that are necessary to deliver and maintain a high-quality Microsoft Teams deployment.</span></span> <span data-ttu-id="9777a-105">在首次试点或生产部署之前，可以通过在展望阶段规划服务管理和质量来帮助确保部署得以成功。</span><span class="sxs-lookup"><span data-stu-id="9777a-105">You can help ensure a successful deployment by planning for service management and quality during the Envision phase, before your first pilot or production deployment.</span></span>

## <a name="service-management-for-teams"></a><span data-ttu-id="9777a-106">Teams 服务管理</span><span class="sxs-lookup"><span data-stu-id="9777a-106">Service management for Teams</span></span>

<span data-ttu-id="9777a-107">服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。</span><span class="sxs-lookup"><span data-stu-id="9777a-107">Service management is a broad topic that covers day-to-day operations of the Microsoft Teams service after it has been deployed and enabled for users.</span></span> <span data-ttu-id="9777a-108">Teams 服务包括 Microsoft 365 或 Office 365，以及在本地部署的基础结构组件 (例如网络) 。</span><span class="sxs-lookup"><span data-stu-id="9777a-108">The Teams service encompasses Microsoft 365 or Office 365 and the infrastructure components that are deployed on-premises (for example, networking).</span></span>

<span data-ttu-id="9777a-109">对于大多数组织而言，服务管理概念很可能不是一个新概念。</span><span class="sxs-lookup"><span data-stu-id="9777a-109">The notion of service management is most likely not a new concept for most organizations.</span></span> <span data-ttu-id="9777a-110">你可能已经实施了与现有服务关联的流程和任务。</span><span class="sxs-lookup"><span data-stu-id="9777a-110">You probably have already implemented processes and tasks that are associated with existing services.</span></span> <span data-ttu-id="9777a-111">尽管如此，当你现在规划服务管理以在将来支持 Microsoft Teams 时，你可能会扩大已实施的方面。</span><span class="sxs-lookup"><span data-stu-id="9777a-111">That said, you can probably augment what you have in place when you plan for service management today to support Microsoft Teams in the future.</span></span>

<span data-ttu-id="9777a-112">服务管理包含管理 Microsoft Teams 端到端时涉及的所有活动和流程。</span><span class="sxs-lookup"><span data-stu-id="9777a-112">Service management encompasses all the activities and processes involved in managing Microsoft Teams end to end.</span></span> <span data-ttu-id="9777a-113">服务管理的一些组件（Microsoft 365 或 Office 365 服务本身包含的基础结构组件）由 Microsoft 负责，而客户对其用户负责管理 Teams、网络和他们提供的终结点的各个方面。</span><span class="sxs-lookup"><span data-stu-id="9777a-113">Some components of service management—the infrastructure components that the Microsoft 365 or Office 365 service itself comprises—are Microsoft’s responsibility, whereas the customer is accountable to its users to manage the various aspects of Teams, the network, and endpoints they provide.</span></span>
<span data-ttu-id="9777a-114">有关客户对 Teams 服务管理的责任及其与影响用户体验质量的关键组件之间的关联的完整讨论，请参阅服务 [管理和质量规划](./prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="9777a-114">For a complete discussion of the customer responsibility for Teams service management and how it relates to the key components that underpin the quality of the user experience, see [Plan for service management and quality](./prepare-network.md).</span></span>

<span data-ttu-id="9777a-115">![质量的三个组件示意图](media/plan-my-service-management-image1.png "质量的三个组件（Microsoft 365 或 Office 365 服务、网络和终结点）的示意图，以及服务管理如何与这三个组件重叠。")</span><span class="sxs-lookup"><span data-stu-id="9777a-115">![Diagram of the three components of quality](media/plan-my-service-management-image1.png "Diagram of the three components of quality--Microsoft 365 or Office 365 service, network, and endpoints--and how service management overlaps all three.")</span></span>

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a><span data-ttu-id="9777a-116">《操作指南》简介</span><span class="sxs-lookup"><span data-stu-id="9777a-116">Introduction to the Operations Guide</span></span> 

<span data-ttu-id="9777a-117">**什么内容**、**什么人** 和 **什么方式** 是在讨论服务质量时需要回答的三个重要问题。</span><span class="sxs-lookup"><span data-stu-id="9777a-117">**What**, **Who**, and **How** are three important questions that need to be answered when it comes to service management.</span></span>

<span data-ttu-id="9777a-118">你可以使用《[操作指南](./1-drive-value-operate-my-service.md)》帮助你解决所有这三个问题。</span><span class="sxs-lookup"><span data-stu-id="9777a-118">You can use the [Operations Guide](./1-drive-value-operate-my-service.md) to help you address all three of these questions.</span></span> <span data-ttu-id="9777a-119">该指南提供了每天、每周、每月及按需执行的活动列表。</span><span class="sxs-lookup"><span data-stu-id="9777a-119">The guide provides a list of activities to be performed on a daily, weekly, monthly, and as-needed basis.</span></span> <span data-ttu-id="9777a-120">这些活动和任务对于维护高质量 Teams 部署至关重要。</span><span class="sxs-lookup"><span data-stu-id="9777a-120">These activities and tasks are critical for maintaining a high-quality Teams deployment.</span></span> <span data-ttu-id="9777a-121">确定谁将负责在服务管理中执行特定活动是在展望阶段早期需要执行以确保部署得以成功的规划的关键方面。</span><span class="sxs-lookup"><span data-stu-id="9777a-121">Determining who will be responsible for performing specific activities in service management is a critical aspect of your planning that you need to do early in the Envision phase to ensure a successful deployment.</span></span> <span data-ttu-id="9777a-122">在确定了任务和活动后，需要你将其分配到的小组或个人了解并遵循这些任务和活动。</span><span class="sxs-lookup"><span data-stu-id="9777a-122">After you’ve figured out the tasks and activities, they need to be understood and followed by the groups or individuals that you assign to them.</span></span> <span data-ttu-id="9777a-123">《操作指南》提供了有关如何执行每个任务的知识和指导，以及/或外部内容的参考。</span><span class="sxs-lookup"><span data-stu-id="9777a-123">The Operations Guide provides knowledge and guidance for how to perform each of the tasks, and/or references to outside content.</span></span>

## <a name="plan-for-operational-role-mapping"></a><span data-ttu-id="9777a-124">规划操作角色映射</span><span class="sxs-lookup"><span data-stu-id="9777a-124">Plan for operational role mapping</span></span>

<span data-ttu-id="9777a-125">早期规划服务管理是一个关键的里程碑，因为在启用首批试点用户时即开始操作阶段。</span><span class="sxs-lookup"><span data-stu-id="9777a-125">Planning for service management early is a critical milestone, because the operations phase begins when the first pilot users are enabled.</span></span> <span data-ttu-id="9777a-126">项目团队必须审阅并同意所需的任务和活动，确定负责每个运营任务的团队，以及得到各个团队的承诺和签字认可。</span><span class="sxs-lookup"><span data-stu-id="9777a-126">The project team must review and agree on the tasks and activities required, identify the team that’s responsible for each operational task, and then get a commitment and sign-off from each respective team.</span></span>

<span data-ttu-id="9777a-127">在完成签字认可后，负责团队必须开始执行这些角色和职责。</span><span class="sxs-lookup"><span data-stu-id="9777a-127">After sign-off is complete, the responsible team must then start operationalizing these roles and responsibilities.</span></span> <span data-ttu-id="9777a-128">这可能包括培训和就绪工作、更新人员配置模型或确保外部合作伙伴已准备好交付。</span><span class="sxs-lookup"><span data-stu-id="9777a-128">This might include training and readiness, updating the staffing model, or ensuring that external partners are ready to deliver.</span></span>

<span data-ttu-id="9777a-129">在"构想"阶段的早期映射操作角色可让所有团队在试点期间启动其操作任务并提升操作，并确保部署开始后一切准备就绪。</span><span class="sxs-lookup"><span data-stu-id="9777a-129">Mapping operational roles early in the Envision phase enables all teams to start their operational tasks during the pilot and ramp up operations and make sure that everything is ready after the deployment starts.</span></span>

<span data-ttu-id="9777a-130">《操作指南》提供了映射到在大多数方案中应该会有效的典型角色的常见任务列表。</span><span class="sxs-lookup"><span data-stu-id="9777a-130">The Operations Guide provides a list of common tasks mapped to typical roles that should be valid in most scenarios.</span></span> <span data-ttu-id="9777a-131">你需要自定义这些职责以适用于你的组织。</span><span class="sxs-lookup"><span data-stu-id="9777a-131">You need to customize these responsibilities to work for your organization.</span></span>

>[!TIP]
><span data-ttu-id="9777a-132">下面是一个模板示例，用于记录为支持此项目而执行的操作角色映射练习的结果。</span><span class="sxs-lookup"><span data-stu-id="9777a-132">The following is an example of a template to document the result of operational roles mapping exercise that you performed to support this project.</span></span>


|<span data-ttu-id="9777a-133">操作角色</span><span class="sxs-lookup"><span data-stu-id="9777a-133">Operational Role</span></span> |<span data-ttu-id="9777a-134">说明</span><span class="sxs-lookup"><span data-stu-id="9777a-134">Description</span></span> |<span data-ttu-id="9777a-135">团队</span><span class="sxs-lookup"><span data-stu-id="9777a-135">Team</span></span> |<span data-ttu-id="9777a-136">联系人详细信息</span><span class="sxs-lookup"><span data-stu-id="9777a-136">Contact Details</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="9777a-137">服务所有者</span><span class="sxs-lookup"><span data-stu-id="9777a-137">Service Owner</span></span>|<span data-ttu-id="9777a-138">服务所有者，与业务部门的界面，策略</span><span class="sxs-lookup"><span data-stu-id="9777a-138">Service owner, interface to business divisions, strategy</span></span>|<span data-ttu-id="9777a-139">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-139">TBA</span></span>|<span data-ttu-id="9777a-140">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-140">TBA</span></span>|
|<span data-ttu-id="9777a-141">音频会议操作</span><span class="sxs-lookup"><span data-stu-id="9777a-141">Audio Conferencing Operations</span></span>|<span data-ttu-id="9777a-142">日常操作、用户和设备帐户移动/添加/更改、监视</span><span class="sxs-lookup"><span data-stu-id="9777a-142">Daily operations, user and device account move/add/change, monitoring</span></span>|<span data-ttu-id="9777a-143">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-143">TBA</span></span>| <span data-ttu-id="9777a-144">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-144">TBA</span></span>| 
|<span data-ttu-id="9777a-145">租户管理员</span><span class="sxs-lookup"><span data-stu-id="9777a-145">Tenant Admin</span></span>|<span data-ttu-id="9777a-146">更改租户范围的设置，启用新功能</span><span class="sxs-lookup"><span data-stu-id="9777a-146">Change tenant-wide settings, enable new features</span></span>|<span data-ttu-id="9777a-147">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-147">TBA</span></span>|<span data-ttu-id="9777a-148">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-148">TBA</span></span>|
|<span data-ttu-id="9777a-149">技术支持</span><span class="sxs-lookup"><span data-stu-id="9777a-149">Help Desk</span></span>|<span data-ttu-id="9777a-150">用于获取支持的用户的界面</span><span class="sxs-lookup"><span data-stu-id="9777a-150">Interface for users to get support</span></span>|<span data-ttu-id="9777a-151">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-151">TBA</span></span>|<span data-ttu-id="9777a-152">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-152">TBA</span></span>|
|<span data-ttu-id="9777a-153">网络操作</span><span class="sxs-lookup"><span data-stu-id="9777a-153">Network Operations</span></span>|<span data-ttu-id="9777a-154">运行 LAN、WAN、Wi-Fi 和 Internet 访问</span><span class="sxs-lookup"><span data-stu-id="9777a-154">Run LAN, WAN, Wi-Fi, and internet access</span></span>|<span data-ttu-id="9777a-155">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-155">TBA</span></span>|<span data-ttu-id="9777a-156">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-156">TBA</span></span>|
|<span data-ttu-id="9777a-157">客户端&终结点团队</span><span class="sxs-lookup"><span data-stu-id="9777a-157">Client & Endpoints Team</span></span>|<span data-ttu-id="9777a-158">管理桌面部署</span><span class="sxs-lookup"><span data-stu-id="9777a-158">Manage desktop deployments</span></span>|<span data-ttu-id="9777a-159">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-159">TBA</span></span>|<span data-ttu-id="9777a-160">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-160">TBA</span></span>|
|<span data-ttu-id="9777a-161">标识操作</span><span class="sxs-lookup"><span data-stu-id="9777a-161">Identity Operations</span></span>|<span data-ttu-id="9777a-162">管理 Active Directory (Active Directory、Active Directory 联合身份验证服务、Azure AD) </span><span class="sxs-lookup"><span data-stu-id="9777a-162">Manage identity infrastructure (Active Directory, Active Directory Federation Services, Azure AD)</span></span>|<span data-ttu-id="9777a-163">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-163">TBA</span></span>|<span data-ttu-id="9777a-164">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-164">TBA</span></span>|
|<span data-ttu-id="9777a-165">采用/更改管理</span><span class="sxs-lookup"><span data-stu-id="9777a-165">Adoption/Change Management</span></span>|<span data-ttu-id="9777a-166">管理解决方案的认知、培训和采用</span><span class="sxs-lookup"><span data-stu-id="9777a-166">Manage awareness, training, and adoption for the solution</span></span>|<span data-ttu-id="9777a-167">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-167">TBA</span></span>|<span data-ttu-id="9777a-168">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-168">TBA</span></span>|
|<span data-ttu-id="9777a-169">Exchange 操作</span><span class="sxs-lookup"><span data-stu-id="9777a-169">Exchange Operations</span></span>|<span data-ttu-id="9777a-170">管理 Exchange 环境</span><span class="sxs-lookup"><span data-stu-id="9777a-170">Manage the Exchange environment</span></span>|<span data-ttu-id="9777a-171">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-171">TBA</span></span>|<span data-ttu-id="9777a-172">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-172">TBA</span></span>|
|<span data-ttu-id="9777a-173">电话操作</span><span class="sxs-lookup"><span data-stu-id="9777a-173">Telephony Operations</span></span>|<span data-ttu-id="9777a-174">管理 SBC 和电话号码</span><span class="sxs-lookup"><span data-stu-id="9777a-174">Manage the SBC's and the phone numbers</span></span>|<span data-ttu-id="9777a-175">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-175">TBA</span></span>|<span data-ttu-id="9777a-176">TBA</span><span class="sxs-lookup"><span data-stu-id="9777a-176">TBA</span></span>|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a><span data-ttu-id="9777a-177">质量支持者角色</span><span class="sxs-lookup"><span data-stu-id="9777a-177">The Quality Champion role</span></span>

<span data-ttu-id="9777a-178">在所有组织中，都需要小组或个人为质量负责。</span><span class="sxs-lookup"><span data-stu-id="9777a-178">A group or individual needs to be accountable for quality in all organizations.</span></span>
<span data-ttu-id="9777a-179">这是服务管理中最重要的角色。</span><span class="sxs-lookup"><span data-stu-id="9777a-179">This is the most important role in service management.</span></span> <span data-ttu-id="9777a-180">质量冠军是一个客户角色，分配给对用户体验充满热情的人或组。</span><span class="sxs-lookup"><span data-stu-id="9777a-180">The quality champion is a customer role that's assigned to a person or group who is passionate about their users' experience.</span></span> <span data-ttu-id="9777a-181">此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。</span><span class="sxs-lookup"><span data-stu-id="9777a-181">This role requires the skills to identify trends in the environment and the sponsorship to work with other teams to drive remediation.</span></span>
<span data-ttu-id="9777a-182">质量冠军的最佳候选者通常是客户服务所有者，根据组织的大小和复杂程度，他们可能是任何对用户体验充满热情的人或组。</span><span class="sxs-lookup"><span data-stu-id="9777a-182">The best candidate for the quality champion is typically the customer service owner, who—depending on the organization’s size and complexity—could be any person or group who is passionate about user experience.</span></span>

<span data-ttu-id="9777a-183">质量保证者利用现有工具和记录的流程（例如呼叫质量仪表板 (CQD) 和质量体验评审指南）来监视用户体验、识别质量趋势，并根据需要推动修正。</span><span class="sxs-lookup"><span data-stu-id="9777a-183">The quality champion leverages existing tools and documented processes, such as the Call Quality Dashboard (CQD) and the Quality Experience Review Guide, to monitor user experience, identify quality trends, and drive remediation where needed.</span></span> <span data-ttu-id="9777a-184">质量冠军会与相应的团队协作，推动补救措施，向指导委员会报告进度并解决问题。</span><span class="sxs-lookup"><span data-stu-id="9777a-184">The quality champion works with the respective teams to drive remediation actions, reporting to a steering committee on their progress and open issues.</span></span>

<span data-ttu-id="9777a-185">操作指南中记录了与该角色关联的任务和活动。</span><span class="sxs-lookup"><span data-stu-id="9777a-185">The tasks and activities associated with the role are documented in the Operations Guide.</span></span> <span data-ttu-id="9777a-186">应在展望阶段早期分配此角色。</span><span class="sxs-lookup"><span data-stu-id="9777a-186">This role should be assigned early in the Envision phase.</span></span> <span data-ttu-id="9777a-187">执行质量支持者角色时的一个主要步骤是获取该角色所需的知识，以及确保在执行任务时满足先决条件。</span><span class="sxs-lookup"><span data-stu-id="9777a-187">A key step in operationalizing the role of Quality Champion is gaining the knowledge required for the role and ensuring the prerequisites are in place to deliver on the tasks.</span></span> <span data-ttu-id="9777a-188">此角色的一个主要任务是运行定期质量体验评审。</span><span class="sxs-lookup"><span data-stu-id="9777a-188">A key task for this role is running a regular Quality Experience Review.</span></span>

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a><span data-ttu-id="9777a-189">《体验质量评审指南》简介</span><span class="sxs-lookup"><span data-stu-id="9777a-189">Introduction to the Quality Experience Review Guide</span></span>

<span data-ttu-id="9777a-190">质量体验评审指南具有一组活动，在对改善用户体验影响最大的关键领域评估和提供修正指南，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="9777a-190">The Quality Experience Review Guide has a set of activities that assess and provide remediation guidance in key areas that have the greatest impact for improving user experience, as shown in the figure below.</span></span>

<span data-ttu-id="9777a-191">![说明在质量体验评审过程中要检查的关键问题](media/plan-my-service-management-image2.png "在质量体验评审期间要检查的关键问题：音频、可靠性和用户测试结果。")</span><span class="sxs-lookup"><span data-stu-id="9777a-191">![Illustration of key areas to examine during quality experience review](media/plan-my-service-management-image2.png "The key areas to examine during a quality experience review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="9777a-192">通过持续评估并修正本文档中所述的方面，你可以降低其对用户体验的潜在负面影响。</span><span class="sxs-lookup"><span data-stu-id="9777a-192">By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="9777a-193">在部署中遇到的大多数用户体验问题可以分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="9777a-193">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="9777a-194">防火墙或代理配置不完整</span><span class="sxs-lookup"><span data-stu-id="9777a-194">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="9777a-195">Wi-Fi 覆盖范围较小</span><span class="sxs-lookup"><span data-stu-id="9777a-195">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="9777a-196">带宽不足</span><span class="sxs-lookup"><span data-stu-id="9777a-196">Insufficient bandwidth</span></span>

-   <span data-ttu-id="9777a-197">VPN</span><span class="sxs-lookup"><span data-stu-id="9777a-197">VPN</span></span>

-   <span data-ttu-id="9777a-198">使用了未优化或内置的音频设备</span><span class="sxs-lookup"><span data-stu-id="9777a-198">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="9777a-199">子网或网络设备存在问题</span><span class="sxs-lookup"><span data-stu-id="9777a-199">Problematic subnets or network devices</span></span>

<span data-ttu-id="9777a-200">《体验质量评审指南》主要指导如何将通话质量仪表板 (CQD) 作为主要工具进行在线使用来报告和调查所述的每个方面，且重点在音频方面，以最大限度地提高采用率和作用。</span><span class="sxs-lookup"><span data-stu-id="9777a-200">The guidance provided in the Quality Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="9777a-201">为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。</span><span class="sxs-lookup"><span data-stu-id="9777a-201">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="9777a-202">我们强烈建议你尽早提名质量冠军。</span><span class="sxs-lookup"><span data-stu-id="9777a-202">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="9777a-203">获得提名后，应开始熟悉质量体验评审指南 [中的内容](./quality-of-experience-review-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="9777a-203">After being nominated, they should start to familiarize themselves with the content in the [Quality Experience Review Guide](./quality-of-experience-review-guide.md).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="9777a-204">决策点</span><span class="sxs-lookup"><span data-stu-id="9777a-204">Decision points</span></span></td><td><ul><li><span data-ttu-id="9777a-205">确定谁对组织中云语音操作负责。</span><span class="sxs-lookup"><span data-stu-id="9777a-205">Decide who is accountable for cloud voice operations in your organization.</span></span></li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="9777a-206">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9777a-206">Next steps</span></span></td><td><ul><li><span data-ttu-id="9777a-207">下载服务管理规划完整指南。</span><span class="sxs-lookup"><span data-stu-id="9777a-207">Download the Planning for Service Management full guide.</span></span></li><li><span data-ttu-id="9777a-208">下载质量体验评审指南。</span><span class="sxs-lookup"><span data-stu-id="9777a-208">Download the Quality Experience Review guide.</span></span></li><li><span data-ttu-id="9777a-209">完整查看操作指南。</span><span class="sxs-lookup"><span data-stu-id="9777a-209">Review the Operations Guide in full.</span></span></li><li><span data-ttu-id="9777a-210">向每个运营团队成员提供所有指南，以便查看并熟悉操作要求。</span><span class="sxs-lookup"><span data-stu-id="9777a-210">Provide all guides to every operations team members to review and be familiar with operations requirements.</span></span></li></ol></td></tr>
</table>

<!--ENDOFSECTION-->