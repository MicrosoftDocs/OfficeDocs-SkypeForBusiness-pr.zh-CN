---
title: 开始使用 Teams 模板
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: 了解如何使用团队模板来创建工作组使用预定义的通道。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b620f163f1dc071bde8a0ed43bf7fe546a9bc04a
ms.sourcegitcommit: 355bcdafa58b6349bb6bc771054f4c9c91387a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013634"
---
# <a name="get-started-with-teams-templates"></a>开始使用 Teams 模板 

工作组模板是预建的团队的结构围绕业务需要或项目设计的定义。 工作组模板可用于快速使用不同的主题的通道创建丰富的协作空格和预安装应用程序提取在任务关键型内容和服务。 工作组模板提供可帮助您轻松地在整个组织中创建一致的团队的预定义的团队结构。 

本文中，我们将介绍可以在模板类型是，哪些基本模板定义的属性和如何使用了几个示例请求从模板创建工作组。
 
本文适用于您，如果您是：

- 负责规划、 部署和管理您的组织内的多个团队<br>
- 开发人员希望以编程方式使用预定义的通道和应用程序创建团队 

## <a name="teams-template-capabilities"></a>工作组模板功能

包含和模板的支持团队中的大多数属性。 但有一些属性，当前不支持的功能。 下表提供了包含的组件和工作组模板中不包含内容的快速摘要。

| **支持的工作组模板的团队属性** | **尚未支持的工作组模板的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 通道设置 |
| 工作组可见性 （公共或专用） | 连接器 |
| 团队设置 （例如，成员、 来宾，@ 提及） | 文件和内容 |
| 自动收藏夹通道 | |
| 已安装应用程序 | |
| 固定的选项卡 | | 

> [!NOTE]
> 我们将为添加更多模板功能的将来版本中的 Microsoft 团队，因此检查返回有关支持的属性的最新信息。

## <a name="what-are-base-template-types"></a>基本模板类型是什么？

基本模板类型是 Microsoft 创建针对特定行业的特殊模板。 这些基本模板通常包含在尚不支持分别在工作组模板中存储和团队属性中不可用的专用应用程序。

定义基本模板类型后，您可以扩展或重写这些特殊模板与您想要指定的其他属性。 但某些基本模板类型包含不能重写的属性。 

默认情况下基本模板设置为**标准**其不包含任何其他专用应用程序或特殊属性。 下面是可用的基本模板类型的当前列表。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 没有其他应用程序和属性 |
| 培训-<br>类团队 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 应用程序：<ul><li>OneNote 类笔记本 （固定到**常规**选项卡） </li><li>分配应用程序 （固定到**常规**选项卡）</li></ul> 团队属性：<ul><li>工作组可见性设置为**HiddenMembership** （不能重写）</li></ul> |
| 培训-<br>员工团队 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 应用程序：<ul><li>OneNote 员工笔记本 （固定到**常规**选项卡）</li></ul> |
|培训-<br>PLC 团队 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 应用程序：<ul><li>OneNote PLC 笔记本 （固定到**常规**选项卡）</ul></li>|
| 零售-<br>存储 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 频道：<ul><li>Shift 提交</li><li>学习</li></ul>团队属性<ul><li>设置为 Public 工作组可见性</li></ul>成员权限<ul><li>阻止创建、 更新或删除通道成员成员</li><li>阻止添加或删除应用程序的成员</li><li>阻止从创建、 更新或删除连接器的成员</li></ul> |
| 零售-<br>管理器协作 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 频道：<ul><li>Shift 提交</li><li>学习</li></ul>团队属性：<ul><li>设置为 Private 工作组可见性</li></ul>成员权限：<ul><li>阻止创建、 更新或删除通道成员成员</li><li>阻止添加或删除应用程序的成员</li><li>阻止从创建、 更新或删除连接器的成员</li></ul>|
| 医疗保健-<br>行政区 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |频道： <ul><li>通知\*</li><li>Huddles\*</li><li>将舍入为</li><li>人员配备扁平化\*</li><li>培训\*</li></ul>\*自动 favorited 通道 |
|医疗保健-<br>医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |频道：<ul><li>通知\*</li><li>合规性\*</li><li>监控</li><li>人力资源</li></li><li>药房</li></ul>\*自动 favorited 通道|
|||

> [!NOTE]
> 我们将添加更多基本模板类型在将来版本的 Microsoft 团队，因此请检查以便获得最新信息支持属性。


## <a name="related-topics"></a>相关主题

- [创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)（在预览）
- [新团队](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams 管理培训](itadmin-readiness.md)
- [Teams 零售模板入门](get-started-with-retail-teams-templates.md)
- [适合于医疗保健组织的 Teams 模板入门](expand-teams-across-your-org/healthcare/healthcare-templates.md)
