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
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772193"
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

默认情况下，基本模板设置为 " **标准** "，它不包含任何其他专用应用或特殊属性。 下面是可用的基本模板类型的当前列表。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 无其他应用和属性 |
| 教育版<br>课堂团队 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 识别<ul><li>OneNote 课堂笔记本 (固定到 " **常规** " 选项卡)  </li><li>"工作分配" 应用 (固定到 " **常规** " 选项卡) </li></ul> 团队属性：<ul><li>无法覆盖设置为 **HiddenMembership** (的团队可见性) </li></ul> |
| 教育版<br>教职员工团队 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 识别<ul><li>OneNote 教职员工笔记本 (固定到 " **常规** " 选项卡) </li></ul> |
|教育版<br>PLC 团队 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 识别<ul><li>OneNote PLC 笔记本 (固定到 " **常规** " 选项卡) </ul></li>|
| 面向<br>应用商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 信道<ul><li>切换切换</li><li>培训</li></ul>团队属性<ul><li>将团队可见性设置为公共</li></ul>成员权限<ul><li>阻止成员创建、更新或删除频道</li><li>阻止成员添加或删除应用</li><li>阻止成员创建、更新或删除连接器</li></ul> |
| 面向<br>经理协作 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 信道<ul><li>培训</li><li>运营</li></ul>团队属性：<ul><li>将团队可见性设置为私密</li></ul>成员权限：<ul><li>阻止成员创建、更新或删除频道</li><li>阻止成员添加或删除应用</li><li>阻止成员创建、更新或删除连接器</li></ul>|
| 行业<br>拖动 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |信道 <ul><li>宣告\*</li><li>Huddles\*</li><li>轮</li><li>调配\*</li><li>培训\*</li></ul>\*自动收藏频道 |
|行业<br>医院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |信道<ul><li>宣告\*</li><li>合规性\*</li><li>Custodial</li><li>人力资源</li></li><li>药房</li></ul>\*自动收藏频道|
|||


使用以下模板在团队客户端和 Microsoft Graph 中创建团队。


| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 采纳 Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  信道 <ul><li>常规</li> <li>宣告</li> <li>拥护方角落</li> <li>工作组表单</li></ul> 识别 <ul><li>源自</li>  <li>日历</li> |
| 管理项目 |`com.microsoft.teams.template.`<br>`ManageAProject`| 信道 <ul><li>常规</li> <li>宣告</li> <li>.Resources</li> <li>规划</li></ul> 识别<ul><li>源自</li><li>OneNote</li></ul> |
| 管理事件|`com.microsoft.teams.template.`<br>`ManageAnEvent` | 信道 <ul><li>常规</li> <li>宣告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和 PR</li></ul> 识别<ul><li>源自</li><li>网站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|板载员工|`com.microsoft.teams.template.`<br>`OnboardEmployees` | 信道 <ul><li>常规</li> <li>宣告</li> <li>员工聊天</li> <li>培训</li></ul>识别<ul><li>源自</li><li>社区</li></ul>|
|组织技术支持| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|信道<ul><li>常规</li><li>宣告</li><li>常见问题</li></ul>识别<ul><li>源自</li><li>OneNote</li></ul> |
| 协作处理患者护理| `healthcareWard `| 信道<ul><li>常规</li><li>宣告</li><li>Huddles</li><li>轮</li><li>调配</li><li>培训</li></ul> 识别 <ul><li>源自</li>|
| 协作处理全球危机或活动 |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| 信道 <ul><li>常规<li>宣告</li><li>世界新闻</li><li>业务连续性</li><li>远程工作</li><li>内部 comms</li><li>外部 comms</li><li>客户投诉</li><li>Kudos</li><li>执行更新</li></ul>识别 <ul><li>表扬</li><li>源自</li><li>网站</li></ul>|
|在银行分支内进行协作| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|信道 <ul><li>常规<li>宣告</li><li>Huddles</li><li>客户会议</li><li>训练</li><li>技能发展</li><li>借贷处理</li><li>客户投诉</li><li>Kudos</li><li>有趣的资料</li><li>合规性</li></ul>|
|协调事件响应| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|信道 <ul><li>常规<li>宣告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>急需</li></ul> 识别 <ul><li>源自</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|医院| `healthcareHospita`控制面板 |信道 <ul><li>常规<li>宣告</li><li>合规性</li><li>Custodial</li><li>人力资源</li><li>药房</li></ul> 识别 <ul><li>源自</li></ul>|
|组织商店| `retailStore` |信道 <ul><li>常规<li>切换切换</li><li>培训</li></ul> 识别 <ul><li>源自</li></ul>|
|质量和安全性 |`com.microsoft.teams.`<br>`template.QualitySafety`|信道 <ul><li>常规<li>宣告</li><li>第1行</li><li>第2行</li><li>第3行</li><li>引起</li><li>培训</li><li>维护</li><li>有趣的资料</li></ul> 识别 <ul><li>源自</li></ul>|
|零售经理协作| `retailManagerCollaboration` |信道 <ul><li>常规<li>运营</li><li>培训</li></ul> 识别 <ul><li>源自</li></ul>|
||||

有关详细信息，请参阅 [管理中心中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md) 。

## <a name="related-topics"></a>相关主题

- [管理控制台中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)
- 在预览中[创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) () 
- [新团队](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams 管理培训](itadmin-readiness.md)