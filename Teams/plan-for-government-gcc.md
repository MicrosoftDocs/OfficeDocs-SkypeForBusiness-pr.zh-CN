---
title: Microsoft 365 政府版规划 - GCC 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: IT 专业人士在处理由美国政府法规制约的数据的实体中驱动 Office 365 部署的指南
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 613110b1e57708ae0b26cfc0e105baa3856f8295
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588156"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="dfcc0-103">规划 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="dfcc0-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="dfcc0-104">本指南适用于面向美国联邦、州、本地、tribal 或 territorial 政府实体或其他实体中的 Office 365 部署的 IT 专业人员, 这些实体或其他实体处理受政府管理法规和要求制约的数据, 其中使用 Microsoft365政府-GCC 适用于满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="dfcc0-105">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求, 并已接受并接受该计划, 则可以跳过步骤1和步骤 2, 直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="dfcc0-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-106">Step 1.</span></span> <span data-ttu-id="dfcc0-107">确定你的组织是否需要 Microsoft 365 政府-GCC 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="dfcc0-108">Microsoft 365 政府版-GCC 环境为云服务 (包括 FedRAMP 中等) 和针对犯罪分子和联邦税务信息系统 (CJI 和 FTI 数据类型) 的要求遵守美国政府规定。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="dfcc0-109">除了享受 Office 365 的功能和功能之外, 组织还受益于 Microsoft 365 政府-GCC 所特有的以下功能:</span><span class="sxs-lookup"><span data-stu-id="dfcc0-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="dfcc0-110">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="dfcc0-111">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="dfcc0-112">对您的组织的客户内容的访问权限受到限制, 无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="dfcc0-113">Microsoft 365 政府版-GCC 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="dfcc0-114">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)(包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)) 中找到有关 Microsoft 365 政府版 (美国) 政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="dfcc0-115">[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍了平台的优势, 这些优势在美国的会议合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="dfcc0-116">你可能想要将服务说明中的信息表传输到 Excel 工作簿中, 并添加两列:**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="dfcc0-117">然后, 您可以与同事一起查看此列表, 以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="dfcc0-119">决策点</span><span class="sxs-lookup"><span data-stu-id="dfcc0-119">Decision points</span></span>|<ul><li><span data-ttu-id="dfcc0-120">确定 Microsoft 365 政府版-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-120">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="dfcc0-121">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="dfcc0-122">Microsoft 365 政府版-GCC 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-122">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="dfcc0-123">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="dfcc0-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-124">Step 2.</span></span> <span data-ttu-id="dfcc0-125">适用于 Microsoft 365 政府版-GCC</span><span class="sxs-lookup"><span data-stu-id="dfcc0-125">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="dfcc0-126">如果确定此服务适合你的组织, 请在[此处开始应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-126">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="dfcc0-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-127">Step 3.</span></span> <span data-ttu-id="dfcc0-128">了解 Microsoft 365 政府版-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-128">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="dfcc0-129">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md), 并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="dfcc0-131">决策点</span><span class="sxs-lookup"><span data-stu-id="dfcc0-131">Decision point</span></span>|<ul><li><span data-ttu-id="dfcc0-132">确定你是否要修改任何默认的 Microsoft 365 政府-GCC 安全设置, 首先要了解你可能做出的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-132">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="dfcc0-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-133">Step 4.</span></span> <span data-ttu-id="dfcc0-134">了解默认情况下当前不可用或已禁用的功能。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-134">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="dfcc0-135">为了满足政府云客户的要求, Microsoft 365 政府版和企业版计划之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-135">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="dfcc0-136">请参考下表, 查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="dfcc0-137">功能</span><span class="sxs-lookup"><span data-stu-id="dfcc0-137">Feature</span></span>                     | <span data-ttu-id="dfcc0-138">GCC</span><span class="sxs-lookup"><span data-stu-id="dfcc0-138">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="dfcc0-139">Base64</span><span class="sxs-lookup"><span data-stu-id="dfcc0-139">Base</span></span> | <span data-ttu-id="dfcc0-140">登录</span><span class="sxs-lookup"><span data-stu-id="dfcc0-140">Login</span></span> | <span data-ttu-id="dfcc0-141">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-141">Available</span></span> |
| | <span data-ttu-id="dfcc0-142">状态</span><span class="sxs-lookup"><span data-stu-id="dfcc0-142">Presence</span></span> | <span data-ttu-id="dfcc0-143">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-143">Available</span></span> |
| | <span data-ttu-id="dfcc0-144">统一状态 (Skype for Business 和团队统一)</span><span class="sxs-lookup"><span data-stu-id="dfcc0-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="dfcc0-145">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-145">Available</span></span> |
| <span data-ttu-id="dfcc0-146">活动</span><span class="sxs-lookup"><span data-stu-id="dfcc0-146">Activity</span></span> | <span data-ttu-id="dfcc0-147">源</span><span class="sxs-lookup"><span data-stu-id="dfcc0-147">Feed</span></span> | <span data-ttu-id="dfcc0-148">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-148">Available</span></span> |
|  | <span data-ttu-id="dfcc0-149">我的活动</span><span class="sxs-lookup"><span data-stu-id="dfcc0-149">My Activity</span></span> | <span data-ttu-id="dfcc0-150">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-150">Available</span></span> |
| <span data-ttu-id="dfcc0-151">聊天</span><span class="sxs-lookup"><span data-stu-id="dfcc0-151">Chat</span></span> | <span data-ttu-id="dfcc0-152">交谈</span><span class="sxs-lookup"><span data-stu-id="dfcc0-152">Conversation</span></span> | <span data-ttu-id="dfcc0-153">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-153">Available</span></span> |
| | <span data-ttu-id="dfcc0-154">文件</span><span class="sxs-lookup"><span data-stu-id="dfcc0-154">Files</span></span> | <span data-ttu-id="dfcc0-155">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-155">Available</span></span> |
| | <span data-ttu-id="dfcc0-156">组织结构图</span><span class="sxs-lookup"><span data-stu-id="dfcc0-156">Org chart</span></span> | <span data-ttu-id="dfcc0-157">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-157">Available</span></span> |
| | <span data-ttu-id="dfcc0-158">活动</span><span class="sxs-lookup"><span data-stu-id="dfcc0-158">Activity</span></span> | <span data-ttu-id="dfcc0-159">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-159">Available</span></span> |
| | <span data-ttu-id="dfcc0-160">互操作 (1:1 团队-Skype for Business 聊天)</span><span class="sxs-lookup"><span data-stu-id="dfcc0-160">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="dfcc0-161">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-161">Available</span></span> |
| <span data-ttu-id="dfcc0-162">团队</span><span class="sxs-lookup"><span data-stu-id="dfcc0-162">Teams</span></span> | <span data-ttu-id="dfcc0-163">频道消息</span><span class="sxs-lookup"><span data-stu-id="dfcc0-163">Channel message</span></span> | <span data-ttu-id="dfcc0-164">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-164">Available</span></span> |
| | <span data-ttu-id="dfcc0-165">信道文件</span><span class="sxs-lookup"><span data-stu-id="dfcc0-165">Channel files</span></span> | <span data-ttu-id="dfcc0-166">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-166">Available</span></span> |
| | <span data-ttu-id="dfcc0-167">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="dfcc0-167">OneNote tab</span></span> | <span data-ttu-id="dfcc0-168">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="dfcc0-168">On the Government backlog</span></span> |
| | <span data-ttu-id="dfcc0-169">通过电子邮件发送频道</span><span class="sxs-lookup"><span data-stu-id="dfcc0-169">Email a channel</span></span> | <span data-ttu-id="dfcc0-170">不可用</span><span class="sxs-lookup"><span data-stu-id="dfcc0-170">Not available</span></span> |
| | <span data-ttu-id="dfcc0-171">添加成员</span><span class="sxs-lookup"><span data-stu-id="dfcc0-171">Add member</span></span> | <span data-ttu-id="dfcc0-172">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-172">Available</span></span> |
| | <span data-ttu-id="dfcc0-173">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="dfcc0-173">Guest access</span></span> | <span data-ttu-id="dfcc0-174">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-174">Available</span></span> |
| <span data-ttu-id="dfcc0-175">会议</span><span class="sxs-lookup"><span data-stu-id="dfcc0-175">Meetings</span></span> | <span data-ttu-id="dfcc0-176">安排会议</span><span class="sxs-lookup"><span data-stu-id="dfcc0-176">Schedule meeting</span></span> | <span data-ttu-id="dfcc0-177">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-177">Available</span></span> |
| | <span data-ttu-id="dfcc0-178">加入会议</span><span class="sxs-lookup"><span data-stu-id="dfcc0-178">Join meeting</span></span> | <span data-ttu-id="dfcc0-179">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-179">Available</span></span> |
| | <span data-ttu-id="dfcc0-180">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="dfcc0-180">VoIP meeting</span></span> | <span data-ttu-id="dfcc0-181">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-181">Available</span></span> |
| | <span data-ttu-id="dfcc0-182">桌面共享</span><span class="sxs-lookup"><span data-stu-id="dfcc0-182">Desktop sharing</span></span> | <span data-ttu-id="dfcc0-183">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-183">Available</span></span> |
| | <span data-ttu-id="dfcc0-184">在共享中提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="dfcc0-184">Give and take control in sharing</span></span> | <span data-ttu-id="dfcc0-185">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-185">Available</span></span> |
| | <span data-ttu-id="dfcc0-186">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="dfcc0-186">Connect from a conference room</span></span> | <span data-ttu-id="dfcc0-187">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-187">Available</span></span> |
| | <span data-ttu-id="dfcc0-188">匿名联接</span><span class="sxs-lookup"><span data-stu-id="dfcc0-188">Anonymous join</span></span> | <span data-ttu-id="dfcc0-189">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-189">Available</span></span> |
| | <span data-ttu-id="dfcc0-190">云录制</span><span class="sxs-lookup"><span data-stu-id="dfcc0-190">Cloud recording</span></span> | <span data-ttu-id="dfcc0-191">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="dfcc0-191">On the Government backlog</span></span> |
| | <span data-ttu-id="dfcc0-192">会议笔记</span><span class="sxs-lookup"><span data-stu-id="dfcc0-192">Meeting notes</span></span> | <span data-ttu-id="dfcc0-193">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-193">Available</span></span> |
| | <span data-ttu-id="dfcc0-194">广播会议</span><span class="sxs-lookup"><span data-stu-id="dfcc0-194">Broadcast meetings</span></span> | <span data-ttu-id="dfcc0-195">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="dfcc0-195">On the Government backlog</span></span> |
| | <span data-ttu-id="dfcc0-196">联盟会议</span><span class="sxs-lookup"><span data-stu-id="dfcc0-196">Federated meetings</span></span> | <span data-ttu-id="dfcc0-197">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-197">Available</span></span> |
| | <span data-ttu-id="dfcc0-198">Surface Hub 支持</span><span class="sxs-lookup"><span data-stu-id="dfcc0-198">Surface Hub support</span></span> | <span data-ttu-id="dfcc0-199">不可用</span><span class="sxs-lookup"><span data-stu-id="dfcc0-199">Not available</span></span> |
| <span data-ttu-id="dfcc0-200">呼叫</span><span class="sxs-lookup"><span data-stu-id="dfcc0-200">Calls</span></span> | <span data-ttu-id="dfcc0-201">联系人</span><span class="sxs-lookup"><span data-stu-id="dfcc0-201">Contacts</span></span> | <span data-ttu-id="dfcc0-202">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-202">Available</span></span> |
| | <span data-ttu-id="dfcc0-203">信息</span><span class="sxs-lookup"><span data-stu-id="dfcc0-203">History</span></span> | <span data-ttu-id="dfcc0-204">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-204">Available</span></span> |
| | <span data-ttu-id="dfcc0-205">语音邮件</span><span class="sxs-lookup"><span data-stu-id="dfcc0-205">Voicemail</span></span> | <span data-ttu-id="dfcc0-206">可用</span><span class="sxs-lookup"><span data-stu-id="dfcc0-206">Available</span></span> |
| | <span data-ttu-id="dfcc0-207">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="dfcc0-207">VoIP call</span></span> | <span data-ttu-id="dfcc0-208">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-208">Available</span></span> |
| | <span data-ttu-id="dfcc0-209">Skype for Business-团队通话</span><span class="sxs-lookup"><span data-stu-id="dfcc0-209">Skype for Business - Teams calling</span></span> | <span data-ttu-id="dfcc0-210">可用</span><span class="sxs-lookup"><span data-stu-id="dfcc0-210">Available</span></span> |
| | <span data-ttu-id="dfcc0-211">通话套餐</span><span class="sxs-lookup"><span data-stu-id="dfcc0-211">Calling Plans</span></span> | <span data-ttu-id="dfcc0-212">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-212">Available</span></span> |
| | <span data-ttu-id="dfcc0-213">音频会议 (通过允许会议参与者通过 PSTN 加入)</span><span class="sxs-lookup"><span data-stu-id="dfcc0-213">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="dfcc0-214">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-214">Available</span></span> |
| | <span data-ttu-id="dfcc0-215">Microsoft Phone 系统直接路由</span><span class="sxs-lookup"><span data-stu-id="dfcc0-215">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="dfcc0-216">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-216">Available</span></span> |
| | <span data-ttu-id="dfcc0-217">PSTN 呼叫者的大厅</span><span class="sxs-lookup"><span data-stu-id="dfcc0-217">Lobby for PSTN callers</span></span> | <span data-ttu-id="dfcc0-218">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-218">Available</span></span> |
| | <span data-ttu-id="dfcc0-219">通话队列</span><span class="sxs-lookup"><span data-stu-id="dfcc0-219">Call queue</span></span> | <span data-ttu-id="dfcc0-220">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-220">Available</span></span> |
| | <span data-ttu-id="dfcc0-221">老板和代理人支持</span><span class="sxs-lookup"><span data-stu-id="dfcc0-221">Boss and delegate support</span></span> | <span data-ttu-id="dfcc0-222">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-222">Available</span></span> |
| | <span data-ttu-id="dfcc0-223">咨询和安全转移</span><span class="sxs-lookup"><span data-stu-id="dfcc0-223">Consultative and safe transfer</span></span> | <span data-ttu-id="dfcc0-224">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-224">Available</span></span> |
| | <span data-ttu-id="dfcc0-225">请勿打扰突破</span><span class="sxs-lookup"><span data-stu-id="dfcc0-225">Do not disturb breakthrough</span></span> | <span data-ttu-id="dfcc0-226">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-226">Available</span></span> |
| | <span data-ttu-id="dfcc0-227">独特震铃</span><span class="sxs-lookup"><span data-stu-id="dfcc0-227">Distinctive ring</span></span> | <span data-ttu-id="dfcc0-228">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-228">Available</span></span> |
| | <span data-ttu-id="dfcc0-229">1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级</span><span class="sxs-lookup"><span data-stu-id="dfcc0-229">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="dfcc0-230">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-230">Available</span></span> |
| | <span data-ttu-id="dfcc0-231">转发到组</span><span class="sxs-lookup"><span data-stu-id="dfcc0-231">Forward to group</span></span> | <span data-ttu-id="dfcc0-232">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-232">Available</span></span> |
| | <span data-ttu-id="dfcc0-233">转接至 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="dfcc0-233">Transfer to PSTN call</span></span> | <span data-ttu-id="dfcc0-234">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-234">Available</span></span> |
| | <span data-ttu-id="dfcc0-235">紧急呼叫呼叫计划</span><span class="sxs-lookup"><span data-stu-id="dfcc0-235">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="dfcc0-236">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-236">Available</span></span> |
| | <span data-ttu-id="dfcc0-237">对现有认证的 SIP 电话的支持</span><span class="sxs-lookup"><span data-stu-id="dfcc0-237">Support for existing certified SIP phones</span></span> | <span data-ttu-id="dfcc0-238">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-238">Available</span></span> |
| | <span data-ttu-id="dfcc0-239">USB HID</span><span class="sxs-lookup"><span data-stu-id="dfcc0-239">USB HID</span></span> | <span data-ttu-id="dfcc0-240">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-240">Available</span></span> |
| | <span data-ttu-id="dfcc0-241">用于通话和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="dfcc0-241">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="dfcc0-242">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-242">Available</span></span> |
| | <span data-ttu-id="dfcc0-243">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="dfcc0-243">Organization auto attendant</span></span> | <span data-ttu-id="dfcc0-244">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-244">Available</span></span> |
| | <span data-ttu-id="dfcc0-245">Skype 消费者-团队通话支持</span><span class="sxs-lookup"><span data-stu-id="dfcc0-245">Skype consumer - Teams call support</span></span> | <span data-ttu-id="dfcc0-246">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-246">Available</span></span> |
| <span data-ttu-id="dfcc0-247">文件</span><span class="sxs-lookup"><span data-stu-id="dfcc0-247">Files</span></span> | <span data-ttu-id="dfcc0-248">近来</span><span class="sxs-lookup"><span data-stu-id="dfcc0-248">Recent</span></span> | <span data-ttu-id="dfcc0-249">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-249">Available</span></span> |
| | <span data-ttu-id="dfcc0-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfcc0-250">Microsoft Teams</span></span> | <span data-ttu-id="dfcc0-251">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-251">Available</span></span> |
| <span data-ttu-id="dfcc0-252">储存</span><span class="sxs-lookup"><span data-stu-id="dfcc0-252">Store</span></span> | <span data-ttu-id="dfcc0-253">应用商店</span><span class="sxs-lookup"><span data-stu-id="dfcc0-253">App Store</span></span> | <span data-ttu-id="dfcc0-254">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="dfcc0-254">On the Government backlog</span></span> |
| <span data-ttu-id="dfcc0-255">搜索</span><span class="sxs-lookup"><span data-stu-id="dfcc0-255">Search</span></span> | <span data-ttu-id="dfcc0-256">彩信</span><span class="sxs-lookup"><span data-stu-id="dfcc0-256">Messages</span></span> | <span data-ttu-id="dfcc0-257">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-257">Available</span></span> |
| | <span data-ttu-id="dfcc0-258">人员</span><span class="sxs-lookup"><span data-stu-id="dfcc0-258">People</span></span> | <span data-ttu-id="dfcc0-259">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-259">Available</span></span> |
| | <span data-ttu-id="dfcc0-260">文件</span><span class="sxs-lookup"><span data-stu-id="dfcc0-260">Files</span></span> | <span data-ttu-id="dfcc0-261">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-261">Available</span></span> |
| | <span data-ttu-id="dfcc0-262">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="dfcc0-262">Slash commands</span></span> | <span data-ttu-id="dfcc0-263">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-263">Available</span></span> |
| <span data-ttu-id="dfcc0-264">符合</span><span class="sxs-lookup"><span data-stu-id="dfcc0-264">Compliance</span></span> | <span data-ttu-id="dfcc0-265">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="dfcc0-265">Compliance content search</span></span> | <span data-ttu-id="dfcc0-266">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-266">Available</span></span> |
| | <span data-ttu-id="dfcc0-267">保存</span><span class="sxs-lookup"><span data-stu-id="dfcc0-267">Retention</span></span> | <span data-ttu-id="dfcc0-268">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-268">Available</span></span> |
| | <span data-ttu-id="dfcc0-269">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="dfcc0-269">Audit log search</span></span> | <span data-ttu-id="dfcc0-270">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-270">Available</span></span> |
| | <span data-ttu-id="dfcc0-271">法律封存</span><span class="sxs-lookup"><span data-stu-id="dfcc0-271">Legal hold</span></span> | <span data-ttu-id="dfcc0-272">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-272">Available</span></span> |
| | <span data-ttu-id="dfcc0-273">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="dfcc0-273">eDiscovery</span></span> | <span data-ttu-id="dfcc0-274">有空</span><span class="sxs-lookup"><span data-stu-id="dfcc0-274">Available</span></span> |

> [!Note]

> <span data-ttu-id="dfcc0-275">当其他工作负荷在 GCC 云中完全可用时, 它们将在所有其他集成工作完成后的团队中变为可用。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-275">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="dfcc0-277">决策点</span><span class="sxs-lookup"><span data-stu-id="dfcc0-277">Decision point</span></span>|<ul><li><span data-ttu-id="dfcc0-278">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-278">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="dfcc0-279">第 5 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-279">Step 5.</span></span> <span data-ttu-id="dfcc0-280">规划管理</span><span class="sxs-lookup"><span data-stu-id="dfcc0-280">Plan for governance</span></span>

<span data-ttu-id="dfcc0-281">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-281">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="dfcc0-282">有关详细信息, 请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-282">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="dfcc0-284">决策点</span><span class="sxs-lookup"><span data-stu-id="dfcc0-284">Decision point</span></span>|<ul><li><span data-ttu-id="dfcc0-285">按照[规划团队中的管理](plan-teams-governance.md)指南, 确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="dfcc0-286">第 6 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-286">Step 6.</span></span> <span data-ttu-id="dfcc0-287">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="dfcc0-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="dfcc0-288">在 onboarded 到 Microsoft 365 政府-GCC 后, 您可以按照使用[FastTrack](https://www.microsoft.com/fasttrack)和所选合作伙伴的标准部署方法来实现服务的集成。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-288">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://www.microsoft.com/fasttrack) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="dfcc0-289">准备就绪后, 部署团队以[通过团队和频道在组织内启用协作](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-289">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="dfcc0-290">请确保与你的采纳和更改管理团队或团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-290">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="dfcc0-291">第 7 步</span><span class="sxs-lookup"><span data-stu-id="dfcc0-291">Step 7.</span></span> <span data-ttu-id="dfcc0-292">为会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="dfcc0-292">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="dfcc0-293">这也是将团队与更大的风险承担者组配合使用来开始计划推出会议和[云语音功能](cloud-voice-deployment.md)的一个好时机。</span><span class="sxs-lookup"><span data-stu-id="dfcc0-293">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

