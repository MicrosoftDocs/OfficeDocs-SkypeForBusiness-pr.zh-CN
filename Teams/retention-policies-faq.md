---
title: Microsoft Teams 保留策略常见问题解答
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: 有关 Microsoft 团队中的保留策略的常见问题。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa8e71d167bbb5f5381c66a1a8545a6f94f74e62
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793498"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft Teams 保留策略常见问题解答

> [!NOTE]
> 我们尚不支持保留专用频道消息的配置。 支持在专用频道中共享的文件的保留。

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>我可以在保留策略中设置哪些类型的策略以及它们的工作原理是什么？

在安全 & 合规性中心中，为团队或任何其他工作负荷设置保留策略时，可以设置两种主要类型的策略： 
- 保留：这些策略确保你的数据在给定时间段内保留，无论最终用户工具中发生了什么情况。 它们确保保留数据以满足合规性原因，并在电子数据展示中提供，直到此时间段到期。 在时间到期后，你的策略可以指示是不执行任何操作，也可以删除数据。 在团队中，如果你创建了7年的保留策略，即使最终用户删除其团队消息，这些消息仍会保留为电子数据展示7年。
- 删除：这些策略确保数据不是你的组织的责任。 在指定的持续时间后，将从团队中的所有相关存储中删除数据。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>我们是否可以在组织范围的策略中加入团队？ 

否，目前不能。 你必须使用团队位置行或以下团队 cmdlet 为团队聊天和频道消息创建特定策略： [TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [new-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)。 这些 cmdlet 也具有获取和设置版本。

### <a name="are-these-retention-policies-retroactive"></a>这些保留策略是 retroactive 吗？ 

是的，它们是。 如果创建保留策略以删除超过60天的数据，它将删除在60天前创建的团队数据。 

### <a name="what-is-the-default-retention-policy"></a>默认保留策略是什么？ 

默认情况下，团队聊天、频道和文件数据将永久保留。

### <a name="what-licensing-is-required-for-retention-policies"></a>保留策略需要哪些许可？

保留策略的最低许可要求是 Office 365 E3。 有关许可的详细信息，请阅读[Office 365 团队许可](office-365-licensing.md)。

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>是否可以针对策略中的一组用户或团队设定目标？ 

是的，您这样做。 在 "策略创建向导" 的 "位置" 步骤中，您可以包含或排除团队（**团队频道消息**）或用户（**团队聊天**），并为组织创建目标策略。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>在保留策略中使用组邮箱位置行和团队频道消息位置行的主要区别是什么？ 

如果对 Exchange Online 使用组邮箱和用户邮箱位置行，将从指定的邮箱中删除团队数据。 但是，这只会删除邮箱中的数据。 它不会删除其他团队数据，如聊天服务。 我们建议你使用团队保留策略来正确管理所有团队数据。 团队保留策略从所有存储位置（邮箱、聊天服务、团队客户端）删除团队数据。 

注意：启动团队的保留策略功能可确保只有团队策略删除存储在 Exchange 邮箱位置（用户或组）内的团队项目。 在邮箱上设置的其他策略不会影响团队项目。 过去的情况是如此，但在启动保留策略功能时已修复。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Skype for Business Online 和团队互操作聊天会发生什么情况–它们是否受保留策略的影响？

是的，Skype for business Online 和团队互操作聊天的工作方式相同。 在将 Skype for Business 联机聊天加入团队后，它会成为团队聊天线索中的一条消息，并将 ingested 到相应的邮箱中。 相同的流程有效，团队删除策略将从团队线索中删除这些邮件。 但是，如果为 Skype for business Online 启用了对话历史记录，并且从 Skype for business Online 客户端将其保存到邮箱中，则不会通过团队保留策略处理此聊天数据。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>是否可以通过安全 & 合规性中心 cmdlet 执行这些操作？ 我应该使用什么？ 

方式. 你可以使用[安全 & 合规性中心 Powershell cmdlet]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)创建团队保留策略。 请记住，这些 cmdlet 不是 Exchange Online cmdlet。 下面是我们为团队创建的 cmdlet。 它们遵循当前在安全 & 合规中心中可用的保留 cmdlet 中的现有命名规范和样式。

|设置|规则|
|---|---|
|[新-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>如果有多个具有不同工期的团队的保留策略，则会有一个 wins？

我们遵循[保留策略的原则](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)，我们也建议你执行此操作。 简短答案是： 
-   保留的 wins 始终超过删除
-   保留最长期限始终为 "wins"
-   在位置的隐式包含中显式包含 wins
-   Wins 最短删除周期
