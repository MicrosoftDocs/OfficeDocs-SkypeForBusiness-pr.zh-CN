---
title: 部署 Microsoft 团队云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 05/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 下载站点启用设置方案规划您的团队推出和加速和优化用户应用，认知质量和满意度。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3e40009a76ef7c8f31d659d45de1e4acf0801ec
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "19695507"
---
# <a name="deploy-my-service"></a><span data-ttu-id="cca7a-103">部署我服务</span><span class="sxs-lookup"><span data-stu-id="cca7a-103">Deploy my service</span></span>

<span data-ttu-id="cca7a-104">本文概述了正确部署云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="cca7a-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="cca7a-105">按照部署云语音服务，您可以确保的说明性指导您成功帐户为满足所有要求并提供可重复的结果。</span><span class="sxs-lookup"><span data-stu-id="cca7a-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="cca7a-106">网站启用设置方案的 Microsoft 团队语音工作负荷</span><span class="sxs-lookup"><span data-stu-id="cca7a-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="cca7a-107">使用此设置方案来帮助贵组织成功地规划和执行网站的网站基于推出 Microsoft 团队语音功能。</span><span class="sxs-lookup"><span data-stu-id="cca7a-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="cca7a-108">此设置方案包括所有所需的活动，建议时间线和链接到有关每个活动的相应指南涵盖的端到端指导，帮助确保成功团队语音部署给定网站，侧重于重要的因素向用户。</span><span class="sxs-lookup"><span data-stu-id="cca7a-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="cca7a-109">通过完成此设置方案中的活动，您的组织可以：</span><span class="sxs-lookup"><span data-stu-id="cca7a-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="cca7a-110">有效地规划和安排团队推出。</span><span class="sxs-lookup"><span data-stu-id="cca7a-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="cca7a-111">加快和优化用户应用。</span><span class="sxs-lookup"><span data-stu-id="cca7a-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="cca7a-112">降低支持需求并提高用户满意度。</span><span class="sxs-lookup"><span data-stu-id="cca7a-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="cca7a-113">本文和相关设置方案不目的介绍每个技术的配置步骤所需的服务启用或提供拨号音到特定站点。</span><span class="sxs-lookup"><span data-stu-id="cca7a-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="cca7a-114">相反，它们重点关注活动和轻松地向板载用户推荐的任务，并使其开始使用通过快速地平滑过渡与高应用率，同时最小化的支持要求的团队语音工作负荷。</span><span class="sxs-lookup"><span data-stu-id="cca7a-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="cca7a-115">有关如何配置团队语音环境，最佳的技术指导信息，请参阅[配置团队语音工作负荷](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)，[配置团队中直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)，入职培训清单[团队的核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)，[网络团队](onboarding-checklist-configure-networking.md)，和[启用 Office 365](onboarding-checklist-enable-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cca7a-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="cca7a-116">设置方案重点领域</span><span class="sxs-lookup"><span data-stu-id="cca7a-116">Playbook focus areas</span></span>

<span data-ttu-id="cca7a-117">设置方案的重点是解决影响用户的角度看团队语音部署的因素。</span><span class="sxs-lookup"><span data-stu-id="cca7a-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="cca7a-118">活动和任务分为以下领域：</span><span class="sxs-lookup"><span data-stu-id="cca7a-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="cca7a-119">服务准备的验证</span><span class="sxs-lookup"><span data-stu-id="cca7a-119">Validation of service readiness</span></span>
    - <span data-ttu-id="cca7a-120">音频会议</span><span class="sxs-lookup"><span data-stu-id="cca7a-120">Audio Conferencing</span></span>
    - <span data-ttu-id="cca7a-121">通话套餐</span><span class="sxs-lookup"><span data-stu-id="cca7a-121">Calling Plans</span></span>
    - <span data-ttu-id="cca7a-122">直接路由</span><span class="sxs-lookup"><span data-stu-id="cca7a-122">Direct Routing</span></span>

-   <span data-ttu-id="cca7a-123">用户启用</span><span class="sxs-lookup"><span data-stu-id="cca7a-123">User enablement</span></span>

-   <span data-ttu-id="cca7a-124">端点</span><span class="sxs-lookup"><span data-stu-id="cca7a-124">Endpoints</span></span>

-   <span data-ttu-id="cca7a-125">使用率和质量</span><span class="sxs-lookup"><span data-stu-id="cca7a-125">Usage and quality</span></span>

-   <span data-ttu-id="cca7a-126">采用</span><span class="sxs-lookup"><span data-stu-id="cca7a-126">Adoption</span></span>

<span data-ttu-id="cca7a-127">[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="cca7a-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="cca7a-128">每个五个焦点区域是单独的工作表的工作簿中，每个部署任务和活动拖动到一个这些工作表被分组。</span><span class="sxs-lookup"><span data-stu-id="cca7a-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="cca7a-129">![设置方案的屏幕截图](media/deploy-my-service-image1.png "设置方案的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="cca7a-129">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="cca7a-130">您将在您的团队推出的范围内创建的每个站点设置方案的单独实例。</span><span class="sxs-lookup"><span data-stu-id="cca7a-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="cca7a-131">如何使用设置方案</span><span class="sxs-lookup"><span data-stu-id="cca7a-131">How to use the playbook</span></span>

<span data-ttu-id="cca7a-132">无论的大小和位置的复杂性，启用每个站点需要规划任务和活动足够早期 — 和最佳顺序执行这些 — 之前、 升级期间和实际服务推出之后。</span><span class="sxs-lookup"><span data-stu-id="cca7a-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="cca7a-133">我们建议您执行以下步骤，如您规划和执行自己迁移到 Microsoft 团队语音。</span><span class="sxs-lookup"><span data-stu-id="cca7a-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="cca7a-134">下载 Microsoft 团队语音[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="cca7a-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="cca7a-135">创建一份的每个站点设置方案。</span><span class="sxs-lookup"><span data-stu-id="cca7a-135">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="cca7a-136">在名为 **{SiteName 代码} 设置方案**工作表的选项卡上，与相关网站名称和/或站点代码替换 **{SiteName 代码}** 。</span><span class="sxs-lookup"><span data-stu-id="cca7a-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="cca7a-137">输入**网站名称、 站点代码**，和**计划启动日期**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cca7a-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="cca7a-138">这是关键步骤中，因为它调整设置方案中的每个活动的建议的峰值。</span><span class="sxs-lookup"><span data-stu-id="cca7a-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="cca7a-139">![网站名称为纽约站点代码 NY01 和 20-Mar 18 计划的启动日期示例](media/deploy-my-service-image2.png "网站名称为纽约站点代码 NY01 和 20-Mar 18 计划的启动日期示例")</span><span class="sxs-lookup"><span data-stu-id="cca7a-139">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="cca7a-140">查看每个活动和所需的操作，当您演练日程表更新状态。</span><span class="sxs-lookup"><span data-stu-id="cca7a-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="cca7a-141">状态表示图形，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cca7a-141">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="cca7a-142">![绿色复选标记](media/deploy-my-service-image3.png)**是、 或不适用 （绿色）：** 活动完成后，或不适用于此网站，并需要没有进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="cca7a-142">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="cca7a-143">![黄色感叹号](media/deploy-my-service-image4.png)**活动未完成尚未 （黄色）：** 该活动不起作用，已完成，必须更新为是或否按其计划。</span><span class="sxs-lookup"><span data-stu-id="cca7a-143">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="cca7a-144">![红色 X](media/deploy-my-service-image5.png) **没有 （红色）：** 活动无法完成由于问题，必须执行到项目状态会议。</span><span class="sxs-lookup"><span data-stu-id="cca7a-144">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="cca7a-145">状态成型内每个部分，并节标题格式之一的这些状态指示符。</span><span class="sxs-lookup"><span data-stu-id="cca7a-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="cca7a-146">**每周状态**也会自动更新。</span><span class="sxs-lookup"><span data-stu-id="cca7a-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="cca7a-147">![每周状态汇总中设置方案的屏幕截图](media/deploy-my-service-image6.png "每周状态汇总中设置方案的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="cca7a-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="cca7a-148">您具有的所有位置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="cca7a-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cca7a-149">某些步骤可能不是适用于所有位置和网站。</span><span class="sxs-lookup"><span data-stu-id="cca7a-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="cca7a-150">如果不与网站相关的特定活动，则必须选择**不适用于**此活动。</span><span class="sxs-lookup"><span data-stu-id="cca7a-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="cca7a-151">**不要删除**任何行中设置方案;如果这样做，状态汇总公式将不起作用。</span><span class="sxs-lookup"><span data-stu-id="cca7a-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="cca7a-152">请注意，可能会更多时间比您计划，如号码移植活动和采购活动。</span><span class="sxs-lookup"><span data-stu-id="cca7a-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="cca7a-153">这些活动可以对网站部署时间线产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="cca7a-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="cca7a-154">请务必查看和每周，更新活动列表和关联的日程表和他们出席[调控委员会会议](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)以确保利益干系人了解每个站点和任何可能偏离的部署计划的状态。</span><span class="sxs-lookup"><span data-stu-id="cca7a-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="cca7a-155">决策点</span><span class="sxs-lookup"><span data-stu-id="cca7a-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="cca7a-156">决定是否需要为您的部署网站启用设置方案。</span><span class="sxs-lookup"><span data-stu-id="cca7a-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="cca7a-157">决定谁将负责将部署每个网站自定义 Microsoft 团队网站启用设置方案。</span><span class="sxs-lookup"><span data-stu-id="cca7a-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="cca7a-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cca7a-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="cca7a-159">[下载站点启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="cca7a-159">[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true).</span></span></li><li><span data-ttu-id="cca7a-160">自定义网站启用设置方案为您的第一个网站。</span><span class="sxs-lookup"><span data-stu-id="cca7a-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="cca7a-161">根据需要为其他网站重复。</span><span class="sxs-lookup"><span data-stu-id="cca7a-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->