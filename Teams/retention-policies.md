---
title: Microsoft Teams 中的保留策略
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 在本文中，你将了解保留策略以及如何在 Microsoft 团队中创建和管理它们。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 18364c69baa2bbf226a898a141d5070580177c24
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520759"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams 中的保留策略

保留策略可帮助你更高效地管理组织中的信息。 使用保留策略可以保留满足组织的内部政策、行业法规或法律要求所需的数据，以及删除被视为负担、不再需要保留或没有法律或业务价值的数据。

默认情况下，团队聊天、频道和文件数据将无限期保留，除非有尝试通过保留策略、用户删除、管理员删除等删除内容。作为管理员，你可以为聊天和频道消息设置团队保留策略，并提前确定是保留数据、删除数据还是在特定时间段内保留数据，然后将其删除。

在 [Microsoft 365 合规中心](https://protection.office.com/) 中创建和管理团队和其他工作负荷的保留策略，或者使用安全 & 合规性中心 PowerShell cmdlet。 可将 Teams 保留策略应用于整个组织或特定用户和团队。

> [!NOTE]
> 我们尚不支持保留专用频道消息的配置。 支持保留在私人渠道中共享的文件。

若要了解有关 Microsoft 365 或 Office 365 的保留策略的详细信息，请参阅 [保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。

## <a name="what-are-retention-policies-for-teams"></a>什么是团队的保留策略

在为 Teams 或任何其他工作负载设置保留策略时，可将其设置为：

- **保留数据**：使用保留策略确保将数据保留一段指定的时间，无论用户应用中发生什么情况都是如此。 出于合规性原因而保留数据，并且可用于电子数据展示，直到保留期到期为止，之后，策略会指示是不执行任何操作还是删除数据。 例如，如果创建 Teams 保留策略以将频道消息保留 7 年，则会将用于电子数据展示的消息保留 7 年，即便用户在 Teams 中删除了这些消息也是如此。
- **删除数据**：使用保留策略删除数据，以确保它不会对你的组织造成负担。 借助 Teams 保留策略，当你删除数据时，它将从 Teams 服务上的所有存储位置永久删除。

借助 Teams 保留策略，你可以：

- 将 Teams 聊天和/或频道消息保留一段指定的时间，并且在此期限后不执行任何操作。
- 将 Teams 聊天和/或频道消息保留一段指定的时间，并在此期限后删除数据。
- 在指定的时间段后删除 Teams 聊天和/或频道消息。

> [!NOTE]
> 请记住，在 Teams 中，用户在私人聊天中共享的文件存储在共享该文件的用户的 OneDrive for Business 帐户中。 由团队成员上传到频道对话的文件则存储在团队的 SharePoint 网站中。 因此，若要保留或删除 Teams 中的文件，请创建适用于 OneDrive for Business 和 SharePoint Online 的保留策略。

如果数据受保留策略的约束，用户可以继续使用它，因为该数据将保留在其原始位置。 如果用户编辑或删除受策略约束的数据，则副本将保存到该策略生效时保留该副本的安全位置。

保留策略的最低许可要求是 Office 365 E3。 若要了解有关许可的详细信息，请参阅 [Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-work"></a>Teams 保留策略的工作方式

团队聊天内容存储在 Teamschat 中每个用户的隐藏文件夹中 () 在聊天中的每个用户的邮箱中，而团队频道消息存储在团队的组邮箱中的隐藏文件夹中 () Teamschat。 Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。 借助 Teams 保留策略，当你删除数据时，将从 Exchange 邮箱和基础聊天服务中永久删除该数据。

将 **保留保留** 策略应用到团队聊天或频道邮件时，将发生以下情况：

- 如果在保留期间用户在保留期间内编辑或删除了聊天或频道消息，则会将邮件复制 (如果已编辑，则) 或移动 (如果已将其删除) 到 SubstrateHolds 文件夹并存储在保留期。 如果将策略配置为在保留期到期时删除数据，则将在保留期到期的当天永久删除消息。
- 如果 **保留** 期间用户未删除聊天或频道消息，则邮件将在保留期到期后的一天内移动到 SubstrateHolds 文件夹。 如果将策略配置为在保留期到期时删除数据，则将在消息移至文件夹的一天后永久删除该消息。

将 **保留期间删除** 策略应用到团队聊天和频道消息时，将发生以下情况：

- 当聊天或频道消息到期时，如果保留消息的年龄超过了 **保留-删除** 策略，后端服务标识已过期消息并开始在后端存储 (用户或组邮箱) 中删除它们。
- 在后端存储中删除一条消息后，将触发一个过程，以便在 Azure 已通电的聊天服务和用户的团队应用中删除相同的消息。 对于要在 "团队" 应用中删除的邮件，应用需要连接到 internet 并处于空闲状态 (无用户活动) ，因此删除过程不会影响用户体验。 由于用户可能有多个设备（可能处于不同状态），因此保留删除不会完全与这些设备同步。
- 在后端存储中的消息删除完成后，这些消息将在合规性搜索报告（如电子数据展示）中停止显示。

> [!NOTE]
> 相同的流程适用于 Skype for Business Online 和 Teams 互操作聊天。 当 Skype for Business Online 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。 Teams 保留策略将从 Teams 线程中删除这些消息。 但是，如果已为 Skype for Business Online 开启对话历史记录，并且从 Skype for Business Online 客户端将会话历史记录保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。

> [!NOTE]
> 邮件的删除是永久性和不可逆的。

Teams 中的保留策略基于聊天或频道消息的创建日期，并且具有追溯性。 换言之，如果你创建保留策略来删除 90 天之前的数据，则在 90 天之前创建的 Teams 数据将被删除。

应用于 SharePoint Online 或 OneDrive for Business 的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。 在这种情况下，该文件仍将显示在 Teams 消息中，但当用户单击文件时，将收到“找不到文件”错误。 如果某人手动从 SharePoint Online 或 OneDrive for Business 中删除文件，则在没有应用策略的情况下也会发生这种情况。

### <a name="considerations-and-limitations"></a>注意事项和限制

以下是在使用 Teams 保留策略时需要注意的一些事项和限制：

- Teams 需要与其他工作负载分开的保留策略。 换言之，你必须为 Teams 聊天和/或频道消息创建特定保留策略。 因此，你不能在组织范围的保留策略中包括 Teams。

- 不支持私有频道消息。 目前，Teams 的保留策略仅适用于标准频道消息。

- Teams 不支持高级保留设置，例如，用于为包含关键字或敏感信息的内容应用策略的功能。 目前，Teams 中的保留策略适用于所有聊天和/或频道消息内容。

- 当这些邮件过期时，团队保留策略将触发删除聊天和频道消息的过程， (基于邮件创建日期) 。 但是，根据服务负载，可能需要长达7天才能永久删除后端存储和团队应用中的这些消息。 此外，这些邮件可以使用合规性工具 (电子数据展示、最终用户搜索) ，直至它们被从后端存储中永久删除。

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>多个保留策略和保留原则

如果设置多个具有不同期限的 Teams 保留策略，则[保留策略原则](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)适用。 以下是关于优先级的概述：

- 保留始终优先于删除
- 优选最长的保留期
- 显式添加的位置优先于隐式添加的位置
- 优选最短删除期

## <a name="when-to-use-retention-policies-for-teams"></a>何时使用 Teams 的保留策略

在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。

你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。 你还可以配置适用于组织中特定用户或团队的唯一策略。 对于 Teams 聊天，可选择要为其应用策略的用户。 对于 Teams 频道消息，可选择要为其应用策略的团队。

例如，对于频道消息，可以将一年删除策略应用于组织中的特定团队，并将三年删除策略应用于所有其他团队。

## <a name="manage-retention-policies-for-teams"></a>管理 Teams 的保留策略

### <a name="using-the-security--compliance-center"></a>使用安全与合规中心

#### <a name="create-a-retention-policy"></a>创建保留策略

若要为 Teams 聊天和频道消息创建保留策略，请执行以下操作：

1. 在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。
2. 选择“**创建**”。
3. 在“**为你的策略命名**”页面上，为你的策略输入名称和说明，然后单击“**下一步**”。
4. 在“**设置**”页上，指定是保留数据、删除数据还是先保留后删除，指定保留期，然后单击“**下一步**”。
5. 在“**选择位置**”页面上，执行以下操作，然后单击“**下一步**”：

    - 若要将策略应用于频道消息，请开启“**Teams 频道消息**”。  如果要将策略应用于组织中的特定团队，请选择“**选择团队**”，然后选择所需的团队。
    - 若要将策略应用于聊天，请开启“**Teams 聊天**”。 如果要将策略应用于组织中的特定用户，请选择“**选择用户**”，然后选择所需的用户。
      > [!NOTE]
      > 当开启“**Teams 频道消息**”和/或“**Teams 聊天**”时，所有其他位置都会自动关闭。 Teams 保留策略只能包含 Teams 位置。

        ![“选择位置”页面上的“Teams 频道消息”和“Teams 聊天”选项的屏幕截图](media/retention-policies-create.png)

      > [!IMPORTANT]
      > 团队聊天和频道消息不受应用于 **Exchange 电子邮件** 或 **Microsoft 365 组** 位置中的用户或组邮箱的保留策略的影响。 即使 Teams 聊天和频道消息存储在 Exchange 中，它们也仅受到应用于 Teams 位置的保留策略的影响。

6. 查看设置，在准备就绪后，选择“**创建此策略**”。

#### <a name="edit-a-retention-policy"></a>编辑保留策略

若要编辑 Teams 保留策略，请执行以下操作：

1. 在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。
2. 在保留策略列表中，选中要编辑的保留策略旁边的复选框。
3. 选择要编辑的策略旁边的“**编辑**”，进行更改，单击“**保存**”，然后单击“**关闭**”。

    ![“选择位置”页面上的“Teams 频道消息”和“Teams 聊天”选项的屏幕截图](media/retention-policies-edit.png)

> [!WARNING]
> 如果你已配置特定团队或特定用户以包含团队频道消息或团队聊天的内容，并编辑这些内容以删除该位置的最后一个，则该位置的配置将恢复为 " **全部**"。 请确保这是你希望在保存策略之前执行的配置。
> 
> 例如，如果你指定了一个团队聊天用户以包含在配置为删除数据的保留策略中，然后编辑策略以删除此用户，则默认情况下，所有用户都将遵守永久删除其团队聊天消息的保留策略。 对于团队频道消息，这同样适用于包含。
> 
> 在这种情况下，如果你不希望团队频道消息或团队的 **所有设置均** 受保留策略制约，请将位置切换为 "关"。 或者，将 "排除" 指定为不受策略阻止。


#### <a name="delete-a-retention-policy"></a>删除保留策略

若要删除 Teams 保留策略，请执行以下操作：

1. 在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。
2. 在保留策略列表中，选中要删除的保留策略旁边的复选框。
3. 选择“**删除策略**”。

### <a name="end-user-experience"></a>最终用户体验

对于私人聊天 (1:1 聊天) 或群组聊天，最终用户将看到早于保留策略配置的聊天已删除，并显示一条控制消息，显示 "我们已删除较早的 messaged，因为您的组织的保留策略" 已在尚未删除的邮件上显示。
:::image type="content" source="media/retention-policies-image1.png" alt-text="聊天保留屏幕截图":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="群组聊天保留屏幕截图":::

对于频道消息， (频道成员) 的最终用户将看到邮件过期后，已删除的邮件会从视图中消失。 如果已删除邮件是串接对话的父邮件，则在替换父消息时，将显示一条消息，指出 "此消息已被删除，因为保留策略已删除"。

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前频道的屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后频道的屏幕截图":::

> [!NOTE]
> 最终用户消息目前不能由用户或管理员修改。


### <a name="using-powershell"></a>使用 PowerShell

若要使用 [安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)创建和管理团队保留策略，请使用以下 cmdlet：

|策略|规则|
|---|---|
|[新-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [新-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>已知问题

以下是正在跟踪和调查的 Teams 中的已知保留策略问题。

- 在 "**团队频道消息**位置" 行中的 "**选择团队**" 下，你可能会看到还不是团队的 Microsoft 365 组。 此问题将在未来得到解决。

- 在“**Teams 聊天**”位置行中的“**选择用户**”下，你可能会看到来宾和非邮箱用户。 保留策略不是为来宾设置的，我们正致力于从列表中删除来宾。

- Exchange 生命周期助理 (的 ELC) 每天运行，但在某些情况下，时间延迟已运行最长7天。 因此，如果你创建了 Teams 保留策略来删除 60 天之前的项目，则这些项目最长可保留 67 天。 这不是新情况 - 它遵循 Exchange 模型。 当然，在大多数情况下，不会出现延迟。

## <a name="related-topics"></a>相关主题

- [保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
