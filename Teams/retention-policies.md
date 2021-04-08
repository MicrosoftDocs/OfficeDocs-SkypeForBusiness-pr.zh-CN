---
title: 管理 Microsoft Teams 的保留策略
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft Teams 的保留策略保留组织需要遵守内部策略、行业法规或法律要求的邮件，并删除被视为责任或无法律业务价值的邮件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617754"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>管理 Microsoft Teams 的保留策略

> [!NOTE]
> 如果在 Teams 中看到一条消息，指出你的聊天或消息已被保留策略删除，请参阅 [有关保留策略的 Teams 消息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 本页上的信息适用于管理这些保留策略的 IT 管理员。

Microsoft 365 中的保留策略和保留标签可帮助你更有效地管理组织中的信息。 可以配置保留设置来保留符合组织内部策略、行业法规或法律要求所需的数据。 还可以配置保留设置，删除被视为责任数据、不再需要保留的数据或没有法律或业务价值的数据。

Teams 支持聊天和频道消息的保留策略，因此，作为管理员，你可以主动决定是保留、删除数据还是将其保留特定的一段时间，然后将其删除。 这些操作保留期的开始始终基于消息的创建时间。 可将 Teams 保留策略应用于整个组织或特定用户和团队。 Teams 不支持保留标签。

若要详细了解 Microsoft 365 中的保留解决方案，请参阅 [了解保留策略和保留标签](/microsoft-365/compliance/retention)。

受 Teams 保留策略限制的用户必须具有适当的许可证，例如 Office 365 E3 或 Office 365 A3。 有关这些保留策略的其他许可选项，请参阅 Microsoft [](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) [365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)安全与合规许可指南&部分。 若要详细了解 Teams 许可，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Teams 保留策略如何支持保留和删除操作

如果将 Teams 保留策略配置为保留聊天或频道消息，用户仍可在 Teams 应用中编辑和删除其消息。 虽然用户在 Teams 中不再看到其预先编辑或删除的邮件，但来自这些邮件的数据存储在一个安全的位置，该位置专为合规性管理员电子数据展示搜索设计。 此数据的永久删除不会在配置的保留期结束之前发生，或者如果另一个保留策略配置为保留此数据，或者它受电子数据展示保留 [的影响](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)。

将保留策略配置为删除聊天和频道消息时，这些消息将有资格获得自动删除。 如果消息仍显示在 Teams 应用中，则消息将从其中消失，并且通知用户保留策略 [已删除这些消息](#end-user-experience)。 如果邮件以前受到保留操作并且已被用户编辑或删除，则这些邮件现在将从安全位置删除，不再在电子数据展示搜索中返回。

有关这些策略如何工作的详细信息，具体取决于策略配置和用户操作，以及 Teams 保留策略包含和排除哪些消息数据，请参阅了解 Microsoft [Teams 的保留](/microsoft-365/compliance/retention-policies-teams)期。 该页还说明了为什么在保留策略删除邮件时，有时可能会遇到延迟。 例如，在保留策略中配置的过期期限最多 7 天后，Teams 应用中的用户可以看到消息。

如果使用不同的保留设置设置多个 Teams 保留策略，则保留原则可解决任何冲突。 例如：

- 如果在保留或删除相同内容之间发生冲突，则内容将始终保留在安全位置，以便合规性管理员能够使用电子数据展示进行搜索。
    
    此原则也适用于出于法律或调查原因在电子数据展示保留下的邮件。

- 如果相同内容的保留时间存在冲突，该内容将保留在安全位置中，保留时间最长。

这两个保留原则解决了在 Teams 有多个保留策略时可能出现的大多数冲突，但有关详细信息，请参阅保留原则或优先 [原则？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何时使用 Teams 的保留策略

在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。

你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。 你还可以配置适用于组织中特定用户或团队的唯一策略。 对于 Teams 聊天，可选择要为其应用策略的用户。 对于 Teams 频道消息，可选择要为其应用策略的团队。

例如，对于频道消息，可以将保留策略应用于组织的特定团队，并且该策略在 1 年后配置删除操作。 然后，将另一个保留策略应用到所有其他团队，该策略在 3 年后配置了删除操作。

## <a name="create-and-manage-retention-policies-for-teams"></a>创建和管理 Teams 的保留策略

若要为 Teams 聊天和频道消息创建或编辑保留策略，请使用 Teams 位置 [的保留策略中的说明](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

该页包含有关在 Microsoft 365 中为其他工作负荷创建和管理保留策略的其他信息。 例如，你可能还希望为 Microsoft 365 组创建保留策略，以保留和删除 Teams 中访问并存储在 OneDrive 或 SharePoint 中的文件。  

## <a name="end-user-experience"></a>最终用户体验

对于私人聊天 (1：1 聊天) 或群组聊天，用户将看到超过保留策略配置的聊天被删除，并且自动生成的消息显示"由于你的组织保留策略，我们已删除较旧的消息"显示在尚未删除的消息顶部。 例如：

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知用户聊天消息由于 Teams 保留策略而被删除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中解释消息的用户因 Teams 保留策略而被删除":::

对于频道消息， (频道) 会在消息过期后看到已删除的消息从视图中消失。 如果已删除的邮件是线程对话的父消息，则会显示一条消息，指出"此消息已由于保留策略而被删除"，以表示父消息。 例如：

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的通道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后通道的屏幕截图":::

> [!NOTE]
> 用户由于已删除的消息而看到的消息目前不可配置。

这些显示的消息中的链接将转到 [有关保留策略 的 Teams 消息](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 此最终用户文档可帮助回答有关其消息为何被删除的基本问题。 但是，作为保留策略部署的一部分，请确保与用户和技术支持人员沟通配置的设置的影响。

## <a name="related-topics"></a>相关主题

- [保留策略和保留标签入门](/microsoft-365/compliance/get-started-with-retention)
- [了解 Microsoft Teams 的保留期](/microsoft-365/compliance/retention-policies-teams)
- [创建和配置保留策略](/microsoft-365/compliance/create-retention-policies)
