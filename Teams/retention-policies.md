---
title: 管理存储的保留Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft Teams 保留策略来保留组织需要遵守内部策略、行业法规或法律要求的邮件，并删除被视为责任或无法律业务价值的邮件。
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
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="6528e-103">管理存储的保留Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6528e-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6528e-104">如果在邮件中看到一条消息Teams你的聊天或消息已被保留策略删除，请参阅有关保留Teams[的消息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="6528e-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="6528e-105">本页上的信息适用于管理这些保留策略的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="6528e-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="6528e-106">保留策略和保留标签Microsoft 365有助于更有效地管理组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="6528e-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="6528e-107">可以配置保留设置来保留符合组织内部策略、行业法规或法律要求所需的数据。</span><span class="sxs-lookup"><span data-stu-id="6528e-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="6528e-108">还可以配置保留设置，删除被视为责任数据、不再需要保留的数据或没有法律或业务价值的数据。</span><span class="sxs-lookup"><span data-stu-id="6528e-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="6528e-109">Teams聊天和频道消息的保留策略，以便作为管理员，您可以主动决定是保留、删除数据还是将其保留特定的一段时间，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="6528e-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="6528e-110">这些操作保留期的开始始终基于消息的创建时间。</span><span class="sxs-lookup"><span data-stu-id="6528e-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="6528e-111">可将 Teams 保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="6528e-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="6528e-112">用户不支持保留Teams。</span><span class="sxs-lookup"><span data-stu-id="6528e-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="6528e-113">若要详细了解数据中保留Microsoft 365，请参阅[了解保留策略和保留标签](/microsoft-365/compliance/retention)。</span><span class="sxs-lookup"><span data-stu-id="6528e-113">To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="6528e-114">用户必须拥有适当的许可证，Teams Office 365 E3 或 Office 365 A3。</span><span class="sxs-lookup"><span data-stu-id="6528e-114">Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3.</span></span> <span data-ttu-id="6528e-115">有关这些保留策略的其他许可选项，请参阅安全与合规[](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)Microsoft 365指南中的信息&[部分](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)。</span><span class="sxs-lookup"><span data-stu-id="6528e-115">For other licensing options for these retention policies, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section from [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance).</span></span> <span data-ttu-id="6528e-116">若要详细了解如何为用户Teams，请参阅Microsoft Teams[说明](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="6528e-116">To learn more about licensing for Teams, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a><span data-ttu-id="6528e-117">保留Teams如何支持保留和删除操作</span><span class="sxs-lookup"><span data-stu-id="6528e-117">How Teams retention policies support retain and delete actions</span></span>

<span data-ttu-id="6528e-118">如果配置了Teams保留策略以保留聊天或频道消息，用户仍可在应用内编辑和删除Teams消息。</span><span class="sxs-lookup"><span data-stu-id="6528e-118">If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app.</span></span> <span data-ttu-id="6528e-119">尽管用户在 Teams 中不再看到其预先编辑或删除的邮件，但来自这些消息的数据存储在合规性管理员设计用于电子数据展示搜索的安全位置。</span><span class="sxs-lookup"><span data-stu-id="6528e-119">Although users no longer see their pre-edited or deleted messages in Teams, data from these messages is stored in a secured location that's designed for eDiscovery searches by compliance administrators.</span></span> <span data-ttu-id="6528e-120">此数据的永久删除不会在配置的保留期结束之前发生，或者如果另一个保留策略配置为保留此数据，或者它受电子数据展示保留 [的影响](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)。</span><span class="sxs-lookup"><span data-stu-id="6528e-120">Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it is subject to an [eDiscovery hold](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).</span></span>

<span data-ttu-id="6528e-121">将保留策略配置为删除聊天和频道消息时，这些消息将有资格获得自动删除。</span><span class="sxs-lookup"><span data-stu-id="6528e-121">When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion.</span></span> <span data-ttu-id="6528e-122">如果消息仍显示在 Teams应用中，它们将从该应用中消失，并且通知用户保留策略已删除[这些消息](#end-user-experience)。</span><span class="sxs-lookup"><span data-stu-id="6528e-122">If the messages are still displayed in the Teams app, they will disappear from there and [users are informed that a retention policy has deleted these messages](#end-user-experience).</span></span> <span data-ttu-id="6528e-123">如果邮件以前受到保留操作并且已被用户编辑或删除，则这些邮件现在将从安全位置删除，不再在电子数据展示搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="6528e-123">If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.</span></span>

<span data-ttu-id="6528e-124">有关这些策略如何工作的详细信息，具体取决于策略配置和用户操作，以及包括和排除哪些消息数据作为 Teams 保留策略，请参阅了解 Microsoft Teams 的[保留](/microsoft-365/compliance/retention-policies-teams)。</span><span class="sxs-lookup"><span data-stu-id="6528e-124">For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span> <span data-ttu-id="6528e-125">该页还说明了为什么在保留策略删除邮件时，有时可能会遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="6528e-125">That page also explains why you might sometimes experience delays when retention policies delete messages.</span></span> <span data-ttu-id="6528e-126">例如，在保留策略中配置的过期期限Teams 7 天后，消息对应用应用的用户可见。</span><span class="sxs-lookup"><span data-stu-id="6528e-126">For example, messages can be visible to users in the Teams app up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="6528e-127">如果使用不同的保留Teams设置设置多个保留策略，则保留原则可解决任何冲突。</span><span class="sxs-lookup"><span data-stu-id="6528e-127">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="6528e-128">例如：</span><span class="sxs-lookup"><span data-stu-id="6528e-128">For example:</span></span>

- <span data-ttu-id="6528e-129">如果在保留或删除相同内容之间发生冲突，则内容将始终保留在安全位置，以便合规性管理员能够使用电子数据展示进行搜索。</span><span class="sxs-lookup"><span data-stu-id="6528e-129">If there is a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.</span></span>
    
    <span data-ttu-id="6528e-130">此原则也适用于出于法律或调查原因在电子数据展示保留下的邮件。</span><span class="sxs-lookup"><span data-stu-id="6528e-130">This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.</span></span>

- <span data-ttu-id="6528e-131">如果相同内容的保留时间存在冲突，该内容将保留在安全位置中，保留时间最长。</span><span class="sxs-lookup"><span data-stu-id="6528e-131">If there is a conflict in how long to retain the same content, it is retained in the secured location for the longest retention period.</span></span>

<span data-ttu-id="6528e-132">这两个保留原则解决了针对 Teams 使用多个保留策略时可能出现的大多数冲突，但有关详细信息，请参阅保留原则或优先原则[？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="6528e-132">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="6528e-133">何时使用 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="6528e-133">When to use retention policies for Teams</span></span>

<span data-ttu-id="6528e-134">在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。</span><span class="sxs-lookup"><span data-stu-id="6528e-134">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="6528e-135">你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="6528e-135">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="6528e-136">你还可以配置适用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="6528e-136">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="6528e-137">对于 Teams 聊天，可选择要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="6528e-137">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="6528e-138">对于 Teams 频道消息，可选择要为其应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="6528e-138">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="6528e-139">例如，对于频道消息，可以将保留策略应用于组织的特定团队，并且该策略在 1 年后配置删除操作。</span><span class="sxs-lookup"><span data-stu-id="6528e-139">For example, for channel messages, you can apply a retention policy to specific teams in your organization and that policy is configured with a delete action after 1 year.</span></span> <span data-ttu-id="6528e-140">然后，将另一个保留策略应用到所有其他团队，该策略在 3 年后配置了删除操作。</span><span class="sxs-lookup"><span data-stu-id="6528e-140">Then apply another retention policy to all other teams and that policy is configured with a delete action after 3 years.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="6528e-141">为用户创建和管理保留Teams</span><span class="sxs-lookup"><span data-stu-id="6528e-141">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="6528e-142">若要为聊天和频道消息Teams或编辑保留策略，请使用"保留策略"中的说明Teams[位置](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="6528e-142">To create or edit a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="6528e-143">该页包含有关为云中其他工作负荷创建和管理保留策略Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6528e-143">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="6528e-144">例如，可能还需要为 Microsoft 365 组创建保留策略，以保留和删除在 Teams 中访问并存储在 OneDrive 或 SharePoint 中的文件。</span><span class="sxs-lookup"><span data-stu-id="6528e-144">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="6528e-145">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="6528e-145">End-user experience</span></span>

<span data-ttu-id="6528e-146">对于私人聊天 (1：1 聊天) 或群组聊天，用户将看到超过保留策略配置的聊天被删除，并且自动生成的消息显示"由于你的组织保留策略，我们已删除较旧的消息"显示在尚未删除的消息顶部。</span><span class="sxs-lookup"><span data-stu-id="6528e-146">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="6528e-147">例如：</span><span class="sxs-lookup"><span data-stu-id="6528e-147">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="用户通过Teams通知，由于用户保留策略Teams删除聊天消息":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="由于Teams保留策略，Teams用户":::

<span data-ttu-id="6528e-150">对于频道消息， (频道) 会在消息过期后看到已删除的消息从视图中消失。</span><span class="sxs-lookup"><span data-stu-id="6528e-150">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="6528e-151">如果已删除的邮件是线程对话的父消息，则会显示一条消息，指出"此消息已由于保留策略而被删除"，以表示父消息。</span><span class="sxs-lookup"><span data-stu-id="6528e-151">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="6528e-152">例如：</span><span class="sxs-lookup"><span data-stu-id="6528e-152">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前的通道屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后通道的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="6528e-155">用户由于已删除的消息而看到的消息目前不可配置。</span><span class="sxs-lookup"><span data-stu-id="6528e-155">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="6528e-156">这些显示的消息中的链接将Teams[保留策略的消息](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="6528e-156">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="6528e-157">此最终用户文档可帮助回答有关其消息为何被删除的基本问题。</span><span class="sxs-lookup"><span data-stu-id="6528e-157">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="6528e-158">但是，作为保留策略部署的一部分，请确保与用户和技术支持人员沟通配置的设置的影响。</span><span class="sxs-lookup"><span data-stu-id="6528e-158">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6528e-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="6528e-159">Related topics</span></span>

- [<span data-ttu-id="6528e-160">保留策略和保留标签入门</span><span class="sxs-lookup"><span data-stu-id="6528e-160">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="6528e-161">了解保留期Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6528e-161">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="6528e-162">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="6528e-162">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
