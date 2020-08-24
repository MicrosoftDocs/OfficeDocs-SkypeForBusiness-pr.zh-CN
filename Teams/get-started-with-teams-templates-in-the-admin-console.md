---
title: 使用 Teams 模板创建新团队
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
description: 了解如何使用 Teams 模板通过预安装模板为不同主题创建协作空间。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5a43a34ac130f4b5b168d46fa2a69476c42abd7b
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860793"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>开始使用 Teams 管理控制台中的 Teams 模板

[!INCLUDE [template](includes/preview-feature.md)]

**EDU 客户尚不支持自定义模板。**

> [!NOTE]
> Teams 模板当前不支持创建私人频道。 专用频道创建不包含在模板定义中。

Teams 模板是围绕业务需求或项目设计的团队结构的预设定义。 使用预建的模板或创建自己的模板。 通过 Teams 模板，你可以使用不同主题的频道快速创建丰富的协作空间，并预安装应用，以拉入任务关键型内容和服务。 Teams 模板提供预定义的团队结构，可以帮助你在组织内轻松创建一个一个一个团队。 目前，你可通过 Teams 中的模板或 [Microsoft Graph 创建团队](get-started-with-teams-templates.md)。

在本文中，我们将介绍可在模板中定义的属性、什么基本模板类型以及如何通过模板创建团队。

如果你正在使用，本文很适用于你的需要：

- 负责在整个组织内规划、部署和管理多个团队<br>
- 想要以编程方式使用预定义频道和应用创建团队的开发人员

## <a name="teams-template-capabilities"></a>Teams 模板功能

模板可以包含和支持团队中的大多数属性。 但当前还有一些属性和功能当前不受支持。 下表提供了 Teams 模板中所包含内容及其内容的快速摘要。

| **团队模板支持的团队属性** | **Teams 模板尚不支持团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基种基形模板类型 | 团队成员身份 |
| 团队名称 | 团队图片 |
| 团队说明 | 频道设置 |
| 团队可见 (或专用应用)  | 连接器 |
| 成员 (、来宾、@ 提及等团队)  | 文件和内容 |
| 自动收藏频道 | |
| 安装的应用 | |
| 固定的选项卡 | |

> [!NOTE]
> 我们将在将来的 Microsoft Teams 版本中添加更多模板功能，因此请返回有关受支持属性的最新信息。

## <a name="what-are-base-template-types"></a>什么是基值模板类型

基础模板类型是 Microsoft 为特定行业创建的特殊模板。 这些基准模板通常包含在应用商店中可用的专有应用。

定义基本模板类型后，你可以使用你想要指定的其他属性扩展或覆盖这些特殊模板。 但是某些基本模板类型包含不能替代的属性。

> [!NOTE]
> 可复制而不能编辑 Microsoft Teams 中提供的预定义的基准模板。

| 基种基形模板类型 | 此基本模板附带的属性 |
| ------------------ |----------------------------------------------------- |
| 使用 Office 365 |  频道： <ul><li>常规</li> <li>公告</li> <li>Champions Champions</li> <li>工作组窗体</li></ul> 应用： <ul><li>Wiki</li>  <li>日历</li> |
| 管理项目 | 频道： <ul><li>常规</li> <li>公告</li> <li>资源</li> <li>规划</li></ul> 应用：<ul><li>Wiki</li><li>OneNote</li></ul> |
| 管理事件 | 频道： <ul><li>常规</li> <li>公告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 营地和 PR</li></ul> 应用：<ul><li>Wiki</li><li>网站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|培训员工 | 频道： <ul><li>常规</li> <li>公告</li> <li>员工聊天</li> <li>培训</li></ul>应用：<ul><li>Wiki</li><li>社区</li>|</ul>
|组织技程支持| 频道：<ul><li>常规</li><li>公告</li><li>常见问题</li></ul>应用：<ul><li>Wiki</li><li>OneNote</li></ul> |
| 在病人出色协作 | 频道：<ul><li>常规</li><li>公告</li><li>Huddles</li><li>Rounds</li><li>员工</li><li>培训</li></ul> 应用： <ul><li>Wiki</li>|
| 在全局条件或活动进行协作 |频道： <ul><li>常规<li>公告</li><li>世界新闻</li><li>业务连续性</li><li>远程工作</li><li>内部组件</li><li>外部组件</li><li>客户任务</li><li>Kudos</li><li>高管理器更新</li></ul>应用： <ul><li>表单</li><li>Wiki</li><li>网站</li></ul>|
|在银行分行中协作 |频道： <ul><li>常规<li>公告</li><li>Huddles</li><li>客户会议</li><li>Coaching</li><li>技能开发</li><li>编辑过程</li><li>客户任务</li><li>Kudos</li><li>趣用</li><li>合规性</li></ul>|
|协定事件响应 |频道： <ul><li>常规<li>公告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>Urgent</li></ul> 应用： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|医院 |频道： <ul><li>常规<li>公告</li><li>合规性</li><li>"加利亚/li><li>人力资源</li><li>Pharmacy</li></ul> 应用： <ul><li>Wiki</li></ul>|
|整理商店 |频道： <ul><li>常规<li>Shift 切换</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
|质量和安全 |频道： <ul><li>常规<li>公告</li><li>"<c0><c1</li><li>第 2 行</li><li>第 3 行</li><li>安全</li><li>培训</li><li>维护</li><li>趣用</li></ul> 应用： <ul><li>Wiki</li></ul>|
|Retail - 经理协作 |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
|||

## <a name="template-size-limits"></a>模板大小限制

模板限制为特定数量的频道、选项卡和应用。

 > [!Note]
 > 创建后，可将更多频道、选项卡和应用添加到团队中。

|功能 | 限制|
|-|-|
|每个模板的频道 | 15 |
|模板中的每个频道选项卡 | 20 |
|每个模板的应用 | 50|
|||

有关详细信息 [，请参阅 Teams 的](limits-specifications-teams.md) 限制和规范。

## <a name="related-topics"></a>相关主题

- [创建自定义团队模板](create-a-team-template.md)
- [基于现有团队模板创建团队模板](create-template-from-existing-template.md)
- [基于现有团队创建模板](create-template-from-existing-team.md)
