---
title: Office 365 政府-DoD 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 面向 IT 专业人士的指南，用于驱动在处理受美国政府 DoD 法规制约的数据的实体中的 Office 365 部署。
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
ms.openlocfilehash: 04b0833f453ffac96e9fe2c9cef1b0f2a0797ca2
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581253"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="f2b50-103">规划 Office 365 政府-DoD 部署</span><span class="sxs-lookup"><span data-stu-id="f2b50-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="f2b50-104">本指南适用于正在推动美国联邦政府实体或其他实体中的 Office 365 部署的 IT 专业人士，这些客户负责处理受政府管理法规和要求制约的数据，其中使用 Office 365 政府-DoD 适用于满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="f2b50-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b50-105">如果您的组织已满足 Office 365 政府-DoD 资格要求，并且已被接受并已接受，则可以跳过步骤1和2，然后直接转到步骤3。</span><span class="sxs-lookup"><span data-stu-id="f2b50-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="f2b50-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="f2b50-106">Step 1.</span></span> <span data-ttu-id="f2b50-107">确定你的组织是否需要 Office 365 政府-DoD 并满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="f2b50-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="f2b50-108">Office 365 政府-DoD 环境为云服务的美国政府要求提供合规性。</span><span class="sxs-lookup"><span data-stu-id="f2b50-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="f2b50-109">除了享受 Office 365 的功能和功能之外，组织还受益于 Office 365 政府特有的以下功能：</span><span class="sxs-lookup"><span data-stu-id="f2b50-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="f2b50-110">你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="f2b50-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="f2b50-111">您的组织的客户内容存储在美国。</span><span class="sxs-lookup"><span data-stu-id="f2b50-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="f2b50-112">对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。</span><span class="sxs-lookup"><span data-stu-id="f2b50-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="f2b50-113">Office 365 政府– DoD 遵循美国公共事业部门客户所需的认证和 accreditations。</span><span class="sxs-lookup"><span data-stu-id="f2b50-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="f2b50-114">您可以在[office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Office 365 政府– DoD 产品的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2b50-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="f2b50-115">[Office 365 美国政府服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)介绍了平台的优势，这些优势在美国的满足合规性要求的中心。</span><span class="sxs-lookup"><span data-stu-id="f2b50-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="f2b50-116">你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。</span><span class="sxs-lookup"><span data-stu-id="f2b50-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="f2b50-117">然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="f2b50-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f2b50-119">决策点</span><span class="sxs-lookup"><span data-stu-id="f2b50-119">Decision points</span></span>|<ul><li><span data-ttu-id="f2b50-120">确定 Office 365 政府-DoD 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="f2b50-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="f2b50-121">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="f2b50-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="f2b50-122">Office 365 政府-DoD 仅适用于美国。</span><span class="sxs-lookup"><span data-stu-id="f2b50-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="f2b50-123">非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f2b50-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="f2b50-124">第 2 步</span><span class="sxs-lookup"><span data-stu-id="f2b50-124">Step 2.</span></span> <span data-ttu-id="f2b50-125">适用于 Office 365 政府-DoD</span><span class="sxs-lookup"><span data-stu-id="f2b50-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="f2b50-126">如果确定此服务适合你的组织，请启动[应用此服务](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="f2b50-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="f2b50-127">第 3 步</span><span class="sxs-lookup"><span data-stu-id="f2b50-127">Step 3.</span></span> <span data-ttu-id="f2b50-128">了解 Office 365 政府版-DoD 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="f2b50-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="f2b50-129">我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。</span><span class="sxs-lookup"><span data-stu-id="f2b50-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f2b50-131">决策点</span><span class="sxs-lookup"><span data-stu-id="f2b50-131">Decision point</span></span>|<ul><li><span data-ttu-id="f2b50-132">确定是否需要修改任何默认的 Office 365 政府-DoD 安全设置，解析以首先了解你可能所做的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="f2b50-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="f2b50-133">第 4 步</span><span class="sxs-lookup"><span data-stu-id="f2b50-133">Step 4.</span></span> <span data-ttu-id="f2b50-134">了解 Office 365 政府-DoD 中当前提供哪些团队功能</span><span class="sxs-lookup"><span data-stu-id="f2b50-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="f2b50-135">为了满足政府云客户的要求，Office 365 政府-DoD 和团队中的团队在企业计划中存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="f2b50-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="f2b50-136">请参考下表，查看哪些功能可用。</span><span class="sxs-lookup"><span data-stu-id="f2b50-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="f2b50-137">Microsoft 团队服务说明</span><span class="sxs-lookup"><span data-stu-id="f2b50-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="f2b50-138">第 5 步</span><span class="sxs-lookup"><span data-stu-id="f2b50-138">Step 5.</span></span> <span data-ttu-id="f2b50-139">规划管理</span><span class="sxs-lookup"><span data-stu-id="f2b50-139">Plan for governance</span></span>

<span data-ttu-id="f2b50-140">确定您的监管要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="f2b50-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="f2b50-141">有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="f2b50-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="f2b50-142">决策点</span><span class="sxs-lookup"><span data-stu-id="f2b50-142">Decision point</span></span> |<ul><li><span data-ttu-id="f2b50-143">按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</span><span class="sxs-lookup"><span data-stu-id="f2b50-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="f2b50-144">第 6 步</span><span class="sxs-lookup"><span data-stu-id="f2b50-144">Step 6.</span></span> <span data-ttu-id="f2b50-145">部署协作团队</span><span class="sxs-lookup"><span data-stu-id="f2b50-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="f2b50-146">在 onboarded 到 Office 365 政府-DoD 后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。</span><span class="sxs-lookup"><span data-stu-id="f2b50-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="f2b50-147">请确保与你的采纳和更改管理团队和团队拥护人员联系。</span><span class="sxs-lookup"><span data-stu-id="f2b50-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="f2b50-148">您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。</span><span class="sxs-lookup"><span data-stu-id="f2b50-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
