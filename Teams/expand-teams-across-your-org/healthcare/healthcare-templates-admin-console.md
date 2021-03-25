---
title: 使用 Teams 医疗模板创建团队
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 通过提供预定义的设置、频道和应用模板，使用管理中心中的 Microsoft Teams 模板或借助 Microsoft Graph 快速轻松地创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117870"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="64d06-103">使用 Teams 医疗模板创建团队</span><span class="sxs-lookup"><span data-stu-id="64d06-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="64d06-104">通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="64d06-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="64d06-105">对于医疗保健组织，模板可能尤其强大，因为它们为用户提供结构，引导他们理解如何有效使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="64d06-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="64d06-106">通过模板，管理员还可在组织中部署一致的团队。</span><span class="sxs-lookup"><span data-stu-id="64d06-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="64d06-107">如果你负责在整个医疗组织中规划、部署和管理多个团队，则本文非常适合你。</span><span class="sxs-lookup"><span data-stu-id="64d06-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="64d06-108">选择使用 Teams 医疗模板创建团队的方法：</span><span class="sxs-lookup"><span data-stu-id="64d06-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="64d06-109">人员</span><span class="sxs-lookup"><span data-stu-id="64d06-109">Who</span></span> | <span data-ttu-id="64d06-110">使用方法：</span><span class="sxs-lookup"><span data-stu-id="64d06-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="64d06-111">管理员和 IT 专业人员</span><span class="sxs-lookup"><span data-stu-id="64d06-111">Admins and IT Professionals</span></span> | <span data-ttu-id="64d06-112">[使用 Teams 管理中心](#use-the-teams-templates-in-the-teams-admin-center) 基于医疗 Teams 模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="64d06-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="64d06-113">开发人员和系统整合者</span><span class="sxs-lookup"><span data-stu-id="64d06-113">Developers and systems integrators</span></span> | <span data-ttu-id="64d06-114">[使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 基于医疗 Taeams 模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="64d06-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="64d06-115">使用 Teams 管理中心中的 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="64d06-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="64d06-116">Microsoft Teams 管理员可以使用 Teams 管理中心使用 Teams 模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="64d06-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="64d06-117">我们目前提供两种第一方医疗模板，可用于多种情况。</span><span class="sxs-lookup"><span data-stu-id="64d06-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="64d06-118">要在总体上了解团队模板的详细信息，请参阅 [管理中心中的 Teams 模板入门](../../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="64d06-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="64d06-119">协作处理患者护理</span><span class="sxs-lookup"><span data-stu-id="64d06-119">Collaborate on patient care</span></span>

 <span data-ttu-id="64d06-120">简化病房、医疗站、或科室内的医疗沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="64d06-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="64d06-121">该模板可用于促进患者管理和帮助满足病房运营需求。</span><span class="sxs-lookup"><span data-stu-id="64d06-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="64d06-122">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="64d06-122">Base template type</span></span> |<span data-ttu-id="64d06-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="64d06-123">baseTemplateId</span></span>| <span data-ttu-id="64d06-124">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="64d06-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="64d06-125">协作处理患者护理</span><span class="sxs-lookup"><span data-stu-id="64d06-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="64d06-126">频道：</span><span class="sxs-lookup"><span data-stu-id="64d06-126">Channels:</span></span><ul><li><span data-ttu-id="64d06-127">常规</span><span class="sxs-lookup"><span data-stu-id="64d06-127">General</span></span></li><li><span data-ttu-id="64d06-128">公告</span><span class="sxs-lookup"><span data-stu-id="64d06-128">Announcements</span></span></li><li><span data-ttu-id="64d06-129">小型会议室</span><span class="sxs-lookup"><span data-stu-id="64d06-129">Huddles</span></span></li><li><span data-ttu-id="64d06-130">循环配置</span><span class="sxs-lookup"><span data-stu-id="64d06-130">Rounds</span></span></li><li><span data-ttu-id="64d06-131">人员配备</span><span class="sxs-lookup"><span data-stu-id="64d06-131">Staffing</span></span></li><li><span data-ttu-id="64d06-132">培训</span><span class="sxs-lookup"><span data-stu-id="64d06-132">Training</span></span></li></ul> <span data-ttu-id="64d06-133">应用：</span><span class="sxs-lookup"><span data-stu-id="64d06-133">Apps:</span></span> <ul><li><span data-ttu-id="64d06-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="64d06-134">Wiki</span></span></li><li><span data-ttu-id="64d06-135">列表</span><span class="sxs-lookup"><span data-stu-id="64d06-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="64d06-136">医院</span><span class="sxs-lookup"><span data-stu-id="64d06-136">Hospital</span></span>

<span data-ttu-id="64d06-137">简化医院内多个病房、医疗站和科室之间的沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="64d06-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="64d06-138">此模板包含一组用医院运营的基本渠道，并且可自行扩展以包含专科。</span><span class="sxs-lookup"><span data-stu-id="64d06-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="64d06-139">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="64d06-139">Base template type</span></span> |<span data-ttu-id="64d06-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="64d06-140">baseTemplateId</span></span> | <span data-ttu-id="64d06-141">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="64d06-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="64d06-142">医院</span><span class="sxs-lookup"><span data-stu-id="64d06-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="64d06-143">频道：</span><span class="sxs-lookup"><span data-stu-id="64d06-143">Channels:</span></span> <ul><li><span data-ttu-id="64d06-144">常规</span><span class="sxs-lookup"><span data-stu-id="64d06-144">General</span></span></li><li><span data-ttu-id="64d06-145">公告</span><span class="sxs-lookup"><span data-stu-id="64d06-145">Announcements</span></span></li><li><span data-ttu-id="64d06-146">合规性</span><span class="sxs-lookup"><span data-stu-id="64d06-146">Compliance</span></span></li><li><span data-ttu-id="64d06-147">保管</span><span class="sxs-lookup"><span data-stu-id="64d06-147">Custodial</span></span></li><li><span data-ttu-id="64d06-148">人力资源</span><span class="sxs-lookup"><span data-stu-id="64d06-148">Human resources</span></span></li><li><span data-ttu-id="64d06-149">药房</span><span class="sxs-lookup"><span data-stu-id="64d06-149">Pharmacy</span></span></li></ul> <span data-ttu-id="64d06-150">应用：</span><span class="sxs-lookup"><span data-stu-id="64d06-150">Apps:</span></span> <ul><li><span data-ttu-id="64d06-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="64d06-151">Wiki</span></span></li><li><span data-ttu-id="64d06-152">列表</span><span class="sxs-lookup"><span data-stu-id="64d06-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="64d06-153">将 Teams 模板与 Microsoft Graph 一起使用</span><span class="sxs-lookup"><span data-stu-id="64d06-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="64d06-154">开发人员可使用 Microsoft Graph 通过 Teams 模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="64d06-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="64d06-155">我们目前提供两种第一方医疗模板，可用于多种情况。</span><span class="sxs-lookup"><span data-stu-id="64d06-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="64d06-156">要总体上了解有关团队模板的详细信息，请参阅 [开始使用 Teams 模板](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="64d06-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="64d06-157">有关 Teams 模板和 Microsoft Graph 的信息，请参阅 [Microsoft Teams API 概述](/graph/teams-concept-overview?view=graph-rest-1.0) 和 [teamsTemplate 资源类型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="64d06-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="64d06-158">病房模板</span><span class="sxs-lookup"><span data-stu-id="64d06-158">Ward template</span></span>

<span data-ttu-id="64d06-159">病房模板用于病房、医疗站或科室之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="64d06-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="64d06-160">该模板可用于促进患者管理和帮助满足病房运营需求。</span><span class="sxs-lookup"><span data-stu-id="64d06-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="64d06-161">例如，可在“*公告*”频道中发布病房公告，并可在“*人员配备*”中管理排班。</span><span class="sxs-lookup"><span data-stu-id="64d06-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="64d06-162">如果你想要简化病房操作，则此模板适合你。</span><span class="sxs-lookup"><span data-stu-id="64d06-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="64d06-163">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="64d06-163">Base Template Type</span></span> |<span data-ttu-id="64d06-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="64d06-164">baseTemplateId</span></span> |<span data-ttu-id="64d06-165">基线模板频道</span><span class="sxs-lookup"><span data-stu-id="64d06-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="64d06-166">医疗 - 病房</span><span class="sxs-lookup"><span data-stu-id="64d06-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="64d06-167">公告 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-167">Announcements\*</span></span> <br> <span data-ttu-id="64d06-168">小型会议室 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-168">Huddles\*</span></span> <br> <span data-ttu-id="64d06-169">循环配置 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-169">Rounds\*</span></span> <br> <span data-ttu-id="64d06-170">人员配备 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-170">Staffing\*</span></span> <br> <span data-ttu-id="64d06-171">培训 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="64d06-172">\* 自动收藏</span><span class="sxs-lookup"><span data-stu-id="64d06-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="64d06-173">医院模板</span><span class="sxs-lookup"><span data-stu-id="64d06-173">Hospital template</span></span>

<span data-ttu-id="64d06-174">该医院模板用于医院内多个病房、医疗站和科室之间的沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="64d06-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="64d06-175">此模板包含若干操作频道，包括 *公告*、*保管* 和 *药房*，但我们还通过提供以下脚本扩展了模板，使其包含多个其他部门或以专科为中心的频道。你可以按个人喜好添加、删除或编辑这些频道。</span><span class="sxs-lookup"><span data-stu-id="64d06-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="64d06-176">例如，如果有一个 *内分泌* 科室，但不需要设置 *眼科* 频道，则可以调整该脚本以包括 *内分泌* 频道，并删除 *眼科* 频道。</span><span class="sxs-lookup"><span data-stu-id="64d06-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="64d06-177">我们建议不要自动收藏这些专科频道或模型以病区为模型的频道，以避免通知饱和。</span><span class="sxs-lookup"><span data-stu-id="64d06-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="64d06-178">用户通常会收藏他们发现相关的任何频道。</span><span class="sxs-lookup"><span data-stu-id="64d06-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="64d06-179">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="64d06-179">Base Template Type</span></span> |<span data-ttu-id="64d06-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="64d06-180">baseTemplateId</span></span> |<span data-ttu-id="64d06-181">基线模板频道</span><span class="sxs-lookup"><span data-stu-id="64d06-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="64d06-182">医疗 - 医院</span><span class="sxs-lookup"><span data-stu-id="64d06-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="64d06-183">公告 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-183">Announcements\*</span></span> <br> <span data-ttu-id="64d06-184">合规性 \*</span><span class="sxs-lookup"><span data-stu-id="64d06-184">Compliance\*</span></span> <br> <span data-ttu-id="64d06-185">保管</span><span class="sxs-lookup"><span data-stu-id="64d06-185">Custodial</span></span> <br> <span data-ttu-id="64d06-186">人力资源</span><span class="sxs-lookup"><span data-stu-id="64d06-186">Human Resources</span></span> <br> <span data-ttu-id="64d06-187">药房</span><span class="sxs-lookup"><span data-stu-id="64d06-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="64d06-188">\* 自动收藏</span><span class="sxs-lookup"><span data-stu-id="64d06-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="64d06-189">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="64d06-189">How to use first-party templates</span></span>

<span data-ttu-id="64d06-190">要使用这些模板，只需将请求正文中的“template@odata.bind”属性从“标准”更改为上述 TemplateID。</span><span class="sxs-lookup"><span data-stu-id="64d06-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="64d06-191">要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="64d06-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="64d06-192">模板中的频道将自动创建在“常规”选项卡下方。</span><span class="sxs-lookup"><span data-stu-id="64d06-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="64d06-193">示例：医院模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="64d06-193">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a><span data-ttu-id="64d06-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="64d06-194">Related topics</span></span>

[<span data-ttu-id="64d06-195">Teams 模板入门</span><span class="sxs-lookup"><span data-stu-id="64d06-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="64d06-196">适用于医疗组织的 Teams 入门</span><span class="sxs-lookup"><span data-stu-id="64d06-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)