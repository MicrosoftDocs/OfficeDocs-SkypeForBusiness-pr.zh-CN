---
title: Microsoft 365 政府版规划 - GCC High 部署 - Microsoft Teams
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 面向 IT 专业人士的指南，用于驱动在处理受美国政府法规制约的数据的实体中的 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7be9916a1c51b7e98467d1e8c44a18dd6d227d35
ms.sourcegitcommit: 4e1647d19501b37860d9fc79370fa4347f76f85f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "43079414"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="b2f87-103">规划 Microsoft 365 政府-GCC 高部署</span><span class="sxs-lookup"><span data-stu-id="b2f87-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="b2f87-104">本指南适用于正在推动美国联邦政府实体或其他实体中的 Office 365 部署的 IT 专业人士在美国联邦政府实体或其他实体中使用 Microsoft 365 政府（GCC High）的适用于满足这些要求的用户。</span><span class="sxs-lookup"><span data-stu-id="b2f87-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="b2f87-105">如果您的组织已满足 Microsoft 365 政府– GCC 的高资格要求，并已接受并接受该计划，则可以跳过步骤1和2，然后直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="b2f87-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="b2f87-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="b2f87-106">Step 1.</span></span> <span data-ttu-id="b2f87-107">确定你的组织是否需要 Microsoft 365 政府-GCC 高并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="b2f87-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="b2f87-108">Microsoft 365 政府-GCC 高环境为云服务的美国政府要求提供合规性。</span><span class="sxs-lookup"><span data-stu-id="b2f87-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="b2f87-109">除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府所特有的以下功能-GCC 高：</span><span class="sxs-lookup"><span data-stu-id="b2f87-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="b2f87-110">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="b2f87-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="b2f87-111">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="b2f87-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="b2f87-112">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b2f87-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="b2f87-113">Microsoft 365 政府-GCC 高遵从认证和 accreditations 美国公共事业部门客户所需的认证和。</span><span class="sxs-lookup"><span data-stu-id="b2f87-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="b2f87-114">您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府版（适用于美国政府客户的 GCC）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2f87-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="b2f87-115">[Office 365 美国政府服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)介绍了平台的优势，这些优势在美国的满足合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="b2f87-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="b2f87-116">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="b2f87-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="b2f87-117">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b2f87-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b2f87-119">决策点</span><span class="sxs-lookup"><span data-stu-id="b2f87-119">Decision points</span></span>|<ul><li><span data-ttu-id="b2f87-120">确定 Microsoft 365 政府-GCC 高版是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="b2f87-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="b2f87-121">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="b2f87-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="b2f87-122">Microsoft 365 政府版-GCC 高仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="b2f87-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="b2f87-123">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="b2f87-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="b2f87-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="b2f87-124">Step 2.</span></span> <span data-ttu-id="b2f87-125">适用于 Microsoft 365 政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="b2f87-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="b2f87-126">如果确定此服务适合你的组织，请启动[应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="b2f87-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="b2f87-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="b2f87-127">Step 3.</span></span> <span data-ttu-id="b2f87-128">了解 Microsoft 365 政府版-GCC 高默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="b2f87-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="b2f87-129">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="b2f87-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b2f87-131">决策点</span><span class="sxs-lookup"><span data-stu-id="b2f87-131">Decision point</span></span>|<ul><li><span data-ttu-id="b2f87-132">确定你是否需要修改任何默认的 Microsoft 365 政府-GCC 高安全性设置，以便首先解决你可能所做的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="b2f87-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="b2f87-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="b2f87-133">Step 4.</span></span> <span data-ttu-id="b2f87-134">了解 Microsoft 365 政府中当前提供哪些团队功能-GCC 高</span><span class="sxs-lookup"><span data-stu-id="b2f87-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="b2f87-135">为了满足政府云客户的要求，Microsoft 365 政府中的团队与企业计划中的 Microsoft 政府-GCC 高和团队之间存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="b2f87-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="b2f87-136">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="b2f87-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="b2f87-137">Microsoft 团队服务说明</span><span class="sxs-lookup"><span data-stu-id="b2f87-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="b2f87-138">第 5 步</span><span class="sxs-lookup"><span data-stu-id="b2f87-138">Step 5.</span></span> <span data-ttu-id="b2f87-139">规划管理</span><span class="sxs-lookup"><span data-stu-id="b2f87-139">Plan for governance</span></span>

<span data-ttu-id="b2f87-140">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="b2f87-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="b2f87-141">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="b2f87-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="b2f87-142">决策点</span><span class="sxs-lookup"><span data-stu-id="b2f87-142">Decision point</span></span> |<ul><li><span data-ttu-id="b2f87-143">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="b2f87-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="b2f87-144">第 6 步</span><span class="sxs-lookup"><span data-stu-id="b2f87-144">Step 6.</span></span> <span data-ttu-id="b2f87-145">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="b2f87-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="b2f87-146">在 onboarded 到 Microsoft 365 政府（GCC 高版）后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="b2f87-146">After you've been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="b2f87-147">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="b2f87-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="b2f87-148">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="b2f87-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

