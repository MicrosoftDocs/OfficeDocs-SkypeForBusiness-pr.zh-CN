---
title: Office 365 政府版 - DoD 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 指导 IT 专业人员在处理受美国政府 DoD 法规限制的数据的实体中驱动 Office 365 部署。
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
ms.openlocfilehash: 954eb24cd0d6c79ab3fd30e22521660d2afeb08e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909156"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="031db-103">规划 Office 365 政府版 - DoD 部署</span><span class="sxs-lookup"><span data-stu-id="031db-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="031db-104">本指南适用于在美国政府实体或其他实体中驱动部署 Office 365 的 IT 专业人员，这些实体处理受政府法规和要求限制的数据，在这种情况下，适合使用 Office 365 政府版 - DoD 来满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="031db-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="031db-105">如果您的组织已满足 Office 365 政府版 - DoD 资格要求，并且已申请并接受该计划，您可以跳过步骤 1 和 2，直接转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="031db-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="031db-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="031db-106">Step 1.</span></span> <span data-ttu-id="031db-107">确定组织是否需要 Office 365 政府版 - DoD 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="031db-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="031db-108">Office 365 政府版 - DoD 环境符合美国政府对云服务的要求。</span><span class="sxs-lookup"><span data-stu-id="031db-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="031db-109">除了享受 Office 365 的功能外，组织还受益于 Office 365 政府版独有的以下功能 - DoD：</span><span class="sxs-lookup"><span data-stu-id="031db-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="031db-110">组织的客户内容在逻辑上与商业 Office 365 服务中的客户内容与 Microsoft 隔离。</span><span class="sxs-lookup"><span data-stu-id="031db-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="031db-111">组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="031db-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="031db-112">对组织的客户内容的访问仅限于已屏蔽的 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="031db-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="031db-113">Office 365 政府版 - DoD 符合美国公共服务客户所需的认证和认证。</span><span class="sxs-lookup"><span data-stu-id="031db-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="031db-114">可以在 Office 365 政府版计划中找到有关 Office [365](https://products.office.com/government/compare-office-365-government-plans)政府版 - 美国政府版 DoD 产品/服务（包括 [资格要求）的信息](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。</span><span class="sxs-lookup"><span data-stu-id="031db-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="031db-115">[Office 365 美国政府](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)版服务说明介绍了平台的好处，其中心内容是满足美国内部的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="031db-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="031db-116">您可能希望将服务说明中的信息表转移到 Excel 工作簿并添加两列：与组织 **Y/N** 相关，并且满足组织 **Y/N 的需求**。</span><span class="sxs-lookup"><span data-stu-id="031db-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="031db-117">然后，可以与同事一起查看此列表，确认此服务满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="031db-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="031db-119">决策点</span><span class="sxs-lookup"><span data-stu-id="031db-119">Decision points</span></span>|<ul><li><span data-ttu-id="031db-120">确定 Office 365 政府版 - DoD 是否适合你的组织。</span><span class="sxs-lookup"><span data-stu-id="031db-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="031db-121">确认组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="031db-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="031db-122">Office 365 政府版 - DoD 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="031db-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="031db-123">非美国政府版客户可以从多个 [Office 365 政府版计划中选择](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="031db-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="031db-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="031db-124">Step 2.</span></span> <span data-ttu-id="031db-125">申请 Office 365 政府版 - DoD</span><span class="sxs-lookup"><span data-stu-id="031db-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="031db-126">确定此服务适合你的组织后，请开始 [申请此服务的过程](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="031db-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="031db-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="031db-127">Step 3.</span></span> <span data-ttu-id="031db-128">了解 Office 365 政府版 - DoD 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="031db-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="031db-129">建议在修改管理员和安全设置之前，先仔细[](enable-features-office-365.md)查看这些设置，并考虑对合规性的影响，然后再对默认安全设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="031db-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="031db-131">决策点</span><span class="sxs-lookup"><span data-stu-id="031db-131">Decision point</span></span>|<ul><li><span data-ttu-id="031db-132">确定是否需要修改任何默认的 Office 365 政府版 - DoD 安全设置，首先了解可能进行的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="031db-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="031db-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="031db-133">Step 4.</span></span> <span data-ttu-id="031db-134">了解 Office 365 政府版中当前提供哪些 Teams 功能 - DoD</span><span class="sxs-lookup"><span data-stu-id="031db-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="031db-135">为了适应政府云客户的要求，Office 365 政府版中的 Teams - DoD 和企业版计划中的 Teams 之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="031db-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="031db-136">请参阅下表，了解哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="031db-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="031db-137">Microsoft Teams 服务说明</span><span class="sxs-lookup"><span data-stu-id="031db-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="031db-138">第 5 步</span><span class="sxs-lookup"><span data-stu-id="031db-138">Step 5.</span></span> <span data-ttu-id="031db-139">规划治理</span><span class="sxs-lookup"><span data-stu-id="031db-139">Plan for governance</span></span>

<span data-ttu-id="031db-140">确定治理要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="031db-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="031db-141">有关详细信息 [，请转到 Teams 中的"规划](plan-teams-governance.md) 治理"。</span><span class="sxs-lookup"><span data-stu-id="031db-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="031db-142">决策点</span><span class="sxs-lookup"><span data-stu-id="031db-142">Decision point</span></span> |<ul><li><span data-ttu-id="031db-143">按照 Teams 中治理规划中的准则，确定 [并记录治理要求](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="031db-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="031db-144">第 6 步</span><span class="sxs-lookup"><span data-stu-id="031db-144">Step 6.</span></span> <span data-ttu-id="031db-145">部署 Teams 进行协作</span><span class="sxs-lookup"><span data-stu-id="031db-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="031db-146">加入 Office 365 政府版 - DoD 后，请遵循"如何推出 [Microsoft Teams"中概述的建议部署路径](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="031db-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="031db-147">请务必与采用和更改管理团队以及 Teams 的得主互动。</span><span class="sxs-lookup"><span data-stu-id="031db-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="031db-148">还可以与 [FastTrack 或](https://www.microsoft.com/fasttrack) 所选的合作伙伴合作来载入服务。</span><span class="sxs-lookup"><span data-stu-id="031db-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="031db-149">尚不支持适用于 DOD 环境的 Mac Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="031db-149">The Mac Teams client for DOD environments is not yet supported.</span></span>
