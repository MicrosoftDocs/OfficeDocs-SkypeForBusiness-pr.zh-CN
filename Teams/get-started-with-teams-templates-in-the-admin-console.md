---
title: 在管理中心使用 Teams 模板
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams 模板使用预安装模板创建包含不同主题频道的协作空间。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62bee9c494cc6155a84b30d75ae71528656133be
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508005"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>管理中心中的 Teams 模板入门

**EDU 客户尚不支持创建自定义模板。**

> [!NOTE]
> Teams 模板当前不支持创建专用频道。 专用通道创建不包括在模板定义中。

Teams 模板是围绕业务需求或项目设计的团队结构的预构建定义。 使用预建模板或创建自己的模板。 借助 Teams 模板，可借助不同主题的频道快速创建丰富的协作空间，并预安装应用以拉取任务关键型内容和服务。 Teams 模板提供预定义的团队结构，可帮助你在整个组织中轻松创建一致的团队。 目前，可以通过 Teams 中的模板或 [Microsoft Graph](get-started-with-teams-templates.md)创建团队。

本文介绍可在模板中定义的属性、什么是基本模板类型，以及如何使用几个示例请求从模板创建团队。

如果你负责规划、部署和管理整个组织的多个团队，本文适合你

## <a name="teams-template-capabilities"></a>Teams 模板功能

模板包含并支持团队中的大多数属性。 但是，目前不支持一些属性和功能。 下表提供了 Teams 模板中包含的内容以及不包含的内容的快速摘要。

| **Teams 模板支持的团队属性** | **Teams 模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本模板类型 | 团队成员身份 |
| 团队名称 | 团队图片 |
| 团队说明 | 频道设置 |
| 团队可见性 (公共或专用)  | 连接器 |
| 团队设置 (例如成员、来宾、@ 提及)  | 文件和内容 |
| Autofavorite 通道 | |
| 已安装的应用 | |
| 固定选项卡 | |

> [!NOTE]
> 我们将在将来的 Microsoft Teams 版本中添加更多模板功能，因此请返回查看有关受支持属性的最新版本信息。

## <a name="what-are-base-template-types"></a>什么是基本模板类型

基本模板类型是 Microsoft 为特定行业创建的特殊模板。 这些基本模板通常包含在应用存储区中不可用的专有应用。

定义基本模板类型后，可以使用要指定的其他属性扩展或替代这些特殊模板。 某些基本模板类型包含无法重写的属性。

> [!NOTE]
> Microsoft Teams 中提供的预定义基本模板可以复制，但不能编辑。

| 基本模板类型 | baseTemplateId | 此基本模板提供的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 采用 Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  频道： <ul><li>常规</li> <li>公告</li> <li>得主角</li> <li>团队表单</li></ul> 应用： <ul><li>Wiki</li>  <li>日历</li> |
| 管理项目 |`com.microsoft.teams.template.ManageAProject`| 频道： <ul><li>常规</li> <li>公告</li> <li>资源</li> <li>规划</li></ul> 应用：<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>列表</li>  </ul> |
| 管理事件|`com.microsoft.teams.template.ManageAnEvent` | 频道： <ul><li>常规</li> <li>公告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和 PR</li></ul> 应用：<ul><li>Wiki</li><li>网站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|载入员工|`com.microsoft.teams.template.OnboardEmployees` | 频道： <ul><li>常规</li> <li>公告</li> <li>员工聊天</li> <li>培训</li></ul>应用：<ul><li>Wiki</li><li>社区</li><li>Planner</li></ul>|
|组织技术支持| `com.microsoft.teams.template.OrganizeHelpDesk`|频道：<ul><li>常规</li><li>公告</li><li>常见问题</li></ul>应用：<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>表扬</li></ul> |
| 协作处理患者护理| `healthcareWard`| 频道：<ul><li>常规</li><li>公告</li><li>Huddles</li><li>舍入</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>Wiki</li><li>列表  </li></ul>|
| 协作解决全球问题或事件 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 频道： <ul><li>常规<li>公告</li><li>世界新闻</li><li>业务连续性</li><li>远程工作</li><li>内部通信</li><li>外部通信</li><li>审批请求</li><li>客户投诉</li><li>Kudos</li><li>高管更新</li></ul>应用： <ul><li>表扬</li><li>Wiki</li><li>网站</li><li>Planner</li></ul>|
|在银行分支机构内协作| `com.microsoft.teams.template.CollaborateWithinABankBranch`|频道： <ul><li>常规<li>公告</li><li>Huddles</li><li>客户会议</li><li>审批请求 </li><li>指导</li><li>技能开发</li><li>贷款处理</li><li>客户投诉</li><li>Kudos</li><li>有趣的内容</li><li>合规性</li></ul>应用：<ul><li>表扬 </li></ul>|
|协调事件响应| `com.microsoft.teams.template.CoordinateIncidentResponse`|频道： <ul><li>常规<li>公告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>紧急</li></ul> 应用： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|医院| `healthcareHospital` |频道： <ul><li>常规</li><li>公告</li><li>合规性</li><li>监管</li><li>人力资源</li><li>药物</li></ul> 应用： <ul><li>Wiki</li><li>列表  </li></ul>|
|组织商店| `retailStore` |频道： <ul><li>常规<li>Shift 切换</li><li>学习</li></ul> 应用： <ul><li>Wiki</li><li>Planner</li></ul>|
|质量和安全 |`com.microsoft.teams.template.QualitySafety`|频道： <ul><li>常规<li>公告</li><li>第 1 行</li><li>第 2 行</li><li>第 3 行</li><li>安全</li><li>培训</li><li>维护</li><li>有趣的内容</li></ul> 应用： <ul><li>Wiki</li><li>Planner</li></ul>|
|零售 - 管理器协作| `retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li><li>Planner</li></ul>|
||||

有关模板类别详细信息，请参阅以下类别：

- [财务模板](financial-teams-templates-in-the-admin-console.md)
- [常规模板](general-teams-templates-in-the-admin-console.md)
- [政府模板](government-teams-templates-in-the-admin-console.md)
- [医疗保健模板](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [制造模板](manufacturing-teams-templates-in-the-admin-console.md)
- [零售模板](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>模板大小限制

模板限制为特定数量的通道、选项卡和应用。

 > [!Note]
 > 从模板创建团队后，你可以向团队添加更多频道、选项卡和应用。

|功能 | 限制|
|-|-|
|每个模板的频道数 | 15 |
|模板中每个通道的选项卡数 | 20 |
|每个模板的应用数 | 50|
|||

有关详细信息 [，请参阅 Teams 的限制](limits-specifications-teams.md) 和规范。

## <a name="related-topics"></a>相关主题

- [创建自定义团队模板](create-a-team-template.md)
- [从现有团队模板创建团队模板](create-template-from-existing-template.md)
- [从现有团队创建模板](create-template-from-existing-team.md)
