---
title: Microsoft 365 政府版规划 - GCC 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 面向 IT 专业人员为中处理数据受美国政府法规的实体的驱动器 Office 365 部署指南
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcdad8bfbcb873a84d03ec6c0048e4fe49cd5467
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "29964415"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="88ccb-103">Microsoft 365 政府版-GCC 部署规划</span><span class="sxs-lookup"><span data-stu-id="88ccb-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="88ccb-104">本指南为 IT 专业人员带来了美国联邦、 状态、 本地、 经验，或地域政府实体或其他处理受及政府法规要求约束的数据的实体中的 Office 365 部署其中使用 Microsoft365 政府-GCC 适合满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="88ccb-105">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求和应用于并被接受到程序，您可以跳过步骤 1 和 2，直接转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="88ccb-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="88ccb-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-106">Step 1.</span></span> <span data-ttu-id="88ccb-107">确定您的组织是否需要 Microsoft 365 政府-GCC，并且符合资格要求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="88ccb-108">Microsoft 365 政府-GCC 环境提供符合美国的云服务，包括 FedRAMP 适度和刑事审判和联邦税费信息系统 （CJI 和 FTI 数据类型） 要求的政府要求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="88ccb-109">除了享受的特性和功能的 Office 365，组织受益于对 Microsoft 365 政府-GCC 是唯一的以下功能：</span><span class="sxs-lookup"><span data-stu-id="88ccb-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="88ccb-110">贵组织的客户内容逻辑分离从 microsoft 商业的 Office 365 服务中的客户内容中。</span><span class="sxs-lookup"><span data-stu-id="88ccb-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="88ccb-111">美国境内存储贵组织的客户内容。</span><span class="sxs-lookup"><span data-stu-id="88ccb-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="88ccb-112">贵组织的客户内容的访问仅限于屏蔽 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="88ccb-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="88ccb-113">Microsoft 365 政府-GCC 遵守认证和资格鉴定所需的美国公共部门客户。</span><span class="sxs-lookup"><span data-stu-id="88ccb-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="88ccb-114">您可以找到有关 Microsoft 365 政府-GCC 提供在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)，包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)美国政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88ccb-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="88ccb-115">[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍平台的优点，围绕会议美国境内的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="88ccb-116">您可能希望将服务说明中的信息的转移到 Excel 工作簿和添加两个列：**相关的我的组织是/否**和**满足 Y/N 我的组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="88ccb-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="88ccb-117">然后您可以查看此列表与同事以确认此服务满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="88ccb-118">决策点</span><span class="sxs-lookup"><span data-stu-id="88ccb-118">Decision points</span></span>|<ul><li><span data-ttu-id="88ccb-119">确定 Microsoft 365 政府-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="88ccb-119">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="88ccb-120">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-120">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="88ccb-121">Microsoft 365 政府-GCC 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="88ccb-121">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="88ccb-122">非 – 美国政府客户可以选择从[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)数。</span><span class="sxs-lookup"><span data-stu-id="88ccb-122">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="88ccb-123">第 2 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-123">Step 2.</span></span> <span data-ttu-id="88ccb-124">适用于 Microsoft 365 政府-GCC</span><span class="sxs-lookup"><span data-stu-id="88ccb-124">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="88ccb-125">无决定此服务适合您的组织，启动[此服务此处应用](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="88ccb-125">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="88ccb-126">第 3 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-126">Step 3.</span></span> <span data-ttu-id="88ccb-127">了解 Microsoft 365 政府-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="88ccb-127">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="88ccb-128">我们建议您执行时间仔细检查您的[管理和安全设置](enable-features-office-365.md)，然后再对其进行修改和对默认安全设置进行任何更改之前，请考虑影响合规性。</span><span class="sxs-lookup"><span data-stu-id="88ccb-128">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="88ccb-129">决策点</span><span class="sxs-lookup"><span data-stu-id="88ccb-129">Decision point</span></span>|<ul><li><span data-ttu-id="88ccb-130">决定是否将修改任何默认 Microsoft 365 政府-GCC 安全设置，解决首先了解任何更改的影响您可能会使。</span><span class="sxs-lookup"><span data-stu-id="88ccb-130">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="88ccb-131">第 4 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-131">Step 4.</span></span> <span data-ttu-id="88ccb-132">了解哪些功能目前不可用或默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="88ccb-132">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="88ccb-133">若要容纳政府云客户的要求，有一些区别 Microsoft 365 政府-GCC，企业计划。</span><span class="sxs-lookup"><span data-stu-id="88ccb-133">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="88ccb-134">请参阅下表可查看可用的功能。</span><span class="sxs-lookup"><span data-stu-id="88ccb-134">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="88ccb-135">功能</span><span class="sxs-lookup"><span data-stu-id="88ccb-135">Feature</span></span>                     | <span data-ttu-id="88ccb-136">GCC</span><span class="sxs-lookup"><span data-stu-id="88ccb-136">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="88ccb-137">基本</span><span class="sxs-lookup"><span data-stu-id="88ccb-137">Base</span></span> | <span data-ttu-id="88ccb-138">登录</span><span class="sxs-lookup"><span data-stu-id="88ccb-138">Login</span></span> | <span data-ttu-id="88ccb-139">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-139">Available</span></span> |
| | <span data-ttu-id="88ccb-140">状态</span><span class="sxs-lookup"><span data-stu-id="88ccb-140">Presence</span></span> | <span data-ttu-id="88ccb-141">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-141">Available</span></span> |
| | <span data-ttu-id="88ccb-142">统一的状态 (Skype 业务和团队统一)</span><span class="sxs-lookup"><span data-stu-id="88ccb-142">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="88ccb-143">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-143">Available</span></span> |
| <span data-ttu-id="88ccb-144">活动</span><span class="sxs-lookup"><span data-stu-id="88ccb-144">Activity</span></span> | <span data-ttu-id="88ccb-145">源</span><span class="sxs-lookup"><span data-stu-id="88ccb-145">Feed</span></span> | <span data-ttu-id="88ccb-146">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-146">Available</span></span> |
|  | <span data-ttu-id="88ccb-147">我的活动</span><span class="sxs-lookup"><span data-stu-id="88ccb-147">My Activity</span></span> | <span data-ttu-id="88ccb-148">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-148">Available</span></span> |
| <span data-ttu-id="88ccb-149">聊天</span><span class="sxs-lookup"><span data-stu-id="88ccb-149">Chat</span></span> | <span data-ttu-id="88ccb-150">对话</span><span class="sxs-lookup"><span data-stu-id="88ccb-150">Conversation</span></span> | <span data-ttu-id="88ccb-151">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-151">Available</span></span> |
| | <span data-ttu-id="88ccb-152">文件</span><span class="sxs-lookup"><span data-stu-id="88ccb-152">Files</span></span> | <span data-ttu-id="88ccb-153">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-153">Available</span></span> |
| | <span data-ttu-id="88ccb-154">组织结构图</span><span class="sxs-lookup"><span data-stu-id="88ccb-154">Org chart</span></span> | <span data-ttu-id="88ccb-155">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-155">Available</span></span> |
| | <span data-ttu-id="88ccb-156">活动</span><span class="sxs-lookup"><span data-stu-id="88ccb-156">Activity</span></span> | <span data-ttu-id="88ccb-157">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-157">Available</span></span> |
| | <span data-ttu-id="88ccb-158">互操作 (1:1 团队-Skype 对业务聊天)</span><span class="sxs-lookup"><span data-stu-id="88ccb-158">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="88ccb-159">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-159">Available</span></span> |
| <span data-ttu-id="88ccb-160">团队</span><span class="sxs-lookup"><span data-stu-id="88ccb-160">Teams</span></span> | <span data-ttu-id="88ccb-161">频道消息</span><span class="sxs-lookup"><span data-stu-id="88ccb-161">Channel message</span></span> | <span data-ttu-id="88ccb-162">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-162">Available</span></span> |
| | <span data-ttu-id="88ccb-163">通道文件</span><span class="sxs-lookup"><span data-stu-id="88ccb-163">Channel files</span></span> | <span data-ttu-id="88ccb-164">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-164">Available</span></span> |
| | <span data-ttu-id="88ccb-165">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="88ccb-165">OneNote tab</span></span> | <span data-ttu-id="88ccb-166">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="88ccb-166">On the Government backlog</span></span> |
| | <span data-ttu-id="88ccb-167">电子邮件通道</span><span class="sxs-lookup"><span data-stu-id="88ccb-167">Email a channel</span></span> | <span data-ttu-id="88ccb-168">不可用</span><span class="sxs-lookup"><span data-stu-id="88ccb-168">Not available</span></span> |
| | <span data-ttu-id="88ccb-169">添加成员</span><span class="sxs-lookup"><span data-stu-id="88ccb-169">Add member</span></span> | <span data-ttu-id="88ccb-170">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-170">Available</span></span> |
| | <span data-ttu-id="88ccb-171">来宾访问</span><span class="sxs-lookup"><span data-stu-id="88ccb-171">Guest access</span></span> | <span data-ttu-id="88ccb-172">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-172">Available</span></span> |
| <span data-ttu-id="88ccb-173">会议</span><span class="sxs-lookup"><span data-stu-id="88ccb-173">Meetings</span></span> | <span data-ttu-id="88ccb-174">安排会议</span><span class="sxs-lookup"><span data-stu-id="88ccb-174">Schedule meeting</span></span> | <span data-ttu-id="88ccb-175">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-175">Available</span></span> |
| | <span data-ttu-id="88ccb-176">加入会议</span><span class="sxs-lookup"><span data-stu-id="88ccb-176">Join meeting</span></span> | <span data-ttu-id="88ccb-177">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-177">Available</span></span> |
| | <span data-ttu-id="88ccb-178">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="88ccb-178">VoIP meeting</span></span> | <span data-ttu-id="88ccb-179">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-179">Available</span></span> |
| | <span data-ttu-id="88ccb-180">桌面共享</span><span class="sxs-lookup"><span data-stu-id="88ccb-180">Desktop sharing</span></span> | <span data-ttu-id="88ccb-181">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-181">Available</span></span> |
| | <span data-ttu-id="88ccb-182">在共享授予 and 获得控制权</span><span class="sxs-lookup"><span data-stu-id="88ccb-182">Give and take control in sharing</span></span> | <span data-ttu-id="88ccb-183">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-183">Available</span></span> |
| | <span data-ttu-id="88ccb-184">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="88ccb-184">Connect from a conference room</span></span> | <span data-ttu-id="88ccb-185">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-185">Available</span></span> |
| | <span data-ttu-id="88ccb-186">匿名加入</span><span class="sxs-lookup"><span data-stu-id="88ccb-186">Anonymous join</span></span> | <span data-ttu-id="88ccb-187">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-187">Available</span></span> |
| | <span data-ttu-id="88ccb-188">云录制</span><span class="sxs-lookup"><span data-stu-id="88ccb-188">Cloud recording</span></span> | <span data-ttu-id="88ccb-189">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="88ccb-189">On the Government backlog</span></span> |
| | <span data-ttu-id="88ccb-190">会议笔记</span><span class="sxs-lookup"><span data-stu-id="88ccb-190">Meeting notes</span></span> | <span data-ttu-id="88ccb-191">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-191">Available</span></span> |
| | <span data-ttu-id="88ccb-192">广播的会议</span><span class="sxs-lookup"><span data-stu-id="88ccb-192">Broadcast meetings</span></span> | <span data-ttu-id="88ccb-193">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="88ccb-193">On the Government backlog</span></span> |
| | <span data-ttu-id="88ccb-194">联盟的会议</span><span class="sxs-lookup"><span data-stu-id="88ccb-194">Federated meetings</span></span> | <span data-ttu-id="88ccb-195">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-195">Available</span></span> |
| | <span data-ttu-id="88ccb-196">曲面集线器支持 （预览）</span><span class="sxs-lookup"><span data-stu-id="88ccb-196">Surface Hub support (preview)</span></span> | <span data-ttu-id="88ccb-197">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-197">Available</span></span> |
| <span data-ttu-id="88ccb-198">呼叫</span><span class="sxs-lookup"><span data-stu-id="88ccb-198">Calls</span></span> | <span data-ttu-id="88ccb-199">联系人</span><span class="sxs-lookup"><span data-stu-id="88ccb-199">Contacts</span></span> | <span data-ttu-id="88ccb-200">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-200">Available</span></span> |
| | <span data-ttu-id="88ccb-201">历史记录</span><span class="sxs-lookup"><span data-stu-id="88ccb-201">History</span></span> | <span data-ttu-id="88ccb-202">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-202">Available</span></span> |
| | <span data-ttu-id="88ccb-203">语音邮件</span><span class="sxs-lookup"><span data-stu-id="88ccb-203">Voicemail</span></span> | <span data-ttu-id="88ccb-204">可用</span><span class="sxs-lookup"><span data-stu-id="88ccb-204">Available</span></span> |
| | <span data-ttu-id="88ccb-205">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="88ccb-205">VoIP call</span></span> | <span data-ttu-id="88ccb-206">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-206">Available</span></span> |
| | <span data-ttu-id="88ccb-207">Skype for Business 的团队呼叫</span><span class="sxs-lookup"><span data-stu-id="88ccb-207">Skype for Business - Teams calling</span></span> | <span data-ttu-id="88ccb-208">可用</span><span class="sxs-lookup"><span data-stu-id="88ccb-208">Available</span></span> |
| | <span data-ttu-id="88ccb-209">通话套餐</span><span class="sxs-lookup"><span data-stu-id="88ccb-209">Calling Plans</span></span> | <span data-ttu-id="88ccb-210">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-210">Available</span></span> |
| | <span data-ttu-id="88ccb-211">音频会议 （通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="88ccb-211">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="88ccb-212">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-212">Available</span></span> |
| | <span data-ttu-id="88ccb-213">Microsoft 直接路由的电话系统</span><span class="sxs-lookup"><span data-stu-id="88ccb-213">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="88ccb-214">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-214">Available</span></span> |
| | <span data-ttu-id="88ccb-215">PSTN 呼叫者会议厅</span><span class="sxs-lookup"><span data-stu-id="88ccb-215">Lobby for PSTN callers</span></span> | <span data-ttu-id="88ccb-216">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-216">Available</span></span> |
| | <span data-ttu-id="88ccb-217">呼叫队列</span><span class="sxs-lookup"><span data-stu-id="88ccb-217">Call queue</span></span> | <span data-ttu-id="88ccb-218">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-218">Available</span></span> |
| | <span data-ttu-id="88ccb-219">经理和代理人支持</span><span class="sxs-lookup"><span data-stu-id="88ccb-219">Boss and delegate support</span></span> | <span data-ttu-id="88ccb-220">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-220">Available</span></span> |
| | <span data-ttu-id="88ccb-221">咨询和安全传输</span><span class="sxs-lookup"><span data-stu-id="88ccb-221">Consultative and safe transfer</span></span> | <span data-ttu-id="88ccb-222">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-222">Available</span></span> |
| | <span data-ttu-id="88ccb-223">请勿打扰突破性</span><span class="sxs-lookup"><span data-stu-id="88ccb-223">Do not disturb breakthrough</span></span> | <span data-ttu-id="88ccb-224">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-224">Available</span></span> |
| | <span data-ttu-id="88ccb-225">特殊铃声</span><span class="sxs-lookup"><span data-stu-id="88ccb-225">Distinctive ring</span></span> | <span data-ttu-id="88ccb-226">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-226">Available</span></span> |
| | <span data-ttu-id="88ccb-227">1： 与团队业务的 Skype 组呼叫升级到 1 和 PSTN 参与者</span><span class="sxs-lookup"><span data-stu-id="88ccb-227">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="88ccb-228">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-228">Available</span></span> |
| | <span data-ttu-id="88ccb-229">转发到组</span><span class="sxs-lookup"><span data-stu-id="88ccb-229">Forward to group</span></span> | <span data-ttu-id="88ccb-230">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-230">Available</span></span> |
| | <span data-ttu-id="88ccb-231">转接到 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="88ccb-231">Transfer to PSTN call</span></span> | <span data-ttu-id="88ccb-232">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-232">Available</span></span> |
| | <span data-ttu-id="88ccb-233">紧急呼叫-调用计划</span><span class="sxs-lookup"><span data-stu-id="88ccb-233">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="88ccb-234">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-234">Available</span></span> |
| | <span data-ttu-id="88ccb-235">对现有认证的 SIP 电话支持</span><span class="sxs-lookup"><span data-stu-id="88ccb-235">Support for existing certified SIP phones</span></span> | <span data-ttu-id="88ccb-236">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-236">Available</span></span> |
| | <span data-ttu-id="88ccb-237">隐藏的 USB</span><span class="sxs-lookup"><span data-stu-id="88ccb-237">USB HID</span></span> | <span data-ttu-id="88ccb-238">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-238">Available</span></span> |
| | <span data-ttu-id="88ccb-239">对呼叫和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="88ccb-239">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="88ccb-240">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-240">Available</span></span> |
| | <span data-ttu-id="88ccb-241">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="88ccb-241">Organization auto attendant</span></span> | <span data-ttu-id="88ccb-242">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-242">Available</span></span> |
| | <span data-ttu-id="88ccb-243">Skype 消费者-团队呼叫支持</span><span class="sxs-lookup"><span data-stu-id="88ccb-243">Skype consumer - Teams call support</span></span> | <span data-ttu-id="88ccb-244">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-244">Available</span></span> |
| <span data-ttu-id="88ccb-245">文件</span><span class="sxs-lookup"><span data-stu-id="88ccb-245">Files</span></span> | <span data-ttu-id="88ccb-246">最新</span><span class="sxs-lookup"><span data-stu-id="88ccb-246">Recent</span></span> | <span data-ttu-id="88ccb-247">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-247">Available</span></span> |
| | <span data-ttu-id="88ccb-248">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88ccb-248">Microsoft Teams</span></span> | <span data-ttu-id="88ccb-249">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-249">Available</span></span> |
| <span data-ttu-id="88ccb-250">存储</span><span class="sxs-lookup"><span data-stu-id="88ccb-250">Store</span></span> | <span data-ttu-id="88ccb-251">应用程序商店</span><span class="sxs-lookup"><span data-stu-id="88ccb-251">App Store</span></span> | <span data-ttu-id="88ccb-252">政府待办事项上</span><span class="sxs-lookup"><span data-stu-id="88ccb-252">On the Government backlog</span></span> |
| <span data-ttu-id="88ccb-253">搜索</span><span class="sxs-lookup"><span data-stu-id="88ccb-253">Search</span></span> | <span data-ttu-id="88ccb-254">邮件</span><span class="sxs-lookup"><span data-stu-id="88ccb-254">Messages</span></span> | <span data-ttu-id="88ccb-255">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-255">Available</span></span> |
| | <span data-ttu-id="88ccb-256">人员</span><span class="sxs-lookup"><span data-stu-id="88ccb-256">People</span></span> | <span data-ttu-id="88ccb-257">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-257">Available</span></span> |
| | <span data-ttu-id="88ccb-258">文件</span><span class="sxs-lookup"><span data-stu-id="88ccb-258">Files</span></span> | <span data-ttu-id="88ccb-259">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-259">Available</span></span> |
| | <span data-ttu-id="88ccb-260">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="88ccb-260">Slash commands</span></span> | <span data-ttu-id="88ccb-261">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-261">Available</span></span> |
| <span data-ttu-id="88ccb-262">合规性</span><span class="sxs-lookup"><span data-stu-id="88ccb-262">Compliance</span></span> | <span data-ttu-id="88ccb-263">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="88ccb-263">Compliance content search</span></span> | <span data-ttu-id="88ccb-264">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-264">Available</span></span> |
| | <span data-ttu-id="88ccb-265">保留</span><span class="sxs-lookup"><span data-stu-id="88ccb-265">Retention</span></span> | <span data-ttu-id="88ccb-266">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-266">Available</span></span> |
| | <span data-ttu-id="88ccb-267">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="88ccb-267">Audit log search</span></span> | <span data-ttu-id="88ccb-268">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-268">Available</span></span> |
| | <span data-ttu-id="88ccb-269">合法保留</span><span class="sxs-lookup"><span data-stu-id="88ccb-269">Legal hold</span></span> | <span data-ttu-id="88ccb-270">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-270">Available</span></span> |
| | <span data-ttu-id="88ccb-271">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="88ccb-271">eDiscovery</span></span> | <span data-ttu-id="88ccb-272">有空</span><span class="sxs-lookup"><span data-stu-id="88ccb-272">Available</span></span> |

> [!Note]

> <span data-ttu-id="88ccb-273">一旦其他工作负荷 GCC 云中完全可用，然后他们将变为可用团队中完成所有其他集成工作。</span><span class="sxs-lookup"><span data-stu-id="88ccb-273">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="88ccb-274">决策点</span><span class="sxs-lookup"><span data-stu-id="88ccb-274">Decision point</span></span>|<ul><li><span data-ttu-id="88ccb-275">确定是否团队功能集能满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-275">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="88ccb-276">第 5 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-276">Step 5.</span></span> <span data-ttu-id="88ccb-277">规划调控</span><span class="sxs-lookup"><span data-stu-id="88ccb-277">Plan for governance</span></span>

<span data-ttu-id="88ccb-278">确定调控和如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="88ccb-278">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="88ccb-279">有关详细信息，请转到[团队中的治理规划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="88ccb-279">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="88ccb-280">决策点</span><span class="sxs-lookup"><span data-stu-id="88ccb-280">Decision point</span></span>|<ul><li><span data-ttu-id="88ccb-281">确定并记录您管理要求，[团队中的治理规划](plan-teams-governance.md)中的指南。</span><span class="sxs-lookup"><span data-stu-id="88ccb-281">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="88ccb-282">第 6 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-282">Step 6.</span></span> <span data-ttu-id="88ccb-283">部署团队协作</span><span class="sxs-lookup"><span data-stu-id="88ccb-283">Deploy Teams for collaboration</span></span>

<span data-ttu-id="88ccb-284">您已向 Microsoft 365 政府-GCC，onboarded 后，您可以按照使用[FastTrack](https://www.microsoft.com/fasttrack)和您选择的合作伙伴，为板载到服务的标准的部署方法。</span><span class="sxs-lookup"><span data-stu-id="88ccb-284">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://www.microsoft.com/fasttrack) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="88ccb-285">当您准备好时，到[启用通过团队和通道组织内的协作](teams-overview.md)部署团队。</span><span class="sxs-lookup"><span data-stu-id="88ccb-285">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="88ccb-286">请务必与您应用和变更管理团队或团队拥护者。</span><span class="sxs-lookup"><span data-stu-id="88ccb-286">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="88ccb-287">第 7 步</span><span class="sxs-lookup"><span data-stu-id="88ccb-287">Step 7.</span></span> <span data-ttu-id="88ccb-288">会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="88ccb-288">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="88ccb-289">这也是使用与您更多的利益干系人组团队启动规划推出会议和[云语音功能](cloud-voice-deployment.md)的绝佳时间。</span><span class="sxs-lookup"><span data-stu-id="88ccb-289">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

