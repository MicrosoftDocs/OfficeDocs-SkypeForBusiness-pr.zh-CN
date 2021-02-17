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
# <a name="create-a-team-using-teams-healthcare-templates"></a>使用 Teams 医疗保健模板创建团队

Microsoft Teams 模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。

对于医疗保健组织，模板可能特别强大，因为它们提供结构，让用户以如何有效地使用 Teams 为导向。 模板还允许管理员跨组织部署一致的团队。 如果你负责规划、部署和管理整个医疗保健组织的多个团队，本文适合你。

选择使用 Teams 医疗保健模板创建团队的方法：

| 谁 | 使用方法： |
| ---- | --------- |
| 管理员和 IT 专业人员 | [使用 Teams 管理中心](#use-the-teams-templates-in-the-teams-admin-center) 基于医疗保健团队模板创建团队。|
| 开发人员和系统集成商 | [使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 基于医疗保健团队模板创建团队。 |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>使用 Teams 管理中心中的 Teams 模板

Microsoft Teams 管理员可以使用 Teams 管理中心通过 Teams 模板创建团队。 我们目前提供两个可用于各种情况的第一方医疗保健模板。 若要了解有关团队模板的一般信息，请参阅管理中心 [中的 Teams 模板入门](../../get-started-with-teams-templates-in-the-admin-console.md)。

### <a name="collaborate-on-patient-care"></a>协作处理患者护理

 简化医院、Pod 或部门中的医疗保健通信和协作。 该模板可用于促进医院患者管理和操作需求。

| 基本模板类型 |baseTemplateId| 此基本模板提供的属性 |
| ------------------ |---|----------------------------------------------------- |
| 协作处理患者护理 |`healthcareWard` | 频道：<ul><li>常规</li><li>公告</li><li>Huddles</li><li>舍入</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>Wiki</li><li>列表</li></ul>|
||||

### <a name="hospital"></a>医院

简化医院内多个医生、Pod 和部门之间的通信和协作。 此模板包含一组用于医院操作的基本通道，可以自行扩展以包括特殊功能（即即席）。

| 基本模板类型 |baseTemplateId | 此基本模板提供的属性 |
| ------------------|-- |----------------------------------------------------- |
|医院|`healthcareHospital`|频道： <ul><li>常规</li><li>公告</li><li>合规性</li><li>监管</li><li>人力资源</li><li>药物</li></ul> 应用： <ul><li>Wiki</li><li>列表 </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一同使用

开发人员可以使用 Microsoft Graph 通过 Teams 模板创建团队。 我们目前提供两个可用于各种情况的第一方医疗保健模板。 若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](../../get-started-with-teams-templates.md)。 有关 Teams 模板和 Microsoft Graph 的信息，请参阅 [Microsoft Teams API 概述](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) 和 [teamsTemplate 资源类型](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

### <a name="ward-template"></a>"狱警"模板

该示例模板适用于在室、Pod 或部门内进行的通信和协作。 该模板可用于促进患者管理，以及医院运营需求。 例如，可在公告频道中发布管区公告，在人员配备中管理 *班次*。 如果你希望简化你的行动，则此模板适合你。

|基本模板类型 |baseTemplateId |基线模板通道|
|:--- |:---|:---|
|医疗保健 - 医生 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 公告\* <br> Huddles\* <br> 舍入\* <br> 人员配备\* <br> 培训\* |
|     | |         |

\* 自动收藏

### <a name="hospital-template"></a>医院模板

医院模板用于一个医院内多个患者、Pod 和部门之间的通信和协作。 此模板包括多个操作频道，包括公告、监管和药物，但我们在下面也提供了一个脚本，该脚本使用各种附加的部门或以专业为中心的频道扩展模板，你可以根据你的喜好添加、删除或编辑这些频道。  例如，如果你有一个眼部，但不需要用于 *Ophthalmology* 的通道，则脚本可以调整为包含一个内科通道并删除 *Ophthalmology* 通道。  建议不要自动收藏这些特殊频道或医院模型频道，以避免通知饱和。 用户通常喜欢他们发现相关的任何频道。

|基本模板类型 |baseTemplateId |基线模板通道|
|:--- |:---|:---|
|医疗保健 - 医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 公告\* <br> 合规性\* <br> 监管 <br> 人力资源 <br> 药物 |
| | |  |

\* 自动收藏 

### <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

若要使用这些模板，只需将请求正文中的"template@odata.bind"属性从"standard"更改为上面的 TemplateID。  若要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何 [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 模板中的频道将自动在"常规"选项卡下创建。

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

### <a name="related-topics"></a>相关主题

[开始使用 Teams 模板](../../get-started-with-teams-templates.md)

[适用于医疗保健组织的 Teams 入门](teams-in-hc.md)
