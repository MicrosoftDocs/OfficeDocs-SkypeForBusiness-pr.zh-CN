---
title: 开始使用 Teams 零售模板
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
description: 了解如何使用团队模板，通过提供预定义设置、信道和预安装应用来创建用于零售商需求的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b170047a3b8d3218b8e31bdc9d4b1035eb8706c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583199"
---
# <a name="get-started-with-teams-templates-in-retail"></a>开始使用 Teams 零售模板 

团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。

团队模板具有围绕零售商需求设计的团队结构的预建定义。 你可以使用团队模板快速创建适用于零售商的团队类型，并在组织中部署这些团队。 您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。

在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。

本文适用于您负责在您的零售组织中规划、部署和管理多个团队的情况。 我们假定你的组织中已部署团队服务。 如果尚未推出团队，请先阅读[如何展示 Microsoft 团队](How-to-roll-out-teams.md)。

若要深入了解有关团队模板的详细信息，请参阅[团队模板入门](get-started-with-teams-templates.md)。

## <a name="store-template"></a>存储模板

应用商店模板是创建团队以表示单个零售商店位置的理想之选。 使用应用商店模板，您可以为您的组织中的每个零售商店位置创建一个团队。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 面向 <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 频道 <ul><li>班次切换\*</li><li>培训\*</li></ul>\*自动收藏频道<br><br>团队属性 <ul><li>将团队可见性设置为公共</li></ul> <br>成员权限 <ul><li>无法创建/更新/删除频道 </li><li>无法添加/删除应用程序 </li><li>无法创建/更新/删除选项卡</li><li>无法创建/更新/删除连接器</li><ul>|
||||

为你的组织自定义应用商店模板的建议方法：

- 如果您的组织在每个商店中都有部门，请为每个部门添加一个频道。 这将促进部门内的沟通和协作。

- 如果您的组织有任何内部网站 (例如 SharePoint 网站) ，请考虑将它们固定为相关团队频道中的选项卡。 有关说明，请参阅[团队模板入门](get-started-with-teams-templates.md)。

## <a name="manager-collaboration-template"></a>经理协作模板

经理协作模板是围绕零售商的需求而设计的另一个团队模板。 经理协作模板非常适合为一组经理创建团队，以便在商店/地区等协作。例如，如果您的组织拥有区域，则可以为加利福尼亚地区创建经理协作团队，并包括该地区的所有商店经理以及该地区的地区经理。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 面向 <br>商店 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 频道 <ul><li>运营\*</li><li>培训\*</li></ul>\*自动收藏频道<br><br>团队属性 <ul><li>将团队可见性设置为私密</li></ul> <br>成员权限 <ul><li>可以创建/更新/删除频道 </li><li>可以添加/删除应用程序 </li><li>可以创建/更新/删除选项卡</li><li>可以创建/更新/删除连接器</li><ul>|
||||

为你的组织自定义经理协作模板的推荐方法：

- 如果您的组织具有任何内部网站 (例如，与经理相关的 SharePoint 网站) ，请考虑将它们固定为相关团队频道中的选项卡。 有关说明，请参阅[Microsoft 团队模板文档](get-started-with-teams-templates.md)。

## <a name="how-to-use-first-party-templates"></a>如何使用第一方模板

若要使用这些模板，只需将请求正文中的 "template@odata bind" 属性从 "standard" 更改为上述 TemplateIDs。  有关如何部署团队模板的详细信息，请参阅 Microsoft Graph 有关如何[创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)的文章。

> [!NOTE]
> 模板中的频道将在 "常规" 选项卡下自动创建。

### <a name="example-store-template-extension-script"></a>示例：存储模板扩展脚本

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
