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
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="0d3eb-103">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="0d3eb-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="0d3eb-104">Microsoft 365 中的保留策略和保留标签可帮助你更有效地管理组织的信息。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-104">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="0d3eb-105">可以配置保留设置，以保留符合组织内部策略、行业法规或法律需求所需的数据。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-105">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="0d3eb-106">还可以配置保留设置，删除被视为责任、不再需要保留或无法律或业务价值的数据。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-106">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="0d3eb-107">Teams 支持聊天和频道消息的保留策略，因此，作为管理员，你可以主动决定是保留、删除数据还是将其保留特定的一段时间，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-107">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="0d3eb-108">可将 Teams 保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="0d3eb-109">Teams 不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-109">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="0d3eb-110">若要详细了解保留，以及如何在 Microsoft 365 中为其他工作负荷使用保留策略或保留标签来应用保留设置，请参阅"了解保留策略和保留[标签"。](https://docs.microsoft.com/microsoft-365/compliance/retention)</span><span class="sxs-lookup"><span data-stu-id="0d3eb-110">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="0d3eb-111">Teams 保留策略的最低许可要求是 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-111">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="0d3eb-112">若要详细了解许可，请参阅 Microsoft [Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-112">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="0d3eb-113">Teams 保留策略的工作方式</span><span class="sxs-lookup"><span data-stu-id="0d3eb-113">How Teams retention policies work</span></span>

<span data-ttu-id="0d3eb-114">Teams 聊天消息存储在聊天中包含的每个用户邮箱的隐藏文件夹中，Teams 频道消息存储在团队的组邮箱中的类似隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-114">Teams chat messages are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="0d3eb-115">若要保留受保留策略限制的邮件，内容的副本将自动保留在名为 **"一** 直保留"的隐藏文件夹中，作为 **Exchange** 可恢复项目文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-115">To retain messages that are subject to a retention policy, a copy of the content is automatically kept in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="0d3eb-116">在从Holdholds 文件夹中永久删除这些邮件之前，这些邮件仍由电子数据展示工具搜索。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-116">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="0d3eb-117">有关 Teams 保留策略包含和排除哪些内容以及这些策略如何根据策略配置工作的详细信息，请参阅"了解 Microsoft Teams 的保留[期"。](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="0d3eb-117">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="0d3eb-118">该页解释了为什么保留策略删除消息时有时可能会看到延迟。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-118">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="0d3eb-119">例如，在保留策略中配置的过期期限之后，最多 7 天内可以看到消息。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-119">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="0d3eb-120">如果使用不同的保留设置设置多个 Teams 保留策略，则保留原则会解决任何冲突。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-120">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="0d3eb-121">例如：</span><span class="sxs-lookup"><span data-stu-id="0d3eb-121">For example:</span></span>
- <span data-ttu-id="0d3eb-122">如果在保留或删除相同内容之间发生冲突，则始终保留该内容。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-122">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="0d3eb-123">如果相同内容的保留时间存在冲突，将保留最长的保留期。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-123">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="0d3eb-124">这两个保留原则解决了在 Teams 有多个保留策略时可能出现的大多数冲突，但有关详细信息，请参阅保留原则或优先 [原则？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="0d3eb-124">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="0d3eb-125">何时使用 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="0d3eb-125">When to use retention policies for Teams</span></span>

<span data-ttu-id="0d3eb-126">在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-126">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="0d3eb-127">你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-127">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="0d3eb-128">你还可以配置适用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-128">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="0d3eb-129">对于 Teams 聊天，可选择要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-129">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="0d3eb-130">对于 Teams 频道消息，可选择要为其应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-130">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="0d3eb-131">例如，对于频道消息，可以将一年删除策略应用于组织中的特定团队，并将三年删除策略应用于所有其他团队。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-131">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="0d3eb-132">创建和管理 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="0d3eb-132">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="0d3eb-133">若要为 Teams 聊天和频道消息创建保留策略，请使用 Teams 位置的 [保留策略中的说明](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-133">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="0d3eb-134">该页包含有关在 Microsoft 365 中为其他工作负荷创建和管理保留策略的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-134">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="0d3eb-135">例如，你可能还希望为 Microsoft 365 组创建保留策略，以保留和删除在 Teams 中访问并存储在 OneDrive 或 SharePoint 中的文件。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-135">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="0d3eb-136">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="0d3eb-136">End user experience</span></span>

<span data-ttu-id="0d3eb-137">对于私人聊天 (1：1 聊天) 或群组聊天，最终用户将看到删除比保留策略配置旧的聊天，同时会显示一条控制消息，指出"我们已根据组织保留策略删除了较旧的消息"显示在尚未删除的消息顶部。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-137">For private chats (1:1 chats) or group chats, the end users will see that chats older than the retention policy configuration are deleted and a control message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="用户在 Teams 中通知，由于 Teams 保留策略，聊天消息已删除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中解释消息的用户因 Teams 保留策略而被删除":::

<span data-ttu-id="0d3eb-140">对于频道消息， (频道成员的) 会在消息过期后看到已删除的消息从视图中消失。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-140">For Channel messages, the end users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="0d3eb-141">如果已删除的消息是线程会话的父消息，则会显示一条消息，指出"由于保留策略而已删除此邮件"，而该邮件将代为父消息。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-141">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的通道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后通道的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="0d3eb-144">最终用户因删除的消息而看到的显示消息目前不可配置。</span><span class="sxs-lookup"><span data-stu-id="0d3eb-144">The displayed messages that end users see as a result of deleted messaging are not configurable at this time.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0d3eb-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="0d3eb-145">Related topics</span></span>

- [<span data-ttu-id="0d3eb-146">保留策略和保留标签入门</span><span class="sxs-lookup"><span data-stu-id="0d3eb-146">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="0d3eb-147">了解 Microsoft Teams 的保留期</span><span class="sxs-lookup"><span data-stu-id="0d3eb-147">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="0d3eb-148">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="0d3eb-148">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)