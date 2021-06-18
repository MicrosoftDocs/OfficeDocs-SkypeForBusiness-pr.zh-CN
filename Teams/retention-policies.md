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
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617754"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="9b172-103">管理 Microsoft Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="9b172-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="9b172-104">如果在 Teams 中看到一条消息，并且该消息显示聊天或消息已被保留策略删除，请参阅 [Teams 消息中的保留策略](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="9b172-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="9b172-105">本页上的信息适用于管理这些保留策略的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="9b172-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="9b172-106">保留策略和 Microsoft 365 的保留标签可以帮助你更高效地管理组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="9b172-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="9b172-107">你可以通过配置保留设置，来保留需符合组织内部策略、行业法规或法律需求的数据。</span><span class="sxs-lookup"><span data-stu-id="9b172-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="9b172-108">还可以通过配置保留设置来删除被视为不利因素的数据、不再需要保留的数据，或不具有法律或商业价值的数据。</span><span class="sxs-lookup"><span data-stu-id="9b172-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="9b172-109">Teams 支持聊天和频道消息中的保留策略。因此，作为管理员，你可以主动决定是保留数据、删除数据还是将其保留一段时间后再删除。</span><span class="sxs-lookup"><span data-stu-id="9b172-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="9b172-110">这些操作的保留期的始终始于创建消息的时间。</span><span class="sxs-lookup"><span data-stu-id="9b172-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="9b172-111">可将 Teams 保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="9b172-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="9b172-112">Teams 不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="9b172-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="9b172-113">如需详细了解 Microsoft 365 中的保留解决方案，请参阅[详细了解保留策略和保留标签](/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="9b172-113">To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="9b172-114">受 Teams 保留策略约束的用户必须收到正式许可，例如 Office 365 E3 或 Office 365 A3。</span><span class="sxs-lookup"><span data-stu-id="9b172-114">Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3.</span></span> <span data-ttu-id="9b172-115">有关这些保留策略的其他许可选项，请参阅 [Microsoft 365 安全与合规性许可指南中的](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)[信息治理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)部分。</span><span class="sxs-lookup"><span data-stu-id="9b172-115">For other licensing options for these retention policies, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section from [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance).</span></span> <span data-ttu-id="9b172-116">如需了解有关 Teams 许可的详细信息，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="9b172-116">To learn more about licensing for Teams, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a><span data-ttu-id="9b172-117">Teams 保留策略如何支持保留和删除操作</span><span class="sxs-lookup"><span data-stu-id="9b172-117">How Teams retention policies support retain and delete actions</span></span>

<span data-ttu-id="9b172-118">如果将 Teams 保留策略配置为保留聊天或频道消息，用户仍然可以在其 Teams 应用中编辑和删除其消息。</span><span class="sxs-lookup"><span data-stu-id="9b172-118">If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app.</span></span> <span data-ttu-id="9b172-119">尽管用户不再在 Teams 中看到其预编辑或删除的消息，但这些消息中的数据仍会存储在安全的位置，该位置由合规性管理员为电子数据展示搜索而设计。</span><span class="sxs-lookup"><span data-stu-id="9b172-119">Although users no longer see their pre-edited or deleted messages in Teams, data from these messages is stored in a secured location that's designed for eDiscovery searches by compliance administrators.</span></span> <span data-ttu-id="9b172-120">此数据不会在已配置的保留期结束前永久删除。如果另一个保留策略被配置为保留此数据，或者此数据受 [电子数据展示保留](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)约束，那么此数据也不会被永久删除。</span><span class="sxs-lookup"><span data-stu-id="9b172-120">Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it is subject to an [eDiscovery hold](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).</span></span>

<span data-ttu-id="9b172-121">当保留策略被配置为删除聊天和频道消息时，这些消息将符合自动删除的条件。</span><span class="sxs-lookup"><span data-stu-id="9b172-121">When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion.</span></span> <span data-ttu-id="9b172-122">如果消息仍显示在 Teams 应用中，它们将从该应用中消失，同时[用户将被告知保留策略已删除这些消息](#end-user-experience)。</span><span class="sxs-lookup"><span data-stu-id="9b172-122">If the messages are still displayed in the Teams app, they will disappear from there and [users are informed that a retention policy has deleted these messages](#end-user-experience).</span></span> <span data-ttu-id="9b172-123">如果消息此前受保留操作约束，并且已被用户编辑或删除，则这些消息现在将从安全位置中删除，并且无法再在电子数据展示搜索中找回。</span><span class="sxs-lookup"><span data-stu-id="9b172-123">If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.</span></span>

<span data-ttu-id="9b172-124">这些策略如何发挥作用，需取决于你的策略配置、用户操作以及 Teams 保留策略中包含和排除了哪些消息数据。如需详细了解，请参阅[详细了解用于 Microsoft Teams 的保留](/microsoft-365/compliance/retention-policies-teams)部分。</span><span class="sxs-lookup"><span data-stu-id="9b172-124">For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span> <span data-ttu-id="9b172-125">该页还解释了为什么在保留策略删除消息时有时可能会遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="9b172-125">That page also explains why you might sometimes experience delays when retention policies delete messages.</span></span> <span data-ttu-id="9b172-126">例如，在保留政策已配置的有效期后至多 7 天内，用户可在 Teams 应用中看到消息。</span><span class="sxs-lookup"><span data-stu-id="9b172-126">For example, messages can be visible to users in the Teams app up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="9b172-127">如果使用不同的保留设置设置多个 Teams 保留策略，则保留原则可解决所有冲突。</span><span class="sxs-lookup"><span data-stu-id="9b172-127">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="9b172-128">例如：</span><span class="sxs-lookup"><span data-stu-id="9b172-128">For example:</span></span>

- <span data-ttu-id="9b172-129">如果保留或删除同一内容之间存在冲突，则内容始终保留在安全位置，方便合规性管理员使用电子数据展示搜索该内容。</span><span class="sxs-lookup"><span data-stu-id="9b172-129">If there is a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.</span></span>
    
    <span data-ttu-id="9b172-130">出于法律或调查原因，此原则也适用于电子数据展示保留的消息。</span><span class="sxs-lookup"><span data-stu-id="9b172-130">This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.</span></span>

- <span data-ttu-id="9b172-131">如果保留相同内容的时长存在冲突，则该内容会以最长保留期保留在安全位置。</span><span class="sxs-lookup"><span data-stu-id="9b172-131">If there is a conflict in how long to retain the same content, it is retained in the secured location for the longest retention period.</span></span>

<span data-ttu-id="9b172-132">当你有多个 Teams 保留策略时，这两个保留原则解决了大部分可能由此引发的冲突。如需了解详细信息，请参阅[保留原则，或如何创建优先级？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="9b172-132">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="9b172-133">何时使用 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="9b172-133">When to use retention policies for Teams</span></span>

<span data-ttu-id="9b172-134">在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。</span><span class="sxs-lookup"><span data-stu-id="9b172-134">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="9b172-135">你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="9b172-135">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="9b172-136">你还可以配置适用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="9b172-136">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="9b172-137">对于 Teams 聊天，可选择要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="9b172-137">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="9b172-138">对于 Teams 频道消息，可选择要为其应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="9b172-138">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="9b172-139">例如，对于频道消息来说，可以将保留策略应用于组织中的特定团队，并将保留策略配置为 1 年后删除。</span><span class="sxs-lookup"><span data-stu-id="9b172-139">For example, for channel messages, you can apply a retention policy to specific teams in your organization and that policy is configured with a delete action after 1 year.</span></span> <span data-ttu-id="9b172-140">然后，将另一个保留策略应用到所有其他团队，并将该策略配置为 3 年后删除。</span><span class="sxs-lookup"><span data-stu-id="9b172-140">Then apply another retention policy to all other teams and that policy is configured with a delete action after 3 years.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="9b172-141">在 Teams 创建并管理保留策略：</span><span class="sxs-lookup"><span data-stu-id="9b172-141">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="9b172-142">如需为 Teams 聊天和频道消息创建或编辑保留策略，请使用 [用于 Teams 位置的保留策略](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)中的说明。</span><span class="sxs-lookup"><span data-stu-id="9b172-142">To create or edit a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="9b172-143">该页包含为 Microsoft 365 中其他工作负荷创建和管理保留策略的补充信息。</span><span class="sxs-lookup"><span data-stu-id="9b172-143">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="9b172-144">例如，你可能还想要为 Microsoft 365 组创建保留策略，以保留和删除可通过 Teams 访问并存储在 OneDrive 或 SharePoint 中的文件。</span><span class="sxs-lookup"><span data-stu-id="9b172-144">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="9b172-145">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="9b172-145">End-user experience</span></span>

<span data-ttu-id="9b172-146">对于私人聊天（1：1 聊天）或群组聊天，用户将看到早于保留策略配置的聊天被删除，并在尚未删除的消息顶部看到一条自动生成的消息：“鉴于你所在组织的保留策略，我们删除了较旧的消息”。</span><span class="sxs-lookup"><span data-stu-id="9b172-146">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="9b172-147">例如：</span><span class="sxs-lookup"><span data-stu-id="9b172-147">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="用户在 Teams 中被告知，由于 Teams 的保留策略，聊天消息被删除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="用户在 Teams 中解释，消息由于 Teams 保留政策而被删除":::

<span data-ttu-id="9b172-150">对于频道消息来说，用户（频道成员）将在消息过期后看到已删除消息从视图中消失。</span><span class="sxs-lookup"><span data-stu-id="9b172-150">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="9b172-151">如果已删除的消息是线程会话的父消息，则父消息将由一条消息取代：“由于保留策略，此消息已被删除”。</span><span class="sxs-lookup"><span data-stu-id="9b172-151">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="9b172-152">例如：</span><span class="sxs-lookup"><span data-stu-id="9b172-152">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的频道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后的频道屏幕截图":::

> [!NOTE]
> <span data-ttu-id="9b172-155">此时，无法配置用户看到的由于删除消息而显示的消息。</span><span class="sxs-lookup"><span data-stu-id="9b172-155">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="9b172-156">这些显示的消息中的链接将转到[Teams 消息中的保留策略](https://support.microsoft.com/zh-CN/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="9b172-156">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/zh-CN/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="9b172-157">此文档适用于最终用户，有助于回答一些基本问题，让用户了解为什么他们的消息会被删除。</span><span class="sxs-lookup"><span data-stu-id="9b172-157">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="9b172-158">但是，作为保留策略部署的一部分，请确保向用户和技术支持人员传达配置设置的影响。</span><span class="sxs-lookup"><span data-stu-id="9b172-158">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b172-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="9b172-159">Related topics</span></span>

- [<span data-ttu-id="9b172-160">开始使用保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="9b172-160">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="9b172-161">详细了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="9b172-161">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="9b172-162">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="9b172-162">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
