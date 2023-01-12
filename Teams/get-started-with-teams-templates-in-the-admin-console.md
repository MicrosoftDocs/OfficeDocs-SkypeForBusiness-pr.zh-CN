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
- m365-frontline
- tier2
- highpri
description: 了解团队模板以及如何在 Microsoft Teams 管理中心对其进行管理。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 063f84ffc0b34c99ff937c4a5496d5df3be2ddf5
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778982"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>在管理中心内开始使用 Teams 模板

**EDU 客户尚不支持创建自定义模板的功能。**

> [!NOTE]
> - 团队模板当前不支持专用频道和共享频道。 专用通道和共享通道创建不包括在模板定义中。
>
> - GCC 环境中的团队模板不支持敏感度标签。 从模板创建团队流中的敏感度标签选项不会应用于团队。

## <a name="overview"></a>概述

Microsoft Teams 中的团队模板是围绕业务需求或项目设计的团队结构的定义。 作为管理员，你可以使用模板在组织中轻松部署一致的团队。 借助模板，用户可以使用预定义的设置、频道和应用快速创建丰富的协作空间。

可以在 Microsoft Teams 管理中心或使用 PowerShell 管理团队模板。 可以使用我们提供的预生成模板，还可以 [创建自己的自定义模板](#create-your-own-team-templates)。 还可以 [应用模板策略](#apply-team-template-policies) 来控制哪些模板可供 Teams 中的用户使用。

本文概述了如何在 Teams 管理中心使用团队模板。 你将了解模板中支持的属性、我们提供的预生成模板、模板大小限制、如何创建和管理模板等。

> [!NOTE]
> 用户可以 [从 Teams 应用中的预生成或自定义团队模板创建团队](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) 。 开发人员还可以使用 Microsoft Graph 从预生成或自定义团队模板以编程方式创建团队。 若要了解详细信息，请参阅 [使用 Microsoft Graph 开始使用团队模板](get-started-with-teams-templates.md)。

## <a name="team-template-capabilities"></a>团队模板功能

团队模板包含并支持团队中的大多数属性。 但目前不支持一些属性和功能。 下面是团队模板中包含的内容和未包含的内容的摘要。

| **团队模板支持的团队属性** | **团队模板尚不支持的团队属性** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 模板类型 | 团队成员资格 |
| 团队名称 | 团队图片 |
| 团队说明 | 通道设置 |
| 公共或专用)  (团队可见性 | 连接器 |
| 团队设置 (例如，成员、来宾、@ 提及)  | 文件和内容 |
| Autofavorite 通道 | |
| 已安装的应用 | |
| 固定选项卡 | |

> [!NOTE]
> 我们将在 Microsoft Teams 的未来版本中添加更多模板功能，因此请回来查看有关受支持属性的最新信息。

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Teams 管理中心中的预生成团队模板

下面是 Teams 管理中心中提供的预生成团队模板。 预建模板是我们为特定行业创建的模板。 若要查看这些模板，请在 Teams 管理中心的左侧导航中转到 **Teams** > **团队模板**。

可以复制预生成的模板，但不能对其进行编辑。 如果要更改预生成模板中的属性，可以从现有模板创建新模板，然后添加或删除所需的属性。 请记住，某些模板中的某些属性无法更改。

> [!NOTE]
> 星号 (*) 指示该模板是 *Microsoft 365 连接的模板*。 当用户使用模板创建团队时，连接的 SharePoint 模板将应用于网站和团队。 SharePoint 组件（如页面、列表和 Power Platform 集成）会自动添加并固定为选项卡到团队中的“常规”频道。 用户可以直接从 Teams 中编辑这些页面和列表。
>
> 若要了解有关 SharePoint 模板的详细信息，请参阅 [应用和自定义 SharePoint 网站模板](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)。

>[!div class="mx-tdBreakAll"]
>| 模板类型 | TemplateId | 此基本模板包含的属性 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>|管理项目* |`com.microsoft.teams.template.ManageAProject`| 频道： <ul><li>常规</li> <li>公告</li> <li>资源</li> <li>规划</li></ul> 应用：<ul><li>审批</li><li>公告</li><li>列表<ul><li>项目跟踪器</li><li>问题跟踪器</li></ul></li><li>里程碑</li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>我们的站点</li></ul></li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul> |
|管理事件*|`com.microsoft.teams.template.ManageAnEvent` | 频道： <ul><li>常规</li> <li>公告</li> <li>预算</li> <li>内容</li><li>后勤工作</li> <li>规划</li> <li> 市场营销和公关</li></ul> 应用：<ul><li>审批</li><li>公告</li> <li>员工想法</li><li>列表<ul><li>内容计划程序</li></ul></li><li>里程碑</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint Pages<ul><li>我们的站点</li><li>关于我们的活动</li></ul><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li> |
|加入员工*|`com.microsoft.teams.template.OnboardEmployees` | 频道： <ul><li>常规</li> <li>公告</li> <li>员工聊天</li> <li>培训</li></ul>应用：<ul><li>公告</li><li>员工想法</li><li>列表<ul><li>载入清单</li></ul></li><li>里程碑</li><li>Power Automate</li> <li>SharePoint Pages<ul><li>开始使用</li><li>培训</li></ul><li>按 Planner 和 To Do 完成的任务</li><li>Viva Engage</li><li>Wiki</li></ul>|
|采用Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  频道： <ul><li>常规</li> <li>公告</li> <li>冠军角</li> <li>团队表单</li><li>日历</li></ul> 应用： <ul><li>公告</li>  <li>频道日历</li> <li>里程碑</li><li>Wiki</li></ul>|
|组织技术支持*| `com.microsoft.teams.template.OrganizeHelpDesk`|频道：<ul><li>常规</li><li>公告</li><li>常见问题</li></ul>应用：<ul><li>问题报告</li><li>列表<ul><li>设备</li><li>票</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>我们的站点</li><li>常见问题解答</li></ul></li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul> |
|事件响应| `com.microsoft.teams.template.CoordinateIncidentResponse`|频道： <ul><li>常规<li>公告</li><li>后勤工作</li><li>规划</li><li>恢复</li><li>紧急</li></ul> 应用： <ul><li>审批</li><li>公告</li><li>Excel</li><li>检查</li><li>里程碑</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|
|危机通信* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 频道： <ul><li>常规<li>公告</li><li>高管更新</li><li>规划</li><li>后勤工作</li></ul>应用： <ul><li>审批</li><li>问题报告</li><li>列表<ul><li>内容计划程序</li><li>项目计划</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>我们的站点</li><li>最新更新</li></ul><li>按 Planner 和 To Do 完成的任务</li>|
|管理应用商店*| `com.microsoft.teams.template.retailStore` |频道： <ul><li>常规<li>Shift Handoff</li><li>存储就绪情况</li><li>学习</li></ul> 应用： <ul><li>审批</li><li>检查</li><li>列表<ul><li>清单列表</li></ul></li><li>SharePoint Pages<ul><li>我们的商店</li></ul></li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|
|银行分行| `com.microsoft.teams.template.CollaborateWithinABankBranch`|频道： <ul><li>常规<li>公告</li><li>小型会议室</li><li>客户会议</li><li>审批请求 </li><li>指导</li><li>技能开发</li><li>贷款处理</li><li>客户投诉</li><li>称赞</li><li>有趣的内容</li><li>合规性</li></ul>应用：<ul><li>审批</li><li>公告</li><li>频道日历</li><li>员工想法</li><li>问题报告</li><li>表扬</li><li>排班</li><li>Wiki</li></ul>|
|患者护理| `com.microsoft.teams.template.healthcareWard`| 频道：<ul><li>常规</li><li>公告</li><li>小型会议室</li><li>循环配置</li><li>人员配备</li><li>培训</li></ul> 应用： <ul><li>审批</li><li>公告</li><li>检查</li><li>列表</li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|
|医院| `com.microsoft.teams.template.healthcareHospital` |频道： <ul><li>常规</li><li>公告</li><li>合规性</li><li>保管</li><li>人力资源</li><li>药房</li></ul> 应用： <ul><li>审批</li><li>公告</li><li>员工想法</li><li>检查</li><li>列表</li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|
|质量与安全 |`com.microsoft.teams.template.QualitySafety`|频道： <ul><li>常规</li><li>领导</li><li>维护</li><li>生产线 1</li><li>生产线 2</li><li>生产线 3</li><li>健康和安全</li><li>培训</li><li>有趣的内容</li></ul> 应用： <ul><li>审批</li><li>检查</li><li>问题报告</li><li>排班</li> <li>按 Planner 和 To Do 完成的任务</li> <li>Wiki</li> </ul>|
|面向经理的零售*| `com.microsoft.teams.template.retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>审批</li><li>检查</li><li>SharePoint Pages<ul><li>我们的商店</li></ul></li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|
|管理志愿者| `com.microsoft.teams.template.ManageVolunteers` |频道： <ul><li>常规<li>公告</li><li>报告</li><li>志愿者管理</li><li>参与机会</li><li>志愿者登录</li></ul> 应用： <ul><li>OneNote</li><li>Power Apps</li><li>Power BI</li><li>SharePoint</li><li>按 Planner 和 To Do 完成的任务</li><li>网站</li><li>YouTube</li></ul>|
|一线协作| `com.microsoft.teams.template.Frontline` |频道： <ul><li>常规<li>公告</li><li>Shift Handoff</li><li>运营</li><li>学习</li></ul> 应用： <ul><li>审批</li><li>问题报告</li><li>列表</li><li>表扬</li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>按类别和行业划分的团队模板

有关在行业内使用预生成模板的方法的详细信息，请参阅：

- [常规团队模板](general-teams-templates-in-the-admin-console.md)
- [财务团队模板](financial-teams-templates-in-the-admin-console.md)
- [政府团队模板](government-teams-templates-in-the-admin-console.md)
- [医疗保健团队模板](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [制造团队模板](manufacturing-teams-templates-in-the-admin-console.md)
- [非营利组织团队模板](team-templates-nonprofit.md)
- [零售团队模板](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>团队模板大小限制

模板限制为特定数量的通道、选项卡和应用。

 > [!Note]
 > 从模板创建团队后，可以向团队添加更多频道、选项卡和应用。

|功能 | 限制|
|-|-|
|每个模板的通道数 | 15 |
|模板中每个通道的选项卡数 | 20 |
|每个模板的应用数 | 50|

有关详细信息，请参阅 [Teams 的限制和规范](limits-specifications-teams.md)。

## <a name="manage-team-templates"></a>管理团队模板

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

#### <a name="view-team-templates"></a>查看团队模板

若要查看团队模板，请在 Teams 管理中心的左侧导航中转到 **“Teams** > **团队模板**”。 选择模板以查看更多详细信息，包括其包含的频道和应用。

#### <a name="create-your-own-team-templates"></a>创建自己的团队模板

可以从头开始、从现有团队和现有模板创建自己的自定义模板。 若要了解详细信息，请参阅：

- [创建自定义团队模板](create-a-team-template.md)
- [从现有团队创建模板](create-template-from-existing-team.md)
- [从现有团队模板创建团队模板](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>应用团队模板策略

若要控制用户在 Teams 中看到的用于 [创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)的模板，可以设置模板策略并将其分配给组织中的用户和组。 若要了解详细信息，请参阅 [在 Teams 管理中心中管理团队模板](templates-policies.md)。

### <a name="manage-team-templates-using-powershell"></a>使用 PowerShell 管理团队模板

使用以下 cmdlet 在 PowerShell 中管理模板。

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>相关文章

- [基于模板创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)
- [克隆团队](/graph/api/team-clone)
- [Teams 和 SharePoint 集成概述](/sharepoint/teams-connected-sites)
