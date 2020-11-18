---
title: Microsoft 365 政府版-GCC 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 面向 IT 专业人士的指南，用于在处理受美国政府法规制约的数据的实体中驱动 Microsoft 365 部署
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
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085606"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="7bb6d-103">规划 Microsoft 365 政府版-GCC 部署</span><span class="sxs-lookup"><span data-stu-id="7bb6d-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="7bb6d-104">本指南适用于在美国联邦、州、当地、tribal 或 territorial 政府实体或其他负责处理政府管理法规和要求的数据的其他实体（其中，Microsoft 365 政府-GCC 适用于满足这些要求的情况下）部署 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="7bb6d-105">2020年3月26日，：不要错过我们可下载 [的适用于 GCC 的快速入门指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bb6d-106">由于 coronavirus (COVID-19) pandemic，Microsoft 团队在网上通话和音频/视频会议方面遇到了巨大的高峰。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="7bb6d-107">为响应更空前的通话增加，并确保连续性和可用性，Microsoft 允许 Microsoft 团队拥有的音频/视频服务器利用我们的商业数据中心中的处理能力和我们的政府数据中心。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="7bb6d-108">这些音频/视频服务器驻留在 Microsoft Azure FedRAMP 中的 Microsoft Azure 高资格鉴定边界服务器，并且不存储任何客户内容。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="7bb6d-109">但是，这些服务器正在处理通话和会议的音频和视频，并在此期间内由我们的商业员工进行操作。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="7bb6d-110">经确认，被筛选的人员正在监视这些服务器，以便通过查看这些服务器的交互式登录项来对客户数据进行潜在访问。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="7bb6d-111">合格的人员在访问客户内容方面满足了 GCC 的要求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="7bb6d-112">有关筛选要求的详细信息，请参阅 [GCC 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="7bb6d-113">感谢您的支持，因为我们采取措施来确保我们的服务在这些特别时间内保持可用且可靠。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="7bb6d-114">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求，并已接受并接受该计划，则可以跳过步骤1和步骤2，直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="7bb6d-115">第 1 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-115">Step 1.</span></span> <span data-ttu-id="7bb6d-116">确定你的组织是否需要 Microsoft 365 政府-GCC 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="7bb6d-117">Microsoft 365 政府-GCC 环境为云服务（包括 FedRAMP 中等）和 CJI (和 FTI 数据) 类型的要求遵守美国政府要求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="7bb6d-118">除了享受 Microsoft 365 的功能和功能之外，组织还受益于 Microsoft 365 政府-GCC 所特有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="7bb6d-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="7bb6d-119">你的组织的客户内容从 Microsoft 的商业 Microsoft 365 服务中的客户内容被逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="7bb6d-120">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="7bb6d-121">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="7bb6d-122">Microsoft 365 政府版-GCC 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="7bb6d-123">有关 microsoft [365 政府版计划](https://products.office.com/government/compare-office-365-government-plans)（包括 [资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）的 microsoft 365 政府版的详细信息，请参阅我们的政府客户。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="7bb6d-124">[Microsoft 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍了平台的优势，这些优势在美国的会议合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-124">The [Microsoft 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="7bb6d-125">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列： **与我的组织进行相关** 并 **满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="7bb6d-126">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="7bb6d-128">决策点</span><span class="sxs-lookup"><span data-stu-id="7bb6d-128">Decision points</span></span>|<ul><li><span data-ttu-id="7bb6d-129">确定 Microsoft 365 政府版-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="7bb6d-130">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="7bb6d-131">Microsoft 365 政府版-GCC 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="7bb6d-132">非美国政府客户可以从许多 [Microsoft 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="7bb6d-133">第 2 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-133">Step 2.</span></span> <span data-ttu-id="7bb6d-134">适用于 Microsoft 365 政府版-GCC</span><span class="sxs-lookup"><span data-stu-id="7bb6d-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="7bb6d-135">如果确定此服务适合你的组织，请在 [此处开始应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="7bb6d-136">第 3 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-136">Step 3.</span></span> <span data-ttu-id="7bb6d-137">了解 Microsoft 365 政府版-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="7bb6d-138">我们建议你在修改你的管理员和安全设置之前认真检查你的 [管理员和安全设置](enable-features-office-365.md) ，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="7bb6d-140">决策点</span><span class="sxs-lookup"><span data-stu-id="7bb6d-140">Decision point</span></span>|<ul><li><span data-ttu-id="7bb6d-141">确定你是否要修改任何默认的 Microsoft 365 政府-GCC 安全设置，首先要了解你可能做出的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="7bb6d-142">第 4 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-142">Step 4.</span></span> <span data-ttu-id="7bb6d-143">了解默认情况下当前不可用或已禁用的功能。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="7bb6d-144">为了满足政府云客户的要求，Microsoft 365 政府版和企业版计划之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="7bb6d-145">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="7bb6d-146">Microsoft 团队服务说明</span><span class="sxs-lookup"><span data-stu-id="7bb6d-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="7bb6d-147">当其他工作负荷在 GCC 云中完全可用时，它们将在所有其他集成工作完成后的团队中变为可用。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="7bb6d-149">决策点</span><span class="sxs-lookup"><span data-stu-id="7bb6d-149">Decision point</span></span>|<ul><li><span data-ttu-id="7bb6d-150">确定团队功能集是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="7bb6d-151">第 5 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-151">Step 5.</span></span> <span data-ttu-id="7bb6d-152">规划管理</span><span class="sxs-lookup"><span data-stu-id="7bb6d-152">Plan for governance</span></span>

<span data-ttu-id="7bb6d-153">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="7bb6d-154">有关详细信息，请转到 [团队中的管理计划](plan-teams-governance.md) 。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="7bb6d-156">决策点</span><span class="sxs-lookup"><span data-stu-id="7bb6d-156">Decision point</span></span>|<ul><li><span data-ttu-id="7bb6d-157">按照 [规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="7bb6d-158">第 6 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-158">Step 6.</span></span> <span data-ttu-id="7bb6d-159">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="7bb6d-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="7bb6d-160">在 onboarded 到 Microsoft 365 政府-GCC 后，请按照 [如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="7bb6d-161">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="7bb6d-162">您还可以与 [FastTrack](https://www.microsoft.com/fasttrack) 或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="7bb6d-163">第 7 步</span><span class="sxs-lookup"><span data-stu-id="7bb6d-163">Step 7.</span></span> <span data-ttu-id="7bb6d-164">为会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="7bb6d-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="7bb6d-165">这也是将团队与更大的风险承担者组配合使用来开始计划推出会议和 [云语音功能](cloud-voice-deployment.md)的一个好时机。</span><span class="sxs-lookup"><span data-stu-id="7bb6d-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

