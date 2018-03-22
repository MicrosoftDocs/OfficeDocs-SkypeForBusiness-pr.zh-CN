---
title: 配置 Microsoft 小组核心功能的服务清单
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 当您将配置团队按照核心待办任务，此核对清单中的活动。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 424d4f5ec56698974059631992b3a46759e4955c
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="configure-microsoft-teams-core-capabilities"></a>配置 Microsoft 小组核心能力

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 验证您的环境，包括所有的团队系统必备组件 | 在其他平台来构建端对端协作解决方案取决于团队。 与您的 IT 团队，以确保您已经部署并正确配置 Exchange、 SharePoint Online，和 OneDrive 的业务合作。 | | [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact) <br/><br/>[如何交换和 Microsoft 小组进行交互](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact) |
| 2  | 验证组织中启用了团队 | 默认情况下，所有组织，团队被打开的。 检查**服务和外接程序**在 Office 365 管理中心来验证您组织中启用了团队页面，如有必要，请启用它。 | | [在 Office 365 提供组织中设置 Microsoft 小组](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up) |
| 3  | 配置角色和权限 | 团队支持两种类型的角色： 成员和所有者。 <br/><br/>向团队中添加成员后, 一个所有者可以升级到所有者角色的成员。 作为最佳操作，建议您有至少两个所有者指派给每个团队。 <br/><br/>默认情况下，在组织中拥有邮箱驻留在 Exchange Online 上的每个人都可以创建一个团队。 创建新的团队的用户会自动授予该团队的所有者角色。 <br/><br/>如果需要您可以配置 Office 365 组设置，只允许特定用户创建新的团队。 | | [指派角色和权限，Microsoft 小组中](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions) <br/><br/>[Office 365 组和 Microsoft 小组](https://docs.microsoft.com/MicrosoftTeams/office-365-groups) <br/><br/>[管理者可以创建 Office 365 组](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 配置租户范围的团队设置 | 您可以在组织级别配置团队中的某些设置。 启用为团队的用户从租户配置继承这些设置：<ul><li>常规</li><li>电子邮件集成</li><li>应用</li><li>自定义云存储</li><li>通话和会议</li><li>消息</li></ul>| | [启用 Microsoft 小组 Office 365 提供组织中的功能](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365) |
| 5  | 可选： 配置来宾访问 | 在团队中使用来宾访问权限与用户协作组织之外通过授予其访问权限的团队和渠道。 来宾访问权限是在团队组织级设置。 它是默认关闭的。 <br/>启用来宾访问和配置来宾租户范围设置，如果您的组织计划使用该功能。 | | [在 Microsoft 小组的来宾访问](https://docs.microsoft.com/MicrosoftTeams/guest-access) |
| 6  | 可选： 配置团队命名策略 | 当用户创建或编辑团队名称，团队利用 Office 365 组的命名策略。 <br/><br/>默认情况下，当用户创建一个团队应用没有命名限制。 <br/><br/>如果您需要强制实施团队名称规则，配置 Office 365 组命名策略应用于您的组织。 您可以设置必填字段的前缀和后缀并指定禁止的词语。 | | [如果在 Microsoft 小组创建团队，规划 Office 365 组](https://docs.microsoft.com/microsoftteams/plan-office-365-groups) <br/><br/>[Office 365 的组命名策略](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 将 Exchange 配置为团队 SMTP 域 | 团队使用 Exchange 联机使用的 SMTP 域将通知发送给团队成员 — — email.teams.microsoft.com — — 当他们已经添加或删除了。 <br/><br/>请务必将此 SMTP 域添加到 Exchange 基础结构中的接受的域列表。 | | [添加 Microsoft 小组 SMTP 域作为接受域在 Exchange 联机](https://docs.microsoft.com/MicrosoftTeams/smtp-accepted-domain) |
| 8  | 配置和管理团队的用户访问 | 尽管强烈建议所有用户都启用团队，您可以允许或禁止对团队基于每个用户的访问由分配或删除团队的产品许可证。 | | [管理用户对 Microsoft 小组访问](https://docs.microsoft.com/MicrosoftTeams/user-access) |
| 9  | 将许可证分配给用户 | 将许可证分配给用户的音频会议、 电话系统和调用计划等功能 | | [分配 Skype for Business 和 Microsoft Teams 许可证](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) <br/><br/>[MyAdvisor – 用户启用脚本](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_6,5_2_0_3) |
| 10 | 可选： 使用 PowerShell 管理团队 | 您可以使用 PowerShell 的 cmdlet，而不是 Office 365 管理中心管理团队设置。 | | [Microsoft 小组 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |