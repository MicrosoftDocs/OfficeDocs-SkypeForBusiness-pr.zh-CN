---
title: 使用 Teams 医疗保健模板创建团队
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
description: 使用管理中心中的 Microsoft Teams 模板或 Microsoft Graph，通过提供预定义的设置、频道和应用模板，快速轻松地创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260304"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="a1a0b-103">使用 Teams 医疗保健模板创建团队</span><span class="sxs-lookup"><span data-stu-id="a1a0b-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="a1a0b-104">Microsoft Teams 模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a1a0b-105">对于医疗保健组织，模板可能特别强大，因为它们提供结构，让用户以如何有效地使用 Teams 为导向。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="a1a0b-106">模板还允许管理员跨组织部署一致的团队。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="a1a0b-107">如果你负责规划、部署和管理整个医疗保健组织的多个团队，本文适合你。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="a1a0b-108">选择使用 Teams 医疗保健模板创建团队的方法：</span><span class="sxs-lookup"><span data-stu-id="a1a0b-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="a1a0b-109">谁</span><span class="sxs-lookup"><span data-stu-id="a1a0b-109">Who</span></span> | <span data-ttu-id="a1a0b-110">使用方法：</span><span class="sxs-lookup"><span data-stu-id="a1a0b-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="a1a0b-111">管理员和 IT 专业人员</span><span class="sxs-lookup"><span data-stu-id="a1a0b-111">Admins and IT Professionals</span></span> | <span data-ttu-id="a1a0b-112">[使用 Teams 管理中心](#use-the-teams-templates-in-the-teams-admin-center) 基于医疗保健团队模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="a1a0b-113">开发人员和系统集成商</span><span class="sxs-lookup"><span data-stu-id="a1a0b-113">Developers and systems integrators</span></span> | <span data-ttu-id="a1a0b-114">[使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 基于医疗保健团队模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="a1a0b-115">使用 Teams 管理中心中的 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="a1a0b-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="a1a0b-116">Microsoft Teams 管理员可以使用 Teams 管理中心通过 Teams 模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="a1a0b-117">我们目前提供两个可用于各种情况的第一方医疗保健模板。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="a1a0b-118">若要了解有关团队模板的一般信息，请参阅管理中心 [中的 Teams 模板入门](../../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="a1a0b-119">协作处理患者护理</span><span class="sxs-lookup"><span data-stu-id="a1a0b-119">Collaborate on patient care</span></span>

 <span data-ttu-id="a1a0b-120">简化医院、Pod 或部门中的医疗保健通信和协作。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a1a0b-121">该模板可用于促进医院患者管理和操作需求。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="a1a0b-122">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="a1a0b-122">Base template type</span></span> |<span data-ttu-id="a1a0b-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a1a0b-123">baseTemplateId</span></span>| <span data-ttu-id="a1a0b-124">此基本模板提供的属性</span><span class="sxs-lookup"><span data-stu-id="a1a0b-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="a1a0b-125">协作处理患者护理</span><span class="sxs-lookup"><span data-stu-id="a1a0b-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="a1a0b-126">频道：</span><span class="sxs-lookup"><span data-stu-id="a1a0b-126">Channels:</span></span><ul><li><span data-ttu-id="a1a0b-127">常规</span><span class="sxs-lookup"><span data-stu-id="a1a0b-127">General</span></span></li><li><span data-ttu-id="a1a0b-128">公告</span><span class="sxs-lookup"><span data-stu-id="a1a0b-128">Announcements</span></span></li><li><span data-ttu-id="a1a0b-129">Huddles</span><span class="sxs-lookup"><span data-stu-id="a1a0b-129">Huddles</span></span></li><li><span data-ttu-id="a1a0b-130">舍入</span><span class="sxs-lookup"><span data-stu-id="a1a0b-130">Rounds</span></span></li><li><span data-ttu-id="a1a0b-131">人员配备</span><span class="sxs-lookup"><span data-stu-id="a1a0b-131">Staffing</span></span></li><li><span data-ttu-id="a1a0b-132">培训</span><span class="sxs-lookup"><span data-stu-id="a1a0b-132">Training</span></span></li></ul> <span data-ttu-id="a1a0b-133">应用：</span><span class="sxs-lookup"><span data-stu-id="a1a0b-133">Apps:</span></span> <ul><li><span data-ttu-id="a1a0b-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="a1a0b-134">Wiki</span></span></li><li><span data-ttu-id="a1a0b-135">列表</span><span class="sxs-lookup"><span data-stu-id="a1a0b-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="a1a0b-136">医院</span><span class="sxs-lookup"><span data-stu-id="a1a0b-136">Hospital</span></span>

<span data-ttu-id="a1a0b-137">简化医院内多个医生、Pod 和部门之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a1a0b-138">此模板包含一组用于医院操作的基本通道，可以自行扩展以包括特殊功能（即即席）。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="a1a0b-139">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="a1a0b-139">Base template type</span></span> |<span data-ttu-id="a1a0b-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a1a0b-140">baseTemplateId</span></span> | <span data-ttu-id="a1a0b-141">此基本模板提供的属性</span><span class="sxs-lookup"><span data-stu-id="a1a0b-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="a1a0b-142">医院</span><span class="sxs-lookup"><span data-stu-id="a1a0b-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="a1a0b-143">频道：</span><span class="sxs-lookup"><span data-stu-id="a1a0b-143">Channels:</span></span> <ul><li><span data-ttu-id="a1a0b-144">常规</span><span class="sxs-lookup"><span data-stu-id="a1a0b-144">General</span></span></li><li><span data-ttu-id="a1a0b-145">公告</span><span class="sxs-lookup"><span data-stu-id="a1a0b-145">Announcements</span></span></li><li><span data-ttu-id="a1a0b-146">合规性</span><span class="sxs-lookup"><span data-stu-id="a1a0b-146">Compliance</span></span></li><li><span data-ttu-id="a1a0b-147">监管</span><span class="sxs-lookup"><span data-stu-id="a1a0b-147">Custodial</span></span></li><li><span data-ttu-id="a1a0b-148">人力资源</span><span class="sxs-lookup"><span data-stu-id="a1a0b-148">Human resources</span></span></li><li><span data-ttu-id="a1a0b-149">药物</span><span class="sxs-lookup"><span data-stu-id="a1a0b-149">Pharmacy</span></span></li></ul> <span data-ttu-id="a1a0b-150">应用：</span><span class="sxs-lookup"><span data-stu-id="a1a0b-150">Apps:</span></span> <ul><li><span data-ttu-id="a1a0b-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="a1a0b-151">Wiki</span></span></li><li><span data-ttu-id="a1a0b-152">列表</span><span class="sxs-lookup"><span data-stu-id="a1a0b-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="a1a0b-153">将 Teams 模板与 Microsoft Graph 一同使用</span><span class="sxs-lookup"><span data-stu-id="a1a0b-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="a1a0b-154">开发人员可以使用 Microsoft Graph 通过 Teams 模板创建团队。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="a1a0b-155">我们目前提供两个可用于各种情况的第一方医疗保健模板。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="a1a0b-156">若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="a1a0b-157">有关 Teams 模板和 Microsoft Graph 的信息，请参阅 [Microsoft Teams API 概述](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) 和 [teamsTemplate 资源类型](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="a1a0b-158">"狱警"模板</span><span class="sxs-lookup"><span data-stu-id="a1a0b-158">Ward template</span></span>

<span data-ttu-id="a1a0b-159">该示例模板适用于在室、Pod 或部门内进行的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a1a0b-160">该模板可用于促进患者管理，以及医院运营需求。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="a1a0b-161">例如，可在公告频道中发布管区公告，在人员配备中管理 *班次*。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="a1a0b-162">如果你希望简化你的行动，则此模板适合你。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="a1a0b-163">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="a1a0b-163">Base Template Type</span></span> |<span data-ttu-id="a1a0b-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a1a0b-164">baseTemplateId</span></span> |<span data-ttu-id="a1a0b-165">基线模板通道</span><span class="sxs-lookup"><span data-stu-id="a1a0b-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="a1a0b-166">医疗保健 - 医生</span><span class="sxs-lookup"><span data-stu-id="a1a0b-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="a1a0b-167">公告\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-167">Announcements\*</span></span> <br> <span data-ttu-id="a1a0b-168">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-168">Huddles\*</span></span> <br> <span data-ttu-id="a1a0b-169">舍入\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-169">Rounds\*</span></span> <br> <span data-ttu-id="a1a0b-170">人员配备\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-170">Staffing\*</span></span> <br> <span data-ttu-id="a1a0b-171">培训\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="a1a0b-172">\* 自动收藏</span><span class="sxs-lookup"><span data-stu-id="a1a0b-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="a1a0b-173">医院模板</span><span class="sxs-lookup"><span data-stu-id="a1a0b-173">Hospital template</span></span>

<span data-ttu-id="a1a0b-174">医院模板用于一个医院内多个患者、Pod 和部门之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a1a0b-175">此模板包括多个操作频道，包括公告、监管和药物，但我们在下面也提供了一个脚本，该脚本使用各种附加的部门或以专业为中心的频道扩展模板，你可以根据你的喜好添加、删除或编辑这些频道。 </span><span class="sxs-lookup"><span data-stu-id="a1a0b-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="a1a0b-176">例如，如果你有一个眼部，但不需要用于 *Ophthalmology* 的通道，则脚本可以调整为包含一个内科通道并删除 *Ophthalmology* 通道。 </span><span class="sxs-lookup"><span data-stu-id="a1a0b-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="a1a0b-177">建议不要自动收藏这些特殊频道或医院模型频道，以避免通知饱和。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="a1a0b-178">用户通常喜欢他们发现相关的任何频道。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="a1a0b-179">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="a1a0b-179">Base Template Type</span></span> |<span data-ttu-id="a1a0b-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a1a0b-180">baseTemplateId</span></span> |<span data-ttu-id="a1a0b-181">基线模板通道</span><span class="sxs-lookup"><span data-stu-id="a1a0b-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="a1a0b-182">医疗保健 - 医院</span><span class="sxs-lookup"><span data-stu-id="a1a0b-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="a1a0b-183">公告\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-183">Announcements\*</span></span> <br> <span data-ttu-id="a1a0b-184">合规性\*</span><span class="sxs-lookup"><span data-stu-id="a1a0b-184">Compliance\*</span></span> <br> <span data-ttu-id="a1a0b-185">监管</span><span class="sxs-lookup"><span data-stu-id="a1a0b-185">Custodial</span></span> <br> <span data-ttu-id="a1a0b-186">人力资源</span><span class="sxs-lookup"><span data-stu-id="a1a0b-186">Human Resources</span></span> <br> <span data-ttu-id="a1a0b-187">药物</span><span class="sxs-lookup"><span data-stu-id="a1a0b-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="a1a0b-188">\* 自动收藏</span><span class="sxs-lookup"><span data-stu-id="a1a0b-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="a1a0b-189">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="a1a0b-189">How to use first-party templates</span></span>

<span data-ttu-id="a1a0b-190">若要使用这些模板，只需将请求正文中的"template@odata.bind"属性从"standard"更改为上面的 TemplateID。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="a1a0b-191">若要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何 [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="a1a0b-192">模板中的频道将自动在"常规"选项卡下创建。</span><span class="sxs-lookup"><span data-stu-id="a1a0b-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="a1a0b-193">示例：医院模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="a1a0b-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="a1a0b-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="a1a0b-194">Related topics</span></span>

[<span data-ttu-id="a1a0b-195">开始使用 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="a1a0b-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="a1a0b-196">适用于医疗保健组织的 Teams 入门</span><span class="sxs-lookup"><span data-stu-id="a1a0b-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
