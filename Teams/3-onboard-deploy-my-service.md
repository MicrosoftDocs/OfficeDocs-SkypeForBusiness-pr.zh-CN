---
title: 部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下载网站支持行动手册以规划团队推出并加速和优化用户的采纳、质量和满意度的理解。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17b73629aa874232a449605b45f97ea10e445204
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232283"
---
# <a name="deploy-my-service"></a><span data-ttu-id="3857d-103">部署服务</span><span class="sxs-lookup"><span data-stu-id="3857d-103">Deploy my service</span></span>

<span data-ttu-id="3857d-104">本文概述了正确部署云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="3857d-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="3857d-105">通过遵循部署云语音服务的说明性指南, 你可以确保成功地考虑所有要求并提供可重复的结果。</span><span class="sxs-lookup"><span data-stu-id="3857d-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="3857d-106">Microsoft 团队的网站支持行动手册语音工作负载</span><span class="sxs-lookup"><span data-stu-id="3857d-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="3857d-107">使用本行动手册可帮助你的组织在逐个网站的基础上成功地计划和执行 Microsoft 团队语音功能的推出。</span><span class="sxs-lookup"><span data-stu-id="3857d-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="3857d-108">包括所有所需的活动、推荐的时间线和指向每个活动的相应指南的链接, 此操作手册介绍了端到端指南以帮助确保成功的团队为特定网站进行语音部署, 重点关注重要因素给用户。</span><span class="sxs-lookup"><span data-stu-id="3857d-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="3857d-109">通过完成本操作手册中的活动, 你的组织可以:</span><span class="sxs-lookup"><span data-stu-id="3857d-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="3857d-110">有效地规划和安排团队推出。</span><span class="sxs-lookup"><span data-stu-id="3857d-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="3857d-111">加速和优化用户采纳。</span><span class="sxs-lookup"><span data-stu-id="3857d-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="3857d-112">减少支持需求并提高用户满意度。</span><span class="sxs-lookup"><span data-stu-id="3857d-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="3857d-113">本文和关联的操作手册不用于描述服务启用所需的每个技术配置步骤或向特定网站提供拨号音。</span><span class="sxs-lookup"><span data-stu-id="3857d-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="3857d-114">而是将重点放在最适合于板载用户的活动和任务, 并让他们通过快速平稳过渡来开始使用团队语音工作负载, 同时将支持需求降至最低。</span><span class="sxs-lookup"><span data-stu-id="3857d-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="3857d-115">有关如何最佳配置团队语音环境的技术指导, 请参阅用于[配置团队语音工作负载](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)的加入清单、[配置团队中的直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)、[团队核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)、[网络对于团队](onboarding-checklist-configure-networking.md)和[启用 Office 365](onboarding-checklist-enable-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="3857d-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="3857d-116">行动手册重点领域</span><span class="sxs-lookup"><span data-stu-id="3857d-116">Playbook focus areas</span></span>

<span data-ttu-id="3857d-117">行动手册的重点是解决影响用户对团队语音部署的认知的因素。</span><span class="sxs-lookup"><span data-stu-id="3857d-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="3857d-118">活动和任务分组到以下重点区域:</span><span class="sxs-lookup"><span data-stu-id="3857d-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="3857d-119">服务准备情况验证</span><span class="sxs-lookup"><span data-stu-id="3857d-119">Validation of service readiness</span></span>
    - <span data-ttu-id="3857d-120">音频会议</span><span class="sxs-lookup"><span data-stu-id="3857d-120">Audio Conferencing</span></span>
    - <span data-ttu-id="3857d-121">通话套餐</span><span class="sxs-lookup"><span data-stu-id="3857d-121">Calling Plans</span></span>
    - <span data-ttu-id="3857d-122">直接路由</span><span class="sxs-lookup"><span data-stu-id="3857d-122">Direct Routing</span></span>

-   <span data-ttu-id="3857d-123">用户启用</span><span class="sxs-lookup"><span data-stu-id="3857d-123">User enablement</span></span>

-   <span data-ttu-id="3857d-124">终结点</span><span class="sxs-lookup"><span data-stu-id="3857d-124">Endpoints</span></span>

-   <span data-ttu-id="3857d-125">使用情况和质量</span><span class="sxs-lookup"><span data-stu-id="3857d-125">Usage and quality</span></span>

-   <span data-ttu-id="3857d-126">采用</span><span class="sxs-lookup"><span data-stu-id="3857d-126">Adoption</span></span>

<span data-ttu-id="3857d-127">[适用于语音 (行动手册) 的网站支持行动手册](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="3857d-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="3857d-128">这五个焦点区域中的每一个都是工作簿中的单独工作表, 每个部署任务和活动都分组到其中一个工作表中。</span><span class="sxs-lookup"><span data-stu-id="3857d-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="3857d-129">![网站支持行动手册的屏幕截图](media/deploy-my-service-image1.png "行动手册的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="3857d-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="3857d-130">你将为团队推出的范围内的每个网站创建一个单独的 "行动手册" 实例。</span><span class="sxs-lookup"><span data-stu-id="3857d-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="3857d-131">如何使用行动手册</span><span class="sxs-lookup"><span data-stu-id="3857d-131">How to use the playbook</span></span>

<span data-ttu-id="3857d-132">无论位置的大小和复杂程度如何, 启用每个网站都需要尽早对任务和活动进行计划, 并在实际服务推出之前和之后以最佳顺序执行它们。</span><span class="sxs-lookup"><span data-stu-id="3857d-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="3857d-133">我们建议你在计划和执行你自己的 Microsoft 团队语音操作时, 按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="3857d-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="3857d-134">下载适用于 Microsoft 团队语音的[网站支持行动手册 (行动手册)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 。</span><span class="sxs-lookup"><span data-stu-id="3857d-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="3857d-135">为每个网站创建一个单独的行动手册副本。</span><span class="sxs-lookup"><span data-stu-id="3857d-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="3857d-136">在名为 "**行动手册: {Sitename 代码}**" 的工作表的选项卡上, 将 **{sitename 代码}** 替换为相关的站点名称和/或站点代码。</span><span class="sxs-lookup"><span data-stu-id="3857d-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="3857d-137">输入**网站名称、网站代码**和**计划启动日期**, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="3857d-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="3857d-138">这是一个关键步骤, 因为它可调整行动手册中每个活动的建议截止时间。</span><span class="sxs-lookup"><span data-stu-id="3857d-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="3857d-139">![包含网站名称、网站代码和计划启动日期的示例](media/deploy-my-service-image2.png "示例, 包含纽约的网站名、网站代码 NY01 和计划开始日期 20-3 月 18")日</span><span class="sxs-lookup"><span data-stu-id="3857d-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="3857d-140">检查每个活动, 执行必要的操作, 并在遍历日程表时更新状态。</span><span class="sxs-lookup"><span data-stu-id="3857d-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="3857d-141">状态以图形形式表示, 如下所述:</span><span class="sxs-lookup"><span data-stu-id="3857d-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="3857d-142">![绿色复选标记](media/deploy-my-service-image3.png)为 **"是" 或 "不适用" (绿色)** 的插图: 活动已完成, 或者不适用于此网站, 不需要执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="3857d-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="3857d-143">![](media/deploy-my-service-image4.png) <strong>活动尚未完成的黄色感叹号的插图 (黄色):</strong>该活动尚未完成, 并且必须在其计划中更新为 "是" 或 "否"。</span><span class="sxs-lookup"><span data-stu-id="3857d-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="3857d-144">![红色 X 表示 "不](media/deploy-my-service-image5.png) <strong>否" (红色)</strong>的插图: 由于存在问题, 无法完成活动, 并且必须携带给项目状态会议。</span><span class="sxs-lookup"><span data-stu-id="3857d-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="3857d-145">状态将在每个分区内进行汇总, 分区标题将设置为这些状态标记之一。</span><span class="sxs-lookup"><span data-stu-id="3857d-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="3857d-146">**每周状态**也会自动更新。</span><span class="sxs-lookup"><span data-stu-id="3857d-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="3857d-147">![行动手册中的 "每周状态" 滚动屏幕截图](media/deploy-my-service-image6.png "行动手册中的 \"每周状态\" 滚动屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="3857d-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="3857d-148">对您拥有的所有位置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="3857d-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3857d-149">某些步骤可能不适用于所有位置和网站。</span><span class="sxs-lookup"><span data-stu-id="3857d-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="3857d-150">如果特定活动不与网站相关, 则必须选择 "**不适**用于此活动"。</span><span class="sxs-lookup"><span data-stu-id="3857d-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="3857d-151">**不要删除操作**手册中的任何行;如果执行此操作, 则状态汇总公式将不起作用。</span><span class="sxs-lookup"><span data-stu-id="3857d-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="3857d-152">注意可能花费比计划更多时间的活动, 例如号码移植和采购活动。</span><span class="sxs-lookup"><span data-stu-id="3857d-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="3857d-153">这些活动可能会对网站部署时间线产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="3857d-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="3857d-154">请务必查看和更新活动列表和关联的日程表每周, 并在[筹划指导委员会会议](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)中展示它们, 以确保利益干系人了解每个网站的状态以及部署计划的任何可能的偏差。</span><span class="sxs-lookup"><span data-stu-id="3857d-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="3857d-155">决策点</span><span class="sxs-lookup"><span data-stu-id="3857d-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="3857d-156">确定你的部署是否需要网站支持行动手册。</span><span class="sxs-lookup"><span data-stu-id="3857d-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="3857d-157">确定负责为您要部署的每个网站自定义 Microsoft 团队的网站支持行动手册的人员。</span><span class="sxs-lookup"><span data-stu-id="3857d-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="3857d-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3857d-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="3857d-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下载网站支持行动手册</a>。</span><span class="sxs-lookup"><span data-stu-id="3857d-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="3857d-160">为您的第一个网站自定义 "网站支持行动手册"。</span><span class="sxs-lookup"><span data-stu-id="3857d-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="3857d-161">根据需要重复其他网站的操作。</span><span class="sxs-lookup"><span data-stu-id="3857d-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->