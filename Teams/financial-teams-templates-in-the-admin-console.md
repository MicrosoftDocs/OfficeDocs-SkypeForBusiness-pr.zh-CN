---
title: 使用财务团队模板
author: lanachin
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
description: 了解如何管理和使用 Teams 管理中心和 Microsoft Graph 中的财务团队模板，以快速轻松地为金融服务组织创建团队。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9273f8519fd7aeea90ff35f49ca0d6986afa2d59
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991101"
---
# <a name="use-financial-team-templates"></a>使用财务团队模板

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于金融服务组织，团队模板可能特别强大，因为它们可帮助你在整个组织中快速部署一致的团队。 模板还可帮助员工了解如何有效地使用Teams。

Teams 包括专为金融服务组织设计的模板。 使用这些预建模板快速创建团队，让员工进行沟通和协作。 在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。

如何管理和使用团队模板取决于你是管理人员还是开发人员。

|如果是： | 然后，可以： |
| ---- | --------- |
| 管理人员或 IT 专业人员 |[管理 Teams 管理中心的团队模板](#manage-team-templates-in-the-teams-admin-center)。 查看团队模板，并应用模板策略，确定员工可以在 Teams 中使用哪些模板来创建团队。 |
| 开发人员 | [使用 Microsoft Graph ](#use-team-templates-with-microsoft-graph) 从团队模板中创建团队。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

作为管理人员，你可以在 Microsoft Teams 管理中心内管理团队模板。 可在此处查看有关每个模板的详细信息。 还可以[创建模板策略](templates-policies.md)并将其分配给员工，以确定在 Teams 中使用哪些模板来[创建团队](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)。

若要了解有关团队模板的详细信息，请参阅[管理中心的 Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

我们当前为金融服务组织提供以下预建的团队模板。 若要查看，请在 Teams 管理中心的左侧导航栏中，转到 **Teams** > **团队模板**。

### <a name="collaborate-within-a-bank-branch"></a>在银行分支机构内协作

通过碰头会、客户会议、业务流程(如按揭合作)使银行分支机构员工集中协作，并通过“公告”和“称赞”让每个人都参与其中。

| 模板类型 |TemplateId| 此基本模板包含的属性 |
| ------------------ |--|----------------------------------------------------- |
|银行分支机构| `CollaborateWithinABankBranch`|频道： <ul><li>常规<li>公告</li><li>小型会议室</li><li>客户会议</li><li>审批请求 </li><li>指导</li><li>技能开发</li><li>贷款处理</li><li>客户投诉</li><li>称赞</li><li>有趣的内容</li><li>合规性</li></ul>应用：<ul><li>表扬 </li><li>问题发布者</li><li>Wiki</li><li>日历</li><li>审批</li><li>公告</li><li>想法</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一起使用

开发人员可以使用 Microsoft Graph 从预先构建的团队模板中创建团队。 若要详细了解如何将团队模板与Microsoft Graph 配合使用，请参阅[使用 Microsoft Graph 团队模板入门](get-started-with-teams-templates.md)， [ Microsoft Teams API 概述](/graph/teams-concept-overview?view=graph-rest-1.0)，[teamsTemplate 资源类型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

### <a name="bank-branch"></a>银行分支机构

通过碰头会、客户会议、业务流程(如按揭合作)使银行分支机构员工集中协作，并通过“公告”和“称赞”让每个人都参与其中。

| 模板类型 |TemplateId| 模板频道 |
| ------------------ |--|----------------------------------------------------- |
|银行分支机构|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|常规<br>公告<br>小型会议室<br>客户会议<br>审批请求<br>指导<br>技能开发<br>贷款处理<br>客户投诉<br>称赞<br>有趣的内容<br>合规性|
||||

> [!NOTE]
> 有关适用于金融服务组织的其他模板，请参阅[ Microsoft Graph中为中小型企业构建的团队模板](smb-templates.md)。