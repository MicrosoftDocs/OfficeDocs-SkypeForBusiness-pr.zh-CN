---
title: 使用医疗保健团队模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: 了解如何管理和使用 Teams 管理中心和 Microsoft Graph 中的医疗保健团队模板，以快速轻松地为医疗保健组织创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778962"
---
# <a name="use-healthcare-team-templates"></a>使用医疗保健团队模板

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于医疗保健组织，团队模板可能特别强大，因为它们可帮助你在整个组织中快速部署一致的团队。 模板还可帮助员工了解如何有效地使用Teams。

Teams 包括专为医疗保健组织设计的模板。 使用这些预建模板快速创建团队，让员工就患者护理或操作需求进行沟通和协作。 在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。

如何管理和使用团队模板取决于你是管理人员还是开发人员。

|如果是： | 然后，可以： |
| ---- | --------- |
| 管理人员或 IT 专业人员 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 开发人员 | [使用 Microsoft Graph ](#use-team-templates-with-microsoft-graph) 从团队模板中创建团队。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

作为管理人员，你可以在 Microsoft Teams 管理中心内管理团队模板。 可在此处查看有关每个模板的详细信息。 还可以[创建模板策略](../../templates-policies.md)并将其分配给员工，以确定在 Teams 中使用哪些模板来[创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)。

若要了解有关团队模板的详细信息，请参阅[管理中心的 Teams 模板入门](../../get-started-with-teams-templates-in-the-admin-console.md)。

我们目前提供以下预构建的医疗保健团队模板。 若要查看，请在 Teams 管理中心的左侧导航栏中，转到 **Teams** > **团队模板**。

### <a name="patient-care"></a>患者护理

简化病房、医疗站、或科室内的医疗沟通和协作。 使用此模板可促进患者管理和病房的运营需求。 例如，在公告 *频道* 中发布病房通知，在 *人员配备* 频道中管理班次。

>[!div class="mx-tdBreakAll"]
>| 模板类型 |TemplateId| 此基本模板包含的属性 |
>| ------------------ |---|----------------------------------------------------- |
>| 患者护理 |`healthcareWard` | 频道：<ul><li>常规</li><li>公告</li><li>小型会议室</li><li>循环配置</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>审批</li><li>公告</li><li>检查</li><li>列表</li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|

### <a name="hospital"></a>医院

简化医院内多个病房、医疗站和科室之间的沟通和协作。 此模板包含一组用于医院运营的频道，并且可以扩展用于自定义。

>[!div class="mx-tdBreakAll"]
>| 模板类型 |TemplateId | 此基本模板包含的属性 |
>| ------------------|-- |----------------------------------------------------- |
>|医院|`healthcareHospital`|频道： <ul><li>常规</li><li>公告</li><li>合规性</li></li><li>保管</li><li>人力资源</li><li>药房</li></ul>  应用： <ul><li>审批</li><li>公告</li><li>员工想法</li><li>检查</li><li>列表</li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一起使用

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

下面是预建的医疗保健团队模板。

### <a name="patient-care"></a>患者护理

此模板用于病房、医疗站或科室之间的通信和协作。 使用此模板可促进患者管理和病房的运营需求。 例如，可在“*公告*”频道中发布病房公告，并可在“*人员配备*”中管理排班。 如果你想要简化病房操作，则此模板适合你。

>[!div class="mx-tdBreakAll"]
>|模板类型 |TemplateId |模板频道|
>|:--- |:---|:---|
>|医疗 - 病房 | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | 常规<br>公告&sup2; <br> 碰头会&sup2; <br> 层数&sup2; <br> 人员配备&sup2; <br> 训练&sup2; |

&sup2;自动收藏的频道

### <a name="hospital"></a>医院

该医院模板用于医院内多个病房、医疗站和科室之间的沟通和协作。 它包括多个运营渠道，例如 *公告*、 *保管* 和 *药房*。 我们还提供了一个脚本，可用于通过更多部门或专业频道扩展模板。 可以根据需求对它进行编辑。

例如，如果你有 *内分泌科* ，但不需要 *眼科* 通道，则可以调整脚本以包括 *内分泌学* 通道并删除 *眼科* 通道。 我们建议不要自动收藏这些专科频道或模型以病区为模型的频道，以避免通知饱和。 用户通常会收藏他们发现相关的任何频道。

>[!div class="mx-tdBreakAll"]
>|模板类型 |TemplateId |模板频道|
>|:--- |:---|:---|
>|医疗 - 医院 | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | 常规<br>公告&sup2; <br> 符合性&sup2; <br> 保管 <br> 人力资源 <br> 药房 |

&sup2;自动收藏的频道

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>如何将团队模板与 Microsoft Graph 配合使用

若要使用这些模板，请将请求正文中的“template@odata.bind”属性从“标准”更改为上面的 Templatelds。 若要详细了解如何部署团队模板，请参阅 Microsoft Graph 文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 模板中的频道将自动创建在 **“常规”** 选项卡下方。

#### <a name="example-hospital-template-extension-script"></a>示例：医院模板扩展脚本

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

### <a name="related-articles"></a>相关文章

- [基于模板创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [在管理中心内开始使用 Teams 模板](../../get-started-with-teams-templates-in-the-admin-console.md)
- [开始使用 Microsoft Graph 的团队模板](../../get-started-with-teams-templates.md)
- [适用于医疗保健组织的 Teams 入门](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)