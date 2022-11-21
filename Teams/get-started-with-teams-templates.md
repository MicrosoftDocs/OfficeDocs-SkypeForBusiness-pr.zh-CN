---
title: 开始使用 Microsoft Graph 的团队模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
description: 了解仅适用于 Microsoft Graph 的团队模板。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4560e5845b2f9beabc8227d79bebc889c9d42c37
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131121"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>开始使用 Microsoft Graph 的团队模板

> [!NOTE]
> 团队模板当前不支持创建专用频道。 专用频道创建不包括在模板定义中。

Microsoft Teams 中的团队模板是围绕业务需求或项目设计的团队结构的定义。 使用团队模板，可以使用预定义的设置、频道和应用快速轻松地创建丰富的协作空间。 团队模板可帮助你在整个组织中部署一致的团队。

使用 Microsoft Graph，可以 [创建自己的模板](/graph/api/resources/teamtemplate?view=graph-rest-beta) ，或使用 Teams 附带的预生成团队模板来创建团队。 在本文中，你将了解可在模板中定义的属性，以及仅适用于 Microsoft Graph 的预生成模板。

如果你在以下的情况下，本文适合你：

- 负责规划、部署和管理组织中的多个团队<br>
- 希望以编程方式创建具有预定义频道和应用的团队的开发人员

## <a name="team-template-capabilities"></a>团队模板功能

模板包含并支持团队中的大多数属性。 但目前不支持一些属性和功能。 下面是团队模板中包括的内容和未包含的内容的快速摘要。

| **团队模板支持的团队属性** | **团队模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 通道设置 |
| 公共或专用)  (团队可见性 | 连接器 |
| 团队设置 (例如，成员、来宾、@ 提及)  | 文件和内容 |
| 自动收藏频道 | |
| 已安装的应用 | |
| 固定选项卡 | |

> [!NOTE]
> 我们将在 Microsoft Teams 的未来版本中添加更多模板功能，因此请回来查看有关受支持属性的最新信息。

## <a name="pre-built-templates"></a>预建模板

预构建的团队模板是我们为特定行业创建的模板。 下面是仅适用于 Microsoft Graph 的预生成模板。

| 模板类型 | TemplateId | 此基本模板包含的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 没有其他应用和属性 |
| 教育-<br>课堂团队 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 应用：<ul><li>OneNote 课堂笔记本 (固定到“ **常规** ”选项卡)  </li><li>作业应用 (固定到“ **常规** ”选项卡) </li></ul> 团队属性：<ul><li>无法覆盖设置为 **HiddenMembership** (的团队可见性) </li></ul> |
| 教育-<br>教职员工团队 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 应用：<ul><li>OneNote 教职员工笔记本 (固定到“ **常规** ”选项卡) </li></ul> |
|教育-<br>PLC 团队 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 应用：<ul><li>OneNote PLC 笔记本 (固定到“ **常规** ”选项卡) </ul></li>|

> [!NOTE]
> 有关可在 Teams 客户端和 Microsoft Graph 中使用的预生成模板的列表，请参阅 [Teams 管理中心中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="related-articles"></a>相关文章

- [在管理中心内开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)
- [创建](/graph/api/team-post?view=graph-rest-beta) 预览版团队 () 
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
