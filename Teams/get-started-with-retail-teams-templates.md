---
title: 在零售业工作组模板入门
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用工作组模板创建团队结构设计零售商需求。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664705"
---
# <a name="get-started-with-teams-templates-in-retail"></a>在零售业工作组模板入门 

工作组模板允许您快速和轻松创建团队提供的预定义的模板的设置、 通道和预安装的应用程序。

工作组模板具有预建的团队结构围绕零售商需求而设计的定义。 工作组模板可用于快速创建适用于零售商并将它们部署在整个组织的团队的类型。 您还可以扩展工作组模板创建适合您组织的特定需求的团队。

本文中，我们将介绍每个工作组模板和我们建议使用它们。

本文适用于您，如果您是负责规划、 部署和管理多个团队整个组织零售。

若要详细了解团队模板通常情况下，请参阅[入门工作组模板](get-started-with-teams-templates.md)。

## <a name="store-template"></a>存储模板

存储模板非常适合于创建团队表示单个零售存储位置。 使用存储模板时，可以创建您的组织中的每个零售店铺团队。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售- <br>存储 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 频道 <ul><li>引进提交\*</li><li>学习\*</li></ul>\*自动 favorited 通道<br><br>团队属性 <ul><li>设置为 Public 工作组可见性</li></ul> <br>成员权限 <ul><li>无法创建/更新/删除通道 </li><li>无法添加/删除应用程序 </li><li>无法创建/更新/删除选项卡</li><li>无法创建/更新/删除连接器</li><ul>|
||||

建议使用自定义您的组织的存储区模板的方法：

- 如果您的组织内每个存储有部门，添加为每个部门的通道。 这将有助于通信和部门的协作。

- 如果您的组织有任何内部网站 （例如，SharePoint 网站），请考虑这些固定用作相关团队通道中的选项卡。 有关说明，请参阅[入门工作组模板](get-started-with-teams-templates.md)。

## <a name="manager-collaboration-template"></a>管理器协作模板

另一个设计零售商周围的工作组模板需要的管理器协作模板。 管理器协作模板非常适合于创建一组管理跨存储/地区等协作的团队。例如，如果您的组织具有区域，您可能为加利福尼亚地区创建管理器协作工作组和包括在该区域中，所有存储区管理器，以及为该区域的区域管理器。

| 基本模板类型 | baseTemplateId | 此基本模板附带的属性 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 零售- <br>存储 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 频道 <ul><li>运营\*</li><li>学习\*</li></ul>\*自动 favorited 通道<br><br>团队属性 <ul><li>设置为 Private 工作组可见性</li></ul> <br>成员权限 <ul><li>可以创建/更新/删除通道 </li><li>可以添加/删除应用程序 </li><li>可以创建/更新/删除选项卡</li><li>可以创建/更新/删除连接器</li><ul>|
||||

建议使用自定义您的组织的管理器协作模板的方法：

- 如果您的组织相关经理任何内部网站 （例如，SharePoint 网站），请考虑这些固定用作相关团队通道中的选项卡 (参考文档[此处](get-started-with-teams-templates.md)的说明)。