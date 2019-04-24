---
title: 适用于医疗保健组织的 Teams 模板入门
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 适用于医疗保健组织的 Teams 模板入门
ms.openlocfilehash: 38b2067bc91a79ff2efa8bc20726ad14d793aa24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245879"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="5066c-103">适用于医疗保健组织的 Teams 模板入门</span><span class="sxs-lookup"><span data-stu-id="5066c-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="5066c-104">Microsoft 团队模板允许您快速和轻松创建团队提供的预定义的模板的设置、 通道和预安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5066c-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5066c-105">对于医疗保健机构模板可以是特别强大，因为它们提供用户成为方向如何最有效地利用团队使用的结构。</span><span class="sxs-lookup"><span data-stu-id="5066c-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="5066c-106">模板还允许管理员在整个组织中部署一致的团队。</span><span class="sxs-lookup"><span data-stu-id="5066c-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="5066c-107">本文适用于您，如果您是负责规划、 部署和管理组织医疗保健跨多个团队。</span><span class="sxs-lookup"><span data-stu-id="5066c-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="5066c-108">我们当前提供两个第一方医疗保健模板，您可以利用的很多情况。</span><span class="sxs-lookup"><span data-stu-id="5066c-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="5066c-109">若要了解有关工作组模板通常情况下，请参阅[入门工作组模板](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="5066c-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="5066c-110">行政区模板</span><span class="sxs-lookup"><span data-stu-id="5066c-110">Ward template</span></span>

<span data-ttu-id="5066c-111">行政区模板旨在的沟通和协作行政区、 盒或部门内。</span><span class="sxs-lookup"><span data-stu-id="5066c-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="5066c-112">模板可用于加快患者管理，以及行政区操作需求。</span><span class="sxs-lookup"><span data-stu-id="5066c-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="5066c-113">例如，可以在*通知*频道张贴行政区通知和引进可以管理*人员*中。</span><span class="sxs-lookup"><span data-stu-id="5066c-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="5066c-114">如果您希望优化行政区操作，此模板将为您。</span><span class="sxs-lookup"><span data-stu-id="5066c-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="5066c-115">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="5066c-115">Base Template Type</span></span> |<span data-ttu-id="5066c-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5066c-116">baseTemplateId</span></span> |<span data-ttu-id="5066c-117">比较基准模板通道</span><span class="sxs-lookup"><span data-stu-id="5066c-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5066c-118">医疗保健-行政区</span><span class="sxs-lookup"><span data-stu-id="5066c-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="5066c-119">通知\*</span><span class="sxs-lookup"><span data-stu-id="5066c-119">Announcements\*</span></span> <br> <span data-ttu-id="5066c-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="5066c-120">Huddles\*</span></span> <br> <span data-ttu-id="5066c-121">将舍入为\*</span><span class="sxs-lookup"><span data-stu-id="5066c-121">Rounds\*</span></span> <br> <span data-ttu-id="5066c-122">人员配备扁平化\*</span><span class="sxs-lookup"><span data-stu-id="5066c-122">Staffing\*</span></span> <br> <span data-ttu-id="5066c-123">培训\*</span><span class="sxs-lookup"><span data-stu-id="5066c-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="5066c-124">\*自动 favorited</span><span class="sxs-lookup"><span data-stu-id="5066c-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="5066c-125">医院模板</span><span class="sxs-lookup"><span data-stu-id="5066c-125">Hospital template</span></span>

<span data-ttu-id="5066c-126">医院模板旨在的沟通和多个病房、 盒和医院中的部门之间的协作。</span><span class="sxs-lookup"><span data-stu-id="5066c-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="5066c-127">包含此模板中的多个操作通道包括*通知*、 *Custodial*和*药房*，但我们还提供低于该值脚本扩展的模板，其中包含各种的其他部门或您可以添加、 删除，或编辑您的喜好的专业中心通道。</span><span class="sxs-lookup"><span data-stu-id="5066c-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="5066c-128">例如，如果您有了*内分泌科*科，但不需要*眼科*通道，然后脚本可以调整以包括*内分泌科*通道并删除*眼科*通道。</span><span class="sxs-lookup"><span data-stu-id="5066c-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="5066c-129">我们建议，这些专业或行政区建模通道不会自动-favorited 以避免通知饱和度。</span><span class="sxs-lookup"><span data-stu-id="5066c-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="5066c-130">用户通常最喜爱的任何通道他们发现相关。</span><span class="sxs-lookup"><span data-stu-id="5066c-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="5066c-131">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="5066c-131">Base Template Type</span></span> |<span data-ttu-id="5066c-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="5066c-132">baseTemplateId</span></span> |<span data-ttu-id="5066c-133">比较基准模板通道</span><span class="sxs-lookup"><span data-stu-id="5066c-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="5066c-134">医疗保健-医院</span><span class="sxs-lookup"><span data-stu-id="5066c-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="5066c-135">通知\*</span><span class="sxs-lookup"><span data-stu-id="5066c-135">Announcements\*</span></span> <br> <span data-ttu-id="5066c-136">合规性\*</span><span class="sxs-lookup"><span data-stu-id="5066c-136">Compliance\*</span></span> <br> <span data-ttu-id="5066c-137">监控</span><span class="sxs-lookup"><span data-stu-id="5066c-137">Custodial</span></span> <br> <span data-ttu-id="5066c-138">人力资源</span><span class="sxs-lookup"><span data-stu-id="5066c-138">Human Resources</span></span> <br> <span data-ttu-id="5066c-139">药房</span><span class="sxs-lookup"><span data-stu-id="5066c-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="5066c-140">\*自动 favorited</span><span class="sxs-lookup"><span data-stu-id="5066c-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="5066c-141">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="5066c-141">How to use first party templates</span></span>

<span data-ttu-id="5066c-142">若要使用这些模板，只需更改为上面 TemplateIDs 从标准在请求正文中的 template@odata.bind 属性。</span><span class="sxs-lookup"><span data-stu-id="5066c-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="5066c-143">有关如何部署工作组模板的详细信息，请参阅 Microsoft Graph[创建团队的文章](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="5066c-143">For more information on how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="5066c-144">在常规选项卡下，将自动创建模板中的通道。</span><span class="sxs-lookup"><span data-stu-id="5066c-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="5066c-145">示例： 医院模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="5066c-145">Example: Hospital template extension script</span></span>

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
              "displayName": "Women’s Health",
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

## <a name="related-topics"></a><span data-ttu-id="5066c-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="5066c-146">Related topics</span></span>

[<span data-ttu-id="5066c-147">开始使用 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="5066c-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="5066c-148">适用于医疗保健组织的 Teams 入门</span><span class="sxs-lookup"><span data-stu-id="5066c-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
