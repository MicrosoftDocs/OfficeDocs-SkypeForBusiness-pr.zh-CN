---
title: 规划 Microsoft 365 政府-GCC 部署的 Microsoft 团队
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 07/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: 面向 IT 专业人员为中处理数据受美国政府法规的实体的驱动器 Office 365 部署指南
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 430b6c6de5468442f7a290b07b28eb59d276e00c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885769"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="11ff0-103">Microsoft 365 政府版-GCC 部署规划</span><span class="sxs-lookup"><span data-stu-id="11ff0-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="11ff0-104">本指南为 IT 专业人员带来了美国联邦、 状态、 本地、 经验，或地域政府实体或其他处理受及政府法规要求约束的数据的实体中的 Office 365 部署其中使用 Microsoft365 政府-GCC 适合满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="11ff0-105">如果您的组织已满足 Microsoft 365 政府-GCC 资格要求和应用于并被接受到程序，您可以跳过步骤 1 到 4，直接转到步骤 5 以开始部署。</span><span class="sxs-lookup"><span data-stu-id="11ff0-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 through 4 and go directly to step 5 to begin your deployment.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="11ff0-106">步骤 1。</span><span class="sxs-lookup"><span data-stu-id="11ff0-106">Step 1.</span></span> <span data-ttu-id="11ff0-107">确定您的组织是否需要 Microsoft 365 政府-GCC，并且符合资格要求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="11ff0-108">Microsoft 365 政府-GCC 环境提供符合美国的云服务，包括 FedRAMP 适度和刑事审判和联邦税费信息系统 （CJI 和 FTI 数据类型） 要求的政府要求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="11ff0-109">除了享受的特性和功能的 Office 365，组织受益于对 Microsoft 365 政府-GCC 是唯一的以下功能：</span><span class="sxs-lookup"><span data-stu-id="11ff0-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="11ff0-110">贵组织的客户内容逻辑分离从 microsoft 商业的 Office 365 服务中的客户内容中。</span><span class="sxs-lookup"><span data-stu-id="11ff0-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="11ff0-111">美国境内存储贵组织的客户内容。</span><span class="sxs-lookup"><span data-stu-id="11ff0-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="11ff0-112">贵组织的客户内容的访问仅限于屏蔽 Microsoft 人员。</span><span class="sxs-lookup"><span data-stu-id="11ff0-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="11ff0-113">Microsoft 365 政府-GCC 遵守认证和资格鉴定所需的美国公共部门客户。</span><span class="sxs-lookup"><span data-stu-id="11ff0-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="11ff0-114">您可以找到有关 Microsoft 365 政府-GCC 提供在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)，包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)美国政府客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="11ff0-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="11ff0-115">[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍平台的优点，围绕会议美国境内的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="11ff0-116">您可能希望将服务说明中的信息的转移到 Excel 工作簿和添加两个列：**相关的我的组织是/否**和**满足 Y/N 我的组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="11ff0-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="11ff0-117">然后您可以查看此列表与同事以确认此服务满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="11ff0-118">决策点</span><span class="sxs-lookup"><span data-stu-id="11ff0-118">Decision points</span></span>|<ul><li><span data-ttu-id="11ff0-119">确定 Microsoft 365 政府-GCC 是否适合您的组织。</span><span class="sxs-lookup"><span data-stu-id="11ff0-119">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="11ff0-120">确认您的组织满足资格要求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-120">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="11ff0-121">下一步</span><span class="sxs-lookup"><span data-stu-id="11ff0-121">Next step</span></span>|<ul><li><span data-ttu-id="11ff0-122">了解由 Microsoft 365 政府-GCC 提供的功能。</span><span class="sxs-lookup"><span data-stu-id="11ff0-122">Understand the capabilities provided by Microsoft 365 Government - GCC.</span></span></li></ul>|

> [!Note]
> <span data-ttu-id="11ff0-123">Microsoft 365 政府-GCC 仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="11ff0-123">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="11ff0-124">非 – 美国政府客户可以选择从[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)数。</span><span class="sxs-lookup"><span data-stu-id="11ff0-124">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="11ff0-125">步骤 2。</span><span class="sxs-lookup"><span data-stu-id="11ff0-125">Step 2.</span></span> <span data-ttu-id="11ff0-126">了解哪些功能目前不可用或默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="11ff0-126">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="11ff0-127">若要容纳政府云客户的要求，有一些区别 Microsoft 365 政府-GCC，企业计划。</span><span class="sxs-lookup"><span data-stu-id="11ff0-127">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="11ff0-128">下表中列出的功能不可用。</span><span class="sxs-lookup"><span data-stu-id="11ff0-128">The features listed in the following table are unavailable.</span></span>

| <span data-ttu-id="11ff0-129">功能</span><span class="sxs-lookup"><span data-stu-id="11ff0-129">Feature</span></span>                     | <span data-ttu-id="11ff0-130">原因</span><span class="sxs-lookup"><span data-stu-id="11ff0-130">Reason</span></span>            |
|-----------------------------|-------------------|
| <span data-ttu-id="11ff0-131">呼叫和会议录音</span><span class="sxs-lookup"><span data-stu-id="11ff0-131">Call and Meeting Recording</span></span>  | <span data-ttu-id="11ff0-132">记录是依赖于在 Microsoft 流，将在将来美国政府计划中可用。</span><span class="sxs-lookup"><span data-stu-id="11ff0-132">Recording is dependent on Microsoft Stream, which will be available in US Government plans in the future.</span></span> |
| <span data-ttu-id="11ff0-133">应用</span><span class="sxs-lookup"><span data-stu-id="11ff0-133">Apps</span></span>       | <span data-ttu-id="11ff0-134">应用程序 （如自动程序、 选项卡，和连接器） 将不可用最初，但我们正在使其可为所有及其组件满足 FedRAMP 适度合规性栏。</span><span class="sxs-lookup"><span data-stu-id="11ff0-134">Apps (such as bots, tabs, and connectors) won’t be available initially, but we’re working to make them available as soon as all their components meet the FedRAMP Moderate compliance bar.</span></span> |
| <span data-ttu-id="11ff0-135">电子邮件通道</span><span class="sxs-lookup"><span data-stu-id="11ff0-135">Email a channel</span></span>             | <span data-ttu-id="11ff0-136">政府计划中不支持当前功能体系结构。</span><span class="sxs-lookup"><span data-stu-id="11ff0-136">The current feature architecture isn’t supported in government plans.</span></span> |
| <span data-ttu-id="11ff0-137">统一的状态</span><span class="sxs-lookup"><span data-stu-id="11ff0-137">Unified Presence</span></span>            | <span data-ttu-id="11ff0-138">我们为我们首先对此重要的功能的企业客户的完成工作。</span><span class="sxs-lookup"><span data-stu-id="11ff0-138">We’re finishing work for our enterprise customers first for this important feature.</span></span> <span data-ttu-id="11ff0-139">它将可供政府客户将来。</span><span class="sxs-lookup"><span data-stu-id="11ff0-139">It will be available to government customers in the future.</span></span> |
| <span data-ttu-id="11ff0-140">团队 & SfB 之间的互操作性聊天用户</span><span class="sxs-lookup"><span data-stu-id="11ff0-140">Interop chat between Teams & SfB users</span></span>            | <span data-ttu-id="11ff0-141">互操作所依赖上统一状态服务 (UPS)，但直到 GCC 团队租户启用 UPS 无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="11ff0-141">Interop is dependent on Unified Presence Service (UPS) and cannot work until GCC Teams Tenants are enabled for UPS.</span></span> |

<span data-ttu-id="11ff0-142">|发送电子邮件通知 |美国政府计划中不支持当前功能体系结构。</span><span class="sxs-lookup"><span data-stu-id="11ff0-142">| Email Notifications         | The current feature architecture isn’t supported in the US Government plans.</span></span> <span data-ttu-id="11ff0-143">若要使此功能可供美国政府计划客户将来正在进行工作。</span><span class="sxs-lookup"><span data-stu-id="11ff0-143">Work is ongoing to make this feature available to US Government plan customers in the future.</span></span> |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="11ff0-144">决策点</span><span class="sxs-lookup"><span data-stu-id="11ff0-144">Decision point</span></span>|<ul><li><span data-ttu-id="11ff0-145">确定 Microsoft 365 政府-GCC 功能集是否能满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-145">Decide whether the Microsoft 365 Government - GCC feature set meets your organization’s needs.</span></span></li></ul> |
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="11ff0-146">下一步</span><span class="sxs-lookup"><span data-stu-id="11ff0-146">Next step</span></span>|<ul><li><span data-ttu-id="11ff0-147">了解默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="11ff0-147">Understand default security settings.</span></span></li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="11ff0-148">步骤 3。</span><span class="sxs-lookup"><span data-stu-id="11ff0-148">Step 3.</span></span> <span data-ttu-id="11ff0-149">了解 Microsoft 365 政府-GCC 默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="11ff0-149">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="11ff0-150">我们建议您执行时间仔细检查您的[管理和安全设置](enable-features-office-365.md)，然后再对其进行修改和对默认安全设置进行任何更改之前，请考虑影响合规性。</span><span class="sxs-lookup"><span data-stu-id="11ff0-150">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="11ff0-151">决策点</span><span class="sxs-lookup"><span data-stu-id="11ff0-151">Decision point</span></span>|<ul><li><span data-ttu-id="11ff0-152">决定是否将修改任何默认 Microsoft 365 政府-GCC 安全设置，首先了解的任何更改影响的解决您可能会使。</span><span class="sxs-lookup"><span data-stu-id="11ff0-152">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impacts of any changes you might make.</span></span></li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="11ff0-153">步骤 4。</span><span class="sxs-lookup"><span data-stu-id="11ff0-153">Step 4.</span></span> <span data-ttu-id="11ff0-154">适用于 Microsoft 365 政府-GCC</span><span class="sxs-lookup"><span data-stu-id="11ff0-154">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="11ff0-155">无决定此服务适合您的组织，启动[此服务此处应用](https://products.office.com/government/eligibility-validation)的过程。</span><span class="sxs-lookup"><span data-stu-id="11ff0-155">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="11ff0-156">步骤 5。</span><span class="sxs-lookup"><span data-stu-id="11ff0-156">Step 5.</span></span> <span data-ttu-id="11ff0-157">规划调控</span><span class="sxs-lookup"><span data-stu-id="11ff0-157">Plan for governance</span></span>

<span data-ttu-id="11ff0-158">确定调控和如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="11ff0-158">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="11ff0-159">有关详细信息，请转到[团队中的治理规划](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="11ff0-159">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="11ff0-160">步骤 6。</span><span class="sxs-lookup"><span data-stu-id="11ff0-160">Step 6.</span></span> <span data-ttu-id="11ff0-161">部署团队协作</span><span class="sxs-lookup"><span data-stu-id="11ff0-161">Deploy Teams for collaboration</span></span>

<span data-ttu-id="11ff0-162">您已向 Microsoft 365 政府-GCC，onboarded 后，您可以按照使用[FastTrack](https://fasttrack.microsoft.com/fasttrack-faq)和您选择的合作伙伴，为板载到服务的标准的部署方法。</span><span class="sxs-lookup"><span data-stu-id="11ff0-162">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://fasttrack.microsoft.com/fasttrack-faq) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="11ff0-163">当您准备好时，到[启用通过团队和通道组织内的协作](teams-overview.md)部署团队。</span><span class="sxs-lookup"><span data-stu-id="11ff0-163">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="11ff0-164">请务必与您应用和变更管理团队或团队拥护者。</span><span class="sxs-lookup"><span data-stu-id="11ff0-164">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="11ff0-165">步骤 7。</span><span class="sxs-lookup"><span data-stu-id="11ff0-165">Step 7.</span></span> <span data-ttu-id="11ff0-166">会议和语音部署团队</span><span class="sxs-lookup"><span data-stu-id="11ff0-166">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="11ff0-167">这也是使用与您更多的利益干系人组团队启动规划推出会议和[云语音功能](cloud-voice-deployment.md)的绝佳时间。</span><span class="sxs-lookup"><span data-stu-id="11ff0-167">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

