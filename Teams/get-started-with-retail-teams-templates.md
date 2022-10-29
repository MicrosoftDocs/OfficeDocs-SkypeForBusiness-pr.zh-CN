---
title: 使用零售团队模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何管理和使用 Teams 管理中心和 Microsoft Graph 中的零售团队模板，以快速轻松地为零售组织创建团队。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39b474231c2dcd536684514853a34672100801e5
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784307"
---
# <a name="use-retail-team-templates"></a>使用零售团队模板

## <a name="overview"></a>概述

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于零售商，团队模板可能特别强大，因为它们可帮助你在整个组织中快速部署一致的团队。 模板还可帮助员工了解如何有效地使用Teams。

Teams 包括专为零售商需求设计的模板。 使用这些预建模板快速创建团队，让员工进行沟通和协作。 在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。

如何管理和使用团队模板取决于你是管理人员还是开发人员。

|如果是： | 然后，可以： |
| ---- | --------- |
| 管理人员或 IT 专业人员 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 开发人员 | [使用 Microsoft Graph ](#use-team-templates-with-microsoft-graph) 从团队模板中创建团队。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

作为管理人员，你可以在 Microsoft Teams 管理中心内管理团队模板。 可在此处查看有关每个模板的详细信息。 还可以[创建模板策略](templates-policies.md)并将其分配给员工，以确定在 Teams 中使用哪些模板来[创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)。

若要了解有关团队模板的详细信息，请参阅[管理中心的 Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

我们当前提供以下预建的零售团队模板。 若要查看，请在 Teams 管理中心的左侧导航栏中，转到 **Teams** > **团队模板**。

> [!NOTE]
> 星号 (*) 指示该模板是 *Microsoft 365 连接的模板*。 当用户使用模板创建团队时，连接的 SharePoint 模板将应用于网站和团队。 SharePoint 组件（如页面、列表和 Power Platform 集成）会自动添加并固定为选项卡到团队中的“常规”频道。 用户可以直接从 Teams 中编辑这些页面和列表。
>
> 若要了解有关 SharePoint 模板的详细信息，请参阅 [应用和自定义 SharePoint 网站模板](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)。

### <a name="manage-a-store"></a>管理应用商店*

将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。 集成其他应用程序以简化班次开始和结束流程。

> [!div class="mx-tdBreakAll"]
>| 模板类型 |TemplateId | 此基本模板包含的属性 |
>| ------------------|-- |----------------------------------------------------- |
>| 管理应用商店| `retailStore` |频道： <ul><li>常规<li>Shift Handoff</li><li>存储就绪情况</li><li>学习</li></ul> 应用： <ul><li>审批</li><li>检查</li><li>列表<ul><li>清单列表</li></ul></li><li>SharePoint Pages<ul><li>我们的商店</li></ul></li><li>排班</li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>面向经理的零售*

为一组经理创建团队，以便跨商店或区域进行协作。 例如，如果你的组织具有区域，则可以为加州区域创建一个团队，并包括该区域中的所有商店经理以及该区域的区域经理。

> [!div class="mx-tdBreakAll"]
>| 模板类型| TemplateId | 此基本模板包含的属性 |
>| ------------------|- |----------------------------------------------------- |
>| 零售经理| `retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>审批</li><li>检查</li><li>SharePoint Pages<ul><li>我们的商店</li></ul></li><li>按 Planner 和 To Do 完成的任务</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一起使用

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

下面是预建的医疗保健团队模板。

> [!NOTE]
> 星号 (*) 指示该模板是 *Microsoft 365 连接的模板*。 当用户使用模板创建团队时，连接的 SharePoint 模板将应用于网站和团队。 SharePoint 组件（如页面、列表和 Power Platform 集成）会自动添加并固定为选项卡到团队中的“常规”频道。 用户可以直接从 Teams 中编辑这些页面和列表。
>
> 若要了解有关 SharePoint 模板的详细信息，请参阅 [应用和自定义 SharePoint 网站模板](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)。

### <a name="manage-a-store"></a>管理应用商店*

使用此模板为组织中的每个零售商店位置创建团队。

> [!div class="mx-tdBreakAll"]
>| 模板类型 | TemplateId | 模板频道 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 零售 - <br>商店 | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| 频道 <ul><li>常规</li><li>Shift Handoff</li><li>存储就绪情况</li><li>学习</li></ul>团队属性 <ul><li>团队可见性设置为“公共”</li></ul> <br>成员权限 <ul><li>无法创建、更新或删除频道 </li><li>无法添加或删除应用 </li><li>无法创建、更新或删除选项卡</li><li>无法创建、更新或删除连接器</li><ul>|

为组织自定义商店模板的建议方法：

- 如果你的组织在每个商店都有部门，请为每个部门添加一个频道。 添加频道可促进部门之间的沟通和协作。

- 如果你的组织具有任何内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。

### <a name="retail-for-managers"></a>面向经理的零售*

使用此模板为一组经理创建团队，以便跨商店或区域进行协作。 例如，如果你的组织具有区域，则可以为加州区域创建一个团队，并包括该区域中的所有商店经理以及该区域的区域经理。

> [!div class="mx-tdBreakAll"]
>| 模板类型 | TemplateId | 模板频道 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 零售 - <br>经理协作 | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| 频道 <ul><li>常规</li><li>运营</li><li>学习</li></ul>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> <br>成员权限 <ul><li>可以创建、更新和删除频道 </li><li>可以添加和删除应用 </li><li>可以创建、更新和删除选项卡</li><li>可以创建、更新和删除连接器</li><ul>|

为组织自定义经理协作模板的建议方法：

- 如果你的组织具有任何与经理相关的内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>如何将团队模板与 Microsoft Graph 配合使用

若要使用这些模板，请将请求正文中的“template@odata.bind”属性从“标准”更改为上面的 Templatelds。  若要详细了解如何部署团队模板，请参阅 Microsoft Graph 文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 模板中的频道将自动创建在“**常规**”选项卡下方。

### <a name="example-store-template-extension-script"></a>示例：商店模板扩展脚本

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```

> [!NOTE]
> 如果使用 Microsoft Graph 从现有 Microsoft 365 组或使用 Microsoft 365 连接模板的团队创建团队，则连接的 SharePoint 模板不会自动应用于网站或团队。 创建团队后，需要手动应用 SharePoint 网站模板。 在 Teams 中，转到团队，选择右上角的“ **更多选项”** > **SharePoint 中打开**。 然后选择 **“设置** > **”“应用网站模板** ”并选择相应的网站模板。

## <a name="related-articles"></a>相关文章

- [在管理中心内开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)
- [基于模板创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)