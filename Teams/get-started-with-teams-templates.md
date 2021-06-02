---
title: 开始使用 Microsoft Graph 的团队模板
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
description: 了解如何使用 Microsoft Graph中的团队模板创建包含不同主题的频道的协作空间，并预安装应用以提供内容和服务。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0208b8c6ad16cc42611768a25237a6e48bf60401
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717823"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>开始使用 Microsoft Graph 的团队模板

> [!NOTE]
> 团队模板当前不支持创建专用频道。 专用通道创建不包括在模板定义中。

团队模板是围绕业务需求或项目设计的团队结构的预构建定义。 可以在 [管理控制台 中创建自己的模板](get-started-with-teams-templates-in-the-admin-console.md)。 使用 Microsoft Graph，可以使用预建的模板 。 可以使用团队模板通过不同主题的频道快速创建丰富的协作空间，并预安装应用以拉取任务关键型内容和服务。 团队模板提供预定义的团队结构，可帮助你在整个组织中轻松创建一致的团队。

本文介绍可在模板中定义的属性、基本模板类型，以及如何使用几个示例请求从模板创建团队。

本文适用于你：你可：

- 负责在整个组织中规划、部署和管理多个团队<br>
- 想要以编程方式创建具有预定义通道和应用的团队的开发人员

## <a name="team-template-capabilities"></a>团队模板功能

模板包含并支持团队中的大多数属性。 但是，目前不支持一些属性和功能。 下表提供了团队模板中包含的内容以及不包含的内容的快速摘要。

| **团队模板支持的团队属性** | **团队模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本模板类型 | 团队成员身份 |
| 团队名称 | 团队图片 |
| 团队说明 | 频道设置 |
| 团队可见性 (公共或专用)  | 连接器 |
| 团队设置 (例如成员、来宾、@ 提及)  | 文件和内容 |
| 自动收藏频道 | |
| 已安装的应用 | |
| 固定的选项卡 | |

> [!NOTE]
> 我们将在将来的 Microsoft Teams 版本中添加更多模板功能，因此请返回查看有关受支持属性的最新版本信息。

## <a name="what-are-base-template-types"></a>什么是基本模板类型

基本模板类型是 Microsoft 为特定行业创建的特殊模板。 这些基本模板通常包含在应用商店中不可用的专有应用。 此外，基本模板通常包含尚不在团队模板中单独支持的团队属性。 了解如何使用 Microsoft [Graph 中的团队Graph。](get-started-with-teams-templates.md)

定义基本模板类型后，可以使用要指定的其他属性扩展或替代这些特殊模板。 某些基本模板类型包含无法重写的属性。

默认情况下，基本模板设置为 **"标准**"，其中不包含任何其他专有应用或特殊属性。 下面是可用基本模板类型的当前列表。

| 基本模板类型 | baseTemplateId | 此基本模板包含的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 无其他应用和属性 |
| 教育 -<br>课堂团队 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 应用：<ul><li>OneNote课堂笔记本 (固定到"**常规"选项卡**)  </li><li>作业应用 (固定到" **常规"选项卡**) </li></ul> 团队属性：<ul><li>团队可见性设置为 **HiddenMembership (** 无法重写) </li></ul> |
| 教育 -<br>教职员工团队 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 应用：<ul><li>OneNote教职 (笔记本已固定到"**常规"** 选项卡) </li></ul> |
|教育 -<br>PLC 团队 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 应用：<ul><li>OneNotePLC Notebook (固定到"**常规"选项卡**) </ul></li>|
| 零售 -<br>商店 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailStore')` | 频道：<ul><li>换班</li><li>学习</li></ul>团队属性<ul><li>团队可见性设置为“公共”</li></ul>成员权限<ul><li>防止成员创建、更新或删除频道</li><li>防止成员添加或删除应用</li><li>防止成员创建、更新或删除连接器</li></ul> |
| 零售 -<br>管理器协作 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailManagerCollaboration')` | 频道：<ul><li>学习</li><li>运营</li></ul>团队属性：<ul><li>团队可见性设置为“专用”</li></ul>成员权限：<ul><li>防止成员创建、更新或删除频道</li><li>防止成员添加或删除应用</li><li>防止成员创建、更新或删除连接器</li></ul>|
| 医疗保健 -<br>Ward |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareWard')` |频道： <ul><li>公告 \*</li><li>小型会议室 \*</li><li>循环配置</li><li>人员配备 \*</li><li>培训 \*</li></ul>\*自动收藏的频道 |
|医疗保健 -<br>医院 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareHospital')` |频道：<ul><li>公告 \*</li><li>合规性 \*</li><li>保管</li><li>人力资源</li></li><li>药房</li></ul>\*自动收藏的通道|
|||


使用以下模板在 Teams 客户端和 Microsoft Graph。


| 基本模板类型 | baseTemplateId | 此基本模板包含的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 采用Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  频道： <ul><li>常规</li> <li>公告</li> <li>冠军角</li> <li>团队表单</li></ul> 应用： <ul><li>Wiki</li>  <li>日历</li> |
| 管理项目 |`com.microsoft.teams.template.`<br>`ManageAProject`| 频道： <ul><li>常规</li> <li>公告</li> <li>资源</li> <li>规划</li></ul> 应用：<ul><li>Wiki</li><li>OneNote</li></ul> |
| 管理事件|`com.microsoft.teams.template.`<br>`ManageAnEvent` | 频道： <ul><li>常规</li> <li>公告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和 PR</li></ul> 应用：<ul><li>Wiki</li><li>网站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|培训员工|`com.microsoft.teams.template.`<br>`OnboardEmployees` | 频道： <ul><li>常规</li> <li>公告</li> <li>员工聊天</li> <li>培训</li></ul>应用：<ul><li>Wiki</li><li>社区</li></ul>|
|组织技术支持| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|频道：<ul><li>常规</li><li>公告</li><li>常见问题</li></ul>应用：<ul><li>Wiki</li><li>OneNote</li></ul> |
| 协作处理患者护理| `healthcareWard `| 频道：<ul><li>常规</li><li>公告</li><li>小型会议室</li><li>循环配置</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>Wiki</li>|
| 协作解决全球问题或事件 |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| 频道： <ul><li>常规<li>公告</li><li>世界新闻</li><li>业务连续性</li><li>远程工作</li><li>内部通信</li><li>外部通信</li><li>客户投诉</li><li>Kudos</li><li>高管更新</li></ul>应用： <ul><li>表扬</li><li>Wiki</li><li>网站</li></ul>|
|在银行分支机构内协作| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|频道： <ul><li>常规<li>公告</li><li>小型会议室</li><li>客户会议</li><li>指导</li><li>技能开发</li><li>贷款处理</li><li>客户投诉</li><li>Kudos</li><li>有趣的内容</li><li>合规性</li></ul>|
|协调事件响应| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|频道： <ul><li>常规<li>公告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>紧急</li></ul> 应用： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|医院| `healthcareHospita`l |频道： <ul><li>常规<li>公告</li><li>合规性</li><li>保管</li><li>人力资源</li><li>药房</li></ul> 应用： <ul><li>Wiki</li></ul>|
|组织商店| `retailStore` |频道： <ul><li>常规<li>换班</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
|质量和安全 |`com.microsoft.teams.`<br>`template.QualitySafety`|频道： <ul><li>常规<li>公告</li><li>第 1 行</li><li>第 2 行</li><li>第 3 行</li><li>安全</li><li>培训</li><li>维护</li><li>有趣的内容</li></ul> 应用： <ul><li>Wiki</li></ul>|
|零售 - 经理协作| `retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||

有关详细信息 [，请参阅管理中心中的](get-started-with-teams-templates-in-the-admin-console.md) 团队模板入门。

## <a name="related-topics"></a>相关主题

- [管理员控制台中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)
- [在预览版](/graph/api/team-post?view=graph-rest-beta) (创建团队) 
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams 管理培训](itadmin-readiness.md)
