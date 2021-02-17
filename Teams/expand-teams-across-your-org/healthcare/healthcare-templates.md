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
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>医疗保健组织的 Teams 模板入门

Microsoft Teams 模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。

对于医疗保健组织，模板可能特别强大，因为它们提供结构，让用户以如何有效地使用 Teams 为导向。 模板还允许管理员跨组织部署一致的团队。 如果你负责规划、部署和管理整个医疗保健组织的多个团队，本文适合你。

我们目前提供两个可用于各种情况的第一方医疗保健模板。 若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](../../get-started-with-teams-templates.md)。

## <a name="ward-template"></a>"狱警"模板

该示例模板适用于在室、Pod 或部门内进行的通信和协作。 该模板可用于促进患者管理，以及医院运营需求。 例如，可在公告频道中发布管区公告，在人员配备中管理 *班次*。 如果你希望简化你的行动，则此模板适合你。

|基本模板类型 |baseTemplateId |基线模板通道|
|:--- |:---|:---|
|医疗保健 - 医生 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 公告\* <br> Huddles\* <br> 舍入\* <br> 人员配备\* <br> 培训\* |
|     | |         |

\* 自动收藏

## <a name="hospital-template"></a>医院模板

医院模板用于一个医院内多个患者、Pod 和部门之间的通信和协作。 此模板包括多个操作频道，包括公告、监管和药物，但我们在下面也提供了一个脚本，该脚本使用各种附加的部门或以专业为中心的频道扩展模板，你可以根据你的喜好添加、删除或编辑这些频道。  例如，如果你有一个眼部，但不需要用于 *Ophthalmology* 的通道，则脚本可以调整为包含一个内科通道并删除 *Ophthalmology* 通道。  建议不要自动收藏这些特殊频道或医院模型频道，以避免通知饱和。 用户通常喜欢他们发现相关的任何频道。

|基本模板类型 |baseTemplateId |基线模板通道|
|:--- |:---|:---|
|医疗保健 - 医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 公告\* <br> 合规性\* <br> 监管 <br> 人力资源 <br> 药物 |
| | |  |

\* 自动收藏 

## <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

若要使用这些模板，只需将请求正文中的"template@odata.bind"属性从"standard"更改为上面的 TemplateID。  若要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何 [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 模板中的频道将自动在"常规"选项卡下创建。

### <a name="example-hospital-template-extension-script"></a>示例：医院模板扩展脚本

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

## <a name="related-topics"></a>相关主题

[开始使用 Teams 模板](../../get-started-with-teams-templates.md)

[适用于医疗保健组织的 Teams 入门](teams-in-hc.md)

[在管理控制台中开始使用 Teams 模板](../../get-started-with-teams-templates-in-the-admin-console.md)
