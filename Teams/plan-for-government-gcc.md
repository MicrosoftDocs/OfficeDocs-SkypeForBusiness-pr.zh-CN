---
title: Microsoft 365 政府版 - GCC 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 有关 IT 专业人员在处理受美国政府法规限制的数据的实体中驱动 Microsoft 365 部署的指南
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117830"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="f719a-103">规划 Microsoft 365 政府版 - GCC 部署</span><span class="sxs-lookup"><span data-stu-id="f719a-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="f719a-104">本指南适用于在美国联邦、州、地方、部落或政府实体或处理受政府法规和要求（使用 Microsoft 365 政府版 - GCC）满足这些要求的其他实体中驱动 Microsoft 365 部署的 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="f719a-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="f719a-105">2020 年 3 月 26 日新版：不要错过 GCC 的可下载快速 [入门指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="f719a-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f719a-106">由于 COVID-19 和 COVID-19 的 (，Microsoft Teams 在线呼叫和音频/视频会议) 高峰。</span><span class="sxs-lookup"><span data-stu-id="f719a-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="f719a-107">为了应对呼叫的前所未有的增加，为了确保连续性和可用性，Microsoft 允许 Microsoft Teams GCC 音频/视频服务器在我们的商业数据中心以及政府数据中心利用处理能力。</span><span class="sxs-lookup"><span data-stu-id="f719a-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="f719a-108">这些音频/视频服务器驻留在美国的 Microsoft Azure FedRAMP 高认证边界服务器内，不存储任何客户内容。</span><span class="sxs-lookup"><span data-stu-id="f719a-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="f719a-109">但是，这些服务器正在处理呼叫和会议的音频和视频，并在此过渡期间在我们的商业人员下操作。</span><span class="sxs-lookup"><span data-stu-id="f719a-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="f719a-110">合格、经筛选的人员通过查看这些服务器的任何交互式登录来监视这些服务器，以可能访问客户数据。</span><span class="sxs-lookup"><span data-stu-id="f719a-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="f719a-111">合格人员符合访问客户内容的 GCC 要求。</span><span class="sxs-lookup"><span data-stu-id="f719a-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="f719a-112">有关筛选要求的详细信息，请参阅 [GCC 服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="f719a-112">For details about screening requirements, see the [GCC service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="f719a-113">感谢你的支持，因为我们采取一些措施来确保我们的服务在这些特殊时刻保持可用和可靠。</span><span class="sxs-lookup"><span data-stu-id="f719a-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="f719a-114">如果你的组织已满足 Microsoft 365 政府版 - GCC 资格要求，并且已申请并接受该计划，你可以跳过步骤 1 和 2 并直接转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="f719a-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="f719a-115">第 1 步</span><span class="sxs-lookup"><span data-stu-id="f719a-115">Step 1.</span></span> <span data-ttu-id="f719a-116">确定组织是否需要 Microsoft 365 政府版 - GCC 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="f719a-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="f719a-117">Microsoft 365 政府版 - GCC 环境符合美国政府对云服务（包括 FedRAMP 中等）的要求，以及适用于犯罪和联邦税务信息系统的要求 (CJI 和 FTI 数据类型) 。</span><span class="sxs-lookup"><span data-stu-id="f719a-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="f719a-118">除了享受 Microsoft 365 的功能外，组织还受益于 Microsoft 365 政府版 - GCC 独有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="f719a-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="f719a-119">组织的客户内容在逻辑上与 Microsoft 商业版 Microsoft 365 服务中的客户内容分开。</span><span class="sxs-lookup"><span data-stu-id="f719a-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="f719a-120">组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="f719a-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="f719a-121">对组织的客户内容的访问仅限于已筛选的 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="f719a-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="f719a-122">Microsoft 365 政府版 - GCC 符合美国公共服务部门客户所需的认证和认证。</span><span class="sxs-lookup"><span data-stu-id="f719a-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="f719a-123">有关 Microsoft 365 政府版 - GCC 产品/服务（适用于美国政府客户）的信息，请参阅 [Microsoft 365 政府版计划](https://products.office.com/government/compare-office-365-government-plans)， [包括资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。</span><span class="sxs-lookup"><span data-stu-id="f719a-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="f719a-124">[Microsoft 365 美国政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)版服务说明介绍了该平台的好处，其中心内容是满足美国内部的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="f719a-124">The [Microsoft 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="f719a-125">您可能希望将服务说明中的信息表转移到 Excel 工作簿并添加两列：与我的组织 **Y/N** 相关和满足我的组织 **Y/N 的需求**。</span><span class="sxs-lookup"><span data-stu-id="f719a-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="f719a-126">然后，可以与同事一起查看此列表，确认此服务满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="f719a-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f719a-128">决策点</span><span class="sxs-lookup"><span data-stu-id="f719a-128">Decision points</span></span>|<ul><li><span data-ttu-id="f719a-129">确定 Microsoft 365 政府版 - GCC 是否适合组织。</span><span class="sxs-lookup"><span data-stu-id="f719a-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="f719a-130">确认组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="f719a-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="f719a-131">Microsoft 365 政府版 - GCC 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="f719a-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="f719a-132">非美国政府版客户可以从许多 [Microsoft 365 政府版计划中选择](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="f719a-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="f719a-133">第 2 步</span><span class="sxs-lookup"><span data-stu-id="f719a-133">Step 2.</span></span> <span data-ttu-id="f719a-134">申请 Microsoft 365 政府版 - GCC</span><span class="sxs-lookup"><span data-stu-id="f719a-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="f719a-135">确定此服务适合你的组织后，请在此处 [开始申请此服务的过程](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="f719a-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="f719a-136">第 3 步</span><span class="sxs-lookup"><span data-stu-id="f719a-136">Step 3.</span></span> <span data-ttu-id="f719a-137">了解 Microsoft 365 政府版 - GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="f719a-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="f719a-138">建议在修改管理员和安全设置之前仔细查看这些设置[](enable-features-office-365.md)，并考虑对合规性的影响，然后再对默认安全设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="f719a-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f719a-140">决策点</span><span class="sxs-lookup"><span data-stu-id="f719a-140">Decision point</span></span>|<ul><li><span data-ttu-id="f719a-141">决定是否要修改任何默认的 Microsoft 365 政府版 - GCC 安全设置，以首先了解可能做出的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="f719a-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="f719a-142">第 4 步</span><span class="sxs-lookup"><span data-stu-id="f719a-142">Step 4.</span></span> <span data-ttu-id="f719a-143">了解默认情况下哪些功能当前不可用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="f719a-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="f719a-144">为了适应政府云客户的要求，Microsoft 365 政府版 - GCC 和企业版计划之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="f719a-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="f719a-145">请参阅下表，了解哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="f719a-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="f719a-146">Microsoft Teams 服务说明</span><span class="sxs-lookup"><span data-stu-id="f719a-146">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="f719a-147">其他工作负荷在 GCC 云中完全可用后，当所有其他集成工作完成时，这些工作负荷将在 Teams 中可用。</span><span class="sxs-lookup"><span data-stu-id="f719a-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f719a-149">决策点</span><span class="sxs-lookup"><span data-stu-id="f719a-149">Decision point</span></span>|<ul><li><span data-ttu-id="f719a-150">确定 Teams 功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="f719a-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="f719a-151">第 5 步</span><span class="sxs-lookup"><span data-stu-id="f719a-151">Step 5.</span></span> <span data-ttu-id="f719a-152">规划治理</span><span class="sxs-lookup"><span data-stu-id="f719a-152">Plan for governance</span></span>

<span data-ttu-id="f719a-153">确定监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="f719a-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="f719a-154">有关详细信息 [，请转到规划 Teams](plan-teams-governance.md) 中的治理。</span><span class="sxs-lookup"><span data-stu-id="f719a-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f719a-156">决策点</span><span class="sxs-lookup"><span data-stu-id="f719a-156">Decision point</span></span>|<ul><li><span data-ttu-id="f719a-157">按照在 Teams 中规划治理中的准则，确定 [并记录治理要求](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="f719a-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="f719a-158">第 6 步</span><span class="sxs-lookup"><span data-stu-id="f719a-158">Step 6.</span></span> <span data-ttu-id="f719a-159">部署 Teams 进行协作</span><span class="sxs-lookup"><span data-stu-id="f719a-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="f719a-160">加入 Microsoft 365 政府版 – GCC 后，请按照如何推出 Microsoft Teams 中概述的建议 [部署路径操作](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f719a-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="f719a-161">请务必与采用和更改管理团队以及 Teams 冠军互动。</span><span class="sxs-lookup"><span data-stu-id="f719a-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="f719a-162">还可以与 [FastTrack 或](https://www.microsoft.com/fasttrack) 所选合作伙伴合作来载入服务。</span><span class="sxs-lookup"><span data-stu-id="f719a-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="f719a-163">第 7 步</span><span class="sxs-lookup"><span data-stu-id="f719a-163">Step 7.</span></span> <span data-ttu-id="f719a-164">为会议和语音部署 Teams</span><span class="sxs-lookup"><span data-stu-id="f719a-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="f719a-165">这也是将 Teams 与更广泛的利益干系人组一起开始规划推出会议和云语音 [功能的一个不错时间](./cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="f719a-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](./cloud-voice-landing-page.md).</span></span>