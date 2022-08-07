---
title: 加入清单 - 配置核心功能 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 为组织配置 Teams 时，请按照此清单中的核心、要执行的任务和活动进行操作。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 170f62afd6cd75d5060243271fb951cf9dd4aa5c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270887"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>配置 Microsoft Teams 核心功能

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 验证环境是否包含所有 Teams 先决条件 | Teams 依赖于其他平台来构建端到端协作解决方案。 与 IT 团队协作，确保已部署并正确配置 Exchange、SharePoint Online 和 OneDrive for Business。 | | [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md) |
| 2  | 验证是否为租户启用了 Teams | 默认情况下，所有组织都会启用 Teams。 检查 **Microsoft 365 管理中心中的“服务&加载项**”页，验证是否为组织启用了 Teams，并在必要时启用它。 | | [在 Microsoft 365 或 Office 365 中设置 Microsoft Teams](office-365-set-up.md) |
| 3  | 配置角色和权限 | Teams 支持两种类型的角色：成员和所有者。 <br/><br/>将成员添加到团队后，所有者还可以将成员提升为“所有者”角色。 最佳做法是，建议为每个团队分配至少两个所有者。 <br/><br/>默认情况下，组织中托管邮箱Exchange Online的每个人都可以创建团队。 创建新团队的用户将自动被授予该团队的所有者角色。 <br/><br/>如果需要，可以将 Microsoft 365 组设置配置为仅允许特定用户创建新团队。 | | [在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md) <br/><br/>[Microsoft 365 组和 Microsoft Teams](office-365-groups.md) <br/><br/>[管理谁可以创建Microsoft 365 组](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 配置租户范围的 Teams 设置 | 可以在租户级别配置一些 Teams 设置。 为 Teams 启用的用户从租户配置继承以下设置：<ul><li>常规</li><li>电子邮件集成</li><li>应用</li><li>自定义云存储</li><li>通话和会议</li><li>消息传递</li></ul>| | [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md) |
| 5  | 可选：配置来宾访问权限 | 你可以使用 Teams 中的来宾访问权限，通过授予他们访问团队和频道的权限，与组织外部的人员进行协作。 来宾访问是 Teams 中的租户级设置。 默认情况下处于禁用状态。 <br/>如果组织计划使用该功能，请启用来宾访问并配置租户范围的来宾设置。 | | [Microsoft Teams 中的来宾访问](guest-access.md) |
| 6  | 可选：配置 Teams 命名策略 | 当用户创建或编辑团队名称时，Teams 会利用Microsoft 365 组的命名策略。 <br/><br/>默认情况下，用户创建团队时不应用命名限制。 <br/><br/>如果需要对团队名称强制实施规则，请配置适用于组织的Microsoft 365 组命名策略。 可以设置必需的前缀和后缀，并指定阻止的单词。 | | [在 Microsoft Teams 中创建团队时规划 Microsoft 365 组](plan-office-365-groups.md) <br/><br/>[Microsoft 365 组命名策略](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 为 Teams SMTP 域配置 Exchange | 添加或删除团队成员时，Teams 使用Exchange Online使用 SMTP 域（email.teams.microsoft.com）向团队成员发送通知。 <br/><br/>请务必将此 SMTP 域添加到 Exchange 基础结构中接受的域列表。 | | [在 Exchange 中创建安全发件人列表](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | 配置和管理用户对 Teams 的访问权限 | 尽管强烈建议为 Teams 启用所有用户，但可以通过分配或删除 Teams 产品许可证，允许或禁止按用户访问 Teams。 | | [管理 Microsoft Teams 的用户访问](user-access.md) |
| 9  | 向用户分配许可证 | 为用户分配音频会议、电话系统和通话套餐等功能的许可证 | | [分配 Microsoft Teams 加载项许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 可选：使用 PowerShell 管理 Teams | 可以使用 PowerShell cmdlet 而不是Microsoft 365 管理中心来管理和管理 Teams 设置。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |