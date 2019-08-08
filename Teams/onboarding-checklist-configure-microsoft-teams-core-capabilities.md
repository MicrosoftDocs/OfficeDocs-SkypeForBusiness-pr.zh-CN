---
title: 配置 Microsoft Teams 核心功能的上线清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在配置团队时, 请按照此清单中的核心、待办任务和活动进行操作。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ee5e3ab901cb5bc0fb35aee9dbc03e9b636621
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238599"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>配置 Microsoft 团队核心功能

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 验证你的环境是否包括所有团队先决条件 | 团队依赖于其他平台来构建端到端协作解决方案。 与你的 IT 团队协作, 确保你已部署并正确配置了 Exchange、SharePoint Online 和 OneDrive for business。 | | [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md) |
| 2  | 验证是否已为租户启用团队 | 默认情况下, 团队为所有组织启用团队。 检查 Microsoft 365 管理中心中的 "**服务 & 加载项**" 页面, 验证是否已为租户启用团队, 并根据需要启用团队。 | | [在你的 Office 365 组织中设置 Microsoft Teams](office-365-set-up.md) |
| 3  | 配置角色和权限 | 团队支持两种类型的角色: 成员和所有者。 <br/><br/>将成员添加到团队后, 所有者还可以将成员提升为所有者角色。 最佳做法是, 建议您至少为每个团队分配两个所有者。 <br/><br/>默认情况下, 组织中拥有 Exchange Online 托管邮箱的每个人都可以创建团队。 创建新团队的用户将自动授予该团队的所有者角色。 <br/><br/>如果需要, 您可以将 Office 365 组设置配置为仅让特定用户创建新团队。 | | [在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md) <br/><br/>[Office 365 组和 Microsoft 团队](office-365-groups.md) <br/><br/>[管理可创建 Office 365 组的人员](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 配置租户范围的团队设置 | 你可以在租户级别配置某些团队设置。 已启用团队的用户从租户配置继承这些设置:<ul><li>常规</li><li>电子邮件集成</li><li>应用</li><li>自定义云存储</li><li>通话和会议</li><li>消息</li></ul>| | [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md) |
| 5  | 可选: 配置来宾访问 | 你可以使用团队中的来宾访问通过向团队和频道授予访问权限来与组织外部的人员进行协作。 来宾访问是团队中的租户级别设置。 默认情况下, 它处于关闭状态。 <br/>如果你的组织计划使用该功能, 请启用来宾访问和配置租户范围的来宾设置。 | | [Microsoft Teams 中的来宾访问](guest-access.md) |
| 6  | 可选: 配置团队命名策略 | 当用户创建或编辑团队名称时, 团队会利用 Office 365 组的命名策略。 <br/><br/>默认情况下, 当用户创建团队时, 不会应用任何命名限制。 <br/><br/>如果需要强制执行团队名称规则, 请配置适用于你的组织的 Office 365 组命名策略。 可以设置强制前缀和后缀并指定阻止的字词。 | | [在 Microsoft 团队中创建团队时规划 Office 365 组](plan-office-365-groups.md) <br/><br/>[Office 365 组命名策略](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 配置团队 SMTP 域的 Exchange | 团队使用 Exchange Online 通过 SMTP 域 (email.teams.microsoft.com) 向团队成员发送通知 (在添加或删除它们时)。 <br/><br/>请确保将此 SMTP 域添加到 Exchange 基础结构中的 "接受的域" 列表。 | | [在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域](smtp-accepted-domain.md) |
| 个  | 配置和管理用户对团队的访问权限 | 虽然我们强烈建议你为团队启用所有用户, 但你可以通过分配或删除团队产品许可证, 允许或禁止基于每个用户访问团队。 | | [管理 Microsoft Teams 的用户访问](user-access.md) |
| db-9  | 为用户分配许可证 | 将许可证分配给用户以获取音频会议、电话系统和通话计划等功能 | | [分配 Skype for Business 和 Microsoft Teams 许可证](assign-teams-licenses.md)|
| 10 | 可选: 使用 PowerShell 管理团队 | 你可以使用 PowerShell cmdlet (而不是 Microsoft 365 管理中心) 管理和管理团队设置。 | | [Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
