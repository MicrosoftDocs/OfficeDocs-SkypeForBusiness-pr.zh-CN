---
title: 使用团队模板创建新团队
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
description: 了解如何使用团队模板使用预安装的模板为不同的主题创建协作空间和频道。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ad6118d498a8c835dbc4ccde664874bd24373b52
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135866"
---
# <a name="get-started-with-teams-templates-in-the-admin-console"></a>管理控制台中的团队模板入门

[!INCLUDE [template](includes/preview-feature.md)]

**教育机构客户尚不支持自定义模板。**

> [!NOTE]
> 团队模板当前不支持创建专用通道。 模板定义中不包含专用通道创建。

团队模板是围绕业务需求或项目设计的团队结构的预建定义。 使用预先构建的模板或创建自己的模板。 团队模板让你可以通过频道快速创建丰富的协作空间，以用于不同的主题和预安装应用以纳入关键任务内容和服务。 团队模板提供了预定义的团队结构，可帮助你在组织中轻松创建一致的团队。 当前，你可以使用团队中的模板或使用 [Microsoft Graph](get-started-with-teams-templates.md)创建团队。

在本文中，我们将介绍可在模板中定义的属性、哪些基本模板类型以及如何使用一些示例请求来从模板创建团队。

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

基本模板类型是 Microsoft 为特定行业创建的特殊模板。 这些基本模板通常包含应用商店中提供的专有应用。

定义基本模板类型后，你可以使用你想要指定的其他属性扩展或覆盖这些特殊模板。 但某些基本模板类型包含无法重写的属性。

> [!NOTE]
> Microsoft 团队中提供的预定义的基本模板可以重复，但不能编辑。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ |----|----------------------------------------------------- |
| 采纳 Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  信道 <ul><li>常规</li> <li>宣告</li> <li>拥护方角落</li> <li>工作组表单</li></ul> 识别 <ul><li>源自</li>  <li>日历</li> |
| 管理项目 |`com.microsoft.teams.template.ManageAnEvent`| 信道 <ul><li>常规</li> <li>宣告</li> <li>.Resources</li> <li>规划</li></ul> 识别<ul><li>源自</li><li>OneNote</li></ul> |
| 管理事件|`com.microsoft.teams.template.ManageAnEvent` | 信道 <ul><li>常规</li> <li>宣告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和 PR</li></ul> 识别<ul><li>源自</li><li>网站</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|板载员工|`com.microsoft.teams.template.OnboardEmployees` | 信道 <ul><li>常规</li> <li>宣告</li> <li>员工聊天</li> <li>培训</li></ul>识别<ul><li>源自</li><li>社区</li></ul>|
|组织技术支持| `com.microsoft.teams.template.OrganizeHelpDesk`|信道<ul><li>常规</li><li>宣告</li><li>常见问题</li></ul>识别<ul><li>源自</li><li>OneNote</li></ul> |
| 协作处理患者护理| `healthcareWard `| 信道<ul><li>常规</li><li>宣告</li><li>Huddles</li><li>轮</li><li>调配</li><li>培训</li></ul> 识别 <ul><li>源自</li>|
| 协作处理全球危机或活动 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 信道 <ul><li>常规<li>宣告</li><li>世界新闻</li><li>业务连续性</li><li>远程工作</li><li>内部 comms</li><li>外部 comms</li><li>客户投诉</li><li>Kudos</li><li>执行更新</li></ul>识别 <ul><li>表扬</li><li>源自</li><li>网站</li></ul>|
|在银行分支内进行协作| `com.microsoft.teams.template.CollaborateWithinABankBranch `|信道 <ul><li>常规<li>宣告</li><li>Huddles</li><li>客户会议</li><li>训练</li><li>技能发展</li><li>借贷处理</li><li>客户投诉</li><li>Kudos</li><li>有趣的资料</li><li>合规性</li></ul>|
|协调事件响应| `com.microsoft.teams.template.CoordinateIncidentResponse`|信道 <ul><li>常规<li>宣告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>急需</li></ul> 识别 <ul><li>源自</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|医院| `healthcareHospita`控制面板 |信道 <ul><li>常规<li>宣告</li><li>合规性</li><li>Custodial</li><li>人力资源</li><li>药房</li></ul> 识别 <ul><li>源自</li></ul>|
|组织商店| `retailStore` |信道 <ul><li>常规<li>切换切换</li><li>培训</li></ul> 识别 <ul><li>源自</li></ul>|
|质量和安全性 |`com.microsoft.teams.template.QualitySafety`|信道 <ul><li>常规<li>宣告</li><li>第1行</li><li>第2行</li><li>第3行</li><li>引起</li><li>培训</li><li>维护</li><li>有趣的资料</li></ul> 识别 <ul><li>源自</li></ul>|
|零售经理协作| `retailManagerCollaboration` |信道 <ul><li>常规<li>运营</li><li>培训</li></ul> 识别 <ul><li>源自</li></ul>|
||||

有关模板类别的更多详细信息，请参阅以下内容：

- [财务模板](financial-teams-templates-in-the-admin-console.md)
- [常规模板](general-teams-templates-in-the-admin-console.md)
- [政府模板](government-teams-templates-in-the-admin-console.md)
- [医疗保健模板](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [制造模板](manufacturing-teams-templates-in-the-admin-console.md)
- [零售模板](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>模板大小限制

模板限制为特定数量的频道、选项卡和应用。

 > [!Note]
 > 从模板创建后，您可以向团队添加更多频道、选项卡和应用。

|功能 | 上限|
|-|-|
|每个模板的频道 | 岁 |
|模板中每个通道的选项卡 | 名 |
|每个模板的应用 | 50|
|||

有关详细信息，请参阅 [团队的限制和规范](limits-specifications-teams.md) 。

## <a name="related-topics"></a>相关主题

- [创建自定义团队模板](create-a-team-template.md)
- [从现有团队模板创建团队模板](create-template-from-existing-template.md)
- [从现有团队创建模板](create-template-from-existing-team.md)
