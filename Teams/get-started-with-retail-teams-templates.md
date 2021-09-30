---
title: 使用零售团队模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
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
ms.openlocfilehash: 073d9ee391b42a476b0657dbf910f8d019699358
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991201"
---
# <a name="use-retail-team-templates"></a>使用零售团队模板

通过提供预定义设置、频道和预安装的应用模板，Microsoft Teams 模板让你能够快速轻松地创建团队。

对于零售商，团队模板可能特别强大，因为它们可帮助你在整个组织中快速部署一致的团队。 模板还可帮助员工了解如何有效地使用Teams。

Teams 包括专为零售商需求设计的模板。 使用这些预建模板快速创建团队，让员工进行沟通和协作。 在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。

如何管理和使用团队模板取决于你是管理人员还是开发人员。

|如果是： | 然后，可以： |
| ---- | --------- |
| 管理人员或 IT 专业人员 |[管理中心的 Teams 模板](#manage-team-templates-in-the-teams-admin-center)。 查看团队模板，并应用模板策略，确定员工可以在 Teams 中使用哪些模板来创建团队。 |
| 开发人员 | [使用 Microsoft Graph ](#use-team-templates-with-microsoft-graph) 从团队模板中创建团队。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

作为管理人员，你可以在 Microsoft Teams 管理中心内管理团队模板。 可在此处查看有关每个模板的详细信息。 还可以[创建模板策略](templates-policies.md)并将其分配给员工，以确定在 Teams 中使用哪些模板来[创建团队](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)。 

若要了解有关团队模板的详细信息，请参阅[管理中心的 Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

我们当前提供以下预建的零售团队模板。 若要查看，请在 Teams 管理中心的左侧导航栏中，转到 **Teams** > **团队模板**。

### <a name="organize-a-store"></a>组织商店

将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。 整合其他应用程序，先从简化排版开始，然后是结束流程。

| 模板类型 |TemplateId | 此基本模板包含的属性 |
| ------------------|-- |----------------------------------------------------- |
|组织商店| `retailStore` |频道： <ul><li>常规<li>换班</li><li>应用商店准备就绪<ul><li>检查&sup1;</li></ul></li><li>学习</li></ul> 应用： <ul><li>Wiki</li><li>任务</li><li>排班</li><li>检查</li></ul>|

&sup1;将应用作为选项卡添加到频道中。

### <a name="manager-collaboration"></a>经理协作

经理协作模板非常适合一组经理创建团队，以便他们跨商店/地区进行协作等。例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，其中包括该地区的所有商店经理，以及该地区的区域经理。

| 模板类型| TemplateId | 此基本模板包含的属性 |
| ------------------|- |----------------------------------------------------- |
|适用于经理的零售|`retailManagerCollaboration` |频道： <ul><li>常规<li>运营<ul><li>任务 (操作任务) &sup1;</li><li>检查&sup1;</li></ul></li><li>学习<ul><li>任务 (学习任务) &sup1;</li></ul></li></ul> 应用： <ul><li>Wiki</li><li>任务</li><li>检查</li></ul>|
||||

&sup1;将应用作为选项卡添加到频道中。

## <a name="use-team-templates-with-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一起使用

开发人员可以使用 Microsoft Graph 从预先构建的团队模板中创建团队。 若要详细了解如何将团队模板与Microsoft Graph 配合使用，请参阅[使用 Microsoft Graph 团队模板入门](get-started-with-teams-templates.md)， [ Microsoft Teams API 概述](/graph/teams-concept-overview?view=graph-rest-1.0)，[teamsTemplate 资源类型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

下面是预建的零售团队模板。

### <a name="store"></a>应用商店

商店模板非常适合用于创建一个团队来代表单个零售商店位置。 通过使用商店模板，你可以为组织中的每个零售商店位置创建一个团队。

| 模板类型 | TemplateId | 模板频道 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售 - <br>商店 | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| 频道 <ul><li>常规</li><li>排班处理&sup2;</li><li>应用商店准备就绪</li><li>学习&sup2;</li></ul>团队属性 <ul><li>团队可见性设置为“公共”</li></ul> <br>成员权限 <ul><li>无法创建、更新或删除频道 </li><li>无法添加或删除应用 </li><li>无法创建、更新或删除选项卡</li><li>无法创建、更新或删除连接器</li><ul>|
||||

&sup2;自动收藏的频道

为组织自定义商店模板的建议方法：

- 如果你的组织在每个商店都有部门，请为每个部门添加一个频道。 添加频道可促进部门之间的沟通和协作。

- 如果你的组织具有任何内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。

### <a name="manager-collaboration"></a>经理协作

经理协作模板非常适合一组经理创建团队，以便他们跨商店/地区进行协作等。例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，其中包括该地区的所有商店经理，以及该地区的区域经理。

| 模板类型 | TemplateId | 模板频道 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售 - <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 频道 <ul><li>常规</li><li>操作&sup2;</li><li>学习&sup2;</li></ul>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> <br>成员权限 <ul><li>可以创建、更新和删除频道 </li><li>可以添加和删除应用 </li><li>可以创建、更新和删除选项卡</li><li>可以创建、更新和删除连接器</li><ul>|
||||

&sup2;自动收藏的频道

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

## <a name="related-articles"></a>相关文章

- [在管理中心内开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)
- [在 Teams 应用中的模板创建团队](https://support.microsoft.com/en-us/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)