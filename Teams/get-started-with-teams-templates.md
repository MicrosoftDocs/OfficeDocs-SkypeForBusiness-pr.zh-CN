---
title: 使用 Microsoft Graph 开始使用团队模板
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft Graph 中的团队模板创建具有不同主题的频道的协作空间和预安装应用以提供内容和服务。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee4ab53318766b8daaeea225f8c039e32c8c4241
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294598"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>使用 Microsoft Graph 开始使用团队模板

> [!NOTE]
> 团队模板当前不支持创建专用通道。 模板定义中不包含专用通道创建。

团队模板是围绕业务需求或项目设计的团队结构的预建定义。 你可以 [在管理控制台中创建自己的模板](get-started-with-teams-templates-in-the-admin-console.md)。 使用 Microsoft Graph，你可以使用预生成的模板。 你可以使用团队模板快速创建具有不同主题和预安装应用的频道的丰富协作空间，以纳入关键任务内容和服务。 团队模板提供了预定义的团队结构，可帮助你在组织中轻松创建一致的团队。

在本文中，我们将介绍可在模板中定义的属性、哪些基本模板类型以及你可以如何使用一些示例请求从模板创建团队。

本文适用于您的情况：

- 负责在整个组织中规划、部署和管理多个团队<br>
- 希望使用预定义频道和应用以编程方式创建团队的开发人员

## <a name="teams-template-capabilities"></a>团队模板功能

团队中的大多数属性都包含在模板中并受其支持。 但目前尚不支持一些属性和功能。 下表提供了包含哪些内容以及团队模板中不包含的内容的快速摘要。

| **团队模板支持的团队属性** | **团队模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本模板类型 | 团队成员身份 |
| 团队名称 | 工作组图片 |
| 团队说明 | 频道设置 |
| 团队可见性 (公共或私有)  | 连接器 |
| 团队设置 (例如，"成员"、"来宾"、"@ 提及")  | 文件和内容 |
| 自动收藏的频道 | |
| 已安装应用 | |
| 固定的选项卡 | |

> [!NOTE]
> 我们将在 Microsoft 团队的未来版本中添加更多模板功能，请查看有关支持的属性的最新信息。

## <a name="what-are-base-template-types"></a>什么是基本模板类型

基本模板类型是 Microsoft 为特定行业创建的特殊模板。 这些基本模板通常包含应用商店中不可用的专有应用。 此外，基本模板通常包含团队模板中尚不支持的团队属性。 了解如何 [在 Microsoft Graph 中使用团队模板](get-started-with-teams-templates.md)。

定义基本模板类型后，你可以使用你想要指定的其他属性扩展或覆盖这些特殊模板。 某些基本模板类型包含无法覆盖的属性。

默认情况下，基本模板设置为 " **标准**"，它不包含任何其他专用应用或特殊属性。 下面是可用的基本模板类型的当前列表。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 无其他应用和属性 |
| 教育版<br>课堂团队 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 识别<ul><li>OneNote 课堂笔记本 (固定到 " **常规** " 选项卡)  </li><li>"工作分配" 应用 (固定到 " **常规** " 选项卡) </li></ul> 团队属性：<ul><li>无法覆盖设置为 **HiddenMembership** (的团队可见性) </li></ul> |
| 教育版<br>教职员工团队 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 识别<ul><li>OneNote 教职员工笔记本 (固定到 " **常规** " 选项卡) </li></ul> |
|教育版<br>PLC 团队 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 识别<ul><li>OneNote PLC 笔记本 (固定到 " **常规** " 选项卡) </ul></li>|
| 面向<br>应用商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 信道<ul><li>切换切换</li><li>培训</li></ul>团队属性<ul><li>将团队可见性设置为公共</li></ul>成员权限<ul><li>阻止成员创建、更新或删除频道</li><li>阻止成员添加或删除应用</li><li>阻止成员创建、更新或删除连接器</li></ul> |
| 面向<br>经理协作 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 信道<ul><li>切换切换</li><li>培训</li></ul>团队属性：<ul><li>将团队可见性设置为私密</li></ul>成员权限：<ul><li>阻止成员创建、更新或删除频道</li><li>阻止成员添加或删除应用</li><li>阻止成员创建、更新或删除连接器</li></ul>|
| 行业<br>拖动 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |信道 <ul><li>宣告\*</li><li>Huddles\*</li><li>轮</li><li>调配\*</li><li>培训\*</li></ul>\*自动收藏频道 |
|行业<br>医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |信道<ul><li>宣告\*</li><li>合规性\*</li><li>Custodial</li><li>人力资源</li></li><li>药房</li></ul>\*自动收藏频道|
|||

## <a name="related-topics"></a>相关主题

- [管理控制台中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)
- 在预览中[创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) () 
- [新团队](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams 管理培训](itadmin-readiness.md)