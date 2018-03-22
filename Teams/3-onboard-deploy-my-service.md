---
title: 部署 Microsoft 小组云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 下载站点支持行动手册计划团队推广和加快和优化获得用户的认可，质量和满意的感觉。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ddccd9c52e25ae9d0069119641aa7e8a8077d56
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="deploy-my-service"></a><span data-ttu-id="8b60e-103">部署服务</span><span class="sxs-lookup"><span data-stu-id="8b60e-103">Deploy my service</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="8b60e-104">网站支持 Microsoft 小组语音工作负载的操作手册</span><span class="sxs-lookup"><span data-stu-id="8b60e-104">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="8b60e-105">使用本行动手册帮助您成功地规划和执行 Microsoft 小组语音功能的推出在站点的站点的基础上的组织。</span><span class="sxs-lookup"><span data-stu-id="8b60e-105">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="8b60e-106">所有所需的活动，建议时间线，以及链接到相应的指南，对于每个活动，包括本操作手册介绍了端到端指南，可帮助确保成功团队语音部署为一个给定的站点，将重点放在很重要的因素给用户。</span><span class="sxs-lookup"><span data-stu-id="8b60e-106">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="8b60e-107">通过完成本操作手册中的活动，您的组织可以：</span><span class="sxs-lookup"><span data-stu-id="8b60e-107">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="8b60e-108">有效地计划和安排团队展示。</span><span class="sxs-lookup"><span data-stu-id="8b60e-108">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="8b60e-109">加快和优化获得用户的认可。</span><span class="sxs-lookup"><span data-stu-id="8b60e-109">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="8b60e-110">减少支持需求，提高用户满意度。</span><span class="sxs-lookup"><span data-stu-id="8b60e-110">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="8b60e-111">这篇文章和相关联的操作手册不打算介绍每个技术配置步骤所需的服务支持，或提供给特定站点的拨号音。</span><span class="sxs-lookup"><span data-stu-id="8b60e-111">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="8b60e-112">相反，他们关注的活动和任务到板载用户轻松地建议，并让它们开始消耗团队语音通过快速而顺利的过渡具有高的使用率，同时尽可能减少支持需求的工作负载。</span><span class="sxs-lookup"><span data-stu-id="8b60e-112">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="8b60e-113">有关如何最好地配置团队的声音环境的技术指导，请参阅启用 Office 365[配置团队语音工作负载](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)、[团队核心能力](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)、[网络的团队](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)，和[的服务清单](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span><span class="sxs-lookup"><span data-stu-id="8b60e-113">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [Teams core capabilities](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [networking for Teams](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking), and [enabling Office 365](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="8b60e-114">行动手册重点领域</span><span class="sxs-lookup"><span data-stu-id="8b60e-114">Playbook focus areas</span></span>

<span data-ttu-id="8b60e-115">操作手册的重点是解决影响团队语音部署用户的感知力的因素。</span><span class="sxs-lookup"><span data-stu-id="8b60e-115">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="8b60e-116">活动和任务分为以下重点领域：</span><span class="sxs-lookup"><span data-stu-id="8b60e-116">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="8b60e-117">验证的服务准备工作</span><span class="sxs-lookup"><span data-stu-id="8b60e-117">Validation of service readiness</span></span>

-   <span data-ttu-id="8b60e-118">用户支持</span><span class="sxs-lookup"><span data-stu-id="8b60e-118">User enablement</span></span>

-   <span data-ttu-id="8b60e-119">端点</span><span class="sxs-lookup"><span data-stu-id="8b60e-119">Endpoints</span></span>

-   <span data-ttu-id="8b60e-120">使用情况和质量</span><span class="sxs-lookup"><span data-stu-id="8b60e-120">Usage and quality</span></span>

-   <span data-ttu-id="8b60e-121">采用</span><span class="sxs-lookup"><span data-stu-id="8b60e-121">Adoption</span></span>

<span data-ttu-id="8b60e-122">[网站支持行动手册 （手册） 的声音](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="8b60e-122">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="8b60e-123">每个这些五个重点领域是在单独的工作表在工作簿中，并且每个部署任务和活动进行分组到一个这些表。</span><span class="sxs-lookup"><span data-stu-id="8b60e-123">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="8b60e-124">![操作手册的屏幕抓图](media/deploy-my-service-image1.png "操作手册的屏幕抓图")</span><span class="sxs-lookup"><span data-stu-id="8b60e-124">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="8b60e-125">团队展示的范围内，您将创建为每个站点操作手册的单独实例。</span><span class="sxs-lookup"><span data-stu-id="8b60e-125">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="8b60e-126">如何使用行动手册</span><span class="sxs-lookup"><span data-stu-id="8b60e-126">How to use the playbook</span></span>

<span data-ttu-id="8b60e-127">无论大小和位置的复杂性，使每个站点需要您计划您的任务和活动尽早 — — 和最佳顺序执行它们 — — 之前、 期间和之后的实际服务推出。</span><span class="sxs-lookup"><span data-stu-id="8b60e-127">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="8b60e-128">我们建议您执行这些步骤，为您规划和执行自己通往 Microsoft 小组的声音。</span><span class="sxs-lookup"><span data-stu-id="8b60e-128">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="8b60e-129">对于 Microsoft 小组语音下载[站点支持行动手册 （手册） 的声音](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="8b60e-129">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="8b60e-130">创建一份操作手册，为每个站点。</span><span class="sxs-lookup"><span data-stu-id="8b60e-130">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="8b60e-131">名为**{SiteName 代码} 的手册**的工作表选项卡上，相关的网站名称和/或站点代码替换**{SiteName 代码}** 。</span><span class="sxs-lookup"><span data-stu-id="8b60e-131">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="8b60e-132">输入**站点名称、 站点代码**，和**已计划的启动日期**，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8b60e-132">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="8b60e-133">这是一个关键的步骤，因为它调整为每个活动的行动手册中建议的最后期限。</span><span class="sxs-lookup"><span data-stu-id="8b60e-133">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="8b60e-134">![与纽约、 站点代码 NY01 和 20-3 月 3 日-18 日期计划的启动的站点名称的示例](media/deploy-my-service-image2.png "与纽约、 站点代码 NY01 和 20-3 月 3 日-18 日期计划的启动的站点名称的示例")</span><span class="sxs-lookup"><span data-stu-id="8b60e-134">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="8b60e-135">审查每个活动，采取必要的措施，如走进时间线更新的状态。</span><span class="sxs-lookup"><span data-stu-id="8b60e-135">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="8b60e-136">状态表示以图形方式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b60e-136">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="8b60e-137">![绿色复选标记](media/deploy-my-service-image3.png)**是或不适用 （绿色）：**活动已完成，或不适用于此站点上，并没有采取进一步的措施。</span><span class="sxs-lookup"><span data-stu-id="8b60e-137">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="8b60e-138">![黄色惊叹号](media/deploy-my-service-image4.png)**活动未完成，但 （黄色）：**活动尚未完成，并且必须更新为是或否在其日程上。</span><span class="sxs-lookup"><span data-stu-id="8b60e-138">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="8b60e-139">![红色 X](media/deploy-my-service-image5.png) **没有 （红色）：**活动无法完成，因为一个问题和必须对项目状态会议执行。</span><span class="sxs-lookup"><span data-stu-id="8b60e-139">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="8b60e-140">在每个部分中，成型状态和节标题设置了这些状态指示器之一是。</span><span class="sxs-lookup"><span data-stu-id="8b60e-140">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="8b60e-141">**每周的状态**也会自动更新。</span><span class="sxs-lookup"><span data-stu-id="8b60e-141">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="8b60e-142">![每周状态汇总操作手册中的屏幕快照](media/deploy-my-service-image6.png "每周状态汇总操作手册中的屏幕快照")</span><span class="sxs-lookup"><span data-stu-id="8b60e-142">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="8b60e-143">对于您拥有的所有位置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="8b60e-143">Repeat the steps above for all the locations you have.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8b60e-144">某些步骤可能不适用于所有位置和网站。</span><span class="sxs-lookup"><span data-stu-id="8b60e-144">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="8b60e-145">如果特定活动不相关的网站，您必须选择**不适用**此活动。</span><span class="sxs-lookup"><span data-stu-id="8b60e-145">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="8b60e-146">**不要删除**任何行操作手册;如果那样的话，状态汇总公式将不起作用。</span><span class="sxs-lookup"><span data-stu-id="8b60e-146">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="8b60e-147">请注意可能需要花费更多的时间比您计划，如数字移植的活动和采购活动。</span><span class="sxs-lookup"><span data-stu-id="8b60e-147">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="8b60e-148">这些活动可以对站点部署时间线产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="8b60e-148">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="8b60e-149">请务必检查和更新每周的活动列表和相关联的时间线和它们出席[指导委员会会议](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)，以确保利益相关者都知道每个网站和任何可能的部署计划偏离的状态。</span><span class="sxs-lookup"><span data-stu-id="8b60e-149">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8b60e-150">决策点</span><span class="sxs-lookup"><span data-stu-id="8b60e-150">Decision points</span></span></td><td><ul><li><span data-ttu-id="8b60e-151">决定是否需要为您的部署站点支持行动手册。</span><span class="sxs-lookup"><span data-stu-id="8b60e-151">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="8b60e-152">决定谁将负责对每个站点将部署自定义 Microsoft 小组站点启用手册。</span><span class="sxs-lookup"><span data-stu-id="8b60e-152">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you'll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="8b60e-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8b60e-153">Next steps</span></span></td><td><ul><li><span data-ttu-id="8b60e-154">下载站点支持行动手册。</span><span class="sxs-lookup"><span data-stu-id="8b60e-154">Download the Site Enablement Playbook.</span></span></li><li><span data-ttu-id="8b60e-155">自定义您的第一个站点的站点支持行动手册。</span><span class="sxs-lookup"><span data-stu-id="8b60e-155">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="8b60e-156">根据需要为其他站点重复。</span><span class="sxs-lookup"><span data-stu-id="8b60e-156">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->