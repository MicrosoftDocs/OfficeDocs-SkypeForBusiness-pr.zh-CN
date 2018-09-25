---
title: 配置 Microsoft 团队的核心功能的入职培训清单
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 配置团队时，请按照的核心、 待办事项任务和此检查表中的活动。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 025aa97c62692313b7a1a3e4d00a2325244ee4ea
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016114"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>配置 Microsoft 团队的核心功能

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 验证您的环境包含所有团队系统必备组件 | 团队取决于其他平台来构造的端到端协作解决方案。 使用您的 IT 团队以确保您已部署并正确配置 Exchange 和 SharePoint Online 的 OneDrive for Business。 | | [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact) <br/><br/>[Exchange 与 Microsoft Teams 如何交互](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact) |
| 2  | 验证已为租户启用团队 | 默认值为所有组织情况时，团队处于打开状态。 检查 Office 365 管理中心，若要验证已为您的租户启用团队中的**服务和外接程序**页，并根据需要启用它。 | | [在你的 Office 365 组织中设置 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up) |
| 3  | 配置角色和权限 | 团队支持两种类型的角色： 成员和所有者。 <br/><br/>添加到团队的成员之后, 所有者可以升级到所有者角色的成员。 作为最佳实践，我们建议您拥有至少两个分配给每个工作组的所有者。 <br/><br/>默认情况下，拥有邮箱位于 Exchange Online 组织中的所有人都可以创建工作组。 创建新的工作组的用户会自动授予该团队的所有者角色。 <br/><br/>如果需要您可以配置 Office 365 组设置，以仅使特定用户可以创建新的团队。 | | [在 Microsoft Teams 中分配角色和权限](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions) <br/><br/>[Office 365 组和 Microsoft 团队](https://docs.microsoft.com/MicrosoftTeams/office-365-groups) <br/><br/>[管理谁可以创建 Office 365 组](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 配置租户范围的团队设置 | 您可以在租户级别配置某些团队设置。 启用团队的用户的租户配置从继承这些设置：<ul><li>常规</li><li>电子邮件集成</li><li>应用</li><li>自定义云存储</li><li>通话和会议</li><li>消息</li></ul>| | [在你的 Office 365 组织中启用 Microsoft Teams 功能](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365) |
| 5  | 可选： 配置来宾访问 | 您可以使用团队中的来宾访问与用户协作组织外部通过授予其访问权限的团队和频道。 来宾访问是团队中的租户级设置。 默认情况下，它处于状态。 <br/>启用来宾访问和配置租户范围来宾设置，如果您的组织计划使用该功能。 | | [Microsoft Teams 中的来宾访问](https://docs.microsoft.com/MicrosoftTeams/guest-access) |
| 6  | 可选： 配置团队命名策略 | 用户创建或编辑工作组名称时，团队利用 Office 365 组命名策略。 <br/><br/>默认情况下，当用户创建工作组不应用任何命名限制。 <br/><br/>如果您需要强制实施规则的工作组名称，请配置 Office 365 组命名策略应用于您的组织。 您可以设置强制前缀和后缀，并指定阻止的单词。 | | [在 Microsoft Teams 中创建团队时规划 Office 365 组](https://docs.microsoft.com/microsoftteams/plan-office-365-groups) <br/><br/>[Office 365 组命名策略](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 配置 Exchange 团队 SMTP 域 | 团队使用 Exchange Online 通过 SMTP 域将通知发送给团队成员 — email.teams.microsoft.com — 当他们已添加或删除。 <br/><br/>请务必将此 SMTP 域添加到 Exchange 基础结构中的接受的域列表。 | | [在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域](https://docs.microsoft.com/MicrosoftTeams/smtp-accepted-domain) |
| 8  | 配置和管理用户对团队访问 | 虽然我们强烈建议您为团队启用所有用户，您可以允许或禁止通过分配或移除团队产品许可证的团队访问基于每个用户。 | | [管理对 Microsoft Teams 的用户访问](https://docs.microsoft.com/MicrosoftTeams/user-access) |
| 9  | 向用户分配许可证 | 将许可证分配给您的用户音频会议和电话系统，调用计划等功能 | | [分配 Skype for Business 和 Microsoft Teams 许可证](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) <br/><br/>[MyAdvisor – 用户启用脚本](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_6,5_2_0_3) |
| 10 | 可选： 使用 PowerShell to administer 团队 | 您可以使用 PowerShell cmdlet，而不是在 Office 365 管理中心管理和管理团队设置。 | | [Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |