---
title: 部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下载网站启用操作手册，规划Teams推广，并加速和优化用户采用、质量感知和满意度。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112628"
---
# <a name="deploy-my-service"></a><span data-ttu-id="77994-103">部署服务</span><span class="sxs-lookup"><span data-stu-id="77994-103">Deploy my service</span></span>

<span data-ttu-id="77994-104">本文概述了正确部署云语音服务的要求。</span><span class="sxs-lookup"><span data-stu-id="77994-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="77994-105">遵循部署云语音服务的规范性指南，确保成功满足所有要求并提供可重复的结果。</span><span class="sxs-lookup"><span data-stu-id="77994-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="77994-106">适用于语音工作负荷的站点Microsoft Teams playbook</span><span class="sxs-lookup"><span data-stu-id="77994-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="77994-107">使用此 playbook 可帮助组织成功地规划并执行Microsoft Teams基于站点推出语音功能。</span><span class="sxs-lookup"><span data-stu-id="77994-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="77994-108">包括所有必需活动、建议的时间线以及每个活动的相应指南的链接，此操作手册涵盖端到端指南，可帮助确保为给定网站成功部署 Teams 语音，并重点关注对用户重要的因素。</span><span class="sxs-lookup"><span data-stu-id="77994-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="77994-109">通过完成此操作手册中的活动，组织可以：</span><span class="sxs-lookup"><span data-stu-id="77994-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="77994-110">有效地计划和计划Teams部署。</span><span class="sxs-lookup"><span data-stu-id="77994-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="77994-111">加速和优化用户采用。</span><span class="sxs-lookup"><span data-stu-id="77994-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="77994-112">减少支持需求并增加用户满意度。</span><span class="sxs-lookup"><span data-stu-id="77994-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="77994-113">本文和关联的 Playbook 并非旨在描述启用服务或向特定站点提供拨号音所需的每个技术配置步骤。</span><span class="sxs-lookup"><span data-stu-id="77994-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="77994-114">相反，他们专注于为用户轻松加入而推荐的活动和任务，让他们通过快速流畅的采用率快速Teams使用语音工作负荷，同时尽量减少支持要求。</span><span class="sxs-lookup"><span data-stu-id="77994-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="77994-115">有关如何以最佳方式为 Teams 语音配置环境的技术指南，请参阅用于配置[Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)语音工作负荷、在[Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)中配置直接路由、Teams[核心](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)功能、Teams 网络以及启用 Microsoft 365 或[Office 365](onboarding-checklist-enable-office-365.md)的载入[](prepare-network.md)清单。</span><span class="sxs-lookup"><span data-stu-id="77994-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="77994-116">Playbook 重点区域</span><span class="sxs-lookup"><span data-stu-id="77994-116">Playbook focus areas</span></span>

<span data-ttu-id="77994-117">Playbook 的重点是解决影响用户对语音部署Teams的因素。</span><span class="sxs-lookup"><span data-stu-id="77994-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="77994-118">活动和任务分组到以下重点区域：</span><span class="sxs-lookup"><span data-stu-id="77994-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="77994-119">服务就绪性验证</span><span class="sxs-lookup"><span data-stu-id="77994-119">Validation of service readiness</span></span>
    - <span data-ttu-id="77994-120">音频会议</span><span class="sxs-lookup"><span data-stu-id="77994-120">Audio Conferencing</span></span>
    - <span data-ttu-id="77994-121">通话套餐</span><span class="sxs-lookup"><span data-stu-id="77994-121">Calling Plans</span></span>
    - <span data-ttu-id="77994-122">直接路由</span><span class="sxs-lookup"><span data-stu-id="77994-122">Direct Routing</span></span>

-   <span data-ttu-id="77994-123">用户启用</span><span class="sxs-lookup"><span data-stu-id="77994-123">User enablement</span></span>

-   <span data-ttu-id="77994-124">终结点</span><span class="sxs-lookup"><span data-stu-id="77994-124">Endpoints</span></span>

-   <span data-ttu-id="77994-125">使用情况和质量</span><span class="sxs-lookup"><span data-stu-id="77994-125">Usage and quality</span></span>

-   <span data-ttu-id="77994-126">采用</span><span class="sxs-lookup"><span data-stu-id="77994-126">Adoption</span></span>

<span data-ttu-id="77994-127">适用于[Voice (Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)网站启用 Playbook Microsoft Excel工作簿。</span><span class="sxs-lookup"><span data-stu-id="77994-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="77994-128">这五个重点区域都是工作簿中的一个单独的工作表，每个部署任务和活动都分组到其中一个工作表中。</span><span class="sxs-lookup"><span data-stu-id="77994-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="77994-129">![网站启用 playbook 的屏幕截图](media/deploy-my-service-image1.png "Playbook 的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="77994-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="77994-130">你将为实施计划范围内每个站点创建一个单独的 playbook Teams实例。</span><span class="sxs-lookup"><span data-stu-id="77994-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="77994-131">如何使用 playbook</span><span class="sxs-lookup"><span data-stu-id="77994-131">How to use the playbook</span></span>

<span data-ttu-id="77994-132">无论位置的大小和复杂程度如何，启用每个网站都需要你尽早规划任务和活动，并按最佳顺序执行它们-在推出实际服务之前、期间和之后。</span><span class="sxs-lookup"><span data-stu-id="77994-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="77994-133">建议在计划和执行自己的语音操作时执行Microsoft Teams步骤。</span><span class="sxs-lookup"><span data-stu-id="77994-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="77994-134">下载[适用于语音的"网站启用 Playbook" (Playbook) Microsoft Teams Playbook。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)</span><span class="sxs-lookup"><span data-stu-id="77994-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="77994-135">为每个网站创建一个单独的 playbook 副本。</span><span class="sxs-lookup"><span data-stu-id="77994-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="77994-136">在名为 **Playbook for {SiteName-Code}** 的工作表的选项卡上，将 **{SiteName-Code}** 替换为相关的网站名称和/或站点代码。</span><span class="sxs-lookup"><span data-stu-id="77994-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="77994-137">输入" **网站名称、站点代码**"和 **"计划启动日期**"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="77994-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="77994-138">这是一个关键步骤，因为它会调整操作手册中每个活动的建议期限。</span><span class="sxs-lookup"><span data-stu-id="77994-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="77994-139">![包含网站名称、站点代码和计划启动日期的示例](media/deploy-my-service-image2.png "网站名称为纽约、站点代码 NY01 和 3 月 20 日计划发布日期的示例")</span><span class="sxs-lookup"><span data-stu-id="77994-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="77994-140">查看每个活动，采取必要操作，并更新浏览时间线时的状态。</span><span class="sxs-lookup"><span data-stu-id="77994-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="77994-141">状态以图形方式表示，如下所述：</span><span class="sxs-lookup"><span data-stu-id="77994-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="77994-142">![绿色对号是或不适用于绿色 (的插图) ：活动已完成，或者不适用于此站点，无需进一步 ](media/deploy-my-service-image3.png) 操作。</span><span class="sxs-lookup"><span data-stu-id="77994-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="77994-143">![黄色感叹号插图 活动尚未完成 (黄色) ：活动尚未完成，必须按计划更新为"是"或"否 ](media/deploy-my-service-image4.png) <strong></strong>"。</span><span class="sxs-lookup"><span data-stu-id="77994-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="77994-144&quot;>![红色 X 的插图，指示没有 (") "：活动因问题而无法完成，必须携带到项目 ](media/deploy-my-service-image5.png) <strong></strong>状态会议。</span><span class="sxs-lookup"><span data-stu-id="77994-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="77994-145&quot;>状态在每个部分中汇总，分区标题的格式设置为这些状态指示器之一。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;77994-145&quot;>The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id=&quot;77994-146&quot;>**每周状态** 也会自动更新。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;77994-146&quot;>**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id=&quot;77994-147&quot;>![Playbook 中每周状态汇总的屏幕截图](media/deploy-my-service-image6.png &quot;Playbook 中每周状态汇总的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="77994-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="77994-148">针对你拥有的所有位置重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="77994-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77994-149">某些步骤可能不适用于所有位置和网站。</span><span class="sxs-lookup"><span data-stu-id="77994-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="77994-150">如果特定活动与网站不相关，则必须选择" **不适用于此** 活动"。</span><span class="sxs-lookup"><span data-stu-id="77994-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="77994-151">**不要删除** playbook 中的任何行;如果这样做，状态汇总公式将不起作用。</span><span class="sxs-lookup"><span data-stu-id="77994-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="77994-152">请注意可能需要比计划的时间更多的活动，例如数字移植和采购活动。</span><span class="sxs-lookup"><span data-stu-id="77994-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="77994-153">这些活动可能会对站点部署时间线产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="77994-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="77994-154">请务必每周查看和更新活动列表和相关日程表，并出席指导委员会会议，确保利益干系人[](./envision-steering-committee-complete-guide.md)了解每个网站的状态以及任何可能与部署计划偏差的情况。</span><span class="sxs-lookup"><span data-stu-id="77994-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="77994-155">决策点</span><span class="sxs-lookup"><span data-stu-id="77994-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="77994-156">确定是否需要站点启用 Playbook 进行部署。</span><span class="sxs-lookup"><span data-stu-id="77994-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="77994-157">确定谁将负责为要部署的每一个Microsoft Teams自定义网站启用 Playbook。</span><span class="sxs-lookup"><span data-stu-id="77994-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="77994-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="77994-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="77994-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下载网站启用 Playbook。</a></span><span class="sxs-lookup"><span data-stu-id="77994-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="77994-160">为第一个网站自定义网站启用 Playbook。</span><span class="sxs-lookup"><span data-stu-id="77994-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="77994-161">根据需要对其他网站重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="77994-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->