---
title: Microsoft 365 政府版 - GCC 高部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 指导 IT 专业人员在处理受美国政府法规限制的数据的实体中驱动 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5533b6d5c2e08cb79ec8dd2052d761d86546b05
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117840"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="d62c9-103">规划 Office 365 政府版 - GCC 高部署</span><span class="sxs-lookup"><span data-stu-id="d62c9-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="d62c9-104">本指南适用于推动 Office 365 在美国联邦政府实体或处理受政府法规和要求（使用 Office 365 政府版 - GCC High）满足这些要求的其他实体中的 Office 365 部署 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="d62c9-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="d62c9-105">如果您的组织已满足 Office 365 政府版 - GCC 高资格要求，并且已申请并接受该计划，您可以跳过步骤 1 和 2 并直接转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="d62c9-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="d62c9-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="d62c9-106">Step 1.</span></span> <span data-ttu-id="d62c9-107">确定组织是否需要 Office 365 政府版 - GCC High 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="d62c9-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="d62c9-108">Office 365 政府版 - GCC High 环境符合美国政府对云服务的要求。</span><span class="sxs-lookup"><span data-stu-id="d62c9-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="d62c9-109">除了享受 Office 365 的功能外，组织还受益于 Office 365 政府版独有的以下功能 – GCC High：</span><span class="sxs-lookup"><span data-stu-id="d62c9-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="d62c9-110">组织的客户内容在逻辑上与 Microsoft 商业版 Office 365 服务中的客户内容分开。</span><span class="sxs-lookup"><span data-stu-id="d62c9-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="d62c9-111">组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="d62c9-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="d62c9-112">对组织的客户内容的访问仅限于已筛选的 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="d62c9-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="d62c9-113">Office 365 政府版 – GCC High 符合美国公共服务部门客户所需的认证和认证。</span><span class="sxs-lookup"><span data-stu-id="d62c9-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="d62c9-114">有关 Office 365 政府版 - GCC High 产品/服务（适用于美国政府客户）在 [Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)版计划（包括 [资格要求）中查找详细信息](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。</span><span class="sxs-lookup"><span data-stu-id="d62c9-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="d62c9-115">[Office 365 美国政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)版服务说明介绍了平台的好处，其中心内容是满足美国内部的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="d62c9-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="d62c9-116">您可能希望将服务说明中的信息表转移到 Excel 工作簿并添加两列：与我的组织 **Y/N** 相关和满足我的组织 **Y/N 的需求**。</span><span class="sxs-lookup"><span data-stu-id="d62c9-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="d62c9-117">然后，可以与同事一起查看此列表，确认此服务满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="d62c9-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d62c9-119">决策点</span><span class="sxs-lookup"><span data-stu-id="d62c9-119">Decision points</span></span>|<ul><li><span data-ttu-id="d62c9-120">确定 Office 365 政府版 - GCC High 是否适合组织。</span><span class="sxs-lookup"><span data-stu-id="d62c9-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="d62c9-121">确认组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="d62c9-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="d62c9-122">Office 365 政府版 - GCC High 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="d62c9-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="d62c9-123">非美国政府版客户可以从多个 [Office 365 政府版计划中选择](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="d62c9-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="d62c9-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="d62c9-124">Step 2.</span></span> <span data-ttu-id="d62c9-125">申请 Office 365 政府版 - GCC High</span><span class="sxs-lookup"><span data-stu-id="d62c9-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="d62c9-126">确定此服务适合你的组织后，请开始 [申请此服务的过程](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="d62c9-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="d62c9-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="d62c9-127">Step 3.</span></span> <span data-ttu-id="d62c9-128">了解 Office 365 政府版 - GCC 高默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="d62c9-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="d62c9-129">建议在修改管理员和安全设置之前仔细查看这些设置[](enable-features-office-365.md)，并考虑对合规性的影响，然后再对默认安全设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="d62c9-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d62c9-131">决策点</span><span class="sxs-lookup"><span data-stu-id="d62c9-131">Decision point</span></span>|<ul><li><span data-ttu-id="d62c9-132">确定是否需要修改任何默认的 Office 365 政府版 - GCC 高安全设置，并首先了解可能进行的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="d62c9-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="d62c9-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="d62c9-133">Step 4.</span></span> <span data-ttu-id="d62c9-134">了解 Office 365 政府版 - GCC High 中当前提供哪些 Teams 功能</span><span class="sxs-lookup"><span data-stu-id="d62c9-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="d62c9-135">为了适应政府云客户的要求，Office 365 政府版中的 Teams - GCC High 和企业版计划中的 Teams 之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="d62c9-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="d62c9-136">请参阅下表，了解哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="d62c9-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="d62c9-137">Microsoft Teams 服务说明</span><span class="sxs-lookup"><span data-stu-id="d62c9-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="d62c9-138">第 5 步</span><span class="sxs-lookup"><span data-stu-id="d62c9-138">Step 5.</span></span> <span data-ttu-id="d62c9-139">规划治理</span><span class="sxs-lookup"><span data-stu-id="d62c9-139">Plan for governance</span></span>

<span data-ttu-id="d62c9-140">确定监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="d62c9-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="d62c9-141">有关详细信息 [，请转到规划 Teams](plan-teams-governance.md) 中的治理。</span><span class="sxs-lookup"><span data-stu-id="d62c9-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="d62c9-142">决策点</span><span class="sxs-lookup"><span data-stu-id="d62c9-142">Decision point</span></span> |<ul><li><span data-ttu-id="d62c9-143">按照在 Teams 中规划治理中的准则，确定 [并记录治理要求](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="d62c9-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="d62c9-144">第 6 步</span><span class="sxs-lookup"><span data-stu-id="d62c9-144">Step 6.</span></span> <span data-ttu-id="d62c9-145">部署 Teams 进行协作</span><span class="sxs-lookup"><span data-stu-id="d62c9-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="d62c9-146">加入 Office 365 政府版 - GCC High 后，请按照如何推出 Microsoft Teams 中概述的建议 [部署路径操作](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d62c9-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="d62c9-147">请务必与采用和更改管理团队以及 Teams 冠军互动。</span><span class="sxs-lookup"><span data-stu-id="d62c9-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="d62c9-148">还可以与 [FastTrack 或](https://www.microsoft.com/fasttrack) 所选合作伙伴合作来载入服务。</span><span class="sxs-lookup"><span data-stu-id="d62c9-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="d62c9-149">尚不支持用于 GCCH 环境的 Mac Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="d62c9-149">The Mac Teams client for GCCH environments is not yet supported.</span></span>