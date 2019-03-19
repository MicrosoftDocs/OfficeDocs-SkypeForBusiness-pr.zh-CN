---
title: 适合于医疗保健组织的 Teams 模板入门
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
description: 适合于医疗保健组织的 Teams 模板入门
ms.openlocfilehash: e5116ecf2ab9fa0bbad25222e69317c47cf0c892
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664697"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>适合于医疗保健组织的 Teams 模板入门

Microsoft 团队模板允许您快速和轻松创建团队提供的预定义的模板的设置、 通道和预安装的应用程序。

对于医疗保健机构模板可以是特别强大，因为它们提供用户成为方向如何最有效地利用团队使用的结构。 模板还允许管理员在整个组织中部署一致的团队。 本文适用于您，如果您是负责规划、 部署和管理组织医疗保健跨多个团队。

我们当前提供两个第一方医疗保健模板，您可以利用的很多情况。 若要了解有关工作组模板通常情况下，请参阅[入门工作组模板](../get-started-with-teams-templates.md)。

## <a name="ward-template"></a>行政区模板

行政区模板旨在的沟通和协作行政区、 盒或部门内。 模板可用于加快患者管理，以及行政区操作需求。 例如，可以在*通知*频道张贴行政区通知和引进可以管理*人员*中。 如果您希望优化行政区操作，此模板将为您。

|基本模板类型 |baseTemplateId |比较基准模板通道|
|:--- |:---|:---|
|医疗保健-行政区 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 通知\* <br> Huddles\* <br> 将舍入为\* <br> 人员配备扁平化\* <br> 培训\* |
|     | |         |

\*自动 favorited

## <a name="hospital-template"></a>医院模板

医院模板旨在的沟通和多个病房、 盒和医院中的部门之间的协作。 包含此模板中的多个操作通道包括*通知*、 *Custodial*和*药房*，但我们还提供低于该值脚本扩展的模板，其中包含各种的其他部门或您可以添加、 删除，或编辑您的喜好的专业中心通道。 例如，如果您有了*内分泌科*科，但不需要*眼科*通道，然后脚本可以调整以包括*内分泌科*通道并删除*眼科*通道。 我们建议，这些专业或行政区建模通道不会自动-favorited 以避免通知饱和度。 用户通常最喜爱的任何通道他们发现相关。

|基本模板类型 |baseTemplateId |比较基准模板通道|
|:--- |:---|:---|
|医疗保健-医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 通知\* <br> 合规性\* <br> 监控 <br> 人力资源 <br> 药房 |
| | |  |

\*自动 favorited 

## <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

若要使用这些模板，只需更改为上面 TemplateIDs 从标准在请求正文中的 template@odata.bind 属性。  有关如何部署工作组模板的详细信息，请参阅 Microsoft Graph[创建团队的文章](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

### <a name="example-hospital-template-extension-script"></a>示例： 医院模板扩展脚本

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
