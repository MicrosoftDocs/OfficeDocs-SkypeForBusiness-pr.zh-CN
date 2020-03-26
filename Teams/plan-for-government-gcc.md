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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97f7987d450b5a7b1fc23c39ed1e96ee0f953ae9
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978504"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="168c0-103">规划 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="168c0-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="168c0-104">本指南适用于面向美国联邦、州、本地、tribal 或 territorial 政府实体或其他实体中的 Office 365 部署的 IT 专业人员，这些实体或其他实体处理受政府管理法规和要求制约的数据，其中使用 Microsoft365政府-GCC 适用于满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="168c0-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="168c0-105">2020年3月26日，：不要错过我们可下载[的适用于 GCC 的快速入门指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="168c0-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="168c0-106">由于 coronavirus （COVID-19） pandemic，Microsoft 团队在在线通话和音频/视频会议方面遇到了极大的高峰。</span><span class="sxs-lookup"><span data-stu-id="168c0-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="168c0-107">为响应更空前的通话增加，并确保连续性和可用性，Microsoft 允许 Microsoft 团队拥有的音频/视频服务器利用我们的商业数据中心中的处理能力和我们的政府数据中心。</span><span class="sxs-lookup"><span data-stu-id="168c0-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="168c0-108">这些音频/视频服务器驻留在 Microsoft Azure FedRAMP 中的 Microsoft Azure 高资格鉴定边界服务器，并且不存储任何客户内容。</span><span class="sxs-lookup"><span data-stu-id="168c0-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="168c0-109">但是，这些服务器正在处理通话和会议的音频和视频，并在此期间内由我们的商业员工进行操作。</span><span class="sxs-lookup"><span data-stu-id="168c0-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="168c0-110">经确认，被筛选的人员正在监视这些服务器，以便通过查看这些服务器的交互式登录项来对客户数据进行潜在访问。</span><span class="sxs-lookup"><span data-stu-id="168c0-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="168c0-111">合格的人员在访问客户内容方面满足了 GCC 的要求。</span><span class="sxs-lookup"><span data-stu-id="168c0-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="168c0-112">有关筛选要求的详细信息，请参阅[GCC 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="168c0-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="168c0-113">感谢您的支持，因为我们采取措施来确保我们的服务在这些特别时间内保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="168c0-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="168c0-114">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求，并已接受并接受该计划，则可以跳过步骤1和步骤2，直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="168c0-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="168c0-115">第 1 步</span><span class="sxs-lookup"><span data-stu-id="168c0-115">Step 1.</span></span> <span data-ttu-id="168c0-116">确定你的组织是否需要 Microsoft 365 政府-GCC 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="168c0-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="168c0-117">Microsoft 365 政府版-GCC 环境为云服务（包括 FedRAMP 中等）和针对犯罪分子和联邦税务信息系统（CJI 和 FTI 数据类型）的要求遵守美国政府规定。</span><span class="sxs-lookup"><span data-stu-id="168c0-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="168c0-118">除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府-GCC 所特有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="168c0-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="168c0-119">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="168c0-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="168c0-120">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="168c0-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="168c0-121">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="168c0-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="168c0-122">Microsoft 365 政府版-GCC 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="168c0-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="168c0-123">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府版（美国）政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="168c0-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="168c0-124">[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍了平台的优势，这些优势在美国的会议合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="168c0-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="168c0-125">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="168c0-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="168c0-126">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="168c0-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="168c0-128">决策点</span><span class="sxs-lookup"><span data-stu-id="168c0-128">Decision points</span></span>|<ul><li><span data-ttu-id="168c0-129">确定 Microsoft 365 政府版-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="168c0-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="168c0-130">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="168c0-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="168c0-131">Microsoft 365 政府版-GCC 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="168c0-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="168c0-132">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="168c0-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="168c0-133">第 2 步</span><span class="sxs-lookup"><span data-stu-id="168c0-133">Step 2.</span></span> <span data-ttu-id="168c0-134">适用于 Microsoft 365 政府版-GCC</span><span class="sxs-lookup"><span data-stu-id="168c0-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="168c0-135">如果确定此服务适合你的组织，请在[此处开始应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="168c0-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="168c0-136">第 3 步</span><span class="sxs-lookup"><span data-stu-id="168c0-136">Step 3.</span></span> <span data-ttu-id="168c0-137">了解 Microsoft 365 政府版-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="168c0-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="168c0-138">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="168c0-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="168c0-140">决策点</span><span class="sxs-lookup"><span data-stu-id="168c0-140">Decision point</span></span>|<ul><li><span data-ttu-id="168c0-141">确定你是否要修改任何默认的 Microsoft 365 政府-GCC 安全设置，首先要了解你可能做出的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="168c0-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="168c0-142">第 4 步</span><span class="sxs-lookup"><span data-stu-id="168c0-142">Step 4.</span></span> <span data-ttu-id="168c0-143">了解默认情况下当前不可用或已禁用的功能。</span><span class="sxs-lookup"><span data-stu-id="168c0-143">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="168c0-144">为了满足政府云客户的要求，Microsoft 365 政府版和企业版计划之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="168c0-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="168c0-145">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="168c0-145">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="168c0-146">功能</span><span class="sxs-lookup"><span data-stu-id="168c0-146">Feature</span></span>                     | <span data-ttu-id="168c0-147">GCC</span><span class="sxs-lookup"><span data-stu-id="168c0-147">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="168c0-148">Base64</span><span class="sxs-lookup"><span data-stu-id="168c0-148">Base</span></span> | <span data-ttu-id="168c0-149">登录</span><span class="sxs-lookup"><span data-stu-id="168c0-149">Login</span></span> | <span data-ttu-id="168c0-150">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-150">Available</span></span> |
| | <span data-ttu-id="168c0-151">状态</span><span class="sxs-lookup"><span data-stu-id="168c0-151">Presence</span></span> | <span data-ttu-id="168c0-152">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-152">Available</span></span> |
| | <span data-ttu-id="168c0-153">统一状态（Skype for Business 和团队统一）</span><span class="sxs-lookup"><span data-stu-id="168c0-153">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="168c0-154">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-154">Available</span></span> |
| <span data-ttu-id="168c0-155">活动</span><span class="sxs-lookup"><span data-stu-id="168c0-155">Activity</span></span> | <span data-ttu-id="168c0-156">源</span><span class="sxs-lookup"><span data-stu-id="168c0-156">Feed</span></span> | <span data-ttu-id="168c0-157">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-157">Available</span></span> |
|  | <span data-ttu-id="168c0-158">我的活动</span><span class="sxs-lookup"><span data-stu-id="168c0-158">My Activity</span></span> | <span data-ttu-id="168c0-159">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-159">Available</span></span> |
| <span data-ttu-id="168c0-160">聊天</span><span class="sxs-lookup"><span data-stu-id="168c0-160">Chat</span></span> | <span data-ttu-id="168c0-161">交谈</span><span class="sxs-lookup"><span data-stu-id="168c0-161">Conversation</span></span> | <span data-ttu-id="168c0-162">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-162">Available</span></span> |
| | <span data-ttu-id="168c0-163">文件</span><span class="sxs-lookup"><span data-stu-id="168c0-163">Files</span></span> | <span data-ttu-id="168c0-164">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-164">Available</span></span> |
| | <span data-ttu-id="168c0-165">组织结构图</span><span class="sxs-lookup"><span data-stu-id="168c0-165">Org chart</span></span> | <span data-ttu-id="168c0-166">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-166">Available</span></span> |
| | <span data-ttu-id="168c0-167">活动</span><span class="sxs-lookup"><span data-stu-id="168c0-167">Activity</span></span> | <span data-ttu-id="168c0-168">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-168">Available</span></span> |
| | <span data-ttu-id="168c0-169">互操作（1:1 团队-Skype for Business 聊天）</span><span class="sxs-lookup"><span data-stu-id="168c0-169">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="168c0-170">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-170">Available</span></span> |
| <span data-ttu-id="168c0-171">Teams</span><span class="sxs-lookup"><span data-stu-id="168c0-171">Teams</span></span> | <span data-ttu-id="168c0-172">频道消息</span><span class="sxs-lookup"><span data-stu-id="168c0-172">Channel message</span></span> | <span data-ttu-id="168c0-173">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-173">Available</span></span> |
| | <span data-ttu-id="168c0-174">信道文件</span><span class="sxs-lookup"><span data-stu-id="168c0-174">Channel files</span></span> | <span data-ttu-id="168c0-175">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-175">Available</span></span> |
| | <span data-ttu-id="168c0-176">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="168c0-176">OneNote tab</span></span> | <span data-ttu-id="168c0-177">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="168c0-177">On the Government backlog</span></span> |
| | <span data-ttu-id="168c0-178">通过电子邮件发送频道</span><span class="sxs-lookup"><span data-stu-id="168c0-178">Email a channel</span></span> | <span data-ttu-id="168c0-179">不可用</span><span class="sxs-lookup"><span data-stu-id="168c0-179">Not available</span></span> |
| | <span data-ttu-id="168c0-180">添加成员</span><span class="sxs-lookup"><span data-stu-id="168c0-180">Add member</span></span> | <span data-ttu-id="168c0-181">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-181">Available</span></span> |
| | <span data-ttu-id="168c0-182">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="168c0-182">Guest access</span></span> | <span data-ttu-id="168c0-183">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-183">Available</span></span> |
| <span data-ttu-id="168c0-184">会议</span><span class="sxs-lookup"><span data-stu-id="168c0-184">Meetings</span></span> | <span data-ttu-id="168c0-185">安排会议</span><span class="sxs-lookup"><span data-stu-id="168c0-185">Schedule meeting</span></span> | <span data-ttu-id="168c0-186">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-186">Available</span></span> |
| | <span data-ttu-id="168c0-187">加入会议</span><span class="sxs-lookup"><span data-stu-id="168c0-187">Join meeting</span></span> | <span data-ttu-id="168c0-188">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-188">Available</span></span> |
| | <span data-ttu-id="168c0-189">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="168c0-189">VoIP meeting</span></span> | <span data-ttu-id="168c0-190">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-190">Available</span></span> |
| | <span data-ttu-id="168c0-191">桌面共享</span><span class="sxs-lookup"><span data-stu-id="168c0-191">Desktop sharing</span></span> | <span data-ttu-id="168c0-192">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-192">Available</span></span> |
| | <span data-ttu-id="168c0-193">在共享中提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="168c0-193">Give and take control in sharing</span></span> | <span data-ttu-id="168c0-194">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-194">Available</span></span> |
| | <span data-ttu-id="168c0-195">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="168c0-195">Connect from a conference room</span></span> | <span data-ttu-id="168c0-196">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-196">Available</span></span> |
| | <span data-ttu-id="168c0-197">匿名联接</span><span class="sxs-lookup"><span data-stu-id="168c0-197">Anonymous join</span></span> | <span data-ttu-id="168c0-198">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-198">Available</span></span> |
| | <span data-ttu-id="168c0-199">云录制</span><span class="sxs-lookup"><span data-stu-id="168c0-199">Cloud recording</span></span> | <span data-ttu-id="168c0-200">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-200">Available</span></span> |
| | <span data-ttu-id="168c0-201">会议笔记</span><span class="sxs-lookup"><span data-stu-id="168c0-201">Meeting notes</span></span> | <span data-ttu-id="168c0-202">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-202">Available</span></span> |
| | <span data-ttu-id="168c0-203">实时事件</span><span class="sxs-lookup"><span data-stu-id="168c0-203">Live Events</span></span> | <span data-ttu-id="168c0-204">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-204">Available</span></span> |
| | <span data-ttu-id="168c0-205">联盟会议</span><span class="sxs-lookup"><span data-stu-id="168c0-205">Federated meetings</span></span> | <span data-ttu-id="168c0-206">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-206">Available</span></span> |
| | <span data-ttu-id="168c0-207">Surface Hub 支持</span><span class="sxs-lookup"><span data-stu-id="168c0-207">Surface Hub support</span></span> | <span data-ttu-id="168c0-208">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-208">Available</span></span> |
| <span data-ttu-id="168c0-209">呼叫</span><span class="sxs-lookup"><span data-stu-id="168c0-209">Calls</span></span> | <span data-ttu-id="168c0-210">联系人</span><span class="sxs-lookup"><span data-stu-id="168c0-210">Contacts</span></span> | <span data-ttu-id="168c0-211">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-211">Available</span></span> |
| | <span data-ttu-id="168c0-212">信息</span><span class="sxs-lookup"><span data-stu-id="168c0-212">History</span></span> | <span data-ttu-id="168c0-213">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-213">Available</span></span> |
| | <span data-ttu-id="168c0-214">语音邮件</span><span class="sxs-lookup"><span data-stu-id="168c0-214">Voicemail</span></span> | <span data-ttu-id="168c0-215">可用</span><span class="sxs-lookup"><span data-stu-id="168c0-215">Available</span></span> |
| | <span data-ttu-id="168c0-216">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="168c0-216">VoIP call</span></span> | <span data-ttu-id="168c0-217">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-217">Available</span></span> |
| | <span data-ttu-id="168c0-218">Skype for Business-团队通话</span><span class="sxs-lookup"><span data-stu-id="168c0-218">Skype for Business - Teams calling</span></span> | <span data-ttu-id="168c0-219">可用</span><span class="sxs-lookup"><span data-stu-id="168c0-219">Available</span></span> |
| | <span data-ttu-id="168c0-220">通话套餐</span><span class="sxs-lookup"><span data-stu-id="168c0-220">Calling Plans</span></span> | <span data-ttu-id="168c0-221">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-221">Available</span></span> |
| | <span data-ttu-id="168c0-222">音频会议（通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="168c0-222">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="168c0-223">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-223">Available</span></span> |
| | <span data-ttu-id="168c0-224">Microsoft Phone 系统直接路由</span><span class="sxs-lookup"><span data-stu-id="168c0-224">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="168c0-225">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-225">Available</span></span> |
| | <span data-ttu-id="168c0-226">PSTN 呼叫者的大厅</span><span class="sxs-lookup"><span data-stu-id="168c0-226">Lobby for PSTN callers</span></span> | <span data-ttu-id="168c0-227">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-227">Available</span></span> |
| | <span data-ttu-id="168c0-228">通话队列</span><span class="sxs-lookup"><span data-stu-id="168c0-228">Call queue</span></span> | <span data-ttu-id="168c0-229">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-229">Available</span></span> |
| | <span data-ttu-id="168c0-230">老板和代理人支持</span><span class="sxs-lookup"><span data-stu-id="168c0-230">Boss and delegate support</span></span> | <span data-ttu-id="168c0-231">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-231">Available</span></span> |
| | <span data-ttu-id="168c0-232">咨询和安全转移</span><span class="sxs-lookup"><span data-stu-id="168c0-232">Consultative and safe transfer</span></span> | <span data-ttu-id="168c0-233">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-233">Available</span></span> |
| | <span data-ttu-id="168c0-234">请勿打扰突破</span><span class="sxs-lookup"><span data-stu-id="168c0-234">Do not disturb breakthrough</span></span> | <span data-ttu-id="168c0-235">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-235">Available</span></span> |
| | <span data-ttu-id="168c0-236">独特震铃</span><span class="sxs-lookup"><span data-stu-id="168c0-236">Distinctive ring</span></span> | <span data-ttu-id="168c0-237">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-237">Available</span></span> |
| | <span data-ttu-id="168c0-238">1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级</span><span class="sxs-lookup"><span data-stu-id="168c0-238">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="168c0-239">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-239">Available</span></span> |
| | <span data-ttu-id="168c0-240">转发到组</span><span class="sxs-lookup"><span data-stu-id="168c0-240">Forward to group</span></span> | <span data-ttu-id="168c0-241">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-241">Available</span></span> |
| | <span data-ttu-id="168c0-242">转接至 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="168c0-242">Transfer to PSTN call</span></span> | <span data-ttu-id="168c0-243">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-243">Available</span></span> |
| | <span data-ttu-id="168c0-244">紧急呼叫呼叫计划</span><span class="sxs-lookup"><span data-stu-id="168c0-244">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="168c0-245">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-245">Available</span></span> |
| | <span data-ttu-id="168c0-246">对现有认证的 SIP 电话的支持</span><span class="sxs-lookup"><span data-stu-id="168c0-246">Support for existing certified SIP phones</span></span> | <span data-ttu-id="168c0-247">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-247">Available</span></span> |
| | <span data-ttu-id="168c0-248">USB HID</span><span class="sxs-lookup"><span data-stu-id="168c0-248">USB HID</span></span> | <span data-ttu-id="168c0-249">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-249">Available</span></span> |
| | <span data-ttu-id="168c0-250">用于通话和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="168c0-250">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="168c0-251">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-251">Available</span></span> |
| | <span data-ttu-id="168c0-252">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="168c0-252">Organization auto attendant</span></span> | <span data-ttu-id="168c0-253">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-253">Available</span></span> |
| | <span data-ttu-id="168c0-254">Skype 消费者-团队通话支持</span><span class="sxs-lookup"><span data-stu-id="168c0-254">Skype consumer - Teams call support</span></span> | <span data-ttu-id="168c0-255">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-255">Available</span></span> |
| <span data-ttu-id="168c0-256">文件</span><span class="sxs-lookup"><span data-stu-id="168c0-256">Files</span></span> | <span data-ttu-id="168c0-257">近来</span><span class="sxs-lookup"><span data-stu-id="168c0-257">Recent</span></span> | <span data-ttu-id="168c0-258">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-258">Available</span></span> |
| | <span data-ttu-id="168c0-259">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="168c0-259">Microsoft Teams</span></span> | <span data-ttu-id="168c0-260">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-260">Available</span></span> |
| <span data-ttu-id="168c0-261">应用商店</span><span class="sxs-lookup"><span data-stu-id="168c0-261">Store</span></span> | <span data-ttu-id="168c0-262">应用商店</span><span class="sxs-lookup"><span data-stu-id="168c0-262">App Store</span></span> | <span data-ttu-id="168c0-263">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-263">Available</span></span> |
| <span data-ttu-id="168c0-264">搜索</span><span class="sxs-lookup"><span data-stu-id="168c0-264">Search</span></span> | <span data-ttu-id="168c0-265">彩信</span><span class="sxs-lookup"><span data-stu-id="168c0-265">Messages</span></span> | <span data-ttu-id="168c0-266">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-266">Available</span></span> |
| | <span data-ttu-id="168c0-267">人员</span><span class="sxs-lookup"><span data-stu-id="168c0-267">People</span></span> | <span data-ttu-id="168c0-268">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-268">Available</span></span> |
| | <span data-ttu-id="168c0-269">文件</span><span class="sxs-lookup"><span data-stu-id="168c0-269">Files</span></span> | <span data-ttu-id="168c0-270">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-270">Available</span></span> |
| | <span data-ttu-id="168c0-271">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="168c0-271">Slash commands</span></span> | <span data-ttu-id="168c0-272">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-272">Available</span></span> |
| <span data-ttu-id="168c0-273">符合</span><span class="sxs-lookup"><span data-stu-id="168c0-273">Compliance</span></span> | <span data-ttu-id="168c0-274">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="168c0-274">Compliance content search</span></span> | <span data-ttu-id="168c0-275">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-275">Available</span></span> |
| | <span data-ttu-id="168c0-276">保存</span><span class="sxs-lookup"><span data-stu-id="168c0-276">Retention</span></span> | <span data-ttu-id="168c0-277">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-277">Available</span></span> |
| | <span data-ttu-id="168c0-278">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="168c0-278">Audit log search</span></span> | <span data-ttu-id="168c0-279">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-279">Available</span></span> |
| | <span data-ttu-id="168c0-280">法律封存</span><span class="sxs-lookup"><span data-stu-id="168c0-280">Legal hold</span></span> | <span data-ttu-id="168c0-281">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-281">Available</span></span> |
| | <span data-ttu-id="168c0-282">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="168c0-282">eDiscovery</span></span> | <span data-ttu-id="168c0-283">在线</span><span class="sxs-lookup"><span data-stu-id="168c0-283">Available</span></span> |

> [!Note]
> <span data-ttu-id="168c0-284">当其他工作负荷在 GCC 云中完全可用时，它们将在所有其他集成工作完成后的团队中变为可用。</span><span class="sxs-lookup"><span data-stu-id="168c0-284">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="168c0-286">决策点</span><span class="sxs-lookup"><span data-stu-id="168c0-286">Decision point</span></span>|<ul><li><span data-ttu-id="168c0-287">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="168c0-287">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="168c0-288">第 5 步</span><span class="sxs-lookup"><span data-stu-id="168c0-288">Step 5.</span></span> <span data-ttu-id="168c0-289">规划管理</span><span class="sxs-lookup"><span data-stu-id="168c0-289">Plan for governance</span></span>

<span data-ttu-id="168c0-290">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="168c0-290">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="168c0-291">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="168c0-291">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="168c0-293">决策点</span><span class="sxs-lookup"><span data-stu-id="168c0-293">Decision point</span></span>|<ul><li><span data-ttu-id="168c0-294">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="168c0-294">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="168c0-295">第 6 步</span><span class="sxs-lookup"><span data-stu-id="168c0-295">Step 6.</span></span> <span data-ttu-id="168c0-296">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="168c0-296">Deploy Teams for collaboration</span></span>

<span data-ttu-id="168c0-297">在 onboarded 到 Microsoft 365 政府-GCC 后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="168c0-297">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="168c0-298">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="168c0-298">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="168c0-299">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="168c0-299">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="168c0-300">第 7 步</span><span class="sxs-lookup"><span data-stu-id="168c0-300">Step 7.</span></span> <span data-ttu-id="168c0-301">为会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="168c0-301">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="168c0-302">这也是将团队与更大的风险承担者组配合使用来开始计划推出会议和[云语音功能](cloud-voice-deployment.md)的一个好时机。</span><span class="sxs-lookup"><span data-stu-id="168c0-302">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

