---
title: Microsoft 365 政府版规划 - DoD 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 面向 IT 专业人士的指南，用于驱动在处理受美国政府 DoD 法规制约的数据的实体中的 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: be952d838135a03a873d7193118febf5639bd415
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836852"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a><span data-ttu-id="96281-103">规划 Microsoft 365 政府-DoD 部署</span><span class="sxs-lookup"><span data-stu-id="96281-103">Plan for Microsoft 365 Government - DoD deployments</span></span>

<span data-ttu-id="96281-104">本指南适用于正在推动美国联邦政府实体或其他实体中的 Office 365 部署的 IT 专业人士，这些客户负责处理受政府法规和要求制约的数据，其中使用 Microsoft 365 政府– DoD 适用于满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="96281-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="96281-105">如果您的组织已满足 Microsoft 365 政府-DoD 资格要求，并且已被接受并已接受，则可以跳过步骤1和2，然后直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="96281-105">If your organization has already met the Microsoft 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="96281-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="96281-106">Step 1.</span></span> <span data-ttu-id="96281-107">确定你的组织是否需要 Microsoft 365 政府-DoD 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="96281-107">Determine whether your organization needs Microsoft 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="96281-108">Microsoft 365 政府-DoD 环境为云服务的美国政府要求提供合规性。</span><span class="sxs-lookup"><span data-stu-id="96281-108">The Microsoft 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="96281-109">除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府特有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="96281-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – DoD:</span></span>

- <span data-ttu-id="96281-110">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="96281-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="96281-111">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="96281-111">Your organization’s customer content is stored within the United States.</span></span>
- <span data-ttu-id="96281-112">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="96281-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="96281-113">Microsoft 365 政府-DoD 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="96281-113">Microsoft 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="96281-114">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府-DoD 产品的详细信息。</span><span class="sxs-lookup"><span data-stu-id="96281-114">You can find more information about the Microsoft 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="96281-115">[Office 365 美国政府服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)介绍了平台的优势，这些优势在美国的满足合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="96281-115">The [Office 365 US Government service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform’s benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="96281-116">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="96281-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="96281-117">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="96281-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="96281-119">决策点</span><span class="sxs-lookup"><span data-stu-id="96281-119">Decision points</span></span>|<ul><li><span data-ttu-id="96281-120">确定 Microsoft 365 政府-DoD 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="96281-120">Decide whether Microsoft 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="96281-121">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="96281-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="96281-122">Microsoft 365 政府-DoD 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="96281-122">Microsoft 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="96281-123">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="96281-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---dod"></a><span data-ttu-id="96281-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="96281-124">Step 2.</span></span> <span data-ttu-id="96281-125">适用于 Microsoft 365 政府-DoD</span><span class="sxs-lookup"><span data-stu-id="96281-125">Apply for Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="96281-126">如果确定此服务适合你的组织，请启动[应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="96281-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a><span data-ttu-id="96281-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="96281-127">Step 3.</span></span> <span data-ttu-id="96281-128">了解 Microsoft 365 政府-DoD 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="96281-128">Understand Microsoft 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="96281-129">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="96281-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="96281-131">决策点</span><span class="sxs-lookup"><span data-stu-id="96281-131">Decision point</span></span>|<ul><li><span data-ttu-id="96281-132">确定是否需要修改任何默认的 Microsoft 365 政府-DoD 安全设置，解析以首先了解你可能所做的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="96281-132">Decide whether you’ll need to modify any of the default Microsoft 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a><span data-ttu-id="96281-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="96281-133">Step 4.</span></span> <span data-ttu-id="96281-134">了解 Microsoft 365 政府-DoD 中当前提供哪些团队功能</span><span class="sxs-lookup"><span data-stu-id="96281-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="96281-135">为了满足政府云客户的要求，在企业计划中 Microsoft 365 政府-DoD 和团队中的团队之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="96281-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="96281-136">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="96281-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="96281-137">功能</span><span class="sxs-lookup"><span data-stu-id="96281-137">Feature</span></span>                     | <span data-ttu-id="96281-138">DoD</span><span class="sxs-lookup"><span data-stu-id="96281-138">DoD</span></span>       |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="96281-139">Base64</span><span class="sxs-lookup"><span data-stu-id="96281-139">Base</span></span> | <span data-ttu-id="96281-140">登录</span><span class="sxs-lookup"><span data-stu-id="96281-140">Login</span></span> | <span data-ttu-id="96281-141">有空</span><span class="sxs-lookup"><span data-stu-id="96281-141">Available</span></span> |
| | <span data-ttu-id="96281-142">状态</span><span class="sxs-lookup"><span data-stu-id="96281-142">Presence</span></span> | <span data-ttu-id="96281-143">有空</span><span class="sxs-lookup"><span data-stu-id="96281-143">Available</span></span> |
| | <span data-ttu-id="96281-144">统一状态（Skype for Business 和团队统一）</span><span class="sxs-lookup"><span data-stu-id="96281-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="96281-145">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-145">On the Government backlog</span></span> |
| <span data-ttu-id="96281-146">活动</span><span class="sxs-lookup"><span data-stu-id="96281-146">Activity</span></span> | <span data-ttu-id="96281-147">源</span><span class="sxs-lookup"><span data-stu-id="96281-147">Feed</span></span> | <span data-ttu-id="96281-148">有空</span><span class="sxs-lookup"><span data-stu-id="96281-148">Available</span></span> |
|  | <span data-ttu-id="96281-149">我的活动</span><span class="sxs-lookup"><span data-stu-id="96281-149">My Activity</span></span> | <span data-ttu-id="96281-150">有空</span><span class="sxs-lookup"><span data-stu-id="96281-150">Available</span></span> |
| <span data-ttu-id="96281-151">聊天</span><span class="sxs-lookup"><span data-stu-id="96281-151">Chat</span></span> | <span data-ttu-id="96281-152">交谈</span><span class="sxs-lookup"><span data-stu-id="96281-152">Conversation</span></span> | <span data-ttu-id="96281-153">有空</span><span class="sxs-lookup"><span data-stu-id="96281-153">Available</span></span> |
| | <span data-ttu-id="96281-154">文件</span><span class="sxs-lookup"><span data-stu-id="96281-154">Files</span></span> | <span data-ttu-id="96281-155">有空</span><span class="sxs-lookup"><span data-stu-id="96281-155">Available</span></span> |
| | <span data-ttu-id="96281-156">组织结构图</span><span class="sxs-lookup"><span data-stu-id="96281-156">Org chart</span></span> | <span data-ttu-id="96281-157">有空</span><span class="sxs-lookup"><span data-stu-id="96281-157">Available</span></span> |
| | <span data-ttu-id="96281-158">活动</span><span class="sxs-lookup"><span data-stu-id="96281-158">Activity</span></span> | <span data-ttu-id="96281-159">有空</span><span class="sxs-lookup"><span data-stu-id="96281-159">Available</span></span> |
| | <span data-ttu-id="96281-160">互操作（1:1 团队-Skype for Business 聊天）</span><span class="sxs-lookup"><span data-stu-id="96281-160">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="96281-161">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-161">On the Government backlog</span></span> |
| <span data-ttu-id="96281-162">Teams</span><span class="sxs-lookup"><span data-stu-id="96281-162">Teams</span></span> | <span data-ttu-id="96281-163">频道消息</span><span class="sxs-lookup"><span data-stu-id="96281-163">Channel message</span></span> | <span data-ttu-id="96281-164">有空</span><span class="sxs-lookup"><span data-stu-id="96281-164">Available</span></span> |
| | <span data-ttu-id="96281-165">信道文件</span><span class="sxs-lookup"><span data-stu-id="96281-165">Channel files</span></span> | <span data-ttu-id="96281-166">有空</span><span class="sxs-lookup"><span data-stu-id="96281-166">Available</span></span> |
| | <span data-ttu-id="96281-167">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="96281-167">OneNote tab</span></span> | <span data-ttu-id="96281-168">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-168">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-169">通过电子邮件发送频道</span><span class="sxs-lookup"><span data-stu-id="96281-169">Email a channel</span></span> | <span data-ttu-id="96281-170">不可用</span><span class="sxs-lookup"><span data-stu-id="96281-170">Not available</span></span> |
| | <span data-ttu-id="96281-171">添加成员</span><span class="sxs-lookup"><span data-stu-id="96281-171">Add member</span></span> | <span data-ttu-id="96281-172">有空</span><span class="sxs-lookup"><span data-stu-id="96281-172">Available</span></span> |
| | <span data-ttu-id="96281-173">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="96281-173">Guest access</span></span> | <span data-ttu-id="96281-174">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-174">On the Government backlog</span></span> |
| <span data-ttu-id="96281-175">会议</span><span class="sxs-lookup"><span data-stu-id="96281-175">Meetings</span></span> | <span data-ttu-id="96281-176">安排会议</span><span class="sxs-lookup"><span data-stu-id="96281-176">Schedule meeting</span></span> | <span data-ttu-id="96281-177">有空</span><span class="sxs-lookup"><span data-stu-id="96281-177">Available</span></span> |
| | <span data-ttu-id="96281-178">加入会议</span><span class="sxs-lookup"><span data-stu-id="96281-178">Join meeting</span></span> | <span data-ttu-id="96281-179">有空</span><span class="sxs-lookup"><span data-stu-id="96281-179">Available</span></span> |
| | <span data-ttu-id="96281-180">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="96281-180">VoIP meeting</span></span> | <span data-ttu-id="96281-181">有空</span><span class="sxs-lookup"><span data-stu-id="96281-181">Available</span></span> |
| | <span data-ttu-id="96281-182">桌面共享</span><span class="sxs-lookup"><span data-stu-id="96281-182">Desktop sharing</span></span> | <span data-ttu-id="96281-183">有空</span><span class="sxs-lookup"><span data-stu-id="96281-183">Available</span></span> |
| | <span data-ttu-id="96281-184">在共享中提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="96281-184">Give and take control in sharing</span></span> | <span data-ttu-id="96281-185">有空</span><span class="sxs-lookup"><span data-stu-id="96281-185">Available</span></span> |
| | <span data-ttu-id="96281-186">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="96281-186">Connect from a conference room</span></span> | <span data-ttu-id="96281-187">有空</span><span class="sxs-lookup"><span data-stu-id="96281-187">Available</span></span> |
| | <span data-ttu-id="96281-188">云录制</span><span class="sxs-lookup"><span data-stu-id="96281-188">Cloud recording</span></span> | <span data-ttu-id="96281-189">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-189">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-190">会议笔记</span><span class="sxs-lookup"><span data-stu-id="96281-190">Meeting notes</span></span> | <span data-ttu-id="96281-191">有空</span><span class="sxs-lookup"><span data-stu-id="96281-191">Available</span></span> |
| | <span data-ttu-id="96281-192">广播会议</span><span class="sxs-lookup"><span data-stu-id="96281-192">Broadcast meetings</span></span> | <span data-ttu-id="96281-193">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-193">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-194">云内部（DoD 到 DoD）联合会议</span><span class="sxs-lookup"><span data-stu-id="96281-194">Intra-cloud (DoD to DoD) Federated meetings</span></span> | <span data-ttu-id="96281-195">有空</span><span class="sxs-lookup"><span data-stu-id="96281-195">Available</span></span> |
| | <span data-ttu-id="96281-196">Surface Hub 支持</span><span class="sxs-lookup"><span data-stu-id="96281-196">Surface Hub support</span></span> | <span data-ttu-id="96281-197">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-197">On the Government backlog</span></span> |
| <span data-ttu-id="96281-198">呼叫</span><span class="sxs-lookup"><span data-stu-id="96281-198">Calls</span></span> | <span data-ttu-id="96281-199">联系人</span><span class="sxs-lookup"><span data-stu-id="96281-199">Contacts</span></span> | <span data-ttu-id="96281-200">有空</span><span class="sxs-lookup"><span data-stu-id="96281-200">Available</span></span> |
| | <span data-ttu-id="96281-201">信息</span><span class="sxs-lookup"><span data-stu-id="96281-201">History</span></span> | <span data-ttu-id="96281-202">有空</span><span class="sxs-lookup"><span data-stu-id="96281-202">Available</span></span> |
| | <span data-ttu-id="96281-203">语音邮件</span><span class="sxs-lookup"><span data-stu-id="96281-203">Voicemail</span></span> | <span data-ttu-id="96281-204">可用</span><span class="sxs-lookup"><span data-stu-id="96281-204">Available</span></span> |
| | <span data-ttu-id="96281-205">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="96281-205">VoIP call</span></span> | <span data-ttu-id="96281-206">有空</span><span class="sxs-lookup"><span data-stu-id="96281-206">Available</span></span> |
| | <span data-ttu-id="96281-207">Skype for Business-团队通话</span><span class="sxs-lookup"><span data-stu-id="96281-207">Skype for Business - Teams calling</span></span> | <span data-ttu-id="96281-208">可用</span><span class="sxs-lookup"><span data-stu-id="96281-208">Available</span></span> |
| | <span data-ttu-id="96281-209">通话套餐</span><span class="sxs-lookup"><span data-stu-id="96281-209">Calling Plans</span></span> | <span data-ttu-id="96281-210">不可用</span><span class="sxs-lookup"><span data-stu-id="96281-210">Not Available</span></span> |
| | <span data-ttu-id="96281-211">音频会议（通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="96281-211">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="96281-212">有空</span><span class="sxs-lookup"><span data-stu-id="96281-212">Available</span></span> |
| | <span data-ttu-id="96281-213">Microsoft Phone 系统直接路由</span><span class="sxs-lookup"><span data-stu-id="96281-213">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="96281-214">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-214">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-215">PSTN 呼叫者的大厅</span><span class="sxs-lookup"><span data-stu-id="96281-215">Lobby for PSTN callers</span></span> | <span data-ttu-id="96281-216">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-216">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-217">通话队列</span><span class="sxs-lookup"><span data-stu-id="96281-217">Call queue</span></span> | <span data-ttu-id="96281-218">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-218">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-219">老板和代理人支持</span><span class="sxs-lookup"><span data-stu-id="96281-219">Boss and delegate support</span></span> | <span data-ttu-id="96281-220">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-220">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-221">咨询和安全转移</span><span class="sxs-lookup"><span data-stu-id="96281-221">Consultative and safe transfer</span></span> | <span data-ttu-id="96281-222">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-222">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-223">请勿打扰突破</span><span class="sxs-lookup"><span data-stu-id="96281-223">Do not disturb breakthrough</span></span> | <span data-ttu-id="96281-224">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-224">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-225">独特震铃</span><span class="sxs-lookup"><span data-stu-id="96281-225">Distinctive ring</span></span> | <span data-ttu-id="96281-226">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-226">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-227">1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级</span><span class="sxs-lookup"><span data-stu-id="96281-227">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="96281-228">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-228">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-229">转发到组</span><span class="sxs-lookup"><span data-stu-id="96281-229">Forward to group</span></span> | <span data-ttu-id="96281-230">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-230">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-231">转接至 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="96281-231">Transfer to PSTN call</span></span> | <span data-ttu-id="96281-232">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-232">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-233">紧急呼叫呼叫计划</span><span class="sxs-lookup"><span data-stu-id="96281-233">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="96281-234">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-234">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-235">对现有认证的 SIP 电话的支持</span><span class="sxs-lookup"><span data-stu-id="96281-235">Support for existing certified SIP phones</span></span> | <span data-ttu-id="96281-236">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-236">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-237">USB HID</span><span class="sxs-lookup"><span data-stu-id="96281-237">USB HID</span></span> | <span data-ttu-id="96281-238">有空</span><span class="sxs-lookup"><span data-stu-id="96281-238">Available</span></span> |
| | <span data-ttu-id="96281-239">用于通话和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="96281-239">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="96281-240">有空</span><span class="sxs-lookup"><span data-stu-id="96281-240">Available</span></span> |
| | <span data-ttu-id="96281-241">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="96281-241">Organization auto attendant</span></span> | <span data-ttu-id="96281-242">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="96281-242">On the Government backlog</span></span> |
| | <span data-ttu-id="96281-243">Skype 消费者-团队通话支持</span><span class="sxs-lookup"><span data-stu-id="96281-243">Skype consumer - Teams call support</span></span> | <span data-ttu-id="96281-244">不可用</span><span class="sxs-lookup"><span data-stu-id="96281-244">Not available</span></span> |
| <span data-ttu-id="96281-245">文件</span><span class="sxs-lookup"><span data-stu-id="96281-245">Files</span></span> | <span data-ttu-id="96281-246">近来</span><span class="sxs-lookup"><span data-stu-id="96281-246">Recent</span></span> | <span data-ttu-id="96281-247">有空</span><span class="sxs-lookup"><span data-stu-id="96281-247">Available</span></span> |
| | <span data-ttu-id="96281-248">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96281-248">Microsoft Teams</span></span> | <span data-ttu-id="96281-249">有空</span><span class="sxs-lookup"><span data-stu-id="96281-249">Available</span></span> |
| <span data-ttu-id="96281-250">储存</span><span class="sxs-lookup"><span data-stu-id="96281-250">Store</span></span> | <span data-ttu-id="96281-251">应用商店</span><span class="sxs-lookup"><span data-stu-id="96281-251">App Store</span></span> | <span data-ttu-id="96281-252">不可用</span><span class="sxs-lookup"><span data-stu-id="96281-252">Not available</span></span> |
| <span data-ttu-id="96281-253">搜索</span><span class="sxs-lookup"><span data-stu-id="96281-253">Search</span></span> | <span data-ttu-id="96281-254">彩信</span><span class="sxs-lookup"><span data-stu-id="96281-254">Messages</span></span> | <span data-ttu-id="96281-255">有空</span><span class="sxs-lookup"><span data-stu-id="96281-255">Available</span></span> |
| | <span data-ttu-id="96281-256">人员</span><span class="sxs-lookup"><span data-stu-id="96281-256">People</span></span> | <span data-ttu-id="96281-257">有空</span><span class="sxs-lookup"><span data-stu-id="96281-257">Available</span></span> |
| | <span data-ttu-id="96281-258">文件</span><span class="sxs-lookup"><span data-stu-id="96281-258">Files</span></span> | <span data-ttu-id="96281-259">有空</span><span class="sxs-lookup"><span data-stu-id="96281-259">Available</span></span> |
| | <span data-ttu-id="96281-260">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="96281-260">Slash commands</span></span> | <span data-ttu-id="96281-261">有空</span><span class="sxs-lookup"><span data-stu-id="96281-261">Available</span></span> |
| <span data-ttu-id="96281-262">符合</span><span class="sxs-lookup"><span data-stu-id="96281-262">Compliance</span></span> | <span data-ttu-id="96281-263">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="96281-263">Compliance content search</span></span> | <span data-ttu-id="96281-264">有空</span><span class="sxs-lookup"><span data-stu-id="96281-264">Available</span></span> |
| | <span data-ttu-id="96281-265">保存</span><span class="sxs-lookup"><span data-stu-id="96281-265">Retention</span></span> | <span data-ttu-id="96281-266">有空</span><span class="sxs-lookup"><span data-stu-id="96281-266">Available</span></span> |
| | <span data-ttu-id="96281-267">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="96281-267">Audit log search</span></span> | <span data-ttu-id="96281-268">有空</span><span class="sxs-lookup"><span data-stu-id="96281-268">Available</span></span> |
| | <span data-ttu-id="96281-269">法律封存</span><span class="sxs-lookup"><span data-stu-id="96281-269">Legal hold</span></span> | <span data-ttu-id="96281-270">有空</span><span class="sxs-lookup"><span data-stu-id="96281-270">Available</span></span> |
| | <span data-ttu-id="96281-271">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="96281-271">eDiscovery</span></span> | <span data-ttu-id="96281-272">有空</span><span class="sxs-lookup"><span data-stu-id="96281-272">Available</span></span> |

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="96281-274">决策点</span><span class="sxs-lookup"><span data-stu-id="96281-274">Decision point</span></span>|<ul><li><span data-ttu-id="96281-275">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="96281-275">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="96281-276">第 5 步</span><span class="sxs-lookup"><span data-stu-id="96281-276">Step 5.</span></span> <span data-ttu-id="96281-277">规划管理</span><span class="sxs-lookup"><span data-stu-id="96281-277">Plan for governance</span></span>

<span data-ttu-id="96281-278">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="96281-278">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="96281-279">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="96281-279">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="96281-280">决策点</span><span class="sxs-lookup"><span data-stu-id="96281-280">Decision point</span></span> |<ul><li><span data-ttu-id="96281-281">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="96281-281">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="96281-282">第 6 步</span><span class="sxs-lookup"><span data-stu-id="96281-282">Step 6.</span></span> <span data-ttu-id="96281-283">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="96281-283">Deploy Teams for collaboration</span></span>

<span data-ttu-id="96281-284">在 onboarded 到 Microsoft 365 政府（DoD）后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="96281-284">After you’ve been onboarded to Microsoft 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="96281-285">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="96281-285">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="96281-286">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="96281-286">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
