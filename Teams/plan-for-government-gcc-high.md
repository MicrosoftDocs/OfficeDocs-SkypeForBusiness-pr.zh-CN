---
title: Microsoft 365 政府版规划 - GCC High 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 面向 IT 专业人士的指南，用于驱动在处理受美国政府法规制约的数据的实体中的 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3c44867b14a4b3bf83a45cf1dbbb37151c648a8
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161587"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="10352-103">规划 Microsoft 365 政府-GCC 高部署</span><span class="sxs-lookup"><span data-stu-id="10352-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="10352-104">本指南适用于正在推动美国联邦政府实体或其他实体中的 Office 365 部署的 IT 专业人士在美国联邦政府实体或其他实体中使用 Microsoft 365 政府（GCC 高）的使用以满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="10352-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="10352-105">如果您的组织已满足 Microsoft 365 政府– GCC 的高资格要求，并已接受并接受该计划，则可以跳过步骤1和2，然后直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="10352-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="10352-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="10352-106">Step 1.</span></span> <span data-ttu-id="10352-107">确定你的组织是否需要 Microsoft 365 政府-GCC 高并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="10352-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="10352-108">Microsoft 365 政府-GCC 高环境为云服务的美国政府要求提供合规性。</span><span class="sxs-lookup"><span data-stu-id="10352-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="10352-109">除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府所特有的以下功能-GCC 高：</span><span class="sxs-lookup"><span data-stu-id="10352-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="10352-110">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="10352-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="10352-111">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="10352-111">Your organization’s customer content is stored within the United States.</span></span>
- <span data-ttu-id="10352-112">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="10352-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="10352-113">Microsoft 365 政府-GCC 高遵从认证和 accreditations 美国公共事业部门客户所需的认证和。</span><span class="sxs-lookup"><span data-stu-id="10352-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="10352-114">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府版（适用于美国政府客户的 GCC）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="10352-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="10352-115">[Office 365 美国政府服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)介绍了平台的优势，这些优势在美国的满足合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="10352-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform’s benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="10352-116">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="10352-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="10352-117">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="10352-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="10352-119">决策点</span><span class="sxs-lookup"><span data-stu-id="10352-119">Decision points</span></span>|<ul><li><span data-ttu-id="10352-120">确定 Microsoft 365 政府-GCC 高版是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="10352-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="10352-121">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="10352-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="10352-122">Microsoft 365 政府版-GCC 高仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="10352-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="10352-123">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="10352-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="10352-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="10352-124">Step 2.</span></span> <span data-ttu-id="10352-125">适用于 Microsoft 365 政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="10352-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="10352-126">如果确定此服务适合你的组织，请启动[应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="10352-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="10352-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="10352-127">Step 3.</span></span> <span data-ttu-id="10352-128">了解 Microsoft 365 政府版-GCC 高默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="10352-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="10352-129">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="10352-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="10352-131">决策点</span><span class="sxs-lookup"><span data-stu-id="10352-131">Decision point</span></span>|<ul><li><span data-ttu-id="10352-132">确定你是否需要修改任何默认的 Microsoft 365 政府-GCC 高安全性设置，以便首先解决你可能所做的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="10352-132">Decide whether you’ll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="10352-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="10352-133">Step 4.</span></span> <span data-ttu-id="10352-134">了解 Microsoft 365 政府中当前提供哪些团队功能-GCC 高</span><span class="sxs-lookup"><span data-stu-id="10352-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="10352-135">为了满足政府云客户的要求，Microsoft 365 政府中的团队与企业计划中的 Microsoft 政府-GCC 高和团队之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="10352-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="10352-136">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="10352-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="10352-137">功能</span><span class="sxs-lookup"><span data-stu-id="10352-137">Feature</span></span>                     | <span data-ttu-id="10352-138">GCC 高</span><span class="sxs-lookup"><span data-stu-id="10352-138">GCC High</span></span>       |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="10352-139">Base64</span><span class="sxs-lookup"><span data-stu-id="10352-139">Base</span></span> | <span data-ttu-id="10352-140">登录</span><span class="sxs-lookup"><span data-stu-id="10352-140">Login</span></span> | <span data-ttu-id="10352-141">有空</span><span class="sxs-lookup"><span data-stu-id="10352-141">Available</span></span> |
| | <span data-ttu-id="10352-142">状态</span><span class="sxs-lookup"><span data-stu-id="10352-142">Presence</span></span> | <span data-ttu-id="10352-143">有空</span><span class="sxs-lookup"><span data-stu-id="10352-143">Available</span></span> |
| | <span data-ttu-id="10352-144">统一状态（Skype for Business 和团队统一）</span><span class="sxs-lookup"><span data-stu-id="10352-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="10352-145">有空</span><span class="sxs-lookup"><span data-stu-id="10352-145">Available</span></span> |
| | <span data-ttu-id="10352-146">Linux 客户端</span><span class="sxs-lookup"><span data-stu-id="10352-146">Linux client</span></span> | <span data-ttu-id="10352-147">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-147">On the Government backlog</span></span> |
| <span data-ttu-id="10352-148">活动</span><span class="sxs-lookup"><span data-stu-id="10352-148">Activity</span></span> | <span data-ttu-id="10352-149">源</span><span class="sxs-lookup"><span data-stu-id="10352-149">Feed</span></span> | <span data-ttu-id="10352-150">有空</span><span class="sxs-lookup"><span data-stu-id="10352-150">Available</span></span> |
|  | <span data-ttu-id="10352-151">我的活动</span><span class="sxs-lookup"><span data-stu-id="10352-151">My Activity</span></span> | <span data-ttu-id="10352-152">有空</span><span class="sxs-lookup"><span data-stu-id="10352-152">Available</span></span> |
| <span data-ttu-id="10352-153">聊天</span><span class="sxs-lookup"><span data-stu-id="10352-153">Chat</span></span> | <span data-ttu-id="10352-154">交谈</span><span class="sxs-lookup"><span data-stu-id="10352-154">Conversation</span></span> | <span data-ttu-id="10352-155">有空</span><span class="sxs-lookup"><span data-stu-id="10352-155">Available</span></span> |
| | <span data-ttu-id="10352-156">文件</span><span class="sxs-lookup"><span data-stu-id="10352-156">Files</span></span> | <span data-ttu-id="10352-157">有空</span><span class="sxs-lookup"><span data-stu-id="10352-157">Available</span></span> |
| | <span data-ttu-id="10352-158">组织结构图</span><span class="sxs-lookup"><span data-stu-id="10352-158">Org chart</span></span> | <span data-ttu-id="10352-159">有空</span><span class="sxs-lookup"><span data-stu-id="10352-159">Available</span></span> |
| | <span data-ttu-id="10352-160">活动</span><span class="sxs-lookup"><span data-stu-id="10352-160">Activity</span></span> | <span data-ttu-id="10352-161">有空</span><span class="sxs-lookup"><span data-stu-id="10352-161">Available</span></span> |
| | <span data-ttu-id="10352-162">互操作（1:1 团队-Skype for Business 聊天）</span><span class="sxs-lookup"><span data-stu-id="10352-162">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="10352-163">有空</span><span class="sxs-lookup"><span data-stu-id="10352-163">Available</span></span> |
| <span data-ttu-id="10352-164">Teams</span><span class="sxs-lookup"><span data-stu-id="10352-164">Teams</span></span> | <span data-ttu-id="10352-165">频道消息</span><span class="sxs-lookup"><span data-stu-id="10352-165">Channel message</span></span> | <span data-ttu-id="10352-166">有空</span><span class="sxs-lookup"><span data-stu-id="10352-166">Available</span></span> |
| | <span data-ttu-id="10352-167">信道文件</span><span class="sxs-lookup"><span data-stu-id="10352-167">Channel files</span></span> | <span data-ttu-id="10352-168">有空</span><span class="sxs-lookup"><span data-stu-id="10352-168">Available</span></span> |
| | <span data-ttu-id="10352-169">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="10352-169">OneNote tab</span></span> | <span data-ttu-id="10352-170">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-170">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-171">通过电子邮件发送频道</span><span class="sxs-lookup"><span data-stu-id="10352-171">Email a channel</span></span> | <span data-ttu-id="10352-172">不可用</span><span class="sxs-lookup"><span data-stu-id="10352-172">Not available</span></span> |
| | <span data-ttu-id="10352-173">添加成员</span><span class="sxs-lookup"><span data-stu-id="10352-173">Add member</span></span> | <span data-ttu-id="10352-174">有空</span><span class="sxs-lookup"><span data-stu-id="10352-174">Available</span></span> |
| | <span data-ttu-id="10352-175">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="10352-175">Guest access</span></span> | <span data-ttu-id="10352-176">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-176">On the Government backlog</span></span> |
| <span data-ttu-id="10352-177">会议</span><span class="sxs-lookup"><span data-stu-id="10352-177">Meetings</span></span> | <span data-ttu-id="10352-178">安排会议</span><span class="sxs-lookup"><span data-stu-id="10352-178">Schedule meeting</span></span> | <span data-ttu-id="10352-179">有空</span><span class="sxs-lookup"><span data-stu-id="10352-179">Available</span></span> |
| | <span data-ttu-id="10352-180">加入会议</span><span class="sxs-lookup"><span data-stu-id="10352-180">Join meeting</span></span> | <span data-ttu-id="10352-181">有空</span><span class="sxs-lookup"><span data-stu-id="10352-181">Available</span></span> |
| | <span data-ttu-id="10352-182">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="10352-182">VoIP meeting</span></span> | <span data-ttu-id="10352-183">有空</span><span class="sxs-lookup"><span data-stu-id="10352-183">Available</span></span> |
| | <span data-ttu-id="10352-184">桌面共享</span><span class="sxs-lookup"><span data-stu-id="10352-184">Desktop sharing</span></span> | <span data-ttu-id="10352-185">有空</span><span class="sxs-lookup"><span data-stu-id="10352-185">Available</span></span> |
| | <span data-ttu-id="10352-186">在共享中提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="10352-186">Give and take control in sharing</span></span> | <span data-ttu-id="10352-187">有空</span><span class="sxs-lookup"><span data-stu-id="10352-187">Available</span></span> |
| | <span data-ttu-id="10352-188">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="10352-188">Connect from a conference room</span></span> | <span data-ttu-id="10352-189">有空</span><span class="sxs-lookup"><span data-stu-id="10352-189">Available</span></span> |
| | <span data-ttu-id="10352-190">匿名联接</span><span class="sxs-lookup"><span data-stu-id="10352-190">Anonymous join</span></span> | <span data-ttu-id="10352-191">有空</span><span class="sxs-lookup"><span data-stu-id="10352-191">Available</span></span> |
| | <span data-ttu-id="10352-192">云录制</span><span class="sxs-lookup"><span data-stu-id="10352-192">Cloud recording</span></span> | <span data-ttu-id="10352-193">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-193">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-194">会议笔记</span><span class="sxs-lookup"><span data-stu-id="10352-194">Meeting notes</span></span> | <span data-ttu-id="10352-195">有空</span><span class="sxs-lookup"><span data-stu-id="10352-195">Available</span></span> |
| | <span data-ttu-id="10352-196">广播会议</span><span class="sxs-lookup"><span data-stu-id="10352-196">Broadcast meetings</span></span> | <span data-ttu-id="10352-197">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-197">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-198">云内部（GCCH 到 GCCH）联合会议</span><span class="sxs-lookup"><span data-stu-id="10352-198">Intra-cloud (GCCH to GCCH) Federated meetings</span></span> | <span data-ttu-id="10352-199">有空</span><span class="sxs-lookup"><span data-stu-id="10352-199">Available</span></span> |
| | <span data-ttu-id="10352-200">Surface Hub 支持</span><span class="sxs-lookup"><span data-stu-id="10352-200">Surface Hub support</span></span> | <span data-ttu-id="10352-201">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-201">On the Government backlog</span></span> |
| <span data-ttu-id="10352-202">呼叫</span><span class="sxs-lookup"><span data-stu-id="10352-202">Calls</span></span> | <span data-ttu-id="10352-203">联系人</span><span class="sxs-lookup"><span data-stu-id="10352-203">Contacts</span></span> | <span data-ttu-id="10352-204">有空</span><span class="sxs-lookup"><span data-stu-id="10352-204">Available</span></span> |
| | <span data-ttu-id="10352-205">信息</span><span class="sxs-lookup"><span data-stu-id="10352-205">History</span></span> | <span data-ttu-id="10352-206">有空</span><span class="sxs-lookup"><span data-stu-id="10352-206">Available</span></span> |
| | <span data-ttu-id="10352-207">语音邮件</span><span class="sxs-lookup"><span data-stu-id="10352-207">Voicemail</span></span> | <span data-ttu-id="10352-208">可用</span><span class="sxs-lookup"><span data-stu-id="10352-208">Available</span></span> |
| | <span data-ttu-id="10352-209">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="10352-209">VoIP call</span></span> | <span data-ttu-id="10352-210">有空</span><span class="sxs-lookup"><span data-stu-id="10352-210">Available</span></span> |
| | <span data-ttu-id="10352-211">Skype for Business-团队通话</span><span class="sxs-lookup"><span data-stu-id="10352-211">Skype for Business - Teams calling</span></span> | <span data-ttu-id="10352-212">可用</span><span class="sxs-lookup"><span data-stu-id="10352-212">Available</span></span> |
| | <span data-ttu-id="10352-213">通话套餐</span><span class="sxs-lookup"><span data-stu-id="10352-213">Calling Plans</span></span> | <span data-ttu-id="10352-214">不可用</span><span class="sxs-lookup"><span data-stu-id="10352-214">Not Available</span></span> |
| | <span data-ttu-id="10352-215">音频会议（通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="10352-215">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="10352-216">有空</span><span class="sxs-lookup"><span data-stu-id="10352-216">Available</span></span> |
| | <span data-ttu-id="10352-217">Microsoft Phone 系统直接路由</span><span class="sxs-lookup"><span data-stu-id="10352-217">Microsoft Phone System Direct Routing</span></span> | <span data-ttu-id="10352-218">有空</span><span class="sxs-lookup"><span data-stu-id="10352-218">Available</span></span> |
| | <span data-ttu-id="10352-219">PSTN 呼叫者的大厅</span><span class="sxs-lookup"><span data-stu-id="10352-219">Lobby for PSTN callers</span></span> | <span data-ttu-id="10352-220">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-220">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-221">通话队列</span><span class="sxs-lookup"><span data-stu-id="10352-221">Call queue</span></span> | <span data-ttu-id="10352-222">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-222">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-223">老板和代理人支持</span><span class="sxs-lookup"><span data-stu-id="10352-223">Boss and delegate support</span></span> | <span data-ttu-id="10352-224">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-224">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-225">咨询和安全转移</span><span class="sxs-lookup"><span data-stu-id="10352-225">Consultative and safe transfer</span></span> | <span data-ttu-id="10352-226">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-226">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-227">请勿打扰突破</span><span class="sxs-lookup"><span data-stu-id="10352-227">Do not disturb breakthrough</span></span> | <span data-ttu-id="10352-228">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-228">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-229">独特震铃</span><span class="sxs-lookup"><span data-stu-id="10352-229">Distinctive ring</span></span> | <span data-ttu-id="10352-230">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-230">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-231">1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级</span><span class="sxs-lookup"><span data-stu-id="10352-231">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="10352-232">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-232">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-233">转发到组</span><span class="sxs-lookup"><span data-stu-id="10352-233">Forward to group</span></span> | <span data-ttu-id="10352-234">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-234">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-235">转接至 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="10352-235">Transfer to PSTN call</span></span> | <span data-ttu-id="10352-236">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-236">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-237">紧急呼叫呼叫计划</span><span class="sxs-lookup"><span data-stu-id="10352-237">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="10352-238">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-238">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-239">对现有认证的 SIP 电话的支持</span><span class="sxs-lookup"><span data-stu-id="10352-239">Support for existing certified SIP phones</span></span> | <span data-ttu-id="10352-240">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-240">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-241">USB HID</span><span class="sxs-lookup"><span data-stu-id="10352-241">USB HID</span></span> | <span data-ttu-id="10352-242">有空</span><span class="sxs-lookup"><span data-stu-id="10352-242">Available</span></span> |
| | <span data-ttu-id="10352-243">用于通话和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="10352-243">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="10352-244">有空</span><span class="sxs-lookup"><span data-stu-id="10352-244">Available</span></span> |
| | <span data-ttu-id="10352-245">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="10352-245">Organization auto attendant</span></span> | <span data-ttu-id="10352-246">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="10352-246">On the Government backlog</span></span> |
| | <span data-ttu-id="10352-247">Skype 消费者-团队通话支持</span><span class="sxs-lookup"><span data-stu-id="10352-247">Skype consumer - Teams call support</span></span> | <span data-ttu-id="10352-248">不可用</span><span class="sxs-lookup"><span data-stu-id="10352-248">Not available</span></span> |
| <span data-ttu-id="10352-249">文件</span><span class="sxs-lookup"><span data-stu-id="10352-249">Files</span></span> | <span data-ttu-id="10352-250">近来</span><span class="sxs-lookup"><span data-stu-id="10352-250">Recent</span></span> | <span data-ttu-id="10352-251">有空</span><span class="sxs-lookup"><span data-stu-id="10352-251">Available</span></span> |
| | <span data-ttu-id="10352-252">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10352-252">Microsoft Teams</span></span> | <span data-ttu-id="10352-253">有空</span><span class="sxs-lookup"><span data-stu-id="10352-253">Available</span></span> |
| <span data-ttu-id="10352-254">储存</span><span class="sxs-lookup"><span data-stu-id="10352-254">Store</span></span> | <span data-ttu-id="10352-255">应用商店</span><span class="sxs-lookup"><span data-stu-id="10352-255">App Store</span></span> | <span data-ttu-id="10352-256">不可用</span><span class="sxs-lookup"><span data-stu-id="10352-256">Not available</span></span> |
| <span data-ttu-id="10352-257">搜索</span><span class="sxs-lookup"><span data-stu-id="10352-257">Search</span></span> | <span data-ttu-id="10352-258">彩信</span><span class="sxs-lookup"><span data-stu-id="10352-258">Messages</span></span> | <span data-ttu-id="10352-259">有空</span><span class="sxs-lookup"><span data-stu-id="10352-259">Available</span></span> |
| | <span data-ttu-id="10352-260">人员</span><span class="sxs-lookup"><span data-stu-id="10352-260">People</span></span> | <span data-ttu-id="10352-261">有空</span><span class="sxs-lookup"><span data-stu-id="10352-261">Available</span></span> |
| | <span data-ttu-id="10352-262">文件</span><span class="sxs-lookup"><span data-stu-id="10352-262">Files</span></span> | <span data-ttu-id="10352-263">有空</span><span class="sxs-lookup"><span data-stu-id="10352-263">Available</span></span> |
| | <span data-ttu-id="10352-264">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="10352-264">Slash commands</span></span> | <span data-ttu-id="10352-265">有空</span><span class="sxs-lookup"><span data-stu-id="10352-265">Available</span></span> |
| <span data-ttu-id="10352-266">符合</span><span class="sxs-lookup"><span data-stu-id="10352-266">Compliance</span></span> | <span data-ttu-id="10352-267">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="10352-267">Compliance content search</span></span> | <span data-ttu-id="10352-268">有空</span><span class="sxs-lookup"><span data-stu-id="10352-268">Available</span></span> |
| | <span data-ttu-id="10352-269">保存</span><span class="sxs-lookup"><span data-stu-id="10352-269">Retention</span></span> | <span data-ttu-id="10352-270">有空</span><span class="sxs-lookup"><span data-stu-id="10352-270">Available</span></span> |
| | <span data-ttu-id="10352-271">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="10352-271">Audit log search</span></span> | <span data-ttu-id="10352-272">有空</span><span class="sxs-lookup"><span data-stu-id="10352-272">Available</span></span> |
| | <span data-ttu-id="10352-273">法律封存</span><span class="sxs-lookup"><span data-stu-id="10352-273">Legal hold</span></span> | <span data-ttu-id="10352-274">有空</span><span class="sxs-lookup"><span data-stu-id="10352-274">Available</span></span> |
| | <span data-ttu-id="10352-275">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="10352-275">eDiscovery</span></span> | <span data-ttu-id="10352-276">有空</span><span class="sxs-lookup"><span data-stu-id="10352-276">Available</span></span> |

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="10352-278">决策点</span><span class="sxs-lookup"><span data-stu-id="10352-278">Decision point</span></span>|<ul><li><span data-ttu-id="10352-279">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="10352-279">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="10352-280">第 5 步</span><span class="sxs-lookup"><span data-stu-id="10352-280">Step 5.</span></span> <span data-ttu-id="10352-281">规划管理</span><span class="sxs-lookup"><span data-stu-id="10352-281">Plan for governance</span></span>

<span data-ttu-id="10352-282">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="10352-282">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="10352-283">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="10352-283">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="10352-284">决策点</span><span class="sxs-lookup"><span data-stu-id="10352-284">Decision point</span></span> |<ul><li><span data-ttu-id="10352-285">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="10352-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="10352-286">第 6 步</span><span class="sxs-lookup"><span data-stu-id="10352-286">Step 6.</span></span> <span data-ttu-id="10352-287">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="10352-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="10352-288">在 onboarded 到 Microsoft 365 政府（GCC 高版）后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="10352-288">After you’ve been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="10352-289">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="10352-289">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="10352-290">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="10352-290">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

