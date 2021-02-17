---
title: 医疗保健组织的模板
author: serdarsoysal
ms.author: serdars
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
description: 通过提供预定义的设置、频道和应用模板，将 Microsoft Teams 模板与 Microsoft Graph 一起快速轻松地创建团队。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260334"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="6845a-103">医疗保健组织的 Teams 模板入门</span><span class="sxs-lookup"><span data-stu-id="6845a-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="6845a-104">Microsoft Teams 模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="6845a-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6845a-105">对于医疗保健组织，模板可能特别强大，因为它们提供结构，让用户以如何有效地使用 Teams 为导向。</span><span class="sxs-lookup"><span data-stu-id="6845a-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="6845a-106">模板还允许管理员跨组织部署一致的团队。</span><span class="sxs-lookup"><span data-stu-id="6845a-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="6845a-107">如果你负责规划、部署和管理整个医疗保健组织的多个团队，本文适合你。</span><span class="sxs-lookup"><span data-stu-id="6845a-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="6845a-108">我们目前提供两个可用于各种情况的第一方医疗保健模板。</span><span class="sxs-lookup"><span data-stu-id="6845a-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="6845a-109">若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](../../get-started-with-teams-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="6845a-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="6845a-110">"狱警"模板</span><span class="sxs-lookup"><span data-stu-id="6845a-110">Ward template</span></span>

<span data-ttu-id="6845a-111">该示例模板适用于在室、Pod 或部门内进行的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="6845a-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="6845a-112">该模板可用于促进患者管理，以及医院运营需求。</span><span class="sxs-lookup"><span data-stu-id="6845a-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="6845a-113">例如，可在公告频道中发布管区公告，在人员配备中管理 *班次*。</span><span class="sxs-lookup"><span data-stu-id="6845a-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="6845a-114">如果你希望简化你的行动，则此模板适合你。</span><span class="sxs-lookup"><span data-stu-id="6845a-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="6845a-115">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="6845a-115">Base Template Type</span></span> |<span data-ttu-id="6845a-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6845a-116">baseTemplateId</span></span> |<span data-ttu-id="6845a-117">基线模板通道</span><span class="sxs-lookup"><span data-stu-id="6845a-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="6845a-118">医疗保健 - 医生</span><span class="sxs-lookup"><span data-stu-id="6845a-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="6845a-119">公告\*</span><span class="sxs-lookup"><span data-stu-id="6845a-119">Announcements\*</span></span> <br> <span data-ttu-id="6845a-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="6845a-120">Huddles\*</span></span> <br> <span data-ttu-id="6845a-121">舍入\*</span><span class="sxs-lookup"><span data-stu-id="6845a-121">Rounds\*</span></span> <br> <span data-ttu-id="6845a-122">人员配备\*</span><span class="sxs-lookup"><span data-stu-id="6845a-122">Staffing\*</span></span> <br> <span data-ttu-id="6845a-123">培训\*</span><span class="sxs-lookup"><span data-stu-id="6845a-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="6845a-124">\* 自动收藏</span><span class="sxs-lookup"><span data-stu-id="6845a-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="6845a-125">医院模板</span><span class="sxs-lookup"><span data-stu-id="6845a-125">Hospital template</span></span>

<span data-ttu-id="6845a-126">医院模板用于一个医院内多个患者、Pod 和部门之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="6845a-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="6845a-127">此模板包括多个操作频道，包括公告、监管和药物，但我们在下面也提供了一个脚本，该脚本使用各种附加的部门或以专业为中心的频道扩展模板，你可以根据你的喜好添加、删除或编辑这些频道。 </span><span class="sxs-lookup"><span data-stu-id="6845a-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="6845a-128">例如，如果你有一个眼部，但不需要用于 *Ophthalmology* 的通道，则脚本可以调整为包含一个内科通道并删除 *Ophthalmology* 通道。 </span><span class="sxs-lookup"><span data-stu-id="6845a-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="6845a-129">建议不要自动收藏这些特殊频道或医院模型频道，以避免通知饱和。</span><span class="sxs-lookup"><span data-stu-id="6845a-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="6845a-130">用户通常喜欢他们发现相关的任何频道。</span><span class="sxs-lookup"><span data-stu-id="6845a-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="6845a-131">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="6845a-131">Base Template Type</span></span> |<span data-ttu-id="6845a-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6845a-132">baseTemplateId</span></span> |<span data-ttu-id="6845a-133">基线模板通道</span><span class="sxs-lookup"><span data-stu-id="6845a-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="6845a-134">医疗保健 - 医院</span><span class="sxs-lookup"><span data-stu-id="6845a-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="6845a-135">公告\*</span><span class="sxs-lookup"><span data-stu-id="6845a-135">Announcements\*</span></span> <br> <span data-ttu-id="6845a-136">合规性\*</span><span class="sxs-lookup"><span data-stu-id="6845a-136">Compliance\*</span></span> <br> <span data-ttu-id="6845a-137">监管</span><span class="sxs-lookup"><span data-stu-id="6845a-137">Custodial</span></span> <br> <span data-ttu-id="6845a-138">人力资源</span><span class="sxs-lookup"><span data-stu-id="6845a-138">Human Resources</span></span> <br> <span data-ttu-id="6845a-139">药物</span><span class="sxs-lookup"><span data-stu-id="6845a-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="6845a-140">\* 自动收藏</span><span class="sxs-lookup"><span data-stu-id="6845a-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="6845a-141">如何使用第一方模板</span><span class="sxs-lookup"><span data-stu-id="6845a-141">How to use first-party templates</span></span>

<span data-ttu-id="6845a-142">若要使用这些模板，只需将请求正文中的"template@odata.bind"属性从"standard"更改为上面的 TemplateID。</span><span class="sxs-lookup"><span data-stu-id="6845a-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="6845a-143">若要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何 [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="6845a-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="6845a-144">模板中的频道将自动在"常规"选项卡下创建。</span><span class="sxs-lookup"><span data-stu-id="6845a-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="6845a-145">示例：医院模板扩展脚本</span><span class="sxs-lookup"><span data-stu-id="6845a-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="6845a-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="6845a-146">Related topics</span></span>

[<span data-ttu-id="6845a-147">开始使用 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="6845a-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="6845a-148">适用于医疗保健组织的 Teams 入门</span><span class="sxs-lookup"><span data-stu-id="6845a-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="6845a-149">在管理控制台中开始使用 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="6845a-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
