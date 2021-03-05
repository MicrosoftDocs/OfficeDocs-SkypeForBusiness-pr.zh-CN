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
description: 使用 Microsoft Teams 的保留策略保留符合内部策略、行业法规或法律需求所需的邮件，并删除被视为责任或无法律业务价值的邮件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9422fd2b47ac3d460ee10e8933c45964d78282c1
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460652"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="eb19a-103">管理 Microsoft Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="eb19a-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="eb19a-104">如果在 Teams 中看到一条消息，指出你的聊天或消息已被保留策略删除，请参阅有关保留策略的 [Teams 消息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="eb19a-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="eb19a-105">本页上的信息适用于管理这些保留策略的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="eb19a-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="eb19a-106">Microsoft 365 中的保留策略和保留标签可帮助你更有效地管理组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="eb19a-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="eb19a-107">可以配置保留设置，以保留符合组织内部策略、行业法规或法律需求所需的数据。</span><span class="sxs-lookup"><span data-stu-id="eb19a-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="eb19a-108">还可以配置保留设置，删除被视为责任、不再需要保留或没有法律或业务价值的数据。</span><span class="sxs-lookup"><span data-stu-id="eb19a-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="eb19a-109">Teams 支持聊天和频道消息的保留策略，因此，作为管理员，你可以主动决定是保留此数据、删除数据，还是将其保留特定的一段时间，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="eb19a-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="eb19a-110">可将 Teams 保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="eb19a-110">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="eb19a-111">Teams 不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="eb19a-111">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="eb19a-112">若要详细了解保留，以及如何在 Microsoft 365 中为其他工作负荷使用保留策略或保留标签来应用保留设置，请参阅"了解保留策略和保留[标签"。](https://docs.microsoft.com/microsoft-365/compliance/retention)</span><span class="sxs-lookup"><span data-stu-id="eb19a-112">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="eb19a-113">Teams 保留策略的最低许可要求是 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="eb19a-113">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="eb19a-114">若要详细了解许可，请参阅 Microsoft [Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="eb19a-114">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retentiondeletion-policies-work"></a><span data-ttu-id="eb19a-115">Teams 保留/删除策略如何工作</span><span class="sxs-lookup"><span data-stu-id="eb19a-115">How Teams retention/deletion policies work</span></span>

<span data-ttu-id="eb19a-116">Teams 聊天消息存储在两个位置。</span><span class="sxs-lookup"><span data-stu-id="eb19a-116">Teams chat messages are stored in two locations.</span></span> <span data-ttu-id="eb19a-117">主副本存储在 Azure 中，辅助副本用于编译策略，存储在聊天中包含的每个用户的 Exchange Online 邮箱的隐藏文件夹中，Teams 频道消息存储在团队的组邮箱中的类似隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="eb19a-117">Primary copy is stored in Azure, a secondary copy, that is used for compilance policies, is stored in a hidden folder in the Exchange online mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="eb19a-118">将聊天消息删除策略应用于用户或团队时，首先删除次要副本，然后删除主副本。</span><span class="sxs-lookup"><span data-stu-id="eb19a-118">When a chat message deletion policy is applied to a user or Team, secondary copy is deleted first, followed by primary copy.</span></span> <span data-ttu-id="eb19a-119">电子数据展示或 Teams 搜索基于存储在辅助副本中的邮件，因此删除次要副本时，邮件不可发现。</span><span class="sxs-lookup"><span data-stu-id="eb19a-119">eDiscovery or Teams search is based off of messages stored in secondary copy and hence messages become non discoverable when secondary copy is deleted.</span></span> 

<span data-ttu-id="eb19a-120">将聊天消息保留策略应用于用户或团队时，如果由于其他删除策略或用户本身) 而删除了消息 (，则主副本会被删除，因此 Teams 客户端将看到消息消失，但辅助副本会自动移动到名为"可恢复的项目"文件夹中的隐藏文件夹 **（即"Exchange** 可恢复项目"文件夹中的子文件夹）中。 </span><span class="sxs-lookup"><span data-stu-id="eb19a-120">When a chat message retention poilcy is applied to a user or Team, and if the messages are deleted (either due to another deletion policy or by user themselves), the primary copy is deleted, hence Teams client will see the message disappear, but secondary copy is automatically moved to a hidden folder named **SubstrateHolds** , which is as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="eb19a-121">在从Holdholds 文件夹中永久删除这些邮件之前，电子数据展示工具仍可以搜索这些邮件。</span><span class="sxs-lookup"><span data-stu-id="eb19a-121">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="eb19a-122">有关 Teams 保留策略包含和排除哪些内容以及这些策略如何根据策略配置工作的详细信息，请参阅"了解 Microsoft Teams 的保留[期"。](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="eb19a-122">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="eb19a-123">该页解释了为什么保留策略删除消息时有时可能会看到延迟。</span><span class="sxs-lookup"><span data-stu-id="eb19a-123">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="eb19a-124">例如，在保留策略中配置的过期期限之后，最多 7 天可以显示消息。</span><span class="sxs-lookup"><span data-stu-id="eb19a-124">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="eb19a-125">如果使用不同的保留设置设置多个 Teams 保留策略，则保留原则会解决任何冲突。</span><span class="sxs-lookup"><span data-stu-id="eb19a-125">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="eb19a-126">例如：</span><span class="sxs-lookup"><span data-stu-id="eb19a-126">For example:</span></span>
- <span data-ttu-id="eb19a-127">如果在保留或删除相同内容之间发生冲突，则始终保留该内容。</span><span class="sxs-lookup"><span data-stu-id="eb19a-127">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="eb19a-128">如果保留相同内容的时间有冲突，则保留最长保留期。</span><span class="sxs-lookup"><span data-stu-id="eb19a-128">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="eb19a-129">这两个保留原则解决了在 Teams 有多个保留策略时可能出现的大多数冲突，但有关详细信息，请参阅保留原则或优先 [原则？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="eb19a-129">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="eb19a-130">何时使用 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="eb19a-130">When to use retention policies for Teams</span></span>

<span data-ttu-id="eb19a-131">在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。</span><span class="sxs-lookup"><span data-stu-id="eb19a-131">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="eb19a-132">你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="eb19a-132">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="eb19a-133">你还可以配置适用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="eb19a-133">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="eb19a-134">对于 Teams 聊天，可选择要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="eb19a-134">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="eb19a-135">对于 Teams 频道消息，可选择要为其应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="eb19a-135">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="eb19a-136">例如，对于频道消息，可以将一年删除策略应用于组织中的特定团队，并将三年删除策略应用于所有其他团队。</span><span class="sxs-lookup"><span data-stu-id="eb19a-136">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="eb19a-137">创建和管理 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="eb19a-137">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="eb19a-138">若要为 Teams 聊天和频道消息创建保留策略，请使用 Teams 位置的 [保留策略中的说明](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="eb19a-138">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="eb19a-139">该页包含有关在 Microsoft 365 中为其他工作负荷创建和管理保留策略的其他信息。</span><span class="sxs-lookup"><span data-stu-id="eb19a-139">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="eb19a-140">例如，你可能还希望为 Microsoft 365 组创建保留策略，以保留和删除 Teams 中访问并存储在 OneDrive 或 SharePoint 中的文件。</span><span class="sxs-lookup"><span data-stu-id="eb19a-140">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="eb19a-141">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="eb19a-141">End user experience</span></span>

<span data-ttu-id="eb19a-142">对于私人聊天 (1：1 聊天) 或群组聊天，用户将看到删除比保留策略配置旧的聊天，并且自动生成的消息显示"由于你的组织保留策略，我们已删除较旧的消息"显示在尚未删除的消息顶部。</span><span class="sxs-lookup"><span data-stu-id="eb19a-142">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="eb19a-143">例如：</span><span class="sxs-lookup"><span data-stu-id="eb19a-143">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知用户聊天消息由于 Teams 保留策略而被删除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中解释消息的用户由于 Teams 保留策略而被删除":::

<span data-ttu-id="eb19a-146">对于频道消息， (频道成员) 将在消息过期后看到已删除的消息从视图中消失。</span><span class="sxs-lookup"><span data-stu-id="eb19a-146">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="eb19a-147">如果已删除的消息是线程对话的父消息，则会显示一条消息，指出"此消息已由于保留策略而被删除"，而该邮件将代父消息。</span><span class="sxs-lookup"><span data-stu-id="eb19a-147">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="eb19a-148">例如：</span><span class="sxs-lookup"><span data-stu-id="eb19a-148">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的通道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后频道的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="eb19a-151">用户由于已删除的消息而看到的消息目前不可配置。</span><span class="sxs-lookup"><span data-stu-id="eb19a-151">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="eb19a-152">这些显示的消息中的链接将转到 [有关保留策略的 Teams 消息](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="eb19a-152">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="eb19a-153">此最终用户文档可帮助回答有关其邮件被删除原因的基本问题。</span><span class="sxs-lookup"><span data-stu-id="eb19a-153">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="eb19a-154">但是，作为保留策略部署的一部分，请确保与用户和技术支持人员沟通已配置设置的影响。</span><span class="sxs-lookup"><span data-stu-id="eb19a-154">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb19a-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb19a-155">Related topics</span></span>

- [<span data-ttu-id="eb19a-156">保留策略和保留标签入门</span><span class="sxs-lookup"><span data-stu-id="eb19a-156">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="eb19a-157">了解 Microsoft Teams 的保留期</span><span class="sxs-lookup"><span data-stu-id="eb19a-157">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="eb19a-158">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="eb19a-158">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)
