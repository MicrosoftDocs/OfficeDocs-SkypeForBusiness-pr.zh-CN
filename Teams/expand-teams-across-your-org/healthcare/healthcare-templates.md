---
title: 医疗保健组织的模板
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 通过提供设置、频道和应用的预定义模板，将 Microsoft 团队模板与 Microsoft Graph 配合使用来快速轻松地创建团队。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 63376c68d8267aaa49b4bdf4033d5ebfaa0a446f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766695"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>面向医疗保健组织的团队模板入门

Microsoft 团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。

对于医疗保健组织而言，模板非常强大，因为它们为用户提供了有关如何有效使用团队的结构。 模板还允许管理员在其组织中部署一致的团队。 本文适用于你负责在整个医疗保健组织中规划、部署和管理多个团队的情况。

我们当前提供两个第一方医疗保健模板，可用于各种情况。 若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](../../get-started-with-teams-templates.md)。

## <a name="ward-template"></a>拖动模板

拖动模板适用于拖动、pod 或部门中的通信和协作。 该模板可用于促进患者管理，以及拖动的运行需要。 例如，可以在 *公告* 频道中发布拖动公告，并且可以在 *人员配备* 中管理班次。 如果你想要简化拖动操作，则此模板适用于你。

|基本模板类型 |baseTemplateId |基线模板通道|
|:--- |:---|:---|
|医疗保健-拖动 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 宣告\* <br> Huddles\* <br> 轮\* <br> 调配\* <br> 培训\* |
|     | |         |

\* 自动收藏

## <a name="hospital-template"></a>医院模板

医院模板旨在在医院中的多个 wards、箱和部门之间进行通信和协作。 此模板包含多个操作通道，包括 *公告* 、 *Custodial* 和 *药房* ，但我们还提供以下脚本，它将使用您可以添加到、删除或编辑的各种其他部门或以专业为中心的频道来扩展模板。 例如，如果您有一个 *Endocrinology* 部门，但不需要 *Ophthalmology* 的频道，则可以改编该脚本以包括 *Endocrinology* 频道和删除 *Ophthalmology* 频道。 我们建议，这些专业或拖动建模的通道不是自动收藏，以免出现通知饱和。 用户通常喜欢他们找到的任何频道。

|基本模板类型 |baseTemplateId |基线模板通道|
|:--- |:---|:---|
|医疗保健-医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 宣告\* <br> 合规性\* <br> Custodial <br> 人力资源 <br> 药房 |
| | |  |

\* 自动收藏 

## <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

若要使用这些模板，只需将请求正文中的 "template@odata bind" 属性从 "standard" 更改为上述 TemplateIDs。  有关如何部署团队模板的详细信息，请参阅 Microsoft Graph 有关如何 [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的文章。

> [!NOTE]
> 模板中的频道将在 "常规" 选项卡下自动创建。

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

[管理控制台中的团队模板入门](../../get-started-with-teams-templates-in-the-admin-console.md)
