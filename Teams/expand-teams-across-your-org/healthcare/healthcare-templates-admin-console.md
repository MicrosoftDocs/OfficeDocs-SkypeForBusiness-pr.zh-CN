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
# <a name="create-a-team-using-teams-healthcare-templates"></a>使用 Teams 医疗模板创建团队

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于医疗保健组织，模板可能尤其强大，因为它们为用户提供结构，引导他们理解如何有效使用 Teams。 通过模板，管理员还可在组织中部署一致的团队。 如果你负责在整个医疗组织中规划、部署和管理多个团队，则本文非常适合你。

选择使用 Teams 医疗模板创建团队的方法：

| 人员 | 使用方法： |
| ---- | --------- |
| 管理员和 IT 专业人员 | [使用 Teams 管理中心](#use-the-teams-templates-in-the-teams-admin-center) 基于医疗 Teams 模板创建团队。|
| 开发人员和系统整合者 | [使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 基于医疗 Taeams 模板创建团队。 |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>使用 Teams 管理中心中的 Teams 模板

Microsoft Teams 管理员可以使用 Teams 管理中心使用 Teams 模板创建团队。 我们目前提供两种第一方医疗模板，可用于多种情况。 要在总体上了解团队模板的详细信息，请参阅 [管理中心中的 Teams 模板入门](../../get-started-with-teams-templates-in-the-admin-console.md)。

### <a name="collaborate-on-patient-care"></a>协作处理患者护理

 简化病房、医疗站、或科室内的医疗沟通和协作。 该模板可用于促进患者管理和帮助满足病房运营需求。

| 基本模板类型 |baseTemplateId| 此基本模板包含的属性 |
| ------------------ |---|----------------------------------------------------- |
| 协作处理患者护理 |`healthcareWard` | 频道：<ul><li>常规</li><li>公告</li><li>小型会议室</li><li>循环配置</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>Wiki</li><li>列表</li></ul>|
||||

### <a name="hospital"></a>医院

简化医院内多个病房、医疗站和科室之间的沟通和协作。 此模板包含一组用医院运营的基本渠道，并且可自行扩展以包含专科。

| 基本模板类型 |baseTemplateId | 此基本模板包含的属性 |
| ------------------|-- |----------------------------------------------------- |
|医院|`healthcareHospital`|频道： <ul><li>常规</li><li>公告</li><li>合规性</li><li>保管</li><li>人力资源</li><li>药房</li></ul> 应用： <ul><li>Wiki</li><li>列表 </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一起使用

开发人员可使用 Microsoft Graph 通过 Teams 模板创建团队。 我们目前提供两种第一方医疗模板，可用于多种情况。 要总体上了解有关团队模板的详细信息，请参阅 [开始使用 Teams 模板](../../get-started-with-teams-templates.md)。 有关 Teams 模板和 Microsoft Graph 的信息，请参阅 [Microsoft Teams API 概述](/graph/teams-concept-overview?view=graph-rest-1.0) 和 [teamsTemplate 资源类型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

### <a name="ward-template"></a>病房模板

病房模板用于病房、医疗站或科室之间的通信和协作。 该模板可用于促进患者管理和帮助满足病房运营需求。 例如，可在“*公告*”频道中发布病房公告，并可在“*人员配备*”中管理排班。 如果你想要简化病房操作，则此模板适合你。

|基本模板类型 |baseTemplateId |基线模板频道|
|:--- |:---|:---|
|医疗 - 病房 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 公告 \* <br> 小型会议室 \* <br> 循环配置 \* <br> 人员配备 \* <br> 培训 \* |
|     | |         |

\* 自动收藏

### <a name="hospital-template"></a>医院模板

该医院模板用于医院内多个病房、医疗站和科室之间的沟通和协作。 此模板包含若干操作频道，包括 *公告*、*保管* 和 *药房*，但我们还通过提供以下脚本扩展了模板，使其包含多个其他部门或以专科为中心的频道。你可以按个人喜好添加、删除或编辑这些频道。 例如，如果有一个 *内分泌* 科室，但不需要设置 *眼科* 频道，则可以调整该脚本以包括 *内分泌* 频道，并删除 *眼科* 频道。 我们建议不要自动收藏这些专科频道或模型以病区为模型的频道，以避免通知饱和。 用户通常会收藏他们发现相关的任何频道。

|基本模板类型 |baseTemplateId |基线模板频道|
|:--- |:---|:---|
|医疗 - 医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 公告 \* <br> 合规性 \* <br> 保管 <br> 人力资源 <br> 药房 |
| | |  |

\* 自动收藏 

### <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

要使用这些模板，只需将请求正文中的“template@odata.bind”属性从“标准”更改为上述 TemplateID。  要详细了解如何部署 Teams 模板，请参阅 Microsoft Graph 文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 模板中的频道将自动创建在“常规”选项卡下方。

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

[Teams 模板入门](../../get-started-with-teams-templates.md)

[适用于医疗组织的 Teams 入门](teams-in-hc.md)