---
title: 在管理控制台中使用常规团队模板
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用常规团队模板，通过使用管理控制台提供预定义的设置、信道和预安装应用来创建团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 44be05a7ae1b449e0b267bb0e4ed107c40877f27
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171116"
---
# <a name="use-general-teams-templates-in-the-admin-console"></a>在管理控制台中使用常规团队模板

[!INCLUDE [template](includes/preview-feature.md)]

团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。

团队模板具有围绕财务需求设计的团队结构的预建定义。 您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。

在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。

本文适用于你负责在整个财务组织中规划、部署和管理多个团队的情况。 我们假定你的组织中已部署团队服务。 如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。

若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="global-crisis-or-event"></a>全球危机或活动

跨业务单元对危机团队协作，并帮助创建业务连续性计划、共享远程工作提示、跟踪客户通信，以及使用公告和新闻让每个人都保持联系。

| 基本模板类型 |baseTemplateId | 此基本模板附带的属性 |
| ------------------ |--|----------------------------------------------------- |
| 协作处理全球危机或活动 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |信道 <ul><li>常规<li>宣告</li><li>世界新闻</li><li>业务连续性</li><li>远程工作</li><li>内部 comms</li><li>外部 comms</li><li>客户投诉</li><li>Kudos</li><li>执行更新</li></ul>识别 <ul><li>表扬</li><li>源自</li><li>网站</li></ul>|
||||

## <a name="adopt-office-365"></a>采纳 Office 365

通过宣传和帮助你的同行使用新技术，帮助构建、扩大和维持你的拥护者社区推出。

| 基本模板类型 |baseTemplateId | 此基本模板附带的属性 |
| ------------------|-- |----------------------------------------------------- |
| 采纳 Office 365 | `com.microsoft.teams.template.AdoptOffice365` |  信道 <ul><li>常规</li> <li>宣告</li> <li>拥护方角落</li> <li>工作组表单</li></ul> 识别 <ul><li>源自</li>  <li>日历</li> |li><li>技能发展</li><li>借贷处理</li><li>客户投诉</li><li>Kudos</li><li>有趣的资料</li><li>合规性</li></ul>|
||||

## <a name="manage-a-project"></a>管理项目

通过此模板管理任务、共享文档、开展项目会议和记录风险和决策，以实现常规项目管理。

| 基本模板类型| baseTemplateId | 此基本模板附带的属性 |
| ------------------|-- |----------------------------------------------------- |
| 管理项目| ManageAProject 中的 .com  | 信道 <ul><li>常规</li> <li>宣告</li> <li>.Resources</li> <li>规划</li></ul> 识别<ul><li>源自</li><li>OneNote</li></ul> |
||||

## <a name="manage-an-event"></a>管理事件

管理任务、文档和协作处理提供引人注目事件所需的所有内容。 邀请来宾用户在您的公司内部和外部进行安全协作。

你可能无法访问基于你的应用权限策略的某些应用。

| 基本模板类型 | baseTemplateId| 此基本模板附带的属性 |
| ------------------ |--|----------------------------------------------------- |
| 管理事件| `com.microsoft.teams.template.ManageAnEvent` | 信道 <ul><li>常规</li> <li>宣告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和 PR</li></ul> 识别<ul><li>源自</li><li>网站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>板载员工

通过此中心团队改进您的文化，为您的资源、问题和乐趣，简化您的员工加入。

| 基本模板类型 |baseTemplateId | 此基本模板附带的属性 |
| ------------------|- |----------------------------------------------------- |
|板载员工|`com.microsoft.teams.template.OnboardEmployees`  | 信道 <ul><li>常规</li> <li>宣告</li> <li>员工聊天</li> <li>培训</li></ul>识别<ul><li>源自</li><li>社区</li></ul>|
||||

## <a name="organize-a-help-desk"></a>组织帮助台

协作处理支持帮助台的文档、政策和流程。 集成您的现有票证发放系统或使用我们的模板管理请求。

| 基本模板类型 | | 此基本模板附带的属性 |
| ------------------|-- |----------------------------------------------------- |
|组织技术支持|`com.microsoft.teams.template.OrganizeHelpDesk`| 信道<ul><li>常规</li><li>宣告</li><li>常见问题</li></ul>识别<ul><li>源自</li><li>OneNote</li></ul> |
||||
