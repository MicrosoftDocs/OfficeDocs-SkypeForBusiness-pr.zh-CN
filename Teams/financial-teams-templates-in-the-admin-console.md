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
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 096bab4289d5ac9e81c63f83cd73efd41d98e7be
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198685"
---
# <a name="use-financial-team-templates"></a>使用财务团队模板

通过提供预定义的设置、频道和预安装的应用模板，Microsoft Treams 模板让你能够快速轻松地创建团队。

对于金融服务组织，团队模板可能特别强大，因为它们可帮助你在整个组织中快速部署一致的团队。 模板还可帮助员工了解如何有效地使用Teams。

Teams 包括专为金融服务组织设计的模板。 使用这些预建模板快速创建团队，让员工进行沟通和协作。 在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。

如何管理和使用团队模板取决于你是管理人员还是开发人员。

|如果是： | 然后，可以： |
| ---- | --------- |
| 管理人员或 IT 专业人员 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 开发人员 | [使用 Microsoft Graph ](#use-team-templates-with-microsoft-graph) 从团队模板中创建团队。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理中心的管理团队模板

作为管理人员，你可以在 Microsoft Teams 管理中心内管理团队模板。 可在此处查看有关每个模板的详细信息。 还可以[创建模板策略](templates-policies.md)并将其分配给员工，以确定在 Teams 中使用哪些模板来[创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)。

若要了解有关团队模板的详细信息，请参阅[管理中心的 Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。

我们当前为金融服务组织提供以下预建的团队模板。 若要查看，请在 Teams 管理中心的左侧导航栏中，转到 **Teams** > **团队模板**。

### <a name="collaborate-within-a-bank-branch"></a>在银行分支机构内协作

通过碰头会、客户会议、业务流程(如按揭合作)使银行分支机构员工集中协作，并通过“公告”和“称赞”让每个人都参与其中。

| 模板类型 |TemplateId| 此基本模板包含的属性 |
| ------------------ |--|----------------------------------------------------- |
|银行分支机构| `CollaborateWithinABankBranch`|频道： <ul><li>常规<li>公告</li><li>小型会议室</li><li>客户会议</li><li>审批请求 </li><li>指导</li><li>技能开发</li><li>贷款处理</li><li>客户投诉</li><li>称赞</li><li>有趣的内容</li><li>合规性</li></ul>应用：<ul><li>表扬 </li><li>问题发布者</li><li>Wiki</li><li>日历</li><li>审批</li><li>公告</li><li>想法</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>将 Teams 模板与 Microsoft Graph 一起使用

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>银行分支机构

通过碰头会、客户会议、业务流程(如按揭合作)使银行分支机构员工集中协作，并通过“公告”和“称赞”让每个人都参与其中。

| 模板类型 |TemplateId| 模板频道 |
| ------------------ |--|----------------------------------------------------- |
|银行分支机构|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|常规<br>公告<br>小型会议室<br>客户会议<br>审批请求<br>指导<br>技能开发<br>贷款处理<br>客户投诉<br>称赞<br>有趣的内容<br>合规性|
||||

> [!NOTE]
> 有关适用于金融服务组织的其他模板，请参阅[在 Microsoft Graph 中为中小型企业构建团队模板](smb-templates.md)。

## <a name="related-articles"></a>相关文章

- [在管理中心内开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)
- [基于模板创建团队](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [开始使用 Microsoft Graph 的团队模板](get-started-with-teams-templates.md)