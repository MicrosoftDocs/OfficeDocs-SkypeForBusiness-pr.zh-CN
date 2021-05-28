---
title: 零售版团队模板入门
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何通过提供预定义的设置、频道和预安装的应用，使用团队模板创建专为零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684550"
---
# <a name="create-a-team-using-retail-team-templates"></a>使用零售团队模板创建团队

Microsoft 团队模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。

团队模板具有围绕零售商需求设计的团队结构的预构建定义。 可以使用团队模板快速创建适合零售商的团队类型，并在整个组织中部署它们。 还可以扩展团队模板，创建根据特定组织需求定制的团队。

本文介绍每个团队模板，并推荐其使用方法。

如果你负责在整个零售组织中规划、部署和管理多个团队，则本文非常适合你。 你已在贵组织内部署 Teams 服务。 如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。

若要了解有关团队模板的一般信息，请参阅 [团队模板入门](get-started-with-teams-templates.md)。

| 人员 | 使用方法： |
| ---- | --------- |
| 管理员和 IT 专业人员 | [使用Teams管理中心](#use-the-team-templates-in-the-teams-admin-center)基于零售团队模板创建团队。|
| 开发人员和系统整合者 | [使用 Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph)基于零售团队模板创建团队。 |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a>使用管理中心中的Teams模板

### <a name="organize-a-store"></a>组织商店

将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。 整合其他应用程序，以简化轮班开始和结束流程。

| 基本模板类型 |baseTemplateId | 此基本模板包含的属性 |
| ------------------|-- |----------------------------------------------------- |
|组织商店|`retailStore`|频道： <ul><li>常规<li>换班</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>经理协作

管理器协作模板非常适合创建一个团队，供一组经理跨商店/区域等进行协作。例如，如果您的组织有区域，您可以为加利福尼亚州创建经理协作团队，并包括该区域的所有商店经理以及该区域的区域经理。

| 基本模板类型| baseTemplateId | 此基本模板包含的属性 |
| ------------------|- |----------------------------------------------------- |
|零售 - 经理协作|`retailManagerCollaboration` |频道： <ul><li>常规<li>运营</li><li>学习</li></ul> 应用： <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a>将团队模板与 Microsoft Graph

### <a name="store-template"></a>商店模板

商店模板非常适合用于创建一个团队来代表单个零售商店位置。 通过使用商店模板，你可以为组织中的每个零售商店位置创建一个团队。

| 基本模板类型 | baseTemplateId | 此基本模板包含的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售 - <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 频道 <ul><li>换班\*</li><li>学习\*</li></ul>\*自动收藏的频道<br><br>团队属性 <ul><li>团队可见性设置为“公共”</li></ul> <br>成员权限 <ul><li>无法创建/更新/删除频道 </li><li>无法添加/删除应用 </li><li>无法创建/更新/删除选项卡</li><li>无法创建/更新/删除连接器</li><ul>|
||||

为组织自定义商店模板的建议方法：

- 如果你的组织在每个商店都有部门，请为每个部门添加一个频道。 添加频道可促进部门之间的沟通和协作。

- 如果你的组织具有任何内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。 有关 [说明，请参阅团队模板](get-started-with-teams-templates.md) 入门。

### <a name="manager-collaboration-template"></a>经理协作模板

管理器协作模板是围绕零售商需求设计的另一个团队模板。 经理协作模板非常适合用于创建一个团队，供一组经理跨商店/地区进行协作等。 例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，并包括该地区的所有商店经理以及该地区的区域经理。

| 基本模板类型 | baseTemplateId | 此基本模板包含的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售 - <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 频道 <ul><li>运营\*</li><li>学习\*</li></ul>\*自动收藏的频道<br><br>团队属性 <ul><li>团队可见性设置为“专用”</li></ul> <br>成员权限 <ul><li>可创建/更新/删除频道 </li><li>可添加/删除应用 </li><li>可创建/更新/删除选项卡</li><li>可创建/更新/删除连接器</li><ul>|
||||

为组织自定义经理协作模板的建议方法：

- 如果你的组织具有任何与经理相关的内部网站（例如 SharePoint 网站），请考虑将其固定为相关团队频道中的选项卡。 有关说明，请参阅 Microsoft [团队模板](get-started-with-teams-templates.md) 文档。

## <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

若要使用这些模板，请将请求正文中的“template@odata.bind”属性从“标准”更改为上述模板 ID。  若要详细了解如何部署团队模板，请参阅 Microsoft Graph文章，了解如何[创建团队](/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 模板中的频道将自动创建在“常规”选项卡下方。

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
