---
title: Microsoft Teams 中的保留策略
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 了解保留策略以及如何在团队中创建和管理它们。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160746"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams 中的保留策略

保留策略可帮助您更有效地管理组织中的信息。 使用保留策略来保留符合组织的内部策略、行业法规或法律需求的数据，并删除被视为责任的数据，而不再需要保留，或者没有法律或商业价值。

默认情况下，团队聊天、频道和文件数据将永久保留。 作为管理员，你可以为聊天和频道消息设置团队保留策略，并提前确定是保留数据、删除数据还是在特定时间段内保留数据，然后将其删除。

在[Office 365 安全 & 合规中心](https://protection.office.com/)或使用安全 & 合规中心 PowerShell cmdlet 中，你可以创建和管理团队和其他工作负荷的保留策略。 您可以将团队保留策略应用于整个组织或特定用户和团队。

> [!NOTE]
> 我们尚不支持保留专用频道消息的配置。 支持在专用频道中共享的文件的保留。

若要了解有关 Office 365 的保留策略的详细信息，请参阅[保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。

## <a name="what-are-retention-policies-for-teams"></a>团队的保留策略是什么？

为团队或任何其他工作负荷设置保留策略时，可以将其设置为：

- **保留数据**：使用保留策略确保数据在指定时间段内保留，无论用户应用中发生了什么情况。 出于合规性原因，将保留数据，并且电子数据展示在保留期到期之前可用，之后你的策略指示是不执行任何操作，还是删除数据。 例如，如果创建团队保留策略以将频道消息保留7年，则邮件将在7年后保留，即使用户在团队中删除了他们的邮件也是如此。
- **删除数据**：使用保留策略删除数据，以确保它不是你的组织的责任。 使用团队保留策略，删除数据时，将从团队服务上的所有存储位置中永久删除该数据。

利用团队的保留策略，您可以：

- 保留特定工期的团队聊天和/或频道消息，然后不执行任何操作。
- 在指定工期内保留团队聊天和/或频道消息，然后删除数据。
- 在指定的持续时间后删除团队聊天和/或频道消息。

> [!NOTE]
> 请记住，在团队中，用户在私人聊天中共享的文件存储在共享该文件的用户的 OneDrive for Business 帐户中。 以及团队成员上载到频道对话的文件存储在团队的 SharePoint 网站中。 因此，若要在团队中保留或删除文件，请创建适用于 OneDrive for business 和 SharePoint Online 的保留策略。

当数据受保留策略制约时，用户可以继续使用它，因为数据保留在其原始位置。 如果用户编辑或删除受策略制约的数据，则会将副本保存到在策略生效时保留的安全位置。

保留策略的最低许可要求是 Office 365 E3。 若要了解有关许可的详细信息，请参阅[适用于团队的 Office 365 许可](Office-365-licensing.md)。

## <a name="how-teams-retention-policies-work"></a>团队保留策略的工作原理

团队聊天存储在聊天中每个用户的邮箱的隐藏 SubstrateHolds 文件夹中，而团队频道消息存储在团队的组邮箱中的隐藏 SubstratesHolds 文件夹中。 团队使用同时存储此数据的 Azure 支持的聊天服务，并且默认情况下，此服务会永久存储数据。 使用团队保留策略，删除数据时，将从 Exchange 邮箱和基础聊天服务中永久删除数据。

将保留策略应用到团队聊天和频道消息时，将发生以下情况：

- 如果在保留期间用户在保留期间内编辑或删除了聊天或频道消息，则会将邮件复制（如果已编辑）或移动（如果它已被删除）到 SubstrateHolds 文件夹，并在保留期到期之前存储在该文件夹中。 如果在保留期到期时将策略配置为删除数据，则邮件将在保留期过期的那一天被永久删除。
- 如果在保留期间用户未删除聊天或频道消息，则邮件将在保留期到期后的一天内移动到 SubstrateHolds 文件夹。 如果在保留期到期时将策略配置为删除数据，邮件将在移动到文件夹后被永久删除一天。

> [!NOTE]
> 相同的流程适用于 Skype for Business Online 和团队互操作聊天。 当将 Skype for Business Online 聊天加入团队时，它将成为团队聊天线索中的一条消息，并 ingested 到相应的邮箱中。 团队保留策略将从团队线程中删除这些消息。 但是，如果为 Skype for business Online 和 Skype for business Online 客户端中的 Skype for business Online 客户端启用了对话历史记录，则不会由团队保留策略处理聊天数据。

团队中的保留策略基于创建聊天或频道消息的日期以及 retroactive。 换句话说，如果创建保留策略以删除超过90天的数据，则将删除工作组数据创建超过90天前的数据。

在 SharePoint Online 或 OneDrive for business 中应用的保留策略可能会删除在团队聊天或频道消息中引用的文件，然后再删除这些邮件。 在此方案中，文件仍将显示在 "团队" 消息中，但当用户单击该文件时，将收到 "找不到文件" 错误。 如果有人手动从 SharePoint Online 或 OneDrive for business 中删除文件，则在缺少策略时也可能会发生这种情况。

### <a name="considerations-and-limitations"></a>注意事项和限制

下面是使用团队保留策略时应注意的一些注意事项和限制：

- 团队需要与其他工作负荷分开的保留策略。 换句话说，你必须为团队聊天和/或频道消息创建特定的保留策略。 因此，您不能在组织范围的保留策略中包含团队。

- 不支持专用信道消息。 此时，团队的保留策略仅适用于标准频道消息。

- 团队不支持高级保留设置，如将策略应用于包含关键字或敏感信息的内容的功能。 目前，团队中的保留策略适用于所有聊天和/或频道消息内容。

- 团队最多可能需要三天的时间来清理已过期的消息。 团队保留策略将在保留期到期时删除聊天和频道消息。 但是，可能需要长达三天的时间来清理这些邮件并永久删除它们。 此外，聊天和频道消息将在保留期到期后和邮件永久删除的时间之间通过电子数据展示工具进行搜索。

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>多个保留策略和保留原则

如果您使用不同的工期设置多个团队保留策略，则应用[保留策略原则](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)。 下面概述了优先顺序：

- 保留的 wins 始终超过删除
- 保留最长期限始终为 "wins"
- 在位置的隐式包含中显式包含 wins
- Wins 最短删除周期

## <a name="when-to-use-retention-policies-for-teams"></a>何时使用团队的保留策略

在许多情况下，组织会将私人聊天数据视为比频道消息更多的责任，这通常是更多与项目相关的对话。

你可以为私人聊天（1:1 或1：许多聊天）和频道消息设置单独的保留策略。 您还可以配置应用于组织中特定用户或团队的唯一策略。 对于团队聊天，你可以选择要应用该策略的用户。 对于团队频道消息，你可以选择应用策略的团队。

例如，对于频道消息，你可以将一年的删除策略应用到组织中的特定团队，并向所有其他团队应用三年删除策略。

## <a name="manage-retention-policies-for-teams"></a>管理团队的保留策略

### <a name="using-the-security--compliance-center"></a>使用安全 & 合规中心

#### <a name="create-a-retention-policy"></a>创建保留策略

若要为团队聊天和频道消息创建保留策略，请执行下列操作：

1. 在安全 & 合规中心的左侧导航中，转到 "**信息管理** > **保留**"。
2. 选择 "**创建**"。
3. 在 "为**你的策略命名**" 页面上，输入你的策略的名称和说明，然后单击 "**下一步**"。
4. 在 "**设置**" 页面上，指定是要保留数据、删除数据还是同时保留时间，然后单击 "**下一步**"。
5. 在 "**选择位置**" 页上，执行下列操作，然后单击 "**下一步**"：

    - 若要将策略应用到信道消息，请打开**团队频道消息**。  如果要将策略应用到组织中的特定团队，请选择 "**选择团队**"，然后选择所需团队。
    - 若要将策略应用于聊天，请打开**团队聊天**。 如果要将策略应用到组织中的特定用户，请选择 "**选择用户**"，然后选择所需的用户。
      > [!NOTE]
      > 当您打开**团队频道消息**和/或**团队聊天**时，所有其他位置将自动关闭。 团队保留策略只能包含团队位置。

        !["选择位置" 页上的团队频道消息和团队聊天选项的屏幕截图](media/retention-policies-create.png)

      > [!IMPORTANT]
      > 团队聊天和频道消息不受应用于**Exchange 电子邮件**或**Office 365 组**位置中的用户或组邮箱的保留策略的影响。 尽管团队聊天和频道邮件存储在 Exchange 中，但它们仅受应用于团队位置的保留策略的影响。

6. 查看您的设置，然后在准备就绪后，选择 "**创建此策略**"。

#### <a name="edit-a-retention-policy"></a>编辑保留策略

若要编辑团队保留策略，请执行下列操作：

1. 在安全 & 合规中心的左侧导航中，转到 "**信息管理** > **保留**"。
2. 在 "保留策略" 列表中，选中要编辑的保留策略旁边的复选框。
3. 选择要编辑的内容旁边的 "**编辑**"，进行所需的更改，单击 "**保存**"，然后单击 "**关闭**"。

    !["选择位置" 页上的团队频道消息和团队聊天选项的屏幕截图](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>删除保留策略

若要删除团队保留策略，请执行下列操作：

1. 在安全 & 合规中心的左侧导航中，转到 "**信息管理** > **保留**"。
2. 在 "保留策略" 列表中，选中要删除的保留策略旁边的复选框。
3. 选择 "**删除策略**"。

### <a name="using-powershell"></a>使用 PowerShell

若要使用 PowerShell 创建和管理团队保留策略，请使用以下 cmdlet。

|设置|规则|
|---|---|
|[新-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>已知问题

以下是正在跟踪和调查的团队中的保留策略的已知问题。

- 在 "**团队频道消息**位置" 行中的 "**选择团队**" 下，你可能会看到也不是团队的 Office 365 组。 未来将对此进行寻址。

- 在 "**团队聊天**位置" 行中的 "**选择用户**" 下，你可能会看到来宾和非邮箱用户。 保留策略不适于为来宾设置，我们正在努力从列表中删除这些保留策略。

- Exchange 生命周期助理（ELC）每天运行，但其 SLA 为7天。 因此，如果你有一个团队保留策略来删除超过60天的项目，这些项目最多可持续67天。 这不是一种新情况-它遵循 Exchange 模型。 当然，在大多数情况下，没有延迟。

## <a name="related-topics"></a>相关主题

- [保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
