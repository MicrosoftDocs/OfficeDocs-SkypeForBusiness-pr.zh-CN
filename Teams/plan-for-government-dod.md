---
title: Microsoft 365 政府版规划 - DoD 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 面向 IT 专业人员为中处理数据受美国政府 DoD 法规的实体的驱动器 Office 365 部署指南。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 239996abd87c52905758d6bff5ddeb6bf7805e89
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462761"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a><span data-ttu-id="c1f87-103">Microsoft 365 政府版-DoD 部署规划</span><span class="sxs-lookup"><span data-stu-id="c1f87-103">Plan for Microsoft 365 Government - DoD deployments</span></span>

<span data-ttu-id="c1f87-104">本指南为 IT 专业人员带来了部署 Office 365 在美国联邦政府实体或处理受制政府法规的数据和要求，其中使用 Microsoft 365 政府版 – DoD 适合于其他实体满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="c1f87-105">如果您的组织已满足 Microsoft 365 政府 – DoD 资格要求和应用于并被接受到程序，您可以跳过步骤 1 和 2，直接转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="c1f87-105">If your organization has already met the Microsoft 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="c1f87-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="c1f87-106">Step 1.</span></span> <span data-ttu-id="c1f87-107">确定您的组织是否需要 Microsoft 365 政府-DoD，并且符合资格要求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-107">Determine whether your organization needs Microsoft 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="c1f87-108">Microsoft 365 政府-DoD 环境提供符合美国的云服务的政府要求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-108">The Microsoft 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="c1f87-109">除了享受的特性和功能的 Office 365，组织受益于对 Microsoft 365 政府版 – DoD 是唯一的以下功能：</span><span class="sxs-lookup"><span data-stu-id="c1f87-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – DoD:</span></span>

- <span data-ttu-id="c1f87-110">贵组织的客户内容逻辑分离从 microsoft 商业的 Office 365 服务中的客户内容中。</span><span class="sxs-lookup"><span data-stu-id="c1f87-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="c1f87-111">美国境内存储贵组织的客户内容。</span><span class="sxs-lookup"><span data-stu-id="c1f87-111">Your organization’s customer content is stored within the United States.</span></span>
- <span data-ttu-id="c1f87-112">贵组织的客户内容的访问仅限于屏蔽 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="c1f87-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="c1f87-113">Microsoft 365 政府版 – DoD 遵守认证和资格鉴定所需的美国公共部门客户。</span><span class="sxs-lookup"><span data-stu-id="c1f87-113">Microsoft 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="c1f87-114">您可以找到有关 Microsoft 365 政府 – DoD 提供在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)，包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)美国政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1f87-114">You can find more information about the Microsoft 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="c1f87-115">[Office 365 美国政府服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)介绍平台的优点，在会议合规性要求美国境内居中。</span><span class="sxs-lookup"><span data-stu-id="c1f87-115">The [Office 365 US Government service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform’s benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="c1f87-116">您可能希望将服务说明中的信息的转移到 Excel 工作簿和添加两个列：**相关的我的组织是/否**和**满足 Y/N 我的组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="c1f87-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="c1f87-117">然后您可以查看此列表与同事以确认此服务满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c1f87-118">决策点</span><span class="sxs-lookup"><span data-stu-id="c1f87-118">Decision points</span></span>|<ul><li><span data-ttu-id="c1f87-119">确定 Microsoft 365 政府-DoD 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="c1f87-119">Decide whether Microsoft 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="c1f87-120">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-120">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="c1f87-121">Microsoft 365 政府-DoD 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="c1f87-121">Microsoft 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="c1f87-122">非 – 美国政府客户可以选择从[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)数。</span><span class="sxs-lookup"><span data-stu-id="c1f87-122">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---dod"></a><span data-ttu-id="c1f87-123">第 2 步</span><span class="sxs-lookup"><span data-stu-id="c1f87-123">Step 2.</span></span> <span data-ttu-id="c1f87-124">适用于 Microsoft 365 政府-DoD</span><span class="sxs-lookup"><span data-stu-id="c1f87-124">Apply for Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="c1f87-125">无决定的此服务适合您的组织，启动[此服务应用](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="c1f87-125">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a><span data-ttu-id="c1f87-126">第 3 步</span><span class="sxs-lookup"><span data-stu-id="c1f87-126">Step 3.</span></span> <span data-ttu-id="c1f87-127">了解 Microsoft 365 政府-DoD 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="c1f87-127">Understand Microsoft 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="c1f87-128">我们建议您执行时间仔细检查您的[管理和安全设置](enable-features-office-365.md)，然后再对其进行修改和对默认安全设置进行任何更改之前，请考虑影响合规性。</span><span class="sxs-lookup"><span data-stu-id="c1f87-128">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c1f87-129">决策点</span><span class="sxs-lookup"><span data-stu-id="c1f87-129">Decision point</span></span>|<ul><li><span data-ttu-id="c1f87-130">决定是否需要修改任何默认 Microsoft 365 政府-DoD 安全设置，解决首先了解任何更改的影响您可能会使。</span><span class="sxs-lookup"><span data-stu-id="c1f87-130">Decide whether you’ll need to modify any of the default Microsoft 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a><span data-ttu-id="c1f87-131">第 4 步</span><span class="sxs-lookup"><span data-stu-id="c1f87-131">Step 4.</span></span> <span data-ttu-id="c1f87-132">了解哪些团队功能在 Microsoft 365 政府-DoD 当前可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-132">Understand which Teams capabilities are currently available in Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="c1f87-133">若要容纳政府云客户的要求，有一些区别 リ モ ・ Microsoft 365 政府-DoD 和团队中的企业计划。</span><span class="sxs-lookup"><span data-stu-id="c1f87-133">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="c1f87-134">请参阅下表可查看可用的功能。</span><span class="sxs-lookup"><span data-stu-id="c1f87-134">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="c1f87-135">功能</span><span class="sxs-lookup"><span data-stu-id="c1f87-135">Feature</span></span>                     | <span data-ttu-id="c1f87-136">DoD</span><span class="sxs-lookup"><span data-stu-id="c1f87-136">DoD</span></span>       |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="c1f87-137">基本</span><span class="sxs-lookup"><span data-stu-id="c1f87-137">Base</span></span> | <span data-ttu-id="c1f87-138">登录</span><span class="sxs-lookup"><span data-stu-id="c1f87-138">Login</span></span> | <span data-ttu-id="c1f87-139">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-139">Available</span></span> |
| | <span data-ttu-id="c1f87-140">状态</span><span class="sxs-lookup"><span data-stu-id="c1f87-140">Presence</span></span> | <span data-ttu-id="c1f87-141">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-141">Available</span></span> |
| | <span data-ttu-id="c1f87-142">统一的状态 (Skype 业务和团队统一)</span><span class="sxs-lookup"><span data-stu-id="c1f87-142">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="c1f87-143">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-143">On the Government backlog</span></span> |
| <span data-ttu-id="c1f87-144">活动</span><span class="sxs-lookup"><span data-stu-id="c1f87-144">Activity</span></span> | <span data-ttu-id="c1f87-145">源</span><span class="sxs-lookup"><span data-stu-id="c1f87-145">Feed</span></span> | <span data-ttu-id="c1f87-146">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-146">Available</span></span> |
|  | <span data-ttu-id="c1f87-147">我的活动</span><span class="sxs-lookup"><span data-stu-id="c1f87-147">My Activity</span></span> | <span data-ttu-id="c1f87-148">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-148">Available</span></span> |
| <span data-ttu-id="c1f87-149">聊天</span><span class="sxs-lookup"><span data-stu-id="c1f87-149">Chat</span></span> | <span data-ttu-id="c1f87-150">对话</span><span class="sxs-lookup"><span data-stu-id="c1f87-150">Conversation</span></span> | <span data-ttu-id="c1f87-151">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-151">Available</span></span> |
| | <span data-ttu-id="c1f87-152">文件</span><span class="sxs-lookup"><span data-stu-id="c1f87-152">Files</span></span> | <span data-ttu-id="c1f87-153">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-153">Available</span></span> |
| | <span data-ttu-id="c1f87-154">组织结构图</span><span class="sxs-lookup"><span data-stu-id="c1f87-154">Org chart</span></span> | <span data-ttu-id="c1f87-155">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-155">Available</span></span> |
| | <span data-ttu-id="c1f87-156">活动</span><span class="sxs-lookup"><span data-stu-id="c1f87-156">Activity</span></span> | <span data-ttu-id="c1f87-157">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-157">Available</span></span> |
| | <span data-ttu-id="c1f87-158">互操作 (1:1 团队-Skype 对业务聊天)</span><span class="sxs-lookup"><span data-stu-id="c1f87-158">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="c1f87-159">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-159">On the Government backlog</span></span> |
| <span data-ttu-id="c1f87-160">团队</span><span class="sxs-lookup"><span data-stu-id="c1f87-160">Teams</span></span> | <span data-ttu-id="c1f87-161">频道消息</span><span class="sxs-lookup"><span data-stu-id="c1f87-161">Channel message</span></span> | <span data-ttu-id="c1f87-162">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-162">Available</span></span> |
| | <span data-ttu-id="c1f87-163">通道文件</span><span class="sxs-lookup"><span data-stu-id="c1f87-163">Channel files</span></span> | <span data-ttu-id="c1f87-164">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-164">Available</span></span> |
| | <span data-ttu-id="c1f87-165">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="c1f87-165">OneNote tab</span></span> | <span data-ttu-id="c1f87-166">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-166">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-167">电子邮件通道</span><span class="sxs-lookup"><span data-stu-id="c1f87-167">Email a channel</span></span> | <span data-ttu-id="c1f87-168">不可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-168">Not available</span></span> |
| | <span data-ttu-id="c1f87-169">添加成员</span><span class="sxs-lookup"><span data-stu-id="c1f87-169">Add member</span></span> | <span data-ttu-id="c1f87-170">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-170">Available</span></span> |
| | <span data-ttu-id="c1f87-171">来宾访问</span><span class="sxs-lookup"><span data-stu-id="c1f87-171">Guest access</span></span> | <span data-ttu-id="c1f87-172">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-172">On the Government backlog</span></span> |
| <span data-ttu-id="c1f87-173">会议</span><span class="sxs-lookup"><span data-stu-id="c1f87-173">Meetings</span></span> | <span data-ttu-id="c1f87-174">安排会议</span><span class="sxs-lookup"><span data-stu-id="c1f87-174">Schedule meeting</span></span> | <span data-ttu-id="c1f87-175">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-175">Available</span></span> |
| | <span data-ttu-id="c1f87-176">加入会议</span><span class="sxs-lookup"><span data-stu-id="c1f87-176">Join meeting</span></span> | <span data-ttu-id="c1f87-177">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-177">Available</span></span> |
| | <span data-ttu-id="c1f87-178">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="c1f87-178">VoIP meeting</span></span> | <span data-ttu-id="c1f87-179">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-179">Available</span></span> |
| | <span data-ttu-id="c1f87-180">桌面共享</span><span class="sxs-lookup"><span data-stu-id="c1f87-180">Desktop sharing</span></span> | <span data-ttu-id="c1f87-181">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-181">Available</span></span> |
| | <span data-ttu-id="c1f87-182">在共享授予 and 获得控制权</span><span class="sxs-lookup"><span data-stu-id="c1f87-182">Give and take control in sharing</span></span> | <span data-ttu-id="c1f87-183">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-183">Available</span></span> |
| | <span data-ttu-id="c1f87-184">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="c1f87-184">Connect from a conference room</span></span> | <span data-ttu-id="c1f87-185">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-185">Available</span></span> |
| | <span data-ttu-id="c1f87-186">云录制</span><span class="sxs-lookup"><span data-stu-id="c1f87-186">Cloud recording</span></span> | <span data-ttu-id="c1f87-187">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-187">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-188">会议笔记</span><span class="sxs-lookup"><span data-stu-id="c1f87-188">Meeting notes</span></span> | <span data-ttu-id="c1f87-189">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-189">Available</span></span> |
| | <span data-ttu-id="c1f87-190">广播的会议</span><span class="sxs-lookup"><span data-stu-id="c1f87-190">Broadcast meetings</span></span> | <span data-ttu-id="c1f87-191">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-191">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-192">联盟的会议</span><span class="sxs-lookup"><span data-stu-id="c1f87-192">Federated meetings</span></span> | <span data-ttu-id="c1f87-193">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-193">Available</span></span> |
| | <span data-ttu-id="c1f87-194">曲面集线器支持</span><span class="sxs-lookup"><span data-stu-id="c1f87-194">Surface Hub support</span></span> | <span data-ttu-id="c1f87-195">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-195">On the Government backlog</span></span> |
| <span data-ttu-id="c1f87-196">呼叫</span><span class="sxs-lookup"><span data-stu-id="c1f87-196">Calls</span></span> | <span data-ttu-id="c1f87-197">联系人</span><span class="sxs-lookup"><span data-stu-id="c1f87-197">Contacts</span></span> | <span data-ttu-id="c1f87-198">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-198">Available</span></span> |
| | <span data-ttu-id="c1f87-199">历史记录</span><span class="sxs-lookup"><span data-stu-id="c1f87-199">History</span></span> | <span data-ttu-id="c1f87-200">可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-200">Available</span></span> |
| | <span data-ttu-id="c1f87-201">语音邮件</span><span class="sxs-lookup"><span data-stu-id="c1f87-201">Voicemail</span></span> | <span data-ttu-id="c1f87-202">可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-202">Available</span></span> |
| | <span data-ttu-id="c1f87-203">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="c1f87-203">VoIP call</span></span> | <span data-ttu-id="c1f87-204">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-204">Available</span></span> |
| | <span data-ttu-id="c1f87-205">Skype for Business 的团队呼叫</span><span class="sxs-lookup"><span data-stu-id="c1f87-205">Skype for Business - Teams calling</span></span> | <span data-ttu-id="c1f87-206">可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-206">Available</span></span> |
| | <span data-ttu-id="c1f87-207">通话套餐</span><span class="sxs-lookup"><span data-stu-id="c1f87-207">Calling Plans</span></span> | <span data-ttu-id="c1f87-208">不可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-208">Not Available</span></span> |
| | <span data-ttu-id="c1f87-209">音频会议 （通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="c1f87-209">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="c1f87-210">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-210">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-211">Microsoft 直接路由的电话系统</span><span class="sxs-lookup"><span data-stu-id="c1f87-211">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="c1f87-212">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-212">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-213">PSTN 呼叫者会议厅</span><span class="sxs-lookup"><span data-stu-id="c1f87-213">Lobby for PSTN callers</span></span> | <span data-ttu-id="c1f87-214">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-214">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-215">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c1f87-215">Call queue</span></span> | <span data-ttu-id="c1f87-216">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-216">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-217">经理和代理人支持</span><span class="sxs-lookup"><span data-stu-id="c1f87-217">Boss and delegate support</span></span> | <span data-ttu-id="c1f87-218">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-218">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-219">咨询和安全传输</span><span class="sxs-lookup"><span data-stu-id="c1f87-219">Consultative and safe transfer</span></span> | <span data-ttu-id="c1f87-220">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-220">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-221">请勿打扰突破性</span><span class="sxs-lookup"><span data-stu-id="c1f87-221">Do not disturb breakthrough</span></span> | <span data-ttu-id="c1f87-222">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-222">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-223">特殊铃声</span><span class="sxs-lookup"><span data-stu-id="c1f87-223">Distinctive ring</span></span> | <span data-ttu-id="c1f87-224">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-224">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-225">1： 与团队业务的 Skype 组呼叫升级到 1 和 PSTN 参与者</span><span class="sxs-lookup"><span data-stu-id="c1f87-225">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="c1f87-226">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-226">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-227">转发到组</span><span class="sxs-lookup"><span data-stu-id="c1f87-227">Forward to group</span></span> | <span data-ttu-id="c1f87-228">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-228">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-229">转接到 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="c1f87-229">Transfer to PSTN call</span></span> | <span data-ttu-id="c1f87-230">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-230">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-231">紧急呼叫-调用计划</span><span class="sxs-lookup"><span data-stu-id="c1f87-231">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="c1f87-232">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-232">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-233">对现有认证的 SIP 电话支持</span><span class="sxs-lookup"><span data-stu-id="c1f87-233">Support for existing certified SIP phones</span></span> | <span data-ttu-id="c1f87-234">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-234">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-235">隐藏的 USB</span><span class="sxs-lookup"><span data-stu-id="c1f87-235">USB HID</span></span> | <span data-ttu-id="c1f87-236">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-236">Available</span></span> |
| | <span data-ttu-id="c1f87-237">对呼叫和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="c1f87-237">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="c1f87-238">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-238">Available</span></span> |
| | <span data-ttu-id="c1f87-239">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="c1f87-239">Organization auto attendant</span></span> | <span data-ttu-id="c1f87-240">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="c1f87-240">On the Government backlog</span></span> |
| | <span data-ttu-id="c1f87-241">Skype 消费者-团队呼叫支持</span><span class="sxs-lookup"><span data-stu-id="c1f87-241">Skype consumer - Teams call support</span></span> | <span data-ttu-id="c1f87-242">不可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-242">Not available</span></span> |
| <span data-ttu-id="c1f87-243">文件</span><span class="sxs-lookup"><span data-stu-id="c1f87-243">Files</span></span> | <span data-ttu-id="c1f87-244">最新</span><span class="sxs-lookup"><span data-stu-id="c1f87-244">Recent</span></span> | <span data-ttu-id="c1f87-245">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-245">Available</span></span> |
| | <span data-ttu-id="c1f87-246">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1f87-246">Microsoft Teams</span></span> | <span data-ttu-id="c1f87-247">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-247">Available</span></span> |
| <span data-ttu-id="c1f87-248">存储</span><span class="sxs-lookup"><span data-stu-id="c1f87-248">Store</span></span> | <span data-ttu-id="c1f87-249">应用程序商店</span><span class="sxs-lookup"><span data-stu-id="c1f87-249">App Store</span></span> | <span data-ttu-id="c1f87-250">不可用</span><span class="sxs-lookup"><span data-stu-id="c1f87-250">Not available</span></span> |
| <span data-ttu-id="c1f87-251">搜索</span><span class="sxs-lookup"><span data-stu-id="c1f87-251">Search</span></span> | <span data-ttu-id="c1f87-252">邮件</span><span class="sxs-lookup"><span data-stu-id="c1f87-252">Messages</span></span> | <span data-ttu-id="c1f87-253">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-253">Available</span></span> |
| | <span data-ttu-id="c1f87-254">人员</span><span class="sxs-lookup"><span data-stu-id="c1f87-254">People</span></span> | <span data-ttu-id="c1f87-255">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-255">Available</span></span> |
| | <span data-ttu-id="c1f87-256">文件</span><span class="sxs-lookup"><span data-stu-id="c1f87-256">Files</span></span> | <span data-ttu-id="c1f87-257">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-257">Available</span></span> |
| | <span data-ttu-id="c1f87-258">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="c1f87-258">Slash commands</span></span> | <span data-ttu-id="c1f87-259">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-259">Available</span></span> |
| <span data-ttu-id="c1f87-260">合规性</span><span class="sxs-lookup"><span data-stu-id="c1f87-260">Compliance</span></span> | <span data-ttu-id="c1f87-261">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="c1f87-261">Compliance content search</span></span> | <span data-ttu-id="c1f87-262">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-262">Available</span></span> |
| | <span data-ttu-id="c1f87-263">保留</span><span class="sxs-lookup"><span data-stu-id="c1f87-263">Retention</span></span> | <span data-ttu-id="c1f87-264">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-264">Available</span></span> |
| | <span data-ttu-id="c1f87-265">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="c1f87-265">Audit log search</span></span> | <span data-ttu-id="c1f87-266">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-266">Available</span></span> |
| | <span data-ttu-id="c1f87-267">合法保留</span><span class="sxs-lookup"><span data-stu-id="c1f87-267">Legal hold</span></span> | <span data-ttu-id="c1f87-268">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-268">Available</span></span> |
| | <span data-ttu-id="c1f87-269">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="c1f87-269">eDiscovery</span></span> | <span data-ttu-id="c1f87-270">有空</span><span class="sxs-lookup"><span data-stu-id="c1f87-270">Available</span></span> |

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c1f87-271">决策点</span><span class="sxs-lookup"><span data-stu-id="c1f87-271">Decision point</span></span>|<ul><li><span data-ttu-id="c1f87-272">确定是否团队功能集能满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-272">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="c1f87-273">第 5 步</span><span class="sxs-lookup"><span data-stu-id="c1f87-273">Step 5.</span></span> <span data-ttu-id="c1f87-274">规划调控</span><span class="sxs-lookup"><span data-stu-id="c1f87-274">Plan for governance</span></span>

<span data-ttu-id="c1f87-275">确定调控和如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="c1f87-275">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="c1f87-276">有关详细信息，请转到[团队中的治理规划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="c1f87-276">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c1f87-277">决策点</span><span class="sxs-lookup"><span data-stu-id="c1f87-277">Decision point</span></span> |<ul><li><span data-ttu-id="c1f87-278">确定并记录您管理要求，[团队中的治理规划](plan-teams-governance.md)中的指南。</span><span class="sxs-lookup"><span data-stu-id="c1f87-278">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="c1f87-279">第 6 步</span><span class="sxs-lookup"><span data-stu-id="c1f87-279">Step 6.</span></span> <span data-ttu-id="c1f87-280">部署团队协作</span><span class="sxs-lookup"><span data-stu-id="c1f87-280">Deploy Teams for collaboration</span></span>

<span data-ttu-id="c1f87-281">您已向 Microsoft 365 政府 – DoD，onboarded 后，您可以按照使用[FastTrack](https://www.microsoft.com/fasttrack)和到板载您选择的合作伙伴服务的标准的部署方法。</span><span class="sxs-lookup"><span data-stu-id="c1f87-281">After you’ve been onboarded to Microsoft 365 Government – DoD, you can follow the standard deployment approach of using [FastTrack](https://www.microsoft.com/fasttrack) and your chosen partner to onboard the service.</span></span>

<span data-ttu-id="c1f87-282">当您准备好时，到[启用通过团队和通道组织内的协作](teams-overview.md)部署团队。</span><span class="sxs-lookup"><span data-stu-id="c1f87-282">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="c1f87-283">请务必与您应用和变更管理团队或团队拥护者。</span><span class="sxs-lookup"><span data-stu-id="c1f87-283">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>
