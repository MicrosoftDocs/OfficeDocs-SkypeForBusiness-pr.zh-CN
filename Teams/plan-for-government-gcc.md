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
ms.openlocfilehash: a1b97e82edd97079c1e4615e5bb7fcf4a1eb2fea
ms.sourcegitcommit: b6eb22e96be5fb18984f1dd05e4eb8f2cfc032f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2020
ms.locfileid: "42968657"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="8a63c-103">规划 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="8a63c-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="8a63c-104">本指南适用于面向美国联邦、州、本地、tribal 或 territorial 政府实体或其他实体中的 Office 365 部署的 IT 专业人员，这些实体或其他实体处理受政府管理法规和要求制约的数据，其中使用 Microsoft365政府-GCC 适用于满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a63c-105">由于 coronavirus （COVID-19） pandemic，Microsoft 团队在在线通话和音频/视频会议方面遇到了极大的高峰。</span><span class="sxs-lookup"><span data-stu-id="8a63c-105">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="8a63c-106">为响应更空前的通话增加，并确保连续性和可用性，Microsoft 允许 Microsoft 团队拥有的音频/视频服务器利用我们的商业数据中心中的处理能力和我们的政府数据中心。</span><span class="sxs-lookup"><span data-stu-id="8a63c-106">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="8a63c-107">这些音频/视频服务器驻留在 Microsoft Azure FedRAMP 中的 Microsoft Azure 高资格鉴定边界服务器，并且不存储任何客户内容。</span><span class="sxs-lookup"><span data-stu-id="8a63c-107">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="8a63c-108">但是，这些服务器正在处理通话和会议的音频和视频，并在此期间内由我们的商业员工进行操作。</span><span class="sxs-lookup"><span data-stu-id="8a63c-108">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="8a63c-109">经确认，被筛选的人员正在监视这些服务器，以便通过查看这些服务器的交互式登录项来对客户数据进行潜在访问。</span><span class="sxs-lookup"><span data-stu-id="8a63c-109">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="8a63c-110">合格的人员在访问客户内容方面满足了 GCC 的要求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-110">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="8a63c-111">有关筛选要求的详细信息，请参阅[GCC 服务说明](Office365-ServiceDescriptions\office-365-platform-service-description\office-365-us-government\gcc.md)。</span><span class="sxs-lookup"><span data-stu-id="8a63c-111">For details about screening requirements, see the [GCC service description](Office365-ServiceDescriptions\office-365-platform-service-description\office-365-us-government\gcc.md).</span></span><br/>
> 
><span data-ttu-id="8a63c-112">感谢您的支持，因为我们采取措施来确保我们的服务在这些特别时间内保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="8a63c-112">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="8a63c-113">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求，并已接受并接受该计划，则可以跳过步骤1和步骤2，直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="8a63c-113">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="8a63c-114">第 1 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-114">Step 1.</span></span> <span data-ttu-id="8a63c-115">确定你的组织是否需要 Microsoft 365 政府-GCC 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-115">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="8a63c-116">Microsoft 365 政府版-GCC 环境为云服务（包括 FedRAMP 中等）和针对犯罪分子和联邦税务信息系统（CJI 和 FTI 数据类型）的要求遵守美国政府规定。</span><span class="sxs-lookup"><span data-stu-id="8a63c-116">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="8a63c-117">除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府-GCC 所特有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="8a63c-117">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="8a63c-118">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="8a63c-118">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="8a63c-119">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="8a63c-119">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="8a63c-120">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="8a63c-120">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="8a63c-121">Microsoft 365 政府版-GCC 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="8a63c-121">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="8a63c-122">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府版（美国）政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a63c-122">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="8a63c-123">[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍了平台的优势，这些优势在美国的会议合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="8a63c-123">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="8a63c-124">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="8a63c-124">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="8a63c-125">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-125">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8a63c-127">决策点</span><span class="sxs-lookup"><span data-stu-id="8a63c-127">Decision points</span></span>|<ul><li><span data-ttu-id="8a63c-128">确定 Microsoft 365 政府版-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="8a63c-128">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="8a63c-129">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-129">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="8a63c-130">Microsoft 365 政府版-GCC 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="8a63c-130">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="8a63c-131">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="8a63c-131">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="8a63c-132">第 2 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-132">Step 2.</span></span> <span data-ttu-id="8a63c-133">适用于 Microsoft 365 政府版-GCC</span><span class="sxs-lookup"><span data-stu-id="8a63c-133">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="8a63c-134">如果确定此服务适合你的组织，请在[此处开始应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="8a63c-134">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="8a63c-135">第 3 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-135">Step 3.</span></span> <span data-ttu-id="8a63c-136">了解 Microsoft 365 政府版-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="8a63c-136">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="8a63c-137">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="8a63c-137">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8a63c-139">决策点</span><span class="sxs-lookup"><span data-stu-id="8a63c-139">Decision point</span></span>|<ul><li><span data-ttu-id="8a63c-140">确定你是否要修改任何默认的 Microsoft 365 政府-GCC 安全设置，首先要了解你可能做出的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="8a63c-140">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="8a63c-141">第 4 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-141">Step 4.</span></span> <span data-ttu-id="8a63c-142">了解默认情况下当前不可用或已禁用的功能。</span><span class="sxs-lookup"><span data-stu-id="8a63c-142">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="8a63c-143">为了满足政府云客户的要求，Microsoft 365 政府版和企业版计划之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="8a63c-143">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="8a63c-144">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="8a63c-144">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="8a63c-145">功能</span><span class="sxs-lookup"><span data-stu-id="8a63c-145">Feature</span></span>                     | <span data-ttu-id="8a63c-146">GCC</span><span class="sxs-lookup"><span data-stu-id="8a63c-146">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="8a63c-147">Base64</span><span class="sxs-lookup"><span data-stu-id="8a63c-147">Base</span></span> | <span data-ttu-id="8a63c-148">登录</span><span class="sxs-lookup"><span data-stu-id="8a63c-148">Login</span></span> | <span data-ttu-id="8a63c-149">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-149">Available</span></span> |
| | <span data-ttu-id="8a63c-150">状态</span><span class="sxs-lookup"><span data-stu-id="8a63c-150">Presence</span></span> | <span data-ttu-id="8a63c-151">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-151">Available</span></span> |
| | <span data-ttu-id="8a63c-152">统一状态（Skype for Business 和团队统一）</span><span class="sxs-lookup"><span data-stu-id="8a63c-152">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="8a63c-153">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-153">Available</span></span> |
| <span data-ttu-id="8a63c-154">活动</span><span class="sxs-lookup"><span data-stu-id="8a63c-154">Activity</span></span> | <span data-ttu-id="8a63c-155">源</span><span class="sxs-lookup"><span data-stu-id="8a63c-155">Feed</span></span> | <span data-ttu-id="8a63c-156">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-156">Available</span></span> |
|  | <span data-ttu-id="8a63c-157">我的活动</span><span class="sxs-lookup"><span data-stu-id="8a63c-157">My Activity</span></span> | <span data-ttu-id="8a63c-158">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-158">Available</span></span> |
| <span data-ttu-id="8a63c-159">聊天</span><span class="sxs-lookup"><span data-stu-id="8a63c-159">Chat</span></span> | <span data-ttu-id="8a63c-160">交谈</span><span class="sxs-lookup"><span data-stu-id="8a63c-160">Conversation</span></span> | <span data-ttu-id="8a63c-161">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-161">Available</span></span> |
| | <span data-ttu-id="8a63c-162">文件</span><span class="sxs-lookup"><span data-stu-id="8a63c-162">Files</span></span> | <span data-ttu-id="8a63c-163">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-163">Available</span></span> |
| | <span data-ttu-id="8a63c-164">组织结构图</span><span class="sxs-lookup"><span data-stu-id="8a63c-164">Org chart</span></span> | <span data-ttu-id="8a63c-165">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-165">Available</span></span> |
| | <span data-ttu-id="8a63c-166">活动</span><span class="sxs-lookup"><span data-stu-id="8a63c-166">Activity</span></span> | <span data-ttu-id="8a63c-167">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-167">Available</span></span> |
| | <span data-ttu-id="8a63c-168">互操作（1:1 团队-Skype for Business 聊天）</span><span class="sxs-lookup"><span data-stu-id="8a63c-168">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="8a63c-169">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-169">Available</span></span> |
| <span data-ttu-id="8a63c-170">Teams</span><span class="sxs-lookup"><span data-stu-id="8a63c-170">Teams</span></span> | <span data-ttu-id="8a63c-171">频道消息</span><span class="sxs-lookup"><span data-stu-id="8a63c-171">Channel message</span></span> | <span data-ttu-id="8a63c-172">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-172">Available</span></span> |
| | <span data-ttu-id="8a63c-173">信道文件</span><span class="sxs-lookup"><span data-stu-id="8a63c-173">Channel files</span></span> | <span data-ttu-id="8a63c-174">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-174">Available</span></span> |
| | <span data-ttu-id="8a63c-175">OneNote 选项卡</span><span class="sxs-lookup"><span data-stu-id="8a63c-175">OneNote tab</span></span> | <span data-ttu-id="8a63c-176">在政府待办事项中</span><span class="sxs-lookup"><span data-stu-id="8a63c-176">On the Government backlog</span></span> |
| | <span data-ttu-id="8a63c-177">通过电子邮件发送频道</span><span class="sxs-lookup"><span data-stu-id="8a63c-177">Email a channel</span></span> | <span data-ttu-id="8a63c-178">不可用</span><span class="sxs-lookup"><span data-stu-id="8a63c-178">Not available</span></span> |
| | <span data-ttu-id="8a63c-179">添加成员</span><span class="sxs-lookup"><span data-stu-id="8a63c-179">Add member</span></span> | <span data-ttu-id="8a63c-180">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-180">Available</span></span> |
| | <span data-ttu-id="8a63c-181">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="8a63c-181">Guest access</span></span> | <span data-ttu-id="8a63c-182">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-182">Available</span></span> |
| <span data-ttu-id="8a63c-183">会议</span><span class="sxs-lookup"><span data-stu-id="8a63c-183">Meetings</span></span> | <span data-ttu-id="8a63c-184">安排会议</span><span class="sxs-lookup"><span data-stu-id="8a63c-184">Schedule meeting</span></span> | <span data-ttu-id="8a63c-185">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-185">Available</span></span> |
| | <span data-ttu-id="8a63c-186">加入会议</span><span class="sxs-lookup"><span data-stu-id="8a63c-186">Join meeting</span></span> | <span data-ttu-id="8a63c-187">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-187">Available</span></span> |
| | <span data-ttu-id="8a63c-188">VoIP 会议</span><span class="sxs-lookup"><span data-stu-id="8a63c-188">VoIP meeting</span></span> | <span data-ttu-id="8a63c-189">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-189">Available</span></span> |
| | <span data-ttu-id="8a63c-190">桌面共享</span><span class="sxs-lookup"><span data-stu-id="8a63c-190">Desktop sharing</span></span> | <span data-ttu-id="8a63c-191">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-191">Available</span></span> |
| | <span data-ttu-id="8a63c-192">在共享中提供和获取控制权</span><span class="sxs-lookup"><span data-stu-id="8a63c-192">Give and take control in sharing</span></span> | <span data-ttu-id="8a63c-193">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-193">Available</span></span> |
| | <span data-ttu-id="8a63c-194">从会议室连接</span><span class="sxs-lookup"><span data-stu-id="8a63c-194">Connect from a conference room</span></span> | <span data-ttu-id="8a63c-195">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-195">Available</span></span> |
| | <span data-ttu-id="8a63c-196">匿名联接</span><span class="sxs-lookup"><span data-stu-id="8a63c-196">Anonymous join</span></span> | <span data-ttu-id="8a63c-197">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-197">Available</span></span> |
| | <span data-ttu-id="8a63c-198">云录制</span><span class="sxs-lookup"><span data-stu-id="8a63c-198">Cloud recording</span></span> | <span data-ttu-id="8a63c-199">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-199">Available</span></span> |
| | <span data-ttu-id="8a63c-200">会议笔记</span><span class="sxs-lookup"><span data-stu-id="8a63c-200">Meeting notes</span></span> | <span data-ttu-id="8a63c-201">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-201">Available</span></span> |
| | <span data-ttu-id="8a63c-202">实时事件</span><span class="sxs-lookup"><span data-stu-id="8a63c-202">Live Events</span></span> | <span data-ttu-id="8a63c-203">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-203">Available</span></span> |
| | <span data-ttu-id="8a63c-204">联盟会议</span><span class="sxs-lookup"><span data-stu-id="8a63c-204">Federated meetings</span></span> | <span data-ttu-id="8a63c-205">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-205">Available</span></span> |
| | <span data-ttu-id="8a63c-206">Surface Hub 支持</span><span class="sxs-lookup"><span data-stu-id="8a63c-206">Surface Hub support</span></span> | <span data-ttu-id="8a63c-207">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-207">Available</span></span> |
| <span data-ttu-id="8a63c-208">呼叫</span><span class="sxs-lookup"><span data-stu-id="8a63c-208">Calls</span></span> | <span data-ttu-id="8a63c-209">联系人</span><span class="sxs-lookup"><span data-stu-id="8a63c-209">Contacts</span></span> | <span data-ttu-id="8a63c-210">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-210">Available</span></span> |
| | <span data-ttu-id="8a63c-211">信息</span><span class="sxs-lookup"><span data-stu-id="8a63c-211">History</span></span> | <span data-ttu-id="8a63c-212">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-212">Available</span></span> |
| | <span data-ttu-id="8a63c-213">语音邮件</span><span class="sxs-lookup"><span data-stu-id="8a63c-213">Voicemail</span></span> | <span data-ttu-id="8a63c-214">可用</span><span class="sxs-lookup"><span data-stu-id="8a63c-214">Available</span></span> |
| | <span data-ttu-id="8a63c-215">VoIP 呼叫</span><span class="sxs-lookup"><span data-stu-id="8a63c-215">VoIP call</span></span> | <span data-ttu-id="8a63c-216">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-216">Available</span></span> |
| | <span data-ttu-id="8a63c-217">Skype for Business-团队通话</span><span class="sxs-lookup"><span data-stu-id="8a63c-217">Skype for Business - Teams calling</span></span> | <span data-ttu-id="8a63c-218">可用</span><span class="sxs-lookup"><span data-stu-id="8a63c-218">Available</span></span> |
| | <span data-ttu-id="8a63c-219">通话套餐</span><span class="sxs-lookup"><span data-stu-id="8a63c-219">Calling Plans</span></span> | <span data-ttu-id="8a63c-220">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-220">Available</span></span> |
| | <span data-ttu-id="8a63c-221">音频会议（通过允许会议参与者通过 PSTN 加入）</span><span class="sxs-lookup"><span data-stu-id="8a63c-221">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="8a63c-222">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-222">Available</span></span> |
| | <span data-ttu-id="8a63c-223">Microsoft Phone 系统直接路由</span><span class="sxs-lookup"><span data-stu-id="8a63c-223">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="8a63c-224">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-224">Available</span></span> |
| | <span data-ttu-id="8a63c-225">PSTN 呼叫者的大厅</span><span class="sxs-lookup"><span data-stu-id="8a63c-225">Lobby for PSTN callers</span></span> | <span data-ttu-id="8a63c-226">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-226">Available</span></span> |
| | <span data-ttu-id="8a63c-227">通话队列</span><span class="sxs-lookup"><span data-stu-id="8a63c-227">Call queue</span></span> | <span data-ttu-id="8a63c-228">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-228">Available</span></span> |
| | <span data-ttu-id="8a63c-229">老板和代理人支持</span><span class="sxs-lookup"><span data-stu-id="8a63c-229">Boss and delegate support</span></span> | <span data-ttu-id="8a63c-230">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-230">Available</span></span> |
| | <span data-ttu-id="8a63c-231">咨询和安全转移</span><span class="sxs-lookup"><span data-stu-id="8a63c-231">Consultative and safe transfer</span></span> | <span data-ttu-id="8a63c-232">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-232">Available</span></span> |
| | <span data-ttu-id="8a63c-233">请勿打扰突破</span><span class="sxs-lookup"><span data-stu-id="8a63c-233">Do not disturb breakthrough</span></span> | <span data-ttu-id="8a63c-234">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-234">Available</span></span> |
| | <span data-ttu-id="8a63c-235">独特震铃</span><span class="sxs-lookup"><span data-stu-id="8a63c-235">Distinctive ring</span></span> | <span data-ttu-id="8a63c-236">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-236">Available</span></span> |
| | <span data-ttu-id="8a63c-237">1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级</span><span class="sxs-lookup"><span data-stu-id="8a63c-237">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="8a63c-238">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-238">Available</span></span> |
| | <span data-ttu-id="8a63c-239">转发到组</span><span class="sxs-lookup"><span data-stu-id="8a63c-239">Forward to group</span></span> | <span data-ttu-id="8a63c-240">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-240">Available</span></span> |
| | <span data-ttu-id="8a63c-241">转接至 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="8a63c-241">Transfer to PSTN call</span></span> | <span data-ttu-id="8a63c-242">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-242">Available</span></span> |
| | <span data-ttu-id="8a63c-243">紧急呼叫呼叫计划</span><span class="sxs-lookup"><span data-stu-id="8a63c-243">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="8a63c-244">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-244">Available</span></span> |
| | <span data-ttu-id="8a63c-245">对现有认证的 SIP 电话的支持</span><span class="sxs-lookup"><span data-stu-id="8a63c-245">Support for existing certified SIP phones</span></span> | <span data-ttu-id="8a63c-246">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-246">Available</span></span> |
| | <span data-ttu-id="8a63c-247">USB HID</span><span class="sxs-lookup"><span data-stu-id="8a63c-247">USB HID</span></span> | <span data-ttu-id="8a63c-248">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-248">Available</span></span> |
| | <span data-ttu-id="8a63c-249">用于通话和会议的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="8a63c-249">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="8a63c-250">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-250">Available</span></span> |
| | <span data-ttu-id="8a63c-251">组织自动助理</span><span class="sxs-lookup"><span data-stu-id="8a63c-251">Organization auto attendant</span></span> | <span data-ttu-id="8a63c-252">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-252">Available</span></span> |
| | <span data-ttu-id="8a63c-253">Skype 消费者-团队通话支持</span><span class="sxs-lookup"><span data-stu-id="8a63c-253">Skype consumer - Teams call support</span></span> | <span data-ttu-id="8a63c-254">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-254">Available</span></span> |
| <span data-ttu-id="8a63c-255">文件</span><span class="sxs-lookup"><span data-stu-id="8a63c-255">Files</span></span> | <span data-ttu-id="8a63c-256">近来</span><span class="sxs-lookup"><span data-stu-id="8a63c-256">Recent</span></span> | <span data-ttu-id="8a63c-257">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-257">Available</span></span> |
| | <span data-ttu-id="8a63c-258">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a63c-258">Microsoft Teams</span></span> | <span data-ttu-id="8a63c-259">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-259">Available</span></span> |
| <span data-ttu-id="8a63c-260">应用商店</span><span class="sxs-lookup"><span data-stu-id="8a63c-260">Store</span></span> | <span data-ttu-id="8a63c-261">应用商店</span><span class="sxs-lookup"><span data-stu-id="8a63c-261">App Store</span></span> | <span data-ttu-id="8a63c-262">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-262">Available</span></span> |
| <span data-ttu-id="8a63c-263">搜索</span><span class="sxs-lookup"><span data-stu-id="8a63c-263">Search</span></span> | <span data-ttu-id="8a63c-264">彩信</span><span class="sxs-lookup"><span data-stu-id="8a63c-264">Messages</span></span> | <span data-ttu-id="8a63c-265">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-265">Available</span></span> |
| | <span data-ttu-id="8a63c-266">人员</span><span class="sxs-lookup"><span data-stu-id="8a63c-266">People</span></span> | <span data-ttu-id="8a63c-267">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-267">Available</span></span> |
| | <span data-ttu-id="8a63c-268">文件</span><span class="sxs-lookup"><span data-stu-id="8a63c-268">Files</span></span> | <span data-ttu-id="8a63c-269">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-269">Available</span></span> |
| | <span data-ttu-id="8a63c-270">斜杠命令</span><span class="sxs-lookup"><span data-stu-id="8a63c-270">Slash commands</span></span> | <span data-ttu-id="8a63c-271">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-271">Available</span></span> |
| <span data-ttu-id="8a63c-272">符合</span><span class="sxs-lookup"><span data-stu-id="8a63c-272">Compliance</span></span> | <span data-ttu-id="8a63c-273">合规性内容搜索</span><span class="sxs-lookup"><span data-stu-id="8a63c-273">Compliance content search</span></span> | <span data-ttu-id="8a63c-274">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-274">Available</span></span> |
| | <span data-ttu-id="8a63c-275">保存</span><span class="sxs-lookup"><span data-stu-id="8a63c-275">Retention</span></span> | <span data-ttu-id="8a63c-276">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-276">Available</span></span> |
| | <span data-ttu-id="8a63c-277">审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="8a63c-277">Audit log search</span></span> | <span data-ttu-id="8a63c-278">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-278">Available</span></span> |
| | <span data-ttu-id="8a63c-279">法律封存</span><span class="sxs-lookup"><span data-stu-id="8a63c-279">Legal hold</span></span> | <span data-ttu-id="8a63c-280">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-280">Available</span></span> |
| | <span data-ttu-id="8a63c-281">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="8a63c-281">eDiscovery</span></span> | <span data-ttu-id="8a63c-282">在线</span><span class="sxs-lookup"><span data-stu-id="8a63c-282">Available</span></span> |

> [!Note]
> <span data-ttu-id="8a63c-283">当其他工作负荷在 GCC 云中完全可用时，它们将在所有其他集成工作完成后的团队中变为可用。</span><span class="sxs-lookup"><span data-stu-id="8a63c-283">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8a63c-285">决策点</span><span class="sxs-lookup"><span data-stu-id="8a63c-285">Decision point</span></span>|<ul><li><span data-ttu-id="8a63c-286">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-286">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="8a63c-287">第 5 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-287">Step 5.</span></span> <span data-ttu-id="8a63c-288">规划管理</span><span class="sxs-lookup"><span data-stu-id="8a63c-288">Plan for governance</span></span>

<span data-ttu-id="8a63c-289">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-289">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="8a63c-290">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="8a63c-290">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8a63c-292">决策点</span><span class="sxs-lookup"><span data-stu-id="8a63c-292">Decision point</span></span>|<ul><li><span data-ttu-id="8a63c-293">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="8a63c-293">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="8a63c-294">第 6 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-294">Step 6.</span></span> <span data-ttu-id="8a63c-295">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="8a63c-295">Deploy Teams for collaboration</span></span>

<span data-ttu-id="8a63c-296">在 onboarded 到 Microsoft 365 政府-GCC 后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="8a63c-296">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="8a63c-297">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="8a63c-297">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="8a63c-298">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="8a63c-298">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="8a63c-299">第 7 步</span><span class="sxs-lookup"><span data-stu-id="8a63c-299">Step 7.</span></span> <span data-ttu-id="8a63c-300">为会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="8a63c-300">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="8a63c-301">这也是将团队与更大的风险承担者组配合使用来开始计划推出会议和[云语音功能](cloud-voice-deployment.md)的一个好时机。</span><span class="sxs-lookup"><span data-stu-id="8a63c-301">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

