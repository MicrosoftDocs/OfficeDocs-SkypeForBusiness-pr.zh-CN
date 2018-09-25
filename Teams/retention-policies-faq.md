---
title: Microsoft 团队保留策略常见问题
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: 有关 Microsoft 团队中的保留策略的常见问题。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c8ebd3d35c471a529899cd46a364511f7ea267c
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004575"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft 团队保留策略常见问题

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>哪些类型的策略可以设置保留策略中以及它们如何工作？

在安全和合规性中心中，工作组或任何其他工作负荷，设置的保留策略时您可以设置策略的两种主要类型： 
- 保留： 这些策略确保您的数据保留给定时间段的时间，无论在最终用户工具会发生什么情况。 他们确保数据保留出于合规性和电子数据展示，直到这次中可用的过期。 时间过后，您的策略可以指明是否不执行任何操作或删除的数据。 在工作组，如果您为 7 年创建保留策略，即使最终用户删除其团队邮件，这些消息仍保留电子数据展示的 7 年。
- 删除： 这些策略确保数据不为您的组织的责任。 指定的持续时间后从团队中的所有相关存储删除数据。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>我们可以在组织范围的策略中包括团队？ 

否，当前不。 您必须创建团队聊天和频道的邮件使用团队位置行或这些团队 cmdlet 的特定策略：[新建 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [新建 TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)。 这些 cmdlet 将获取和设置以及版本。

### <a name="are-these-retention-policies-retroactive"></a>有以下保留策略影响以前的版本？ 

是的它们是。 如果您创建保留策略，以删除早于 60 天的数据，它将删除工作组创建超过 60 天的数据。 

### <a name="what-is-the-default-retention-policy"></a>什么是默认保留策略？ 

默认情况下，团队聊天、 通道和文件数据所永远保留。 用户可以删除内容，但保留策略不存在，团队数据到 Exchange online 邮箱 （用户和组），则始终存档和那里表示电子数据展示。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>可以指定目标用户或工作组在策略中的的设置？ 

是，则执行操作。 在策略创建向导在位置步骤中，可以包括或排除 （**团队通道消息**） 的团队或用户 （**团队聊天**） 并为组织创建目标的策略。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>使用保留策略中的组邮箱位置行和团队通道消息位置行之间的主要区别是什么？ 

如果您使用的 Exchange Online 的组邮箱和用户邮箱位置行，则将从指定的邮箱删除团队数据。 但是，这仅数据从邮箱中删除。 它不会删除其他团队数据，例如聊天服务。 我们建议使用团队保留策略正确管理团队的所有数据。 团队保留策略将团队数据删除所有的存储位置 – 邮箱，聊天服务，团队客户端。 

注意： 启动保留策略功能的团队可确保仅团队策略删除存储在 Exchange 邮箱位置 （用户或组） 内的团队项目。 其他邮箱上的策略安装程序不会影响团队项目。 这是 true 过去，但已解决的保留策略功能与。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>会发生什么情况 Skype 的互操作性聊天业务联机和团队 – 它们受保留策略？

是，业务联机和团队互操作性聊天 Skype 的工作方式相同。 后的业务在线聊天 Skype 进入团队，它将成为团队聊天线程中的邮件，并获取 ingested 到适当的邮箱。 使相同流动 works – 团队删除策略将从团队线程中删除这些消息。 但是，如果对话历史记录处于的 Skype 业务 online 并从业务联机客户端的 Skype 那些被保存到邮箱，团队保留策略不处理此聊天数据。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>怎么办？ 这些通过安全性和合规性中心 cmdlet 我应使用什么？ 

绝对。 您可以创建使用[安全性和合规性中心 Powershell cmdlet]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)的团队保留策略。 请记住这些不是 Exchange Online cmdlet。 以下是我们创建团队的 cmdlet。 他们遵循现有术语和样式从目前可保留 cmdlet 在安全性和合规性中心。

|策略|规则|
|---|---|
|[新 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[设置 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [设置 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[删除 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [删除 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>如果有多个团队具有不同的工期，哪一个 wins 的保留策略？

我们将按照[的保留策略的原则](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)，，我们建议您执行太。 短答案是： 
-   通过删除 wins 始终保留
-   最长保留期始终 wins
-   显式包含 wins 高于隐式包含位置方面
-   最短删除期间 wins
