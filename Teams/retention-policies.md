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
description: 使用 Microsoft Teams 的保留策略保留符合内部策略、行业法规或法律需求所需的消息，并删除被视为责任或无法律业务价值的邮件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786824"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams 中的保留策略

Microsoft 365 中的保留策略和保留标签可帮助你更有效地管理组织的信息。 可以配置保留设置，以保留符合组织内部策略、行业法规或法律需求所需的数据。 还可以配置保留设置，删除被视为责任、不再需要保留或无法律或业务价值的数据。

Teams 支持聊天和频道消息的保留策略，因此，作为管理员，你可以主动决定是保留、删除数据还是将其保留特定的一段时间，然后将其删除。 可将 Teams 保留策略应用于整个组织或特定用户和团队。 Teams 不支持保留标签。

若要详细了解保留，以及如何在 Microsoft 365 中为其他工作负荷使用保留策略或保留标签来应用保留设置，请参阅"了解保留策略和保留[标签"。](https://docs.microsoft.com/microsoft-365/compliance/retention)

Teams 保留策略的最低许可要求是 Microsoft 365 E3。 若要详细了解许可，请参阅 Microsoft [Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-work"></a>Teams 保留策略的工作方式

Teams 聊天消息存储在聊天中包含的每个用户邮箱的隐藏文件夹中，Teams 频道消息存储在团队的组邮箱中的类似隐藏文件夹中。 若要保留受保留策略限制的邮件，内容的副本将自动保留在名为 **"一** 直保留"的隐藏文件夹中，作为 **Exchange** 可恢复项目文件夹中的子文件夹。 在从Holdholds 文件夹中永久删除这些邮件之前，这些邮件仍由电子数据展示工具搜索。

有关 Teams 保留策略包含和排除哪些内容以及这些策略如何根据策略配置工作的详细信息，请参阅"了解 Microsoft Teams 的保留[期"。](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> 该页解释了为什么保留策略删除消息时有时可能会看到延迟。 例如，在保留策略中配置的过期期限之后，最多 7 天内可以看到消息。

如果使用不同的保留设置设置多个 Teams 保留策略，则保留原则会解决任何冲突。 例如：
- 如果在保留或删除相同内容之间发生冲突，则始终保留该内容。
- 如果相同内容的保留时间存在冲突，将保留最长的保留期。

这两个保留原则解决了在 Teams 有多个保留策略时可能出现的大多数冲突，但有关详细信息，请参阅保留原则或优先 [原则？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何时使用 Teams 的保留策略

在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。

你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。 你还可以配置适用于组织中特定用户或团队的唯一策略。 对于 Teams 聊天，可选择要为其应用策略的用户。 对于 Teams 频道消息，可选择要为其应用策略的团队。

例如，对于频道消息，可以将一年删除策略应用于组织中的特定团队，并将三年删除策略应用于所有其他团队。

## <a name="create-and-manage-retention-policies-for-teams"></a>创建和管理 Teams 的保留策略

若要为 Teams 聊天和频道消息创建保留策略，请使用 Teams 位置的 [保留策略中的说明](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

该页包含有关在 Microsoft 365 中为其他工作负荷创建和管理保留策略的其他信息。 例如，你可能还希望为 Microsoft 365 组创建保留策略，以保留和删除在 Teams 中访问并存储在 OneDrive 或 SharePoint 中的文件。  

## <a name="end-user-experience"></a>最终用户体验

对于私人聊天 (1：1 聊天) 或群组聊天，最终用户将看到删除比保留策略配置旧的聊天，同时会显示一条控制消息，指出"我们已根据组织保留策略删除了较旧的消息"显示在尚未删除的消息顶部。

:::image type="content" source="media/retention-policies-image1.png" alt-text="用户在 Teams 中通知，由于 Teams 保留策略，聊天消息已删除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中解释消息的用户因 Teams 保留策略而被删除":::

对于频道消息， (频道成员的) 会在消息过期后看到已删除的消息从视图中消失。 如果已删除的消息是线程会话的父消息，则会显示一条消息，指出"由于保留策略而已删除此邮件"，而该邮件将代为父消息。

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的通道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后通道的屏幕截图":::

> [!NOTE]
> 最终用户因删除的消息而看到的显示消息目前不可配置。


## <a name="related-topics"></a>相关主题

- [保留策略和保留标签入门](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [了解 Microsoft Teams 的保留期](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [创建和配置保留策略](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)