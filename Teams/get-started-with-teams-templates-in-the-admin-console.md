---
title: 在管理中心内开始使用 Teams 模板
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
description: 了解团队模板以及如何在管理中心内Microsoft Teams模板。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f51c262e26613cf29a7dd2883afbf1cc6871b26
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367514"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>在管理中心内开始使用 Teams 模板

**EDU 客户尚不支持创建自定义模板。**

> [!NOTE]
> 团队模板目前不支持专用频道和敏感度标签。 专用通道创建不包括在模板定义中。 从模板流创建团队 **中的** 敏感度标签选项不会应用于该团队。

## <a name="overview"></a>概述

Microsoft Teams模板是围绕业务需求或项目设计的团队结构的定义。 作为管理员，可以使用模板轻松在整个组织中部署一致的团队。 使用模板，用户可以使用预定义的设置、通道和应用快速创建丰富的协作空间。

可以在管理中心内或Microsoft Teams PowerShell 管理团队模板。 可以使用我们提供的预建模板，也可以 [创建自己的自定义模板](#create-your-own-team-templates)。 还可以应用[模板策略](#apply-team-template-policies)来控制哪些模板可供用户在 Teams。

本文概述了在管理中心内使用Teams模板。 你将了解模板支持的属性、我们提供的预建模板、模板大小限制、如何创建和管理模板等。

> [!NOTE]
> 用户可以通过[预建的或自定义的团队模板](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)在 Teams创建团队。 开发人员还可使用 Microsoft Graph 以编程方式从预建的团队模板创建团队。 若要了解有关详细信息，请参阅[开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)。

## <a name="team-template-capabilities"></a>团队模板功能

团队模板包含并支持团队中的大多数属性。 但是，目前不支持一些属性和功能。 下面是包含的内容以及团队模板中未包含的内容的摘要。

| **团队模板支持的团队属性** | **团队模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 频道设置 |
| 团队可见性 (公共或专用)  | 连接器 |
| 团队设置 (例如成员、来宾、@ 提及)  | 文件和内容 |
| Autofavorite 通道 | |
| 已安装的应用 | |
| 固定的选项卡 | |

> [!NOTE]
> 我们将在将来的 Microsoft Teams 版本中添加更多模板功能，因此请返回查看有关受支持属性的最新版本信息。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>在管理中心内预构建Teams模板

以下是在管理中心内提供的预建Teams模板。 预构建模板是我们为特定行业创建的模板。 若要查看这些模板，在管理中心左侧导航Teams，转到"Teams  >  **模板"。**

可以复制预构建的模板，但不能编辑它们。 如果要更改预构建模板中的属性，可以从现有模板创建新模板，然后添加或删除需要的属性。 请记住，某些模板中的某些属性无法更改。

| 模板类型 | TemplateId | 此基本模板包含的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 采用Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  频道： <ul><li>常规</li> <li>公告</li> <li>冠军角</li> <li>团队表单</li><li>日历</li></ul> 应用： <ul><li>Wiki</li>  <li>频道日历</li> <li>里程碑</li><li>公告</li></ul>|
| 管理项目 |`com.microsoft.teams.template.ManageAProject`| 频道： <ul><li>常规</li> <li>公告</li> <li>资源</li> <li>规划</li></ul> 应用：<ul><li>Wiki</li><li>OneNote</li><li>任务</li><li>列表</li><li>Power Automate</li></ul> |
| 管理事件|`com.microsoft.teams.template.ManageAnEvent` | 频道： <ul><li>常规</li> <li>公告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和 PR</li></ul> 应用：<ul><li>Wiki</li><li>网站</li> <li>YouTube</li> <li>任务</li> <li>OneNote</li> <li>员工想法</li> <li>问题发布者</li><li>Power Automate</li><li>公告</li><li>里程碑</li></ul> |
|培训员工|`com.microsoft.teams.template.OnboardEmployees` | 频道： <ul><li>常规</li> <li>公告</li> <li>员工聊天</li> <li>培训</li></ul>应用：<ul><li>Wiki</li><li>社区</li><li>任务</li><li>员工想法</li><li>Power Automate</li><li>公告</li><li>里程碑</li></ul>|
|组织技术支持| `com.microsoft.teams.template.OrganizeHelpDesk`|频道：<ul><li>常规</li><li>公告</li><li>常见问题</li></ul>应用：<ul><li>Wiki</li><li>OneNote</li><li>任务 </li><li>表扬</li><li>问题发布者</li><li>Power Automate</li><li>公告</li></ul> |
| 患者护理| `com.microsoft.teams.template.healthcareWard`| 频道：<ul><li>常规</li><li>公告</li><li>小型会议室</li><li>循环配置</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>Wiki</li><li>列表  </li><li>审批</li><li>公告</li><li>检查</li></ul>|
| 应对问题沟通 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 频道： <ul><li>常规<li>公告</li><li>世界新闻</li><li>内部通信</li><li>外部通信</li><li>审批请求</li><li>客户升级</li><li>高管更新</li><li>规划</li><li>后勤工作</li></ul>应用： <ul><li>网站</li><li>任务</li><li>问题发布者</li><li>审批</li><li>公告</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|银行分支机构| `com.microsoft.teams.template.CollaborateWithinABankBranch`|频道： <ul><li>常规<li>公告</li><li>小型会议室</li><li>客户会议</li><li>审批请求 </li><li>指导</li><li>技能开发</li><li>贷款处理</li><li>客户投诉</li><li>称赞</li><li>有趣的内容</li><li>合规性</li></ul>应用：<ul><li>表扬 </li><li>问题发布者</li><li>Wiki</li><li>日历</li><li>审批</li><li>公告</li><li>想法</li></ul>|
|事件响应| `com.microsoft.teams.template.CoordinateIncidentResponse`|频道： <ul><li>常规<li>公告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>紧急</li></ul> 应用： <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>任务</li> <li>审批</li> <li>检查</li> <li>Power Automate</li><li>公告</li><li>里程碑</li></ul>|
|医院| `com.microsoft.teams.template.healthcareHospital` |频道： <ul><li>常规</li><li>公告</li><li>合规性</li><li>保管</li><li>人力资源</li><li>药房</li></ul> 应用： <ul><li>Wiki</li><li>列表</li><li>任务</li><li>审批</li><li>排班</li><li>公告</li><li>检查</li><li>想法</li></ul>|
|组织商店| `com.microsoft.teams.template.retailStore` |频道： <ul><li>常规<li>换班</li><li>应用商店准备就绪</li><li>学习</li></ul> 应用： <ul><li>Wiki</li><li>任务</li><li>排班</li><li>检查</li></ul>|
|适用于经理的零售| `com.microsoft.teams.template.retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li><li>任务</li><li>检查</li></ul>|
|质量和安全 |`com.microsoft.teams.template.QualitySafety`|频道： <ul><li>常规<li>公告</li><li>领导</li><li>维护</li><li>生产线 1</li><li>生产线 2</li><li>生产线 3</li><li>运行状况和安全性</li><li>培训</li><li>有趣的内容</li></ul> 应用： <ul><li>Wiki</li><li>任务</li> <li>问题发布者</li> <li>检查</li> </ul>|

### <a name="team-templates-by-category-and-industry"></a>按类别和行业分类的团队模板

有关在行业中使用预建模板的方法详细信息，请参阅：

- [财务团队模板](financial-teams-templates-in-the-admin-console.md)
- [常规团队模板](general-teams-templates-in-the-admin-console.md)
- [政府团队模板](government-teams-templates-in-the-admin-console.md)
- [医疗保健团队模板](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [制造团队模板](manufacturing-teams-templates-in-the-admin-console.md)
- [零售团队模板](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>团队模板大小限制

模板限制为特定数量的通道、选项卡和应用。

 > [!Note]
 > 从模板创建团队后，你可以向团队添加更多频道、选项卡和应用。

|功能 | 限制|
|-|-|
|每个模板的频道数 | 15 |
|模板中每个通道的选项卡数 | 20 |
|每个模板的应用数 | 50|
|||

有关详细信息，请参阅 Teams 的限制[和Teams。](limits-specifications-teams.md)

## <a name="manage-team-templates"></a>管理团队模板

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

#### <a name="view-team-templates"></a>查看团队模板

若要查看团队模板，在管理中心左侧导航Teams，转到"Teams  >  **模板"。** 选择一个模板以查看更多详细信息，包括它包含的通道和应用。

#### <a name="create-your-own-team-templates"></a>创建自己的团队模板

可以从现有团队和现有模板从头开始创建自己的自定义模板。 若要了解详细信息，请参阅：

- [创建自定义团队模板](create-a-team-template.md)
- [从现有团队创建模板](create-template-from-existing-team.md)
- [从现有团队模板创建团队模板](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>应用团队模板策略

若要控制用户在创建团队时Teams模板，可以设置模板策略并将其[](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)分配给组织的用户和组。 若要了解有关详细信息，请参阅管理中心[中的Teams模板](templates-policies.md)。

### <a name="manage-team-templates-using-powershell"></a>使用 PowerShell 管理团队模板

使用以下 cmdlet 在 PowerShell 中管理模板。

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>相关文章

- [基于模板创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)
- [克隆团队](/graph/api/team-clone?view=graph-rest-1.0&tabs=http)
