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
description: 了解仅适用于 Microsoft Graph 的团队Graph。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991111"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>开始使用 Microsoft Graph 的团队模板

> [!NOTE]
> 团队模板当前不支持创建专用频道。 专用通道创建不包括在模板定义中。

Microsoft Teams模板是围绕业务需求或项目设计的团队结构的定义。 使用团队模板，可以使用预定义的设置、频道和应用快速轻松地创建丰富的协作空间。 团队模板可帮助你在整个组织中部署一致的团队。

借助 Microsoft Graph，可以使用预构建的团队模板（随团队一起Teams创建团队）。 本文介绍可在模板中定义的属性，以及仅适用于 Microsoft Graph。

本文适用于你：你可：

- 负责在整个组织中规划、部署和管理多个团队<br>
- 想要以编程方式创建具有预定义通道和应用的团队的开发人员

## <a name="team-template-capabilities"></a>团队模板功能

模板包含并支持团队中的大多数属性。 但是，目前不支持一些属性和功能。 下面是包含的内容和团队模板中不包含的内容的快速摘要。

| **团队模板支持的团队属性** | **团队模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 频道设置 |
| 团队可见性 (公共或专用)  | 连接器 |
| 团队设置 (例如成员、来宾、@ 提及)  | 文件和内容 |
| 自动收藏频道 | |
| 已安装的应用 | |
| 固定的选项卡 | |

> [!NOTE]
> 我们将在将来的 Microsoft Teams 版本中添加更多模板功能，因此请返回查看有关受支持属性的最新版本信息。

## <a name="pre-built-templates"></a>预建模板

预构建的团队模板是我们为特定行业创建的模板。 下面是仅适用于 Microsoft Graph 的预构建模板。

| 模板类型 | TemplateId | 此模板提供的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 无其他应用和属性 |
| 教育 -<br>课堂团队 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 应用：<ul><li>OneNote课堂笔记本 (固定到"**常规"选项卡**)  </li><li>作业应用 (固定到" **常规"选项卡**) </li></ul> 团队属性：<ul><li>团队可见性设置为 **HiddenMembership (** 无法重写) </li></ul> |
| 教育 -<br>教职员工团队 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 应用：<ul><li>OneNote教职 (笔记本已固定到"**常规"** 选项卡) </li></ul> |
|教育 -<br>PLC 团队 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 应用：<ul><li>OneNotePLC Notebook (固定到"**常规"选项卡)**</ul></li>|

> [!NOTE]
> 有关可在 Teams 客户端和 Microsoft Graph 中使用的预构建模板的列表，请参阅 Teams 管理中心中的[团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="related-articles"></a>相关文章

- [在管理中心内开始使用Teams模板](get-started-with-teams-templates-in-the-admin-console.md)
- [在预览版](/graph/api/team-post?view=graph-rest-beta) (创建团队) 
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
