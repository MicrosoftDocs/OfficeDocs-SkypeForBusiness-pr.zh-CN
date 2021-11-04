---
title: 载入清单 - 配置核心功能 - Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 为组织配置任务时，请遵循此清单中的核心Teams和活动。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e376033c0e770dcef5bfa454b365d168ed922c5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767240"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>配置Microsoft Teams核心功能

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 验证环境是否包含所有Teams先决条件 | Teams依赖于其他平台来构造端到端协作解决方案。 与 IT 团队协作，确保已部署并正确配置 Exchange、SharePoint Online 和 OneDrive for Business。 | | [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md) |
| 2  | 验证Teams租户已启用该租户 | Teams所有组织都默认启用此模式。 检查 **&服务** 加载项"页Microsoft 365 管理中心验证Teams为组织启用加载项，并在必要时启用它。 | | [在Microsoft Teams或Microsoft 365中Office 365](office-365-set-up.md) |
| 3  | 配置角色和权限 | Teams支持两种类型的角色：成员和所有者。 <br/><br/>将成员添加到团队后，所有者还可以将成员提升为"所有者"角色。 最佳做法是，建议为每个团队至少分配两个所有者。 <br/><br/>默认情况下，组织中托管有邮箱的每个人都可以创建Exchange Online团队。 创建新团队的用户将自动获得该团队的"所有者"角色。 <br/><br/>如果需要，可以配置组Microsoft 365仅允许特定用户创建新团队。 | | [在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md) <br/><br/>[Microsoft 365组和Microsoft Teams](office-365-groups.md) <br/><br/>[管理可以创建组Microsoft 365人](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 配置租户范围Teams设置 | 可以在租户级别Teams一些自定义设置。 为租户配置启用Teams从租户配置继承这些设置：<ul><li>常规</li><li>电子邮件集成</li><li>应用</li><li>自定义云存储</li><li>通话和会议</li><li>消息传递</li></ul>| | [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md) |
| 5  | 可选：配置来宾访问 | 在团队中，Teams来宾访问权限，通过授予他们访问团队和频道的权限，与组织外部人员进行协作。 来宾访问是租户级别设置，Teams。 默认情况下处于禁用状态。 <br/>如果组织计划使用该功能，请启用来宾访问并配置租户范围的来宾设置。 | | [Microsoft Teams 中的来宾访问](guest-access.md) |
| 6  | 可选：Teams命名策略 | Teams创建或编辑团队名称时，Microsoft 365组使用命名策略。 <br/><br/>默认情况下，当用户创建团队时，不会应用任何命名限制。 <br/><br/>如果需要对团队名称强制实施规则，请Microsoft 365适用于组织的组命名策略。 可以设置强制前缀和后缀，并指定阻止的字词。 | | [在Microsoft 365团队时规划团队Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365组命名策略](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 为 Exchange SMTP Teams配置域 | Teams添加Exchange Online时，使用 SMTP 域（email.teams.microsoft.com）向团队成员发送通知。 <br/><br/>请务必将此 SMTP 域添加到基础结构中的接受域Exchange列表。 | | [在邮件中创建安全发件人Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | 配置和管理用户对 Teams | 尽管强烈建议为所有用户启用 Teams，但可以通过分配或删除 Teams 产品许可证来允许或禁止每个用户访问 Teams。 | | [管理 Microsoft Teams 的用户访问](user-access.md) |
| 9  | 向用户分配许可证 | 为用户分配音频会议、电话系统和呼叫计划等功能的许可证 | | [分配Microsoft Teams附加许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 可选：使用 PowerShell 管理Teams | 可以使用 PowerShell cmdlet 而不是 Microsoft 365 管理中心 来管理和管理Teams设置。 | | [Microsoft TeamsPowerShell](/powershell/module/teams/?view=teams-ps) |