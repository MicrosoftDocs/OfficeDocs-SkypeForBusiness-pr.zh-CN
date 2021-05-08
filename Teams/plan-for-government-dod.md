---
title: Office 365 政府版 - DoD 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 指导 IT 专业人员推动Office 365受美国政府 DoD 法规限制的实体中的部署。
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
ms.openlocfilehash: dd649507c0108e9a3d500f4d30cae46a3181d75d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117850"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="aaa2f-103">规划Office 365 政府版 - DoD 部署</span><span class="sxs-lookup"><span data-stu-id="aaa2f-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="aaa2f-104">本指南适用于在美国政府实体或其他实体中驱动部署 Office 365 的 IT 专业人员，这些实体处理受政府法规和要求限制的数据，而使用 Office 365 政府版 - DoD 适合满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="aaa2f-105">如果你的组织已满足 Office 365 政府版 - DoD 资格要求，并且已申请并接受该计划，你可以跳过步骤 1 和 2 并直接转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="aaa2f-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="aaa2f-106">Step 1.</span></span> <span data-ttu-id="aaa2f-107">确定组织是否需要Office 365 政府版 - DoD 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="aaa2f-108">云Office 365 政府版 - DoD 环境符合美国政府对云服务的要求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="aaa2f-109">除了享受组织功能Office 365，组织还受益于 DoD 独有的Office 365 政府版功能：</span><span class="sxs-lookup"><span data-stu-id="aaa2f-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="aaa2f-110">组织的客户内容在逻辑上与 Microsoft 商业Office 365内容分开。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="aaa2f-111">组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="aaa2f-112">对组织的客户内容的访问仅限于已筛选的 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="aaa2f-113">Office 365 政府版 - DoD 符合美国公共服务部门客户所需的认证和认证。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="aaa2f-114">有关美国政府客户的 Office 365 政府版 - DoD 产品/服务Office 365 政府版[计划，包括](https://products.office.com/government/compare-office-365-government-plans)[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="aaa2f-115">本[Office 365美国政府服务](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)说明介绍了平台的好处，其中心内容是满足美国内部的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="aaa2f-116">你可能希望将服务说明中的信息表转移到 Excel 工作簿并添加两列：与我的组织 **Y/N** 相关和满足我的组织 **Y/N 的需求**。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="aaa2f-117">然后，可以与同事一起查看此列表，确认此服务满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="aaa2f-119">决策点</span><span class="sxs-lookup"><span data-stu-id="aaa2f-119">Decision points</span></span>|<ul><li><span data-ttu-id="aaa2f-120">确定Office 365 政府版 - DoD 是否适合组织。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="aaa2f-121">确认组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="aaa2f-122">Office 365 政府版 - DoD 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="aaa2f-123">非美国政府客户可以从多个计划[Office 365 政府版选择](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="aaa2f-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="aaa2f-124">Step 2.</span></span> <span data-ttu-id="aaa2f-125">申请Office 365 政府版 - DoD</span><span class="sxs-lookup"><span data-stu-id="aaa2f-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="aaa2f-126">确定此服务适合你的组织后，请开始 [申请此服务的过程](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="aaa2f-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="aaa2f-127">Step 3.</span></span> <span data-ttu-id="aaa2f-128">了解Office 365 政府版 - DoD 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="aaa2f-129">建议在修改管理员和安全设置之前仔细查看这些设置[](enable-features-office-365.md)，并考虑对合规性的影响，然后再对默认安全设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="aaa2f-131">决策点</span><span class="sxs-lookup"><span data-stu-id="aaa2f-131">Decision point</span></span>|<ul><li><span data-ttu-id="aaa2f-132">确定是否需要修改任何默认 Office 365 政府版 - DoD 安全设置，并首先了解可能进行的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="aaa2f-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="aaa2f-133">Step 4.</span></span> <span data-ttu-id="aaa2f-134">了解Teams DoD 中当前可用的Office 365 政府版功能</span><span class="sxs-lookup"><span data-stu-id="aaa2f-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="aaa2f-135">为了适应政府云客户的要求，Teams - DoD Office 365 政府版计划Teams云Enterprise差异。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="aaa2f-136">请参阅下表，了解哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="aaa2f-137">Microsoft Teams服务说明</span><span class="sxs-lookup"><span data-stu-id="aaa2f-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="aaa2f-138">第 5 步</span><span class="sxs-lookup"><span data-stu-id="aaa2f-138">Step 5.</span></span> <span data-ttu-id="aaa2f-139">规划治理</span><span class="sxs-lookup"><span data-stu-id="aaa2f-139">Plan for governance</span></span>

<span data-ttu-id="aaa2f-140">确定监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="aaa2f-141">有关详细信息[，请转到规划](plan-teams-governance.md)Teams治理。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="aaa2f-142">决策点</span><span class="sxs-lookup"><span data-stu-id="aaa2f-142">Decision point</span></span> |<ul><li><span data-ttu-id="aaa2f-143">按照在管理中规划治理中的准则，确定[并](plan-teams-governance.md)记录Teams。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="aaa2f-144">第 6 步</span><span class="sxs-lookup"><span data-stu-id="aaa2f-144">Step 6.</span></span> <span data-ttu-id="aaa2f-145">部署Teams进行协作</span><span class="sxs-lookup"><span data-stu-id="aaa2f-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="aaa2f-146">载入到 Office 365 政府版 – DoD 后，请遵循如何推出 Microsoft Teams 中概述[的建议部署Microsoft Teams。](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="aaa2f-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="aaa2f-147">请务必与采用和更改管理团队和Teams合作。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="aaa2f-148">还可以与 [FastTrack 或](https://www.microsoft.com/fasttrack) 所选合作伙伴合作来载入服务。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="aaa2f-149">尚不Teams DOD 环境的 Mac 客户端。</span><span class="sxs-lookup"><span data-stu-id="aaa2f-149">The Mac Teams client for DOD environments is not yet supported.</span></span>