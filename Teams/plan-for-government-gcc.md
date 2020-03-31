---
title: Microsoft 365 政府版规划 - GCC 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT 专业人士在处理由美国政府法规制约的数据的实体中驱动 Office 365 部署的指南
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb36e9decf7fba80250dce1035187b94198bc86d
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053605"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="06987-103">规划 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="06987-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="06987-104">本指南适用于面向美国联邦、州、本地、tribal 或 territorial 政府实体或其他实体中的 Office 365 部署的 IT 专业人员，这些实体或其他实体处理受政府管理法规和要求制约的数据，其中使用 Microsoft365政府-GCC 适用于满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="06987-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="06987-105">2020年3月26日，：不要错过我们可下载[的适用于 GCC 的快速入门指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="06987-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06987-106">由于 coronavirus （COVID-19） pandemic，Microsoft 团队在在线通话和音频/视频会议方面遇到了极大的高峰。</span><span class="sxs-lookup"><span data-stu-id="06987-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="06987-107">为响应更空前的通话增加，并确保连续性和可用性，Microsoft 允许 Microsoft 团队拥有的音频/视频服务器利用我们的商业数据中心中的处理能力和我们的政府数据中心。</span><span class="sxs-lookup"><span data-stu-id="06987-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="06987-108">这些音频/视频服务器驻留在 Microsoft Azure FedRAMP 中的 Microsoft Azure 高资格鉴定边界服务器，并且不存储任何客户内容。</span><span class="sxs-lookup"><span data-stu-id="06987-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="06987-109">但是，这些服务器正在处理通话和会议的音频和视频，并在此期间内由我们的商业员工进行操作。</span><span class="sxs-lookup"><span data-stu-id="06987-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="06987-110">经确认，被筛选的人员正在监视这些服务器，以便通过查看这些服务器的交互式登录项来对客户数据进行潜在访问。</span><span class="sxs-lookup"><span data-stu-id="06987-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="06987-111">合格的人员在访问客户内容方面满足了 GCC 的要求。</span><span class="sxs-lookup"><span data-stu-id="06987-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="06987-112">有关筛选要求的详细信息，请参阅[GCC 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="06987-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="06987-113">感谢您的支持，因为我们采取措施来确保我们的服务在这些特别时间内保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="06987-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="06987-114">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求，并已接受并接受该计划，则可以跳过步骤1和步骤2，直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="06987-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="06987-115">第 1 步</span><span class="sxs-lookup"><span data-stu-id="06987-115">Step 1.</span></span> <span data-ttu-id="06987-116">确定你的组织是否需要 Microsoft 365 政府-GCC 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="06987-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="06987-117">Microsoft 365 政府版-GCC 环境为云服务（包括 FedRAMP 中等）和针对犯罪分子和联邦税务信息系统（CJI 和 FTI 数据类型）的要求遵守美国政府规定。</span><span class="sxs-lookup"><span data-stu-id="06987-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="06987-118">除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府-GCC 所特有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="06987-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="06987-119">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="06987-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="06987-120">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="06987-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="06987-121">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="06987-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="06987-122">Microsoft 365 政府版-GCC 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="06987-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="06987-123">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府版（美国）政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="06987-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="06987-124">[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍了平台的优势，这些优势在美国的会议合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="06987-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="06987-125">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="06987-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="06987-126">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="06987-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="06987-128">决策点</span><span class="sxs-lookup"><span data-stu-id="06987-128">Decision points</span></span>|<ul><li><span data-ttu-id="06987-129">确定 Microsoft 365 政府版-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="06987-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="06987-130">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="06987-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="06987-131">Microsoft 365 政府版-GCC 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="06987-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="06987-132">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="06987-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="06987-133">第 2 步</span><span class="sxs-lookup"><span data-stu-id="06987-133">Step 2.</span></span> <span data-ttu-id="06987-134">适用于 Microsoft 365 政府版-GCC</span><span class="sxs-lookup"><span data-stu-id="06987-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="06987-135">如果确定此服务适合你的组织，请在[此处开始应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="06987-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="06987-136">第 3 步</span><span class="sxs-lookup"><span data-stu-id="06987-136">Step 3.</span></span> <span data-ttu-id="06987-137">了解 Microsoft 365 政府版-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="06987-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="06987-138">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="06987-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="06987-140">决策点</span><span class="sxs-lookup"><span data-stu-id="06987-140">Decision point</span></span>|<ul><li><span data-ttu-id="06987-141">确定你是否要修改任何默认的 Microsoft 365 政府-GCC 安全设置，首先要了解你可能做出的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="06987-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="06987-142">第 4 步</span><span class="sxs-lookup"><span data-stu-id="06987-142">Step 4.</span></span> <span data-ttu-id="06987-143">了解默认情况下当前不可用或已禁用的功能。</span><span class="sxs-lookup"><span data-stu-id="06987-143">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="06987-144">为了满足政府云客户的要求，Microsoft 365 政府版和企业版计划之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="06987-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="06987-145">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="06987-145">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="06987-146">功能</span><span class="sxs-lookup"><span data-stu-id="06987-146">Feature</span></span>                     | <span data-ttu-id="06987-147">GCC</span><span class="sxs-lookup"><span data-stu-id="06987-147">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="06987-148">Base64</span><span class="sxs-lookup"><span data-stu-id="06987-148">Base</span></span> | <span data-ttu-id="06987-149">登录</span><span class="sxs-lookup"><span data-stu-id="06987-149">Login</span></span> | <span data-ttu-id="06987-150">在线</span><span class="sxs-lookup"><span data-stu-id="06987-150">Available</span></span> |
| | <span data-ttu-id="06987-151">状态</span><span class="sxs-lookup"><span data-stu-id="06987-151">Presence</span></span> | <span data-ttu-id="06987-152">在线</span><span class="sxs-lookup"><span data-stu-id="06987-152">Available</span></span> |
| | <span data-ttu-id="06987-153">统一状态（Skype for Business 和团队统一）</span><span class="sxs-lookup"><span data-stu-id="06987-153">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="06987-154">在线</span><span class="sxs-lookup"><span data-stu-id="06987-154">Available</span></span> |
| <span data-ttu-id="06987-155">活动</span><span class="sxs-lookup"><span data-stu-id="06987-155">Activity</span></span> | <span data-ttu-id="06987-156">源</span><span class="sxs-lookup"><span data-stu-id="06987-156">Feed</span></span> | <span data-ttu-id="06987-157">在线</span><span class="sxs-lookup"><span data-stu-id="06987-157">Available</span></span> |
|  | <span data-ttu-id="06987-158">我的活动</span><span class="sxs-lookup"><span data-stu-id="06987-158">My Activity</span></span> | <span data-ttu-id="06987-159">在线</span><span class="sxs-lookup"><span data-stu-id="06987-159">Available</span></span> |
| <span data-ttu-id="06987-160">聊天</span><span class="sxs-lookup"><span data-stu-id="06987-160">Chat</span></span> | <span data-ttu-id="06987-161">交谈</span><span class="sxs-lookup"><span data-stu-id="06987-161">Conversation</span></span> | <span data-ttu-id="06987-162">在线</span><span class="sxs-lookup"><span data-stu-id="06987-162">Available</span></span> |
| | <span data-ttu-id="06987-163">文件</span><span class="sxs-lookup"><span data-stu-id="06987-163">Files</span></span> | <span data-ttu-id="06987-164">在线</span><span class="sxs-lookup"><span data-stu-id="06987-164">Available</span></span> |
| | <span data-ttu-id="06987-165">组织结构图</span><span class="sxs-lookup"><span data-stu-id="06987-165">Org chart</span></span> | <span data-ttu-id="06987-166">在线</span><span class="sxs-lookup"><span data-stu-id="06987-166">Available</span></span> |
| | <span data-ttu-id="06987-167">活动</span><span class="sxs-lookup"><span data-stu-id="06987-167">Activity</span></span> | <span data-ttu-id="06987-168">在线</span><span class="sxs-lookup"><span data-stu-id="06987-168">Available</span></span> |
| | <span data-ttu-id="06987-169">互操作（1:1 团队-Skype for Business 聊天）</span><span class="sxs-lookup"><span data-stu-id="06987-169">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="06987-170">在线</span><span class="sxs-lookup"><span data-stu-id="06987-170">Available</span></span> |
| <span data-ttu-id="06987-171">Teams</span><span class="sxs-lookup"><span data-stu-id="06987-171">Teams</span></span> | <span data-ttu-id="06987-172">频道消息</span><span class="sxs-lookup"><span data-stu-id="06987-172">Channel message</span></span> | <span data-ttu-id="06987-173">在线</span><span class="sxs-lookup"><span data-stu-id="06987-173">Available</span></span> |
| | <span data-ttu-id="06987-174">信道文件</span><span class="sxs-lookup"><span data-stu-id="06987-174">Channel files</span></span> | <span data-ttu-id="06987-175">在线</span><span class="sxs-lookup"><span data-stu-id="06987-175">Available</span></span> |
| | <span data-ttu-id="06987-176">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="06987-176">OneNote tab</span></span> | <span data-ttu-id="06987-177">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="06987-177">On the Government backlog</span></span> |
| | <span data-ttu-id="06987-178">通过电子邮件发送频道</span><span class="sxs-lookup"><span data-stu-id="06987-178">Email a channel</span></span> | <span data-ttu-id="06987-179">不可用</span><span class="sxs-lookup"><span data-stu-id="06987-179">Not available</span></span> |
| | <span data-ttu-id="06987-180">添加成员</span><span class="sxs-lookup"><span data-stu-id="06987-180">Add member</span></span> | <span data-ttu-id="06987-181">在线</span><span class="sxs-lookup"><span data-stu-id="06987-181">Available</span></span> |
| | <span data-ttu-id="06987-182">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="06987-182">Guest access</span></span> | <span data-ttu-id="06987-183">在线</span><span class="sxs-lookup"><span data-stu-id="06987-183">Available</span></span> |
| <span data-ttu-id="06987-184">会议</span><span class="sxs-lookup"><span data-stu-id="06987-184">Meetings</span></span> | <span data-ttu-id="06987-185">安排会议</span><span class="sxs-lookup"><span data-stu-id="06987-185">Schedule meeting</span></span> | <span data-ttu-id="06987-186">在线</span><span class="sxs-lookup"><span data-stu-id="06987-186">Available</span></span> |
| | <span data-ttu-id="06987-187">加入会议</span><span class="sxs-lookup"><span data-stu-id="06987-187">Join meeting</span></span> | <span data-ttu-id="06987-188">在线</span><span class="sxs-lookup"><span data-stu-id="06987-188">Available</span></span> |
| | <span data-ttu-id="06987-189">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="06987-189">VoIP meeting</span></span> | <span data-ttu-id="06987-190">在线</span><span class="sxs-lookup"><span data-stu-id="06987-190">Available</span></span> |
| | <span data-ttu-id="06987-191">桌面共享</span><span class="sxs-lookup"><span data-stu-id="06987-191">Desktop sharing</span></span> | <span data-ttu-id="06987-192">在线</span><span class="sxs-lookup"><span data-stu-id="06987-192">Available</span></span> |
| | <span data-ttu-id="06987-193">在共享中提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="06987-193">Give and take control in sharing</span></span> | <span data-ttu-id="06987-194">在线</span><span class="sxs-lookup"><span data-stu-id="06987-194">Available</span></span> |
| | <span data-ttu-id="06987-195">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="06987-195">Connect from a conference room</span></span> | <span data-ttu-id="06987-196">在线</span><span class="sxs-lookup"><span data-stu-id="06987-196">Available</span></span> |
| | <span data-ttu-id="06987-197">匿名联接</span><span class="sxs-lookup"><span data-stu-id="06987-197">Anonymous join</span></span> | <span data-ttu-id="06987-198">在线</span><span class="sxs-lookup"><span data-stu-id="06987-198">Available</span></span> |
| | <span data-ttu-id="06987-199">云录制</span><span class="sxs-lookup"><span data-stu-id="06987-199">Cloud recording</span></span> | <span data-ttu-id="06987-200">在线</span><span class="sxs-lookup"><span data-stu-id="06987-200">Available</span></span> |
| | <span data-ttu-id="06987-201">会议笔记</span><span class="sxs-lookup"><span data-stu-id="06987-201">Meeting notes</span></span> | <span data-ttu-id="06987-202">在线</span><span class="sxs-lookup"><span data-stu-id="06987-202">Available</span></span> |
| | <span data-ttu-id="06987-203">实时事件</span><span class="sxs-lookup"><span data-stu-id="06987-203">Live Events</span></span> | <span data-ttu-id="06987-204">在线</span><span class="sxs-lookup"><span data-stu-id="06987-204">Available</span></span> |
| | <span data-ttu-id="06987-205">联盟会议</span><span class="sxs-lookup"><span data-stu-id="06987-205">Federated meetings</span></span> | <span data-ttu-id="06987-206">在线</span><span class="sxs-lookup"><span data-stu-id="06987-206">Available</span></span> |
| | <span data-ttu-id="06987-207">Surface Hub 支持</span><span class="sxs-lookup"><span data-stu-id="06987-207">Surface Hub support</span></span> | <span data-ttu-id="06987-208">在线</span><span class="sxs-lookup"><span data-stu-id="06987-208">Available</span></span> |
| <span data-ttu-id="06987-209">呼叫</span><span class="sxs-lookup"><span data-stu-id="06987-209">Calls</span></span> | <span data-ttu-id="06987-210">联系人</span><span class="sxs-lookup"><span data-stu-id="06987-210">Contacts</span></span> | <span data-ttu-id="06987-211">在线</span><span class="sxs-lookup"><span data-stu-id="06987-211">Available</span></span> |
| | <span data-ttu-id="06987-212">信息</span><span class="sxs-lookup"><span data-stu-id="06987-212">History</span></span> | <span data-ttu-id="06987-213">在线</span><span class="sxs-lookup"><span data-stu-id="06987-213">Available</span></span> |
| | <span data-ttu-id="06987-214">语音邮件</span><span class="sxs-lookup"><span data-stu-id="06987-214">Voicemail</span></span> | <span data-ttu-id="06987-215">可用</span><span class="sxs-lookup"><span data-stu-id="06987-215">Available</span></span> |
| | <span data-ttu-id="06987-216">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="06987-216">VoIP call</span></span> | <span data-ttu-id="06987-217">在线</span><span class="sxs-lookup"><span data-stu-id="06987-217">Available</span></span> |
| | <span data-ttu-id="06987-218">Skype for Business-团队通话</span><span class="sxs-lookup"><span data-stu-id="06987-218">Skype for Business - Teams calling</span></span> | <span data-ttu-id="06987-219">可用</span><span class="sxs-lookup"><span data-stu-id="06987-219">Available</span></span> |
| | <span data-ttu-id="06987-220">通话套餐</span><span class="sxs-lookup"><span data-stu-id="06987-220">Calling Plans</span></span> | <span data-ttu-id="06987-221">在线</span><span class="sxs-lookup"><span data-stu-id="06987-221">Available</span></span> |
| | <span data-ttu-id="06987-222">音频会议（通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="06987-222">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="06987-223">在线</span><span class="sxs-lookup"><span data-stu-id="06987-223">Available</span></span> |
| | <span data-ttu-id="06987-224">Microsoft Phone 系统直接路由</span><span class="sxs-lookup"><span data-stu-id="06987-224">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="06987-225">在线</span><span class="sxs-lookup"><span data-stu-id="06987-225">Available</span></span> |
| | <span data-ttu-id="06987-226">PSTN 呼叫者的大厅</span><span class="sxs-lookup"><span data-stu-id="06987-226">Lobby for PSTN callers</span></span> | <span data-ttu-id="06987-227">在线</span><span class="sxs-lookup"><span data-stu-id="06987-227">Available</span></span> |
| | <span data-ttu-id="06987-228">通话队列</span><span class="sxs-lookup"><span data-stu-id="06987-228">Call queue</span></span> | <span data-ttu-id="06987-229">在线</span><span class="sxs-lookup"><span data-stu-id="06987-229">Available</span></span> |
| | <span data-ttu-id="06987-230">老板和代理人支持</span><span class="sxs-lookup"><span data-stu-id="06987-230">Boss and delegate support</span></span> | <span data-ttu-id="06987-231">在线</span><span class="sxs-lookup"><span data-stu-id="06987-231">Available</span></span> |
| | <span data-ttu-id="06987-232">咨询和安全转移</span><span class="sxs-lookup"><span data-stu-id="06987-232">Consultative and safe transfer</span></span> | <span data-ttu-id="06987-233">在线</span><span class="sxs-lookup"><span data-stu-id="06987-233">Available</span></span> |
| | <span data-ttu-id="06987-234">请勿打扰突破</span><span class="sxs-lookup"><span data-stu-id="06987-234">Do not disturb breakthrough</span></span> | <span data-ttu-id="06987-235">在线</span><span class="sxs-lookup"><span data-stu-id="06987-235">Available</span></span> |
| | <span data-ttu-id="06987-236">独特震铃</span><span class="sxs-lookup"><span data-stu-id="06987-236">Distinctive ring</span></span> | <span data-ttu-id="06987-237">在线</span><span class="sxs-lookup"><span data-stu-id="06987-237">Available</span></span> |
| | <span data-ttu-id="06987-238">1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级</span><span class="sxs-lookup"><span data-stu-id="06987-238">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="06987-239">在线</span><span class="sxs-lookup"><span data-stu-id="06987-239">Available</span></span> |
| | <span data-ttu-id="06987-240">转发到组</span><span class="sxs-lookup"><span data-stu-id="06987-240">Forward to group</span></span> | <span data-ttu-id="06987-241">在线</span><span class="sxs-lookup"><span data-stu-id="06987-241">Available</span></span> |
| | <span data-ttu-id="06987-242">转接至 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="06987-242">Transfer to PSTN call</span></span> | <span data-ttu-id="06987-243">在线</span><span class="sxs-lookup"><span data-stu-id="06987-243">Available</span></span> |
| | <span data-ttu-id="06987-244">紧急呼叫呼叫计划</span><span class="sxs-lookup"><span data-stu-id="06987-244">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="06987-245">在线</span><span class="sxs-lookup"><span data-stu-id="06987-245">Available</span></span> |
| | <span data-ttu-id="06987-246">对现有认证的 SIP 电话的支持</span><span class="sxs-lookup"><span data-stu-id="06987-246">Support for existing certified SIP phones</span></span> | <span data-ttu-id="06987-247">在线</span><span class="sxs-lookup"><span data-stu-id="06987-247">Available</span></span> |
| | <span data-ttu-id="06987-248">USB HID</span><span class="sxs-lookup"><span data-stu-id="06987-248">USB HID</span></span> | <span data-ttu-id="06987-249">在线</span><span class="sxs-lookup"><span data-stu-id="06987-249">Available</span></span> |
| | <span data-ttu-id="06987-250">用于通话和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="06987-250">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="06987-251">在线</span><span class="sxs-lookup"><span data-stu-id="06987-251">Available</span></span> |
| | <span data-ttu-id="06987-252">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="06987-252">Organization auto attendant</span></span> | <span data-ttu-id="06987-253">在线</span><span class="sxs-lookup"><span data-stu-id="06987-253">Available</span></span> |
| | <span data-ttu-id="06987-254">Skype 消费者-团队通话支持</span><span class="sxs-lookup"><span data-stu-id="06987-254">Skype consumer - Teams call support</span></span> | <span data-ttu-id="06987-255">在线</span><span class="sxs-lookup"><span data-stu-id="06987-255">Available</span></span> |
| <span data-ttu-id="06987-256">文件</span><span class="sxs-lookup"><span data-stu-id="06987-256">Files</span></span> | <span data-ttu-id="06987-257">近来</span><span class="sxs-lookup"><span data-stu-id="06987-257">Recent</span></span> | <span data-ttu-id="06987-258">在线</span><span class="sxs-lookup"><span data-stu-id="06987-258">Available</span></span> |
| | <span data-ttu-id="06987-259">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06987-259">Microsoft Teams</span></span> | <span data-ttu-id="06987-260">在线</span><span class="sxs-lookup"><span data-stu-id="06987-260">Available</span></span> |
| <span data-ttu-id="06987-261">应用商店</span><span class="sxs-lookup"><span data-stu-id="06987-261">Store</span></span> | <span data-ttu-id="06987-262">应用商店</span><span class="sxs-lookup"><span data-stu-id="06987-262">App Store</span></span> | <span data-ttu-id="06987-263">在线</span><span class="sxs-lookup"><span data-stu-id="06987-263">Available</span></span> |
| <span data-ttu-id="06987-264">搜索</span><span class="sxs-lookup"><span data-stu-id="06987-264">Search</span></span> | <span data-ttu-id="06987-265">彩信</span><span class="sxs-lookup"><span data-stu-id="06987-265">Messages</span></span> | <span data-ttu-id="06987-266">在线</span><span class="sxs-lookup"><span data-stu-id="06987-266">Available</span></span> |
| | <span data-ttu-id="06987-267">人员</span><span class="sxs-lookup"><span data-stu-id="06987-267">People</span></span> | <span data-ttu-id="06987-268">在线</span><span class="sxs-lookup"><span data-stu-id="06987-268">Available</span></span> |
| | <span data-ttu-id="06987-269">文件</span><span class="sxs-lookup"><span data-stu-id="06987-269">Files</span></span> | <span data-ttu-id="06987-270">在线</span><span class="sxs-lookup"><span data-stu-id="06987-270">Available</span></span> |
| | <span data-ttu-id="06987-271">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="06987-271">Slash commands</span></span> | <span data-ttu-id="06987-272">在线</span><span class="sxs-lookup"><span data-stu-id="06987-272">Available</span></span> |
| <span data-ttu-id="06987-273">符合</span><span class="sxs-lookup"><span data-stu-id="06987-273">Compliance</span></span> | <span data-ttu-id="06987-274">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="06987-274">Compliance content search</span></span> | <span data-ttu-id="06987-275">在线</span><span class="sxs-lookup"><span data-stu-id="06987-275">Available</span></span> |
| | <span data-ttu-id="06987-276">保存</span><span class="sxs-lookup"><span data-stu-id="06987-276">Retention</span></span> | <span data-ttu-id="06987-277">在线</span><span class="sxs-lookup"><span data-stu-id="06987-277">Available</span></span> |
| | <span data-ttu-id="06987-278">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="06987-278">Audit log search</span></span> | <span data-ttu-id="06987-279">在线</span><span class="sxs-lookup"><span data-stu-id="06987-279">Available</span></span> |
| | <span data-ttu-id="06987-280">法律封存</span><span class="sxs-lookup"><span data-stu-id="06987-280">Legal hold</span></span> | <span data-ttu-id="06987-281">在线</span><span class="sxs-lookup"><span data-stu-id="06987-281">Available</span></span> |
| | <span data-ttu-id="06987-282">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="06987-282">eDiscovery</span></span> | <span data-ttu-id="06987-283">在线</span><span class="sxs-lookup"><span data-stu-id="06987-283">Available</span></span> |

> [!Note]
> <span data-ttu-id="06987-284">当其他工作负荷在 GCC 云中完全可用时，它们将在所有其他集成工作完成后的团队中变为可用。</span><span class="sxs-lookup"><span data-stu-id="06987-284">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="06987-286">决策点</span><span class="sxs-lookup"><span data-stu-id="06987-286">Decision point</span></span>|<ul><li><span data-ttu-id="06987-287">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="06987-287">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="06987-288">第 5 步</span><span class="sxs-lookup"><span data-stu-id="06987-288">Step 5.</span></span> <span data-ttu-id="06987-289">规划管理</span><span class="sxs-lookup"><span data-stu-id="06987-289">Plan for governance</span></span>

<span data-ttu-id="06987-290">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="06987-290">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="06987-291">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="06987-291">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="06987-293">决策点</span><span class="sxs-lookup"><span data-stu-id="06987-293">Decision point</span></span>|<ul><li><span data-ttu-id="06987-294">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="06987-294">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="06987-295">第 6 步</span><span class="sxs-lookup"><span data-stu-id="06987-295">Step 6.</span></span> <span data-ttu-id="06987-296">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="06987-296">Deploy Teams for collaboration</span></span>

<span data-ttu-id="06987-297">在 onboarded 到 Microsoft 365 政府-GCC 后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="06987-297">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="06987-298">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="06987-298">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="06987-299">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="06987-299">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="06987-300">第 7 步</span><span class="sxs-lookup"><span data-stu-id="06987-300">Step 7.</span></span> <span data-ttu-id="06987-301">为会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="06987-301">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="06987-302">这也是将团队与更大的风险承担者组配合使用来开始计划推出会议和[云语音功能](cloud-voice-deployment.md)的一个好时机。</span><span class="sxs-lookup"><span data-stu-id="06987-302">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

