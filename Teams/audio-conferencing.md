---
title: "Microsoft Teams 中的音频会议"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "在 Microsoft Teams 中部署音频会议实践指导"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: c6791646b58111a9785430b6541c57972a15ab20
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="650dd-103">Microsoft Teams 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="650dd-104">音频会议在公共预览版中提供。</span><span class="sxs-lookup"><span data-stu-id="650dd-104">Audio conferencing is in public preview.</span></span> <span data-ttu-id="650dd-105">早期采用者 (EA) 和预览版客户可以使用该功能，在发布或更新该功能时可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="650dd-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="650dd-106">Office 365 中的音频会议（以前称为 PSTN 会议）允许参与者从任何电话加入会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="650dd-107">现在在 Microsoft Teams 公共预览版中提供此功能，允许用户使用其电话加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-107">This feature is now available in Microsoft Teams, in public preview, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="650dd-108">此文章中的实践指导将带你了解音频会议的 Office 365 FastTrack 客户旅程框架 - 展望、上线和推动价值。</span><span class="sxs-lookup"><span data-stu-id="650dd-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="650dd-109">下面是使用 Office 365 中的[音频会议](https://go.microsoft.com/fwlink/?linkid=858992)完成的内容。</span><span class="sxs-lookup"><span data-stu-id="650dd-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="650dd-110">音频会议支持 Teams 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="650dd-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="650dd-111">当前，现有 Skype for Business 管理中心和远程 PowerShell 提供用于管理音频会议的管理界面。</span><span class="sxs-lookup"><span data-stu-id="650dd-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="650dd-112">展望 <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="650dd-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="650dd-113">展望阶段提供 Office 365 客户旅程的基础，适用于音频会议等所有工作负荷。</span><span class="sxs-lookup"><span data-stu-id="650dd-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="650dd-114">在此阶段，确定业务目标，并集合相关项目利益干系人，以最终交付：</span><span class="sxs-lookup"><span data-stu-id="650dd-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="650dd-115">高级成功计划，包含业务用例、关键利益干系人、目标和关键成果 (OKR)、关键成功指标 (KSI)、风险、环境评估、采用就绪和运营计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="650dd-116">然后是详细的音频会议技术实施计划，以达到所需的最终状态。</span><span class="sxs-lookup"><span data-stu-id="650dd-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="650dd-117">定义音频会议的业务用例</span><span class="sxs-lookup"><span data-stu-id="650dd-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="650dd-118">音频会议允许会议参与者使用传统座机、PBX 或移动电话拨号通过 PSTN 加入会议，从而为组织提供了连接任何安排的会议的附加入口点。</span><span class="sxs-lookup"><span data-stu-id="650dd-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="650dd-119">在以下情况下，这很有用：当组织者或参与者不在计算机前时，当数据连接不可用或不可靠而无法支持语音通信（例如，在移动数据覆盖范围不稳定的远程区域中）时，如果连接到带宽有限的免费公共 Wi-Fi 服务，或者会议参与者更愿意使用他们方便接触到的电话服务终结点拨号加入会议时。</span><span class="sxs-lookup"><span data-stu-id="650dd-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="650dd-120">在此步骤中，核心项目利益干系人将定义支持实施音频会议的业务用例。</span><span class="sxs-lookup"><span data-stu-id="650dd-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="650dd-121">业务用例的目的是定义和记录预期的可衡量业务成果，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="650dd-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="650dd-122">当前业务流程说明。</span><span class="sxs-lookup"><span data-stu-id="650dd-122">Description of current business process.</span></span>

-   <span data-ttu-id="650dd-123">定义现有业务流程上的挑战。</span><span class="sxs-lookup"><span data-stu-id="650dd-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="650dd-124">技术如何能够帮助克服这些挑战。</span><span class="sxs-lookup"><span data-stu-id="650dd-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="650dd-125">克服了这些挑战的情况下预期的可衡量业务成果。</span><span class="sxs-lookup"><span data-stu-id="650dd-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="650dd-126"><strong>当前业务流程说明</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="650dd-127">Contoso 当前依赖现任本地电话服务提供商提供的 PSTN 会议服务，按内部会议和涉及外部各方的会议的会议分钟数收费。</span><span class="sxs-lookup"><span data-stu-id="650dd-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="650dd-128"><strong>现有业务流程上的挑战</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="650dd-129">Contoso 每年为当前 PSTN 会议服务支出大约一百万美元，产生的 75% 的成本用于内部会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="650dd-130">使用传统电话服务终结点加入 PSTN 会议服务托管的会议与组织采用 Teams 作为新式通信与协作平台的计划不一致。</span><span class="sxs-lookup"><span data-stu-id="650dd-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="650dd-131"><strong>技术如何能够克服这些挑战</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="650dd-132">通过采用 Microsoft Teams 作为新式通信与协作平台，要求内部用户主要使用其配备了优化耳机的 PC 和会议室设备加入会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="650dd-133">音频会议服务将可用于支持外部参与者或支持内部参与者不便使用 PC 音频的情况。</span><span class="sxs-lookup"><span data-stu-id="650dd-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="650dd-134"><strong>预期的可衡量业务成果</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="650dd-135">迁移至作为新式通信与协作平台的 Teams，并结合使用音频会议服务，将会大大降低交付 PSTN 会议服务的成本，预期 Contoso 要支出的成本大约只是现有 PSTN 会议服务的年度成本的 20%。</span><span class="sxs-lookup"><span data-stu-id="650dd-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-136">_表 1 业务用例示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="650dd-137">除了定义业务用例外，在此步骤明确组织范围和项目时间线有助于进入展望阶段的下一步。</span><span class="sxs-lookup"><span data-stu-id="650dd-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="650dd-138">确定关键利益干系人</span><span class="sxs-lookup"><span data-stu-id="650dd-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="650dd-139">在上一步中定义的业务用例将包括音频会议实施的组织范围，基于此，可以完成综合性的利益干系人矩阵以包含要在项目中涉及的合适人员。</span><span class="sxs-lookup"><span data-stu-id="650dd-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-140">角色</span><span class="sxs-lookup"><span data-stu-id="650dd-140">Role</span></span></th>
<th align="left"><span data-ttu-id="650dd-141">说明</span><span class="sxs-lookup"><span data-stu-id="650dd-141">Description</span></span></th>
<th align="left"><span data-ttu-id="650dd-142">姓名、联系人信息、位置</span><span class="sxs-lookup"><span data-stu-id="650dd-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-143"><strong>项目执行发起人</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-144">对项目和按项目目标交付具有最高权力和责任</span><span class="sxs-lookup"><span data-stu-id="650dd-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="650dd-145">协助解决项目主管上提的问题</span><span class="sxs-lookup"><span data-stu-id="650dd-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="650dd-146">提倡在公司内就项目目标进行沟通</span><span class="sxs-lookup"><span data-stu-id="650dd-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="650dd-147">负责制定关键的战略决策</span><span class="sxs-lookup"><span data-stu-id="650dd-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="650dd-148">负责提供所需的资源和预算</span><span class="sxs-lookup"><span data-stu-id="650dd-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="650dd-149">主导季度业务回顾 (QBR)</span><span class="sxs-lookup"><span data-stu-id="650dd-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="650dd-150">认可和支持认知推行活动工作</span><span class="sxs-lookup"><span data-stu-id="650dd-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="650dd-151">担当项目部署的项目发起人</span><span class="sxs-lookup"><span data-stu-id="650dd-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-152">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-153"><strong>项目主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-154">管理和领导项目团队</span><span class="sxs-lookup"><span data-stu-id="650dd-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="650dd-155">协调参与项目的合作伙伴和工作团队</span><span class="sxs-lookup"><span data-stu-id="650dd-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="650dd-156">负责制定和管理项目计划以符合季度关键结果</span><span class="sxs-lookup"><span data-stu-id="650dd-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="650dd-157">解决跨智能的问题</span><span class="sxs-lookup"><span data-stu-id="650dd-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="650dd-158">向项目发起人提供定期更新</span><span class="sxs-lookup"><span data-stu-id="650dd-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="650dd-159">将采用的各方面合并到整体项目计划中</span><span class="sxs-lookup"><span data-stu-id="650dd-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="650dd-160">领导月度业务和运营回顾 (MBR)，为季度业务回顾做准备</span><span class="sxs-lookup"><span data-stu-id="650dd-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-161">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-162"><strong>协作主管/架构师</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-163">负责执行公司高层制定的协作策略</span><span class="sxs-lookup"><span data-stu-id="650dd-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="650dd-164">为公司分析和选择符合业务目标的协作产品</span><span class="sxs-lookup"><span data-stu-id="650dd-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="650dd-165">负责设计协作产品的运营</span><span class="sxs-lookup"><span data-stu-id="650dd-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="650dd-166">定义运营和支持模式</span><span class="sxs-lookup"><span data-stu-id="650dd-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="650dd-167">为月度和季度业务回顾做准备</span><span class="sxs-lookup"><span data-stu-id="650dd-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="650dd-168">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-169"><strong>顾问</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-170">负责配置服务</span><span class="sxs-lookup"><span data-stu-id="650dd-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="650dd-171">参与整体解决方案体系结构</span><span class="sxs-lookup"><span data-stu-id="650dd-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-172">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-173"><strong>项目经理</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-174">开发和维护项目计划</span><span class="sxs-lookup"><span data-stu-id="650dd-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="650dd-175">按照项目计划和预算管理项目交付物</span><span class="sxs-lookup"><span data-stu-id="650dd-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="650dd-176">记录和管理项目问题，包括上提问题</span><span class="sxs-lookup"><span data-stu-id="650dd-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="650dd-177">每周鼓舞士气</span><span class="sxs-lookup"><span data-stu-id="650dd-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="650dd-178">与项目执行发起人保持联系并向其提供更新</span><span class="sxs-lookup"><span data-stu-id="650dd-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="650dd-179">与架构师合作定义变更管理方法和通信计划</span><span class="sxs-lookup"><span data-stu-id="650dd-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-180">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-181"><strong>变更管理/采用专业人员</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-182">在发现阶段向采用和培训流程提供信息</span><span class="sxs-lookup"><span data-stu-id="650dd-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="650dd-183">参与采用策略研讨会</span><span class="sxs-lookup"><span data-stu-id="650dd-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="650dd-184">制定和负责采用策略</span><span class="sxs-lookup"><span data-stu-id="650dd-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="650dd-185">制定和执行通信计划</span><span class="sxs-lookup"><span data-stu-id="650dd-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="650dd-186">负责向最终用户提供培训</span><span class="sxs-lookup"><span data-stu-id="650dd-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="650dd-187">收集反馈和进行调查</span><span class="sxs-lookup"><span data-stu-id="650dd-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-188">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-189"><strong>网络主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-190">在发现阶段向网络设计提供信息</span><span class="sxs-lookup"><span data-stu-id="650dd-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="650dd-191">在展望研讨会期间参与计划</span><span class="sxs-lookup"><span data-stu-id="650dd-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="650dd-192">在项目执行期间协调网络团队的工作</span><span class="sxs-lookup"><span data-stu-id="650dd-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-193">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-194"><strong>安全主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-195">在发现阶段向安全设计和流程提供信息</span><span class="sxs-lookup"><span data-stu-id="650dd-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="650dd-196">在展望研讨会期间参与计划</span><span class="sxs-lookup"><span data-stu-id="650dd-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="650dd-197">在项目执行期间协调安全团队的工作</span><span class="sxs-lookup"><span data-stu-id="650dd-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-198">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-199"><strong>电话服务主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-200">在发现阶段向电话服务设计提供信息</span><span class="sxs-lookup"><span data-stu-id="650dd-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="650dd-201">在展望研讨会期间参与计划</span><span class="sxs-lookup"><span data-stu-id="650dd-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="650dd-202">在项目执行期间协调电话服务团队的工作</span><span class="sxs-lookup"><span data-stu-id="650dd-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-203">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-204"><strong>桌面主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-205">在发现阶段向客户端和更新流程提供信息</span><span class="sxs-lookup"><span data-stu-id="650dd-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="650dd-206">在展望研讨会期间参与计划</span><span class="sxs-lookup"><span data-stu-id="650dd-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="650dd-207">在项目执行期间协调桌面团队的工作</span><span class="sxs-lookup"><span data-stu-id="650dd-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-208">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-209"><strong>支持主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-210">在发现阶段向运营和支持模式提供信息</span><span class="sxs-lookup"><span data-stu-id="650dd-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="650dd-211">在展望研讨会期间参与计划</span><span class="sxs-lookup"><span data-stu-id="650dd-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="650dd-212">参与支持模式计划</span><span class="sxs-lookup"><span data-stu-id="650dd-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="650dd-213">在项目执行期间协调支持团队/资源的工作</span><span class="sxs-lookup"><span data-stu-id="650dd-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-214">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-215"><strong>业务单位代表</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-216">参与准备基于最终用户的采用指南和材料</span><span class="sxs-lookup"><span data-stu-id="650dd-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="650dd-217">参与并检查业务用例</span><span class="sxs-lookup"><span data-stu-id="650dd-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-218">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-219"><strong>部署主管</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-220">确保满足部署先决条件</span><span class="sxs-lookup"><span data-stu-id="650dd-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="650dd-221">请客户资源参与准备和部署阶段活动</span><span class="sxs-lookup"><span data-stu-id="650dd-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="650dd-222">参与会议以检查准备和部署状态</span><span class="sxs-lookup"><span data-stu-id="650dd-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-223">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-224"><strong>IT 管理员</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-225">负责为测试计划和执行提供协助的 IT 专业人士</span><span class="sxs-lookup"><span data-stu-id="650dd-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-226">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-227"><strong>服务所有者</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-228">负责音频会议服务整体的运营</span><span class="sxs-lookup"><span data-stu-id="650dd-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="650dd-229">音频会议服务的所有者</span><span class="sxs-lookup"><span data-stu-id="650dd-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-230">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-231"><strong>质量支持者</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-232">推动质量、可靠性和用户反馈</span><span class="sxs-lookup"><span data-stu-id="650dd-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="650dd-233">了解质量趋势，并与各个团队一起推动采取补救措施</span><span class="sxs-lookup"><span data-stu-id="650dd-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="650dd-234">通过指导委员会向领导汇报</span><span class="sxs-lookup"><span data-stu-id="650dd-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="650dd-235">通过“为我的通话评分”和“净推荐值”报告质量、可靠性和用户看法</span><span class="sxs-lookup"><span data-stu-id="650dd-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="650dd-236">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-237">_表 2 利益干系人矩阵模板示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="650dd-238">本文档中上述示例表和后续表用作模板。</span><span class="sxs-lookup"><span data-stu-id="650dd-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="650dd-239">对于需要你在规划过程中完成的信息，以“TBA”（待添加）表示。</span><span class="sxs-lookup"><span data-stu-id="650dd-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="650dd-240">定义目标和关键结果、关键成功指标及风险</span><span class="sxs-lookup"><span data-stu-id="650dd-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="650dd-241">集合了项目利益干系人后，可以将业务用例、组织范围和项目时间线转换为目标和关键结果 (OKR)，以及将衡量项目成功的方式定义为一组关键成功指标 (KSI)。</span><span class="sxs-lookup"><span data-stu-id="650dd-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="650dd-242">定义 OKR 和 KSI 时项目利益干系人全面参与将确保归属感，并且它们将与组织的业务需求一致。</span><span class="sxs-lookup"><span data-stu-id="650dd-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="650dd-243">OKR 将包含在项目开始时设定的一组目标，并具有按季度定义的可衡量的关键结果。</span><span class="sxs-lookup"><span data-stu-id="650dd-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="650dd-244">按月检查关键结果以跟踪整个项目的状态，并且基于进度，可以根据需要对季度计划进行调整。</span><span class="sxs-lookup"><span data-stu-id="650dd-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="650dd-245"><strong>愿景</strong>：通过最大限度地利用 Office 365 投资来提高工作效率</span><span class="sxs-lookup"><span data-stu-id="650dd-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-246"><strong>目标</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-247"><strong>关键结果</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-248"><strong>待办事项</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-249">到 2018 财年结束时在 Teams 中部署音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="650dd-250">FY18Q1：在 Teams 中部署音频会议（全球）</span><span class="sxs-lookup"><span data-stu-id="650dd-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-251">展望</span><span class="sxs-lookup"><span data-stu-id="650dd-251">Envision</span></span></p>
<ul><li><span data-ttu-id="650dd-252">制定成功计划</span><span class="sxs-lookup"><span data-stu-id="650dd-252">Create success plan</span></span></li>
<li><span data-ttu-id="650dd-253">制定详细的技术实施计划</span><span class="sxs-lookup"><span data-stu-id="650dd-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="650dd-254">上线</span><span class="sxs-lookup"><span data-stu-id="650dd-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="650dd-255">执行成功计划</span><span class="sxs-lookup"><span data-stu-id="650dd-255">Execute success plan</span></span></li>
<li><span data-ttu-id="650dd-256">执行技术实施计划</span><span class="sxs-lookup"><span data-stu-id="650dd-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-257">到 2018 财年中期全球停用旧的 PSTN 会议服务</span><span class="sxs-lookup"><span data-stu-id="650dd-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="650dd-258">FY18Q2：全球停用旧的 PSTN 会议服务</span><span class="sxs-lookup"><span data-stu-id="650dd-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-259">推动价值</span><span class="sxs-lookup"><span data-stu-id="650dd-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="650dd-260">激励用户参与并推动采用</span><span class="sxs-lookup"><span data-stu-id="650dd-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="650dd-261">管理和准备变更</span><span class="sxs-lookup"><span data-stu-id="650dd-261">Manage and prepare change</span></span></li>
<li><span data-ttu-id="650dd-262">衡量、分享成功以及重复进行</span><span class="sxs-lookup"><span data-stu-id="650dd-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-263">_表 3 OKR 示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="650dd-264">KSI 通过详细记录好和/或坏的结果来衡量质量和是否成功得到关键结果，以及补充 IKR 的二元性质（实现或未实现）。</span><span class="sxs-lookup"><span data-stu-id="650dd-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="650dd-265">定义 KSI 时，我们建议利用“具体、可衡量、可分配、实际、时间相关”或 SMART 标准。</span><span class="sxs-lookup"><span data-stu-id="650dd-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-266">类型</span><span class="sxs-lookup"><span data-stu-id="650dd-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="650dd-267">KSI 问题 &amp;</span><span class="sxs-lookup"><span data-stu-id="650dd-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="650dd-268">标准</span><span class="sxs-lookup"><span data-stu-id="650dd-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="650dd-269">衡量方式</span><span class="sxs-lookup"><span data-stu-id="650dd-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="650dd-270">成功标准</span><span class="sxs-lookup"><span data-stu-id="650dd-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="650dd-271">衡量时间</span><span class="sxs-lookup"><span data-stu-id="650dd-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="650dd-272">负责方</span><span class="sxs-lookup"><span data-stu-id="650dd-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-273"><strong>使用/采用</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-274">通话质量与以前的解决方案一样或优于以前的解决方案</span><span class="sxs-lookup"><span data-stu-id="650dd-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="650dd-275">调查</span><span class="sxs-lookup"><span data-stu-id="650dd-275">Survey page</span></span></td>
<td align="left"><span data-ttu-id="650dd-276">80% 的用户同意或非常同意</span><span class="sxs-lookup"><span data-stu-id="650dd-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="650dd-277">启用和季度后</span><span class="sxs-lookup"><span data-stu-id="650dd-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="650dd-278">信息技术团队</span><span class="sxs-lookup"><span data-stu-id="650dd-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-279"><strong>使用/采用</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-280">团队轻松确定通信流程</span><span class="sxs-lookup"><span data-stu-id="650dd-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="650dd-281">调查</span><span class="sxs-lookup"><span data-stu-id="650dd-281">Survey page</span></span></td>
<td align="left"><span data-ttu-id="650dd-282">80% 的用户同意或非常同意</span><span class="sxs-lookup"><span data-stu-id="650dd-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="650dd-283">启用和季度后</span><span class="sxs-lookup"><span data-stu-id="650dd-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="650dd-284">变更管理团队</span><span class="sxs-lookup"><span data-stu-id="650dd-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-285"><strong>使用/采用</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-286">用户主动使用解决方案</span><span class="sxs-lookup"><span data-stu-id="650dd-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="650dd-287">Office 365 报告、通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="650dd-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="650dd-288">80% 的用户每天主动使用</span><span class="sxs-lookup"><span data-stu-id="650dd-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="650dd-289">每天</span><span class="sxs-lookup"><span data-stu-id="650dd-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="650dd-290">变更管理团队</span><span class="sxs-lookup"><span data-stu-id="650dd-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-291"><strong>使用/质量</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-292">质量较差的通话/会议的百分比应尽可能低</span><span class="sxs-lookup"><span data-stu-id="650dd-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="650dd-293">通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="650dd-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="650dd-294">&lt; 每月 5% 的通话质量较差</span><span class="sxs-lookup"><span data-stu-id="650dd-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="650dd-295">每天</span><span class="sxs-lookup"><span data-stu-id="650dd-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="650dd-296">信息技术团队</span><span class="sxs-lookup"><span data-stu-id="650dd-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-297"><strong>使用/支持</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-298">我知道如何获取技术支持</span><span class="sxs-lookup"><span data-stu-id="650dd-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="650dd-299">调查</span><span class="sxs-lookup"><span data-stu-id="650dd-299">Survey page</span></span></td>
<td align="left"><span data-ttu-id="650dd-300">90% 的用户同意或非常同意</span><span class="sxs-lookup"><span data-stu-id="650dd-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="650dd-301">启用和季度后</span><span class="sxs-lookup"><span data-stu-id="650dd-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="650dd-302">变更管理团队</span><span class="sxs-lookup"><span data-stu-id="650dd-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-303"><strong>使用/支持</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-304">我对技术支持的质量感到满意</span><span class="sxs-lookup"><span data-stu-id="650dd-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="650dd-305">调查</span><span class="sxs-lookup"><span data-stu-id="650dd-305">Survey page</span></span></td>
<td align="left"><span data-ttu-id="650dd-306">80% 的用户同意或非常同意</span><span class="sxs-lookup"><span data-stu-id="650dd-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="650dd-307">每次事故后</span><span class="sxs-lookup"><span data-stu-id="650dd-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="650dd-308">信息技术团队</span><span class="sxs-lookup"><span data-stu-id="650dd-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-309"><strong>财务</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-310">旧会议分钟数减少</span><span class="sxs-lookup"><span data-stu-id="650dd-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="650dd-311">财务系统</span><span class="sxs-lookup"><span data-stu-id="650dd-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="650dd-312">符合定义的 ROI</span><span class="sxs-lookup"><span data-stu-id="650dd-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="650dd-313">基于 ROI</span><span class="sxs-lookup"><span data-stu-id="650dd-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="650dd-314">变更管理团队</span><span class="sxs-lookup"><span data-stu-id="650dd-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-315">_表 4 KIS 示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="650dd-316">你需要在此行动中确定业务风险，以及为每个确定的风险制定迁移计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="650dd-317">此信息可以收集到风险计划中。</span><span class="sxs-lookup"><span data-stu-id="650dd-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-318">风险</span><span class="sxs-lookup"><span data-stu-id="650dd-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="650dd-319">可能性</span><span class="sxs-lookup"><span data-stu-id="650dd-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="650dd-320">影响</span><span class="sxs-lookup"><span data-stu-id="650dd-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="650dd-321">综合</span><span class="sxs-lookup"><span data-stu-id="650dd-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="650dd-322">迁移计划</span><span class="sxs-lookup"><span data-stu-id="650dd-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-323">即将进行的合并将最多添加 1,000 人</span><span class="sxs-lookup"><span data-stu-id="650dd-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="650dd-324">高</span><span class="sxs-lookup"><span data-stu-id="650dd-324">High availability</span></span></td>
<td align="left"><span data-ttu-id="650dd-325">高</span><span class="sxs-lookup"><span data-stu-id="650dd-325">High availability</span></span></td>
<td align="left"><span data-ttu-id="650dd-326">高</span><span class="sxs-lookup"><span data-stu-id="650dd-326">High availability</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-327">对于合并的公司，有自己的流程（展望、上线、推动价值）的单独 OKR</span><span class="sxs-lookup"><span data-stu-id="650dd-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="650dd-328">不在现有 OKR 中包含它们</span><span class="sxs-lookup"><span data-stu-id="650dd-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-329">电话携号转网将延迟项目完成</span><span class="sxs-lookup"><span data-stu-id="650dd-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="650dd-330">高</span><span class="sxs-lookup"><span data-stu-id="650dd-330">High availability</span></span></td>
<td align="left"><span data-ttu-id="650dd-331">高</span><span class="sxs-lookup"><span data-stu-id="650dd-331">High availability</span></span></td>
<td align="left"><span data-ttu-id="650dd-332">高</span><span class="sxs-lookup"><span data-stu-id="650dd-332">High availability</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-333">提前准备所有所需的信息以支持电话携号转网（即：客户服务记录、帐单详细信息、授权书）</span><span class="sxs-lookup"><span data-stu-id="650dd-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="650dd-334">调整项目时间线以预留电话携号转网过程的周转时间</span><span class="sxs-lookup"><span data-stu-id="650dd-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="650dd-335">向外部参与者说明使用新的电话拨入式会议号码</span><span class="sxs-lookup"><span data-stu-id="650dd-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-336">规划的网络重新设计</span><span class="sxs-lookup"><span data-stu-id="650dd-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="650dd-337">高</span><span class="sxs-lookup"><span data-stu-id="650dd-337">High availability</span></span></td>
<td align="left"><span data-ttu-id="650dd-338">中</span><span class="sxs-lookup"><span data-stu-id="650dd-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="650dd-339">中</span><span class="sxs-lookup"><span data-stu-id="650dd-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="650dd-340">在将 Teams 作为新式通信与协作平台实施之前，对项目范围内的站点进行网络就绪评估</span><span class="sxs-lookup"><span data-stu-id="650dd-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-341">_表 5 风险计划示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="650dd-342">评估环境和采用就绪情况</span><span class="sxs-lookup"><span data-stu-id="650dd-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="650dd-343">为了实现预期 OKR，你可能必须定义解决方案的高级体系结构。</span><span class="sxs-lookup"><span data-stu-id="650dd-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="650dd-344">这将进行环境发现以评估与 IT 和电话服务基础结构、网络和操作有关的所有方面。</span><span class="sxs-lookup"><span data-stu-id="650dd-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="650dd-345">在环境发现中，将包括与最终用户计算有关的所有内容（从硬件要求到软件要求），例如，对个人计算机和移动设备进行就绪评估以支持音频会议业务用例。</span><span class="sxs-lookup"><span data-stu-id="650dd-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="650dd-346">环境发现还可以揭示要[将电话号码转移到 Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e) 是否存在要求。</span><span class="sxs-lookup"><span data-stu-id="650dd-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="650dd-347">这将帮助贵组织相应地调整项目计划，并准备携号转网所需的必要信息。</span><span class="sxs-lookup"><span data-stu-id="650dd-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="650dd-348">你可以通过利用以下[调查表](https://go.microsoft.com/fwlink/?linkid=858995)来进行环境发现。</span><span class="sxs-lookup"><span data-stu-id="650dd-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="650dd-349">环境发现必须包括网络就绪评估以确保网络可以支持实施音频会议服务。</span><span class="sxs-lookup"><span data-stu-id="650dd-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="650dd-350">可以在 [MyAdvisor 网络规划器工具](https://go.microsoft.com/fwlink/?linkid=858999)中利用通过环境发现获取的信息（例如，Internet 连接和 WAN 拓扑的详细信息、站点链接、可用带宽以及人员分析数据（可以转换为每个工作负荷的预期使用情况））来确定支持音频会议服务的网络就绪情况。</span><span class="sxs-lookup"><span data-stu-id="650dd-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="650dd-351">为了进一步确定网络就绪情况，可以使用 [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) 或[网络就绪评估工具合作伙伴](https://go.microsoft.com/fwlink/?linkid=859003)提供的解决方案执行实时媒体流量模拟。</span><span class="sxs-lookup"><span data-stu-id="650dd-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="650dd-352">网络就绪评估的结果将更加清晰地提供有关成功实施音频会议所需的网络优化或补救的信息。</span><span class="sxs-lookup"><span data-stu-id="650dd-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="650dd-353">可以执行人员分析来评估采用就绪情况，以找出组织中可以作为实施音频会议服务的目标的一组人员。</span><span class="sxs-lookup"><span data-stu-id="650dd-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="650dd-354">人员分析包括确定实现预期业务结果所需的其他外设或设备。</span><span class="sxs-lookup"><span data-stu-id="650dd-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="650dd-355">要执行人员分析，你可以召集相关项目利益干系人、利用[人员联盟](https://go.microsoft.com/fwlink/?linkid=859005)研讨会框架和[人员特征矩阵](https://go.microsoft.com/fwlink/?linkid=859006)来召开研讨会。</span><span class="sxs-lookup"><span data-stu-id="650dd-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="650dd-356">可以使用[人员分析报告](https://go.microsoft.com/fwlink/?linkid=859007)模板将人员分析研讨会的结果汇总成报告。</span><span class="sxs-lookup"><span data-stu-id="650dd-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="650dd-357">虽然发现调查表和人员分析示例最初是为 Skype for Business Online 编写的，但大部分内容与 Teams 相关。</span><span class="sxs-lookup"><span data-stu-id="650dd-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="650dd-358">请随意修改和删除与项目无关的项。</span><span class="sxs-lookup"><span data-stu-id="650dd-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="650dd-359">你可以在环境评估和采用就绪评估中确定技术风险，并为每个确定的风险制定迁移计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="650dd-360">此信息应包含在风险计划内。</span><span class="sxs-lookup"><span data-stu-id="650dd-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="650dd-361">映射运营角色</span><span class="sxs-lookup"><span data-stu-id="650dd-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="650dd-362">规划运营和确定将运营音频会议服务的团队是重要的一步，因为必须在已有首批试点用户的情况下开始运营。</span><span class="sxs-lookup"><span data-stu-id="650dd-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="650dd-363">每个确定的团队必须审阅并同意确定的任务和责任，然后开始为运营音频会议服务做准备。</span><span class="sxs-lookup"><span data-stu-id="650dd-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="650dd-364">准备工作可能包括培训和就绪、其他人员配备或确保安排外部提供商交付服务。</span><span class="sxs-lookup"><span data-stu-id="650dd-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-365">运营角色</span><span class="sxs-lookup"><span data-stu-id="650dd-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="650dd-366">说明</span><span class="sxs-lookup"><span data-stu-id="650dd-366">Description</span></span></th>
<th align="left"><span data-ttu-id="650dd-367">团队</span><span class="sxs-lookup"><span data-stu-id="650dd-367">Team Call</span></span></th>
<th align="left"><span data-ttu-id="650dd-368">联系详细信息</span><span class="sxs-lookup"><span data-stu-id="650dd-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-369">服务所有者</span><span class="sxs-lookup"><span data-stu-id="650dd-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="650dd-370">服务所有者、与业务部门的接口、策略</span><span class="sxs-lookup"><span data-stu-id="650dd-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="650dd-371">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-372">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-373">音频会议运营</span><span class="sxs-lookup"><span data-stu-id="650dd-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="650dd-374">日常运营、用户和设备帐户移动/添加/更改、监控</span><span class="sxs-lookup"><span data-stu-id="650dd-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="650dd-375">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-376">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-377">租户管理员</span><span class="sxs-lookup"><span data-stu-id="650dd-377">Office 365 Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="650dd-378">更改租户范围的设置、启用新功能</span><span class="sxs-lookup"><span data-stu-id="650dd-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="650dd-379">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-380">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-381">支持</span><span class="sxs-lookup"><span data-stu-id="650dd-381">Help Desk.</span></span></td>
<td align="left"><span data-ttu-id="650dd-382">供最终用户获取支持的接口</span><span class="sxs-lookup"><span data-stu-id="650dd-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="650dd-383">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-384">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-385">网络运营</span><span class="sxs-lookup"><span data-stu-id="650dd-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="650dd-386">支持 LAN、WAN、Wi-Fi 和 Internet 访问</span><span class="sxs-lookup"><span data-stu-id="650dd-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="650dd-387">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-388">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-389">客户端&amp;和终结点团队</span><span class="sxs-lookup"><span data-stu-id="650dd-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="650dd-390">管理桌面部署</span><span class="sxs-lookup"><span data-stu-id="650dd-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="650dd-391">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-392">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-393">标识运营</span><span class="sxs-lookup"><span data-stu-id="650dd-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="650dd-394">管理标识基础结构（AD、ADFS、Azure AD）</span><span class="sxs-lookup"><span data-stu-id="650dd-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="650dd-395">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-396">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-397">采用/变更管理</span><span class="sxs-lookup"><span data-stu-id="650dd-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="650dd-398">管理解决方案的认知、培训和采用</span><span class="sxs-lookup"><span data-stu-id="650dd-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="650dd-399">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-400">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-401">Exchange 运营</span><span class="sxs-lookup"><span data-stu-id="650dd-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="650dd-402">管理 Exchange 环境</span><span class="sxs-lookup"><span data-stu-id="650dd-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="650dd-403">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-404">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-405">_表 6 运营角色映射示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="650dd-406">为了便于完成更加详细的运营角色映射（包括与每个运营角色关联的任务），你可以使用[运营角色映射工作簿](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16)获取将明确角色和责任的详细信息以支持音频会议服务。</span><span class="sxs-lookup"><span data-stu-id="650dd-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="650dd-407">记录成功计划</span><span class="sxs-lookup"><span data-stu-id="650dd-407">Document success plan</span></span>
---------------------

<span data-ttu-id="650dd-408">成功计划是在展望阶段创建的文档，包括业务案例、服务就绪、采用计划和运营计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="650dd-409">成功计划将提供项目团队（可以包括 FastTrack 或部署合作伙伴），具有用于实现组织的音频会议服务目标的充分信息。</span><span class="sxs-lookup"><span data-stu-id="650dd-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="650dd-410">通常，成功计划包含以下主要部分：</span><span class="sxs-lookup"><span data-stu-id="650dd-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="650dd-411">业务案例</span><span class="sxs-lookup"><span data-stu-id="650dd-411">Business case</span></span>

-   <span data-ttu-id="650dd-412">服务就绪</span><span class="sxs-lookup"><span data-stu-id="650dd-412">Service readiness</span></span>

-   <span data-ttu-id="650dd-413">采用计划</span><span class="sxs-lookup"><span data-stu-id="650dd-413">Adoption plan</span></span>

-   <span data-ttu-id="650dd-414">运营计划</span><span class="sxs-lookup"><span data-stu-id="650dd-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="650dd-415">业务案例</span><span class="sxs-lookup"><span data-stu-id="650dd-415">Business case</span></span>

<span data-ttu-id="650dd-416">业务用例、利益干系人、OKR 和 KSI、风险以及项目时间线通常组成业务案例所需的信息主体。</span><span class="sxs-lookup"><span data-stu-id="650dd-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="650dd-417">你需要在成功计划中记录它们。</span><span class="sxs-lookup"><span data-stu-id="650dd-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="650dd-418">服务就绪</span><span class="sxs-lookup"><span data-stu-id="650dd-418">Service readiness</span></span>

<span data-ttu-id="650dd-419">环境评估提供确定组织实施音频会议的技术就绪情况所需的初步信息。</span><span class="sxs-lookup"><span data-stu-id="650dd-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="650dd-420">此处包括用于解决通过环境评估发现且需要补救的方面的计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="650dd-421">你需要在成功计划中包括服务就绪评估和补救计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="650dd-422">采用计划</span><span class="sxs-lookup"><span data-stu-id="650dd-422">Adoption plan</span></span>

<span data-ttu-id="650dd-423">在采用就绪评估后，必须完成更加详细的计划，以便项目团队制定一套全面的通信计划、培训计划以及启动前、启动时和启动后采用活动。</span><span class="sxs-lookup"><span data-stu-id="650dd-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="650dd-424">在此步骤将确定用于支持采用活动的资源（例如，传单、欢迎电子邮件和培训材料）以及满足组织需求所需的任何自定义项。</span><span class="sxs-lookup"><span data-stu-id="650dd-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="650dd-425">[此处](https://www.microsoft.com/download/details.aspx?id=54244)提供了适用于采用活动的模板。</span><span class="sxs-lookup"><span data-stu-id="650dd-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="650dd-426">运营计划</span><span class="sxs-lookup"><span data-stu-id="650dd-426">Operational plan</span></span>

<span data-ttu-id="650dd-427">运营角色映射行动将设立角色和责任以及为每个运营角色分配的团队以支持实施音频会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="650dd-428">你需要完成此项，并在成功计划中包括运营计划以确保完成解决方案的运营就绪。</span><span class="sxs-lookup"><span data-stu-id="650dd-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="650dd-429">在 Teams 中规划音频会议  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="650dd-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="650dd-430">为了在 Teams 中规划实施音频会议，必须提前制定一系列决策，让贵组织做好更充分的准备以便实施满足业务需求的解决方案。</span><span class="sxs-lookup"><span data-stu-id="650dd-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="650dd-431">这些决策将记录到技术实施计划中。</span><span class="sxs-lookup"><span data-stu-id="650dd-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="650dd-432">音频会议可用情况</span><span class="sxs-lookup"><span data-stu-id="650dd-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="650dd-433">在这些[国家和地区](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US)提供音频会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="650dd-434">由于受到法律约束的原因，为了向跨国组织提供音频会议，必须从音频会议服务覆盖的国家和地区提供 Office 365 订阅的合同。</span><span class="sxs-lookup"><span data-stu-id="650dd-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="650dd-435">确定贵组织符合获取音频会议服务的条件后，将根据可用国家和地区列表编写将实施音频会议服务的用户位置或办公地点列表。</span><span class="sxs-lookup"><span data-stu-id="650dd-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="650dd-436">决策点</span><span class="sxs-lookup"><span data-stu-id="650dd-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-437">确定哪些用户位置或办公地点将实施音频会议服务。</span><span class="sxs-lookup"><span data-stu-id="650dd-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="650dd-438">后续步骤</span><span class="sxs-lookup"><span data-stu-id="650dd-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-439">记录要支持音频会议服务的用户位置或办公地点。</span><span class="sxs-lookup"><span data-stu-id="650dd-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-440">办公地点</span><span class="sxs-lookup"><span data-stu-id="650dd-440">Office</span></span></th>
<th align="left"><span data-ttu-id="650dd-441">位置</span><span class="sxs-lookup"><span data-stu-id="650dd-441">Location</span></span></th>
<th align="left"><span data-ttu-id="650dd-442">PSTN 会议服务</span><span class="sxs-lookup"><span data-stu-id="650dd-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-443">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-444">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="650dd-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="650dd-445">音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-445">Audio Video Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-446">数码港道 100 号</span><span class="sxs-lookup"><span data-stu-id="650dd-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-447">香港 SAR</span><span class="sxs-lookup"><span data-stu-id="650dd-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="650dd-448">旧的 PSTN 会议</span><span class="sxs-lookup"><span data-stu-id="650dd-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-449">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-450">新加坡</span><span class="sxs-lookup"><span data-stu-id="650dd-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="650dd-451">音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-451">Audio Video Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-452">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-453">英国</span><span class="sxs-lookup"><span data-stu-id="650dd-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="650dd-454">音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-454">Audio Video Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-456">法国</span><span class="sxs-lookup"><span data-stu-id="650dd-456">France</span></span></td>
<td align="left"><span data-ttu-id="650dd-457">音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-457">Audio Video Conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-458">_表 7 音频会议服务地点支持列表示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="650dd-459">许可音频会议</span><span class="sxs-lookup"><span data-stu-id="650dd-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="650dd-460">[音频会议许可证](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US)（以前称为 Skype for Business PSTN 会议许可证）作为 Office 365 E5 订阅计划的一部分提供，或者作为 Office 365 E1 或 Office 365 E3 订阅计划的附加内容提供。</span><span class="sxs-lookup"><span data-stu-id="650dd-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="650dd-461">Teams 中的 PSTN 或电话拨入式会议不支持第三方<sup></sup>音频会议提供商 (ACP)。</span><span class="sxs-lookup"><span data-stu-id="650dd-461">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs).</span></span>
> <br><span data-ttu-id="650dd-462">如果你现在已使用 Skype for Business Online PSTN 会议，则可以立即利用 Teams 中的音频会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="650dd-463">为了提供免费电话会议桥接电话号码以及支持向国际电话号码拨出的会议，你需要为贵组织设置[通信点数](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059)。</span><span class="sxs-lookup"><span data-stu-id="650dd-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="650dd-464">在有些国家/地区，仅通过免费电话会议桥接电话号码提供服务，这种情况下，在此类国家/地区，必须使用通信点数以支持拨入。</span><span class="sxs-lookup"><span data-stu-id="650dd-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="650dd-465">实施通信点数时首先要考虑的是确定要购买的初始资金数额。</span><span class="sxs-lookup"><span data-stu-id="650dd-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="650dd-466">可以参考[通信点数](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059)文档中的建议资金数额。</span><span class="sxs-lookup"><span data-stu-id="650dd-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="650dd-467">如果贵组织选择使用自动充值，[通信点数](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059)文档中也提供了触发数额（最低资金数额）建议。</span><span class="sxs-lookup"><span data-stu-id="650dd-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="650dd-468">自动充值数额需要由实际使用情况确定。</span><span class="sxs-lookup"><span data-stu-id="650dd-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="650dd-469">应持续监控通信点数使用情况，并根据需要调整充值数额。</span><span class="sxs-lookup"><span data-stu-id="650dd-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="650dd-470">决策点</span><span class="sxs-lookup"><span data-stu-id="650dd-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-471">如果贵组织尚未购买所需的音频会议许可，确定是通过提升现有 Office 365 订阅还是通过购买音频会议外接程序来获取音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="650dd-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="650dd-472">确定实施音频会议是否需要通信点数。</span><span class="sxs-lookup"><span data-stu-id="650dd-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="650dd-473">如果是，确定要购买的初始资金数额。</span><span class="sxs-lookup"><span data-stu-id="650dd-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="650dd-474">在适用的情况下，确定触发数额和自动充值数额。</span><span class="sxs-lookup"><span data-stu-id="650dd-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="650dd-475">后续步骤</span><span class="sxs-lookup"><span data-stu-id="650dd-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-476">记录将为其分配音频会议许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="650dd-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="650dd-477">记录通信点数计划（初始数额、触发数额、自动充值数额）。</span><span class="sxs-lookup"><span data-stu-id="650dd-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-478">用户</span><span class="sxs-lookup"><span data-stu-id="650dd-478">User</span></span></th>
<th align="left"><span data-ttu-id="650dd-479">办公地点</span><span class="sxs-lookup"><span data-stu-id="650dd-479">Office</span></span></th>
<th align="left"><span data-ttu-id="650dd-480">Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="650dd-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="650dd-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="650dd-482">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-483">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="650dd-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="650dd-485">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-486">Office 365 E3、音频会议外接程序</span><span class="sxs-lookup"><span data-stu-id="650dd-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="650dd-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="650dd-488">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-489">Office 365 E3、音频会议外接程序</span><span class="sxs-lookup"><span data-stu-id="650dd-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="650dd-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="650dd-491">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-492">Office 365 E3、音频会议外接程序</span><span class="sxs-lookup"><span data-stu-id="650dd-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="650dd-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="650dd-494">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-495">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="650dd-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="650dd-497">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-498">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="650dd-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="650dd-500">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-501">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="650dd-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="650dd-503">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-504">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="650dd-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="650dd-506">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-507">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="650dd-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="650dd-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-510">Office 365 E3、音频会议外接程序</span><span class="sxs-lookup"><span data-stu-id="650dd-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="650dd-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="650dd-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="650dd-513">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="650dd-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="650dd-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-516">Office 365 E3、音频会议外接程序</span><span class="sxs-lookup"><span data-stu-id="650dd-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-517">_表 8 音频会议组织者的许可证分配列表示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-518">初始数额</span><span class="sxs-lookup"><span data-stu-id="650dd-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="650dd-519">$ 1,000</span><span class="sxs-lookup"><span data-stu-id="650dd-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-520">触发数额</span><span class="sxs-lookup"><span data-stu-id="650dd-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="650dd-521">$400</span><span class="sxs-lookup"><span data-stu-id="650dd-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-522">自动充值数额</span><span class="sxs-lookup"><span data-stu-id="650dd-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="650dd-523">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-524">_表 9 通信点数计划数量示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="650dd-525">会议桥接电话号码</span><span class="sxs-lookup"><span data-stu-id="650dd-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="650dd-526">Office 365 中的音频会议服务包括：</span><span class="sxs-lookup"><span data-stu-id="650dd-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="650dd-527">多种类型的会议桥接电话号码（收费电话和免费电话）</span><span class="sxs-lookup"><span data-stu-id="650dd-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="650dd-528">多种类别的电话号码（专用和共享）</span><span class="sxs-lookup"><span data-stu-id="650dd-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="650dd-529">对会议桥接支持多种语言（主要和辅助）</span><span class="sxs-lookup"><span data-stu-id="650dd-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="650dd-530">租户的默认电话号码</span><span class="sxs-lookup"><span data-stu-id="650dd-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="650dd-531">有关包含的功能的完整说明，请参阅[为 Skype for Business 设置电话拨入式会议或 PSTN 会议](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US)和[用于电话拨入式会议的电话号码](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**。**</span><span class="sxs-lookup"><span data-stu-id="650dd-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="650dd-532">根据[获取 Skype for Business 服务电话号码](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734)中所述的适用许可证数量，专用会议桥接电话号码的数量不超过每个租户可以获取的电话号码限制。</span><span class="sxs-lookup"><span data-stu-id="650dd-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="650dd-533">免费电话会议桥接电话号码需要通信点数。</span><span class="sxs-lookup"><span data-stu-id="650dd-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="650dd-534">如果存在必须转移到音频会议服务的现有会议桥接电话号码，假定它们满足国家/地区特定的要求，那么可以将现有会议桥接电话号码转移到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="650dd-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="650dd-535">将电话号码转移到 Microsoft 的复杂性根据国家或地区、运营商、涉及的线路数量以及许多其他影响因素而有很大不同。</span><span class="sxs-lookup"><span data-stu-id="650dd-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="650dd-536">要计划电话携号转网，请查看[携号转网指南](https://go.microsoft.com/fwlink/?linkid=859011)。</span><span class="sxs-lookup"><span data-stu-id="650dd-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="650dd-537">有关将电话号码转移到音频会议服务的其他详细信息，请参阅[将电话号码转移到 Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e)。</span><span class="sxs-lookup"><span data-stu-id="650dd-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="650dd-538">决策点</span><span class="sxs-lookup"><span data-stu-id="650dd-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-539">确定组织是否需要专用会议桥接电话号码</span><span class="sxs-lookup"><span data-stu-id="650dd-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="650dd-540">确定将如何为音频会议实施的范围内用户位置或办公地点获取专用会议桥接电话号码（从 Microsoft 获取，或转移现有电话号码）</span><span class="sxs-lookup"><span data-stu-id="650dd-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="650dd-541">如果你选择从 Microsoft 获取，请确定用于为音频会议实施的范围内用户位置或办公地点获取电话号码的方法（表单提交或自动）。</span><span class="sxs-lookup"><span data-stu-id="650dd-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="650dd-542">确定要为每个专用会议桥接电话号码设置的语言首选项</span><span class="sxs-lookup"><span data-stu-id="650dd-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="650dd-543">确定租户默认会议桥接电话号码</span><span class="sxs-lookup"><span data-stu-id="650dd-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="650dd-544">后续步骤</span><span class="sxs-lookup"><span data-stu-id="650dd-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-545">记录电话号码获取的主计划，详细说明为音频会议实施的范围内每个用户位置或办公地点获取电话号码的方式。</span><span class="sxs-lookup"><span data-stu-id="650dd-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="650dd-546">如果适用，完成<a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">新电话号码请求表单</a>，每个位置或办公地点一个表单。</span><span class="sxs-lookup"><span data-stu-id="650dd-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="650dd-547">如果你选择转移现有电话号码，请参阅<a href="https://go.microsoft.com/fwlink/?linkid=859011">携号转网指南</a>以对其进行计划并相应地调整音频会议实施时间线。</span><span class="sxs-lookup"><span data-stu-id="650dd-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="650dd-548">记录详细的会议桥接电话号码配置（共享和专用会议桥接电话号码、每个专用会议桥接电话号码的语言首选项、租户默认会议桥接电话号码）</span><span class="sxs-lookup"><span data-stu-id="650dd-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-549">办公地点</span><span class="sxs-lookup"><span data-stu-id="650dd-549">Office</span></span></th>
<th align="left"><span data-ttu-id="650dd-550">桥接号码获取和桥接类型</span><span class="sxs-lookup"><span data-stu-id="650dd-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="650dd-551">桥接号码</span><span class="sxs-lookup"><span data-stu-id="650dd-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="650dd-552">桥接语言</span><span class="sxs-lookup"><span data-stu-id="650dd-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-553">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-554">获取新的专用</span><span class="sxs-lookup"><span data-stu-id="650dd-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="650dd-555">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-556">英语（澳大利亚）</span><span class="sxs-lookup"><span data-stu-id="650dd-556">en-AU – English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-557">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-558">获取新的共享</span><span class="sxs-lookup"><span data-stu-id="650dd-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="650dd-559">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-560">英语（美国）、中文（简体，中国）</span><span class="sxs-lookup"><span data-stu-id="650dd-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-561">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-562">转网现有的专用</span><span class="sxs-lookup"><span data-stu-id="650dd-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="650dd-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="650dd-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="650dd-564">英语（英国）</span><span class="sxs-lookup"><span data-stu-id="650dd-564">en-GB – English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-566">获取新的专用</span><span class="sxs-lookup"><span data-stu-id="650dd-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="650dd-567">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-568">法语（法国）、英语（美国）</span><span class="sxs-lookup"><span data-stu-id="650dd-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-569">_表 10 会议桥接详细信息示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="650dd-570">本文档中上述示例表和后续表用作模板。</span><span class="sxs-lookup"><span data-stu-id="650dd-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="650dd-571">对于需要你在规划过程中完成的信息，以“TBA”（待添加）表示。</span><span class="sxs-lookup"><span data-stu-id="650dd-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="650dd-572">会议桥接设置</span><span class="sxs-lookup"><span data-stu-id="650dd-572">Conference bridge settings</span></span>

<span data-ttu-id="650dd-573">提供了与音频会议加入体验（会议进入和退出通知以及呼叫方名称记录）、会议组织者的 PIN 长度及电子邮件通知的组织范围的配置选项，以进一步定制最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="650dd-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="650dd-574">会议进入和退出通知以记录的名称、电话号码和声音形式提供。</span><span class="sxs-lookup"><span data-stu-id="650dd-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="650dd-575">PIN 长度可配置为 4 到 12 位，默认为 5 位 PIN。</span><span class="sxs-lookup"><span data-stu-id="650dd-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="650dd-576">默认情况下，在启用音频会议许可证或管理员完成的任何其他更改后，启用通知电子邮件。</span><span class="sxs-lookup"><span data-stu-id="650dd-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="650dd-577">你可以禁用此功能并控制贵组织的最终用户通信。</span><span class="sxs-lookup"><span data-stu-id="650dd-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="650dd-578">对于为其分配了音频会议许可证的用户，可配置默认的收费/免费电话号码（在音频会议协调中显示）以使用：</span><span class="sxs-lookup"><span data-stu-id="650dd-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="650dd-579">租户级别默认电话号码，或</span><span class="sxs-lookup"><span data-stu-id="650dd-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="650dd-580">自动分配的会议桥接电话号码，或</span><span class="sxs-lookup"><span data-stu-id="650dd-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="650dd-581">手动为每个用户定义的会议桥接电话号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="650dd-582">对于用户分散在各地且必须在会议邀请中提供本地号码作为默认会议桥接电话号码的全球性或全国性组织，用户特定的会议桥接电话号码通常很有用。</span><span class="sxs-lookup"><span data-stu-id="650dd-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="650dd-583">从不同城市或国家/地区加入的参与者可以查找在租户级别配置的其他号码，但这些号码并不直接显示在会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="650dd-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="650dd-584">会议邀请提供一个链接，参与者通过该链接可访问 Teams 会议拨入号码页面，在该页面中可查找距离其位置最近的可用会议桥接电话号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="650dd-585">你还可以配置各个会议组织者如何处理未经身份验证的呼叫方，是要求会议组织者先开始会议才能允许未经身份验证的呼叫方加入，还是允许未经身份验证的呼叫方开始会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="650dd-586">提供了可以针对每个用户应用的其他配置，用于控制使用免费电话会议桥接电话号码和从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="650dd-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="650dd-587">这些与成本相关的控制当前仅预览版用户可用。</span><span class="sxs-lookup"><span data-stu-id="650dd-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="650dd-588">你可以在 [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013) 上注册贵组织参与预览版计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="650dd-589">通过这些控制，你可以确定会议组织者是否可以为其组织的会议提供免费电话会议桥接电话号码，以及控制参与者是否可以从其组织的会议拨出。</span><span class="sxs-lookup"><span data-stu-id="650dd-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="650dd-590">拨出控制级别涵盖不允许拨出、仅允许拨出到国内号码、允许拨出到国内号码和国际号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="650dd-591">决策点</span><span class="sxs-lookup"><span data-stu-id="650dd-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-592">确定组织是否需要进入和退出通知，如果需要，确定要实施的通知类型（声音、电话号码或记录的名称）。</span><span class="sxs-lookup"><span data-stu-id="650dd-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="650dd-593">确定满足组织安全要求的音频会议 PIN 长度。</span><span class="sxs-lookup"><span data-stu-id="650dd-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="650dd-594">确定组织是否要控制与音频会议服务有关的最终用户通信。</span><span class="sxs-lookup"><span data-stu-id="650dd-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="650dd-595">确定要分配给每个会议组织者的会议桥接电话号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="650dd-596">确定某些会议组织者是否需要能够在其会议中使用免费电话会议桥接电话号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="650dd-597">确定某些会议组织者是否需要能够允许未经身份验证的呼叫方开始会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="650dd-598">确定某些会议组织者是否需要控制会议拨出。</span><span class="sxs-lookup"><span data-stu-id="650dd-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="650dd-599">后续步骤</span><span class="sxs-lookup"><span data-stu-id="650dd-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-600">记录详细的会议桥接设置（进入和退出通知、PIN 长度、配置更改电子邮件通知）。</span><span class="sxs-lookup"><span data-stu-id="650dd-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="650dd-601">记录要分配给每个会议组织者的会议桥接电话号码，以及用于控制未经身份验证的呼叫方策略、免费电话和拨出的相应设置。</span><span class="sxs-lookup"><span data-stu-id="650dd-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="650dd-602"><strong>启用会议进入和退出通知</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-603">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="650dd-604"><strong>进入/退出通知</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-605">声音</span><span class="sxs-lookup"><span data-stu-id="650dd-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="650dd-606"><strong>要求呼叫方在加入会议之前记录其名称</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-607">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-607">Disabled.</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="650dd-608"><strong>PIN 长度</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-608"><strong>PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-609">5</span><span class="sxs-lookup"><span data-stu-id="650dd-609">Example 5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="650dd-610"><strong>如果用户的拨入设置发生变化，自动向其发送电子邮件</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-611">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-611">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-612">_表 11 会议桥接设置示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-613">用户</span><span class="sxs-lookup"><span data-stu-id="650dd-613">User</span></span></th>
<th align="left"><span data-ttu-id="650dd-614">办公地点</span><span class="sxs-lookup"><span data-stu-id="650dd-614">Office</span></span></th>
<th align="left"><span data-ttu-id="650dd-615">默认收费电话号码</span><span class="sxs-lookup"><span data-stu-id="650dd-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="650dd-616">默认免费电话号码</span><span class="sxs-lookup"><span data-stu-id="650dd-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="650dd-617">允许免费电话</span><span class="sxs-lookup"><span data-stu-id="650dd-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="650dd-618">未经身份验证的呼叫方绕过休息室</span><span class="sxs-lookup"><span data-stu-id="650dd-618">Unauthenticated callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="650dd-619">会议拨出</span><span class="sxs-lookup"><span data-stu-id="650dd-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="650dd-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="650dd-621">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-622">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-623">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-624">是</span><span class="sxs-lookup"><span data-stu-id="650dd-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-625">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="650dd-626">国际和国内</span><span class="sxs-lookup"><span data-stu-id="650dd-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="650dd-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="650dd-628">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-629">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-630">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-631">否</span><span class="sxs-lookup"><span data-stu-id="650dd-631">No</span></span></td>
<td align="left"><span data-ttu-id="650dd-632">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-632">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-633">不允许</span><span class="sxs-lookup"><span data-stu-id="650dd-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="650dd-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="650dd-635">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-636">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-637">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-638">否</span><span class="sxs-lookup"><span data-stu-id="650dd-638">No</span></span></td>
<td align="left"><span data-ttu-id="650dd-639">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-639">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-640">不允许</span><span class="sxs-lookup"><span data-stu-id="650dd-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="650dd-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="650dd-642">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-643">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-644">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-645">是</span><span class="sxs-lookup"><span data-stu-id="650dd-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-646">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-646">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-647">国内</span><span class="sxs-lookup"><span data-stu-id="650dd-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="650dd-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="650dd-649">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-650">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-651">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-652">是</span><span class="sxs-lookup"><span data-stu-id="650dd-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-653">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="650dd-654">国内</span><span class="sxs-lookup"><span data-stu-id="650dd-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="650dd-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="650dd-656">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-657">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-658">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-659">是</span><span class="sxs-lookup"><span data-stu-id="650dd-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-660">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="650dd-661">国内</span><span class="sxs-lookup"><span data-stu-id="650dd-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="650dd-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="650dd-663">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="650dd-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="650dd-665">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-666">是</span><span class="sxs-lookup"><span data-stu-id="650dd-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-667">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="650dd-668">不允许</span><span class="sxs-lookup"><span data-stu-id="650dd-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="650dd-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="650dd-670">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="650dd-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="650dd-672">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-673">是</span><span class="sxs-lookup"><span data-stu-id="650dd-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-674">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-674">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-675">不允许</span><span class="sxs-lookup"><span data-stu-id="650dd-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="650dd-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="650dd-677">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="650dd-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="650dd-679">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-680">是</span><span class="sxs-lookup"><span data-stu-id="650dd-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-681">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-681">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-682">不允许</span><span class="sxs-lookup"><span data-stu-id="650dd-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="650dd-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="650dd-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-685">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-686">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-687">否</span><span class="sxs-lookup"><span data-stu-id="650dd-687">No</span></span></td>
<td align="left"><span data-ttu-id="650dd-688">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-688">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-689">国内</span><span class="sxs-lookup"><span data-stu-id="650dd-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="650dd-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="650dd-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-692">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-693">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-694">是</span><span class="sxs-lookup"><span data-stu-id="650dd-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="650dd-695">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="650dd-696">国际和国内</span><span class="sxs-lookup"><span data-stu-id="650dd-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="650dd-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="650dd-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-699">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-700">TBA</span><span class="sxs-lookup"><span data-stu-id="650dd-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="650dd-701">否</span><span class="sxs-lookup"><span data-stu-id="650dd-701">No</span></span></td>
<td align="left"><span data-ttu-id="650dd-702">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-702">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="650dd-703">国内</span><span class="sxs-lookup"><span data-stu-id="650dd-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-704">_表 12 会议桥接设置分配示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="650dd-705">拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-705">Dial plans</span></span>

<span data-ttu-id="650dd-706">作为 Office 365 的一项电话系统功能的[拨号计划](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)是一组规范化规则，用于将拨打的电话号码转换为替代格式（通常为 [E.164](https://go.microsoft.com/fwlink/?linkid=859014) 格式）以便进行呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="650dd-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="650dd-707">音频会议服务利用电话系统使用的相同功能在会议拨出应用场景中转换拨打的电话号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="650dd-708">拨号计划允许用户按其习惯的方式（例如，对于本地呼叫省略区号，对于国内呼叫省略国家/地区代码，甚至在进行会议拨出时使用简短数字拨号）拨打电话号码。</span><span class="sxs-lookup"><span data-stu-id="650dd-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="650dd-709">在 Office 365 的电话系统功能中，有两种类型的拨号计划：</span><span class="sxs-lookup"><span data-stu-id="650dd-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="650dd-710">**服务拨号计划**。</span><span class="sxs-lookup"><span data-stu-id="650dd-710">**Service dial plan**.</span></span> <span data-ttu-id="650dd-711">这是默认的拨号计划，基于 Office 365 使用位置适用于用户，无法修改。</span><span class="sxs-lookup"><span data-stu-id="650dd-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="650dd-712">**租户拨号计划**。</span><span class="sxs-lookup"><span data-stu-id="650dd-712">**Tenant dial plan**.</span></span> <span data-ttu-id="650dd-713">这是租户中的自定义拨号计划，进一步分成两种类型：</span><span class="sxs-lookup"><span data-stu-id="650dd-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="650dd-714">**租户-全局拨号计划** - 该拨号计划适用于租户中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="650dd-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="650dd-715">**租户-用户拨号计划** - 该拨号计划仅适用于特定用户。</span><span class="sxs-lookup"><span data-stu-id="650dd-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="650dd-716">有关进一步详细信息和示例，请参阅 [Office 365 呼叫计划拨号计划](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)文档。</span><span class="sxs-lookup"><span data-stu-id="650dd-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="650dd-717">分配给用户的有效拨号计划是服务拨号计划（基于用户的 Office 365 使用位置）和租户拨号计划（可以是租户-全局拨号计划或租户-用户拨号计划）的组合。</span><span class="sxs-lookup"><span data-stu-id="650dd-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![此表显示服务和租户拨号计划的三种组合。](media/audio_conferencing_image8.png)

<span data-ttu-id="650dd-719">每个租户拨号计划中最多可以有 25 个规范化规则，因此，需要避免重复出现已作为服务拨号计划的一部分提供的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="650dd-719">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="650dd-720">决策点</span><span class="sxs-lookup"><span data-stu-id="650dd-720">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-721">确定贵组织是否需要自定义拨号计划（业务需求、采用需求等）。</span><span class="sxs-lookup"><span data-stu-id="650dd-721">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="650dd-722">如果适用，确定租户拨号计划（租户-全局或租户-用户）的范围以支持自定义拨号计划的要求。</span><span class="sxs-lookup"><span data-stu-id="650dd-722">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="650dd-723">如果适用，确定为支持音频会议实施的范围内用户位置或办公地点将创建的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-723">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="650dd-724">如果适用，确定哪个用户需要自定义拨号计划以及要为每个用户分配的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-724">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="650dd-725">后续步骤</span><span class="sxs-lookup"><span data-stu-id="650dd-725">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="650dd-726">记录自定义拨号计划和要配置为音频会议实施的一部分的关联规范化规则。</span><span class="sxs-lookup"><span data-stu-id="650dd-726">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="650dd-727">记录要为其分配自定义拨号计划的用户以及要为每个用户分配的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-727">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-728">租户拨号计划名称/说明</span><span class="sxs-lookup"><span data-stu-id="650dd-728">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="650dd-729">规范化规则名称/说明</span><span class="sxs-lookup"><span data-stu-id="650dd-729">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="650dd-730">模式</span><span class="sxs-lookup"><span data-stu-id="650dd-730">IPv6 Pattern</span></span></th>
<th align="left"><span data-ttu-id="650dd-731">转换</span><span class="sxs-lookup"><span data-stu-id="650dd-731">Translation</span></span></th>
<th align="left"><span data-ttu-id="650dd-732">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="650dd-732">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="650dd-733"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-733"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="650dd-734"><em>新南威尔士北莱德 Epping 路一号，AU 拨号计划</em></span><span class="sxs-lookup"><span data-stu-id="650dd-734"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="650dd-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="650dd-736"><em>澳大利亚新南威尔士北莱德 Epping 路一号办公地点的内部号码 (x7000 - x7999)</em></span><span class="sxs-lookup"><span data-stu-id="650dd-736"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-737">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="650dd-737">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="650dd-738">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="650dd-738">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-739">True</span><span class="sxs-lookup"><span data-stu-id="650dd-739">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-740"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-740"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="650dd-741"><em>澳大利亚新南威尔士的本地号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-741"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-742">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="650dd-742">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="650dd-743">+612$1</span><span class="sxs-lookup"><span data-stu-id="650dd-743">+612$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-744">False</span><span class="sxs-lookup"><span data-stu-id="650dd-744">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-745"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-745"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="650dd-746"><em>澳大利亚的免费电话号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-746"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-747">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="650dd-747">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="650dd-748">+61$1</span><span class="sxs-lookup"><span data-stu-id="650dd-748">+61$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-749">False</span><span class="sxs-lookup"><span data-stu-id="650dd-749">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-750"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-750"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="650dd-751"><em>澳大利亚的服务号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-751"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-752">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="650dd-752">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="650dd-753">$1</span><span class="sxs-lookup"><span data-stu-id="650dd-753">$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-754">False</span><span class="sxs-lookup"><span data-stu-id="650dd-754">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="650dd-755"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-755"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="650dd-756"><em>新加坡 OMB，SG 拨号计划</em></span><span class="sxs-lookup"><span data-stu-id="650dd-756"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="650dd-757"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-757"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="650dd-758"><em>新加坡 OMB 办公地点的内部号码 (x8000 - x8999)</em></span><span class="sxs-lookup"><span data-stu-id="650dd-758"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-759">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="650dd-759">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="650dd-760">+656888$1</span><span class="sxs-lookup"><span data-stu-id="650dd-760">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-761">True</span><span class="sxs-lookup"><span data-stu-id="650dd-761">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-762"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-762"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="650dd-763"><em>新加坡的免费电话号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-763"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-764">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="650dd-764">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="650dd-765">+65$1</span><span class="sxs-lookup"><span data-stu-id="650dd-765">+65$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-766">False</span><span class="sxs-lookup"><span data-stu-id="650dd-766">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-767"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-767"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="650dd-768"><em>新加坡的服务号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-768"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-769">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="650dd-769">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="650dd-770">$1</span><span class="sxs-lookup"><span data-stu-id="650dd-770">$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-771">False</span><span class="sxs-lookup"><span data-stu-id="650dd-771">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="650dd-772"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-772"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="650dd-773"><em>39 quai du Président Roosevelt Issy-les-Moulineaux，法国拨号计划</em></span><span class="sxs-lookup"><span data-stu-id="650dd-773"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="650dd-774"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-774"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="650dd-775"><em>法国 Issy-les-Moulineaux 39 quai du Président Roosevelt 办公地点的内部号码 (x7000 - x7999)</em></span><span class="sxs-lookup"><span data-stu-id="650dd-775"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-776">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="650dd-776">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="650dd-777">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="650dd-777">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-778">True</span><span class="sxs-lookup"><span data-stu-id="650dd-778">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-779"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-779"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="650dd-780"><em>法国的免费电话号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-780"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="650dd-781">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="650dd-781">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="650dd-782">+33$1</span><span class="sxs-lookup"><span data-stu-id="650dd-782">+33$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-783">False</span><span class="sxs-lookup"><span data-stu-id="650dd-783">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="650dd-784"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-784"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="650dd-785"><em>法国的服务号码规范化</em></span><span class="sxs-lookup"><span data-stu-id="650dd-785"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="650dd-786">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="650dd-786">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="650dd-787">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="650dd-787">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="650dd-788">$1</span><span class="sxs-lookup"><span data-stu-id="650dd-788">$1</span></span></td>
<td align="left"><span data-ttu-id="650dd-789">False</span><span class="sxs-lookup"><span data-stu-id="650dd-789">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-790">_表 13 租户拨号计划示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-790">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="650dd-791">用户</span><span class="sxs-lookup"><span data-stu-id="650dd-791">User</span></span></th>
<th align="left"><span data-ttu-id="650dd-792">办公地点</span><span class="sxs-lookup"><span data-stu-id="650dd-792">Office</span></span></th>
<th align="left"><span data-ttu-id="650dd-793">拨号计划类型</span><span class="sxs-lookup"><span data-stu-id="650dd-793">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="650dd-794">拨号计划名称</span><span class="sxs-lookup"><span data-stu-id="650dd-794">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-795">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="650dd-795">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="650dd-796">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-796">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-797">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-797">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-798">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="650dd-798">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-799">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="650dd-799">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="650dd-800">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-800">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-801">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-801">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-802">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="650dd-802">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-803">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="650dd-803">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="650dd-804">Epping 路一号</span><span class="sxs-lookup"><span data-stu-id="650dd-804">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="650dd-805">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-805">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-806">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="650dd-806">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-807">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="650dd-807">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="650dd-808">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-808">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-809">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-809">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-810">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="650dd-810">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-811">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="650dd-811">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="650dd-812">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-812">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-813">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-813">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-814">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="650dd-814">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-815">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="650dd-815">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="650dd-816">滨海林荫道一号</span><span class="sxs-lookup"><span data-stu-id="650dd-816">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="650dd-817">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-817">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-818">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="650dd-818">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-819">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="650dd-819">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="650dd-820">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-820">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-821">服务拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-821">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-822">不适用</span><span class="sxs-lookup"><span data-stu-id="650dd-822">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-823">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="650dd-823">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="650dd-824">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-824">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-825">服务拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-825">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-826">不适用</span><span class="sxs-lookup"><span data-stu-id="650dd-826">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-827">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="650dd-827">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="650dd-828">伦敦桥大街 32 号</span><span class="sxs-lookup"><span data-stu-id="650dd-828">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="650dd-829">服务拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-829">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-830">不适用</span><span class="sxs-lookup"><span data-stu-id="650dd-830">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-831">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="650dd-831">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="650dd-832">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-832">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-833">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-833">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-834">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="650dd-834">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-835">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="650dd-835">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="650dd-836">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-836">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-837">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-837">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-838">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="650dd-838">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="650dd-839">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="650dd-839">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="650dd-840">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="650dd-840">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="650dd-841">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-841">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="650dd-842">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="650dd-842">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-843">_表 14 拨号计划分配示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-843">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="650dd-844">Microsoft Teams 配置</span><span class="sxs-lookup"><span data-stu-id="650dd-844">Microsoft Teams configurations</span></span>

<span data-ttu-id="650dd-845">由于音频会议仅可用于安排的会议，因此必须启用控制会议安排（私人会议和频道会议）的租户级别配置。</span><span class="sxs-lookup"><span data-stu-id="650dd-845">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="650dd-846">当前，如果贵组织具有合规性要求以确保所有会议讨论均可发现，当组织者有本地 Exchange 邮箱时，你应禁用私人会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-846">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="650dd-847">在另外一个用例中，如果组织中的所有会议都必须仅<strong>对受邀各方</strong>可见，为了避免向未受邀各方透露会议信息，我们建议禁用在<strong>频道</strong>中安排会议的功能。</span><span class="sxs-lookup"><span data-stu-id="650dd-847">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="650dd-848">这些设置以租户级别配置方式提供，适用于组织中的所有用户，将影响 Teams 中的所有会议安排，并不限于**使用**音频会议的 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-848">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="650dd-849">决策点</span><span class="sxs-lookup"><span data-stu-id="650dd-849">Policy Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-850">确定组织是否需要启用或禁用安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-850">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="650dd-851">确定组织是否需要启用或禁用安排频道会议。</span><span class="sxs-lookup"><span data-stu-id="650dd-851">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="650dd-852">后续步骤</span><span class="sxs-lookup"><span data-stu-id="650dd-852">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="650dd-853">记录 Teams 的会议安排配置。</span><span class="sxs-lookup"><span data-stu-id="650dd-853">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="650dd-854"><strong>允许安排私人会议</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-854"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-855">启用</span><span class="sxs-lookup"><span data-stu-id="650dd-855">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="650dd-856"><strong>允许安排频道会议</strong></span><span class="sxs-lookup"><span data-stu-id="650dd-856"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="650dd-857">禁用</span><span class="sxs-lookup"><span data-stu-id="650dd-857">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="650dd-858">_表 15 Microsoft Teams 会议配置示例_</span><span class="sxs-lookup"><span data-stu-id="650dd-858">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="650dd-859">记录技术实施计划</span><span class="sxs-lookup"><span data-stu-id="650dd-859">Document technical implementation plan</span></span>

<span data-ttu-id="650dd-860">使用上面的决策点记录你的技术实施计划。</span><span class="sxs-lookup"><span data-stu-id="650dd-860">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="650dd-861">此技术实施计划将为项目团队（可以包括 FastTrack 或部署合作伙伴）提供为实施音频会议执行技术上线所需的信息。</span><span class="sxs-lookup"><span data-stu-id="650dd-861">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="650dd-862">通常，技术实施计划包含以下主要部分：</span><span class="sxs-lookup"><span data-stu-id="650dd-862">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="650dd-863">音频会议服务地点支持列表</span><span class="sxs-lookup"><span data-stu-id="650dd-863">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="650dd-864">音频会议组织者的许可证分配列表</span><span class="sxs-lookup"><span data-stu-id="650dd-864">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="650dd-865">通信点数计划数量</span><span class="sxs-lookup"><span data-stu-id="650dd-865">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="650dd-866">会议桥接详细信息</span><span class="sxs-lookup"><span data-stu-id="650dd-866">Conference bridge details</span></span>

-   <span data-ttu-id="650dd-867">会议桥接设置</span><span class="sxs-lookup"><span data-stu-id="650dd-867">Conference bridge settings</span></span>

-   <span data-ttu-id="650dd-868">会议桥接设置分配</span><span class="sxs-lookup"><span data-stu-id="650dd-868">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="650dd-869">租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="650dd-869">Tenant dial plans</span></span>

-   <span data-ttu-id="650dd-870">拨号计划分配</span><span class="sxs-lookup"><span data-stu-id="650dd-870">Dial plan assignments</span></span>

-   <span data-ttu-id="650dd-871">Microsoft Teams 会议配置</span><span class="sxs-lookup"><span data-stu-id="650dd-871">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="650dd-872">完成成功计划和技术实施计划后，你现在即可带领贵组织进入 Office 365 客户旅程的后续步骤。</span><span class="sxs-lookup"><span data-stu-id="650dd-872">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="650dd-873">上线</span><span class="sxs-lookup"><span data-stu-id="650dd-873">Onboard</span></span>
=======

<span data-ttu-id="650dd-874">*即将提供。*</span><span class="sxs-lookup"><span data-stu-id="650dd-874">*Coming Soon*</span></span>

<a name="drive-value"></a><span data-ttu-id="650dd-875">推动价值</span><span class="sxs-lookup"><span data-stu-id="650dd-875">Drive Value</span></span>
===========

<span data-ttu-id="650dd-876">*即将提供。*</span><span class="sxs-lookup"><span data-stu-id="650dd-876">*Coming Soon*</span></span>



### <a name="see-also"></a><span data-ttu-id="650dd-877">另请参阅</span><span class="sxs-lookup"><span data-stu-id="650dd-877">See also</span></span>
[<span data-ttu-id="650dd-878">为 Skype for Business 设置电话拨入式会议或 PSTN 会议</span><span class="sxs-lookup"><span data-stu-id="650dd-878">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
