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
description: 使用 Microsoft Teams 的保留策略可以保留满足组织内部策略、行业法规或法律要求所需的消息，并删除被视为不利因素或没有法律及商业价值的消息。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a122bd1d0bb3c8cba450293b43f7532f36c510831bd301ed30d9955a9a1f8d31
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296689"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>管理 Microsoft Teams 的保留策略

> [!NOTE]
> 如果在 Teams 中看到一条消息，并且该消息显示聊天或消息已被保留策略删除，请参阅 [Teams 消息中的保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 本页上的信息适用于管理这些保留策略的 IT 管理员。

保留策略和 Microsoft 365 的保留标签可以帮助你更高效地管理组织中的信息。 你可以通过配置保留设置，来保留需符合组织内部策略、行业法规或法律需求的数据。 还可以通过配置保留设置来删除被视为不利因素的数据、不再需要保留的数据，或不具有法律或商业价值的数据。

Teams 支持聊天和频道消息中的保留策略。因此，作为管理员，你可以主动决定是保留数据、删除数据还是将其保留一段时间后再删除。 这些操作的保留期的始终始于创建消息的时间。 可将 Teams 保留策略应用于整个组织或特定用户和团队。 Teams 不支持保留标签。

如需详细了解 Microsoft 365 中的保留解决方案，请参阅[详细了解保留策略和保留标签](/microsoft-365/compliance/retention)。

受 Teams 保留策略约束的用户必须收到正式许可，例如 Office 365 E3 或 Office 365 A3。 有关这些保留策略的其他许可选项，请参阅 [Microsoft 365 安全与合规性许可指南中的](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)[信息治理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)部分。 如需了解有关 Teams 许可的详细信息，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Teams 保留策略如何支持保留和删除操作

如果将 Teams 保留策略配置为保留聊天或频道消息，用户仍然可以在其 Teams 应用中编辑和删除其消息。 尽管用户不再在 Teams 中看到其预编辑或删除的消息，但这些消息中的数据仍会存储在安全的位置，该位置由合规性管理员为电子数据展示搜索而设计。 此数据不会在已配置的保留期结束前永久删除。如果另一个保留策略被配置为保留此数据，或者此数据受 [电子数据展示保留](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)约束，那么此数据也不会被永久删除。

当保留策略被配置为删除聊天和频道消息时，这些消息将符合自动删除的条件。 如果消息仍显示在 Teams 应用中，它们将从该应用中消失，同时[用户将被告知保留策略已删除这些消息](#end-user-experience)。 如果消息此前受保留操作约束，并且已被用户编辑或删除，则这些消息现在将从安全位置中删除，并且无法再在电子数据展示搜索中找回。

这些策略如何发挥作用，需取决于你的策略配置、用户操作以及 Teams 保留策略中包含和排除了哪些消息数据。如需详细了解，请参阅[详细了解用于 Microsoft Teams 的保留](/microsoft-365/compliance/retention-policies-teams)部分。 该页还解释了为什么在保留策略删除消息时有时可能会遇到延迟。 例如，在保留政策已配置的有效期后至多 7 天内，用户可在 Teams 应用中看到消息。

如果使用不同的保留设置设置多个 Teams 保留策略，则保留原则可解决所有冲突。 例如：

- 如果保留或删除同一内容之间存在冲突，则内容始终保留在安全位置，方便合规性管理员使用电子数据展示搜索该内容。
    
    出于法律或调查原因，此原则也适用于电子数据展示保留的消息。

- 如果保留相同内容的时长存在冲突，则该内容会以最长保留期保留在安全位置。

当你有多个 Teams 保留策略时，这两个保留原则解决了大部分可能由此引发的冲突。如需了解详细信息，请参阅[保留原则，或如何创建优先级？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何时使用 Teams 的保留策略

在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。

可以非常高效地配置所有消息的单个保留Teams策略。 或者，为了进行更精细的控制，可以：

- 对于私人聊天，请 (1：1 或 1：) 聊天、来自标准通道的消息或来自专用通道的消息制定单独的保留策略。

- 将策略仅应用于组织的特定用户或团队。 对于Teams和专用频道，可以选择策略所应用到的用户。 对于 Teams 频道消息，可选择要为其应用策略的团队。

例如，对于标准频道消息：为组织中特定团队创建保留策略，在 1 年后使用删除操作配置该策略。 然后为所有其他团队的标准频道消息创建另一个保留策略，然后在 3 年后通过删除操作配置该策略。

## <a name="create-and-manage-retention-policies-for-teams"></a>在 Teams 创建并管理保留策略：

若要为邮件创建或编辑Teams策略，请使用保留策略[中的说明Teams位置](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

该页包含为 Microsoft 365 中其他工作负荷创建和管理保留策略的补充信息。 例如，你可能还想要为 Microsoft 365 组创建保留策略，以保留和删除可通过 Teams 访问并存储在 OneDrive 或 SharePoint 中的文件。  

## <a name="end-user-experience"></a>最终用户体验

对于私人聊天（1：1 聊天）或群组聊天，用户将看到早于保留策略配置的聊天被删除，并在尚未删除的消息顶部看到一条自动生成的消息：“鉴于你所在组织的保留策略，我们删除了较旧的消息”。 例如：

:::image type="content" source="media/retention-policies-image1.png" alt-text="用户在 Teams 中被告知，由于 Teams 的保留策略，聊天消息被删除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="用户在 Teams 中解释，消息由于 Teams 保留政策而被删除":::

对于频道消息来说，用户（频道成员）将在消息过期后看到已删除消息从视图中消失。 如果已删除的消息是线程会话的父消息，则父消息将由一条消息取代：“由于保留策略，此消息已被删除”。 例如：

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的频道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后的频道屏幕截图":::

> [!NOTE]
> 此时，无法配置用户看到的由于删除消息而显示的消息。

这些显示的消息中的链接将转到[Teams 消息中的保留策略](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 此文档适用于最终用户，有助于回答一些基本问题，让用户了解为什么他们的消息会被删除。 但是，作为保留策略部署的一部分，请确保向用户和技术支持人员传达配置设置的影响。

## <a name="related-topics"></a>相关主题

- [开始使用保留策略和保留标签](/microsoft-365/compliance/get-started-with-retention)
- [详细了解用于 Microsoft Teams 的保留](/microsoft-365/compliance/retention-policies-teams)
- [创建和配置保留策略](/microsoft-365/compliance/create-retention-policies)
