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
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="63613-103">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="63613-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="63613-104">保留策略可帮助您更有效地管理组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="63613-104">Retention policies help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="63613-105">使用保留策略来保留符合组织的内部策略、行业法规或法律需求的数据，并删除被视为责任的数据，而不再需要保留，或者没有法律或商业价值。</span><span class="sxs-lookup"><span data-stu-id="63613-105">Use retention policies to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs, and to delete data that's considered a liability, that you're no longer required to keep, or has no legal or business value.</span></span>

<span data-ttu-id="63613-106">默认情况下，团队聊天、频道和文件数据将永久保留。</span><span class="sxs-lookup"><span data-stu-id="63613-106">By default, Teams chat, channel, and files data are retained forever.</span></span> <span data-ttu-id="63613-107">作为管理员，你可以为聊天和频道消息设置团队保留策略，并提前确定是保留数据、删除数据还是在特定时间段内保留数据，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="63613-107">As an admin, you can set up Teams retention policies for chat and channel messages and decide proactively whether to retain the data, delete it, or retain it for a specific period of time and then delete it.</span></span>

<span data-ttu-id="63613-108">在[Office 365 安全 & 合规中心](https://protection.office.com/)或使用安全 & 合规中心 PowerShell cmdlet 中，你可以创建和管理团队和其他工作负荷的保留策略。</span><span class="sxs-lookup"><span data-stu-id="63613-108">You create and manage retention policies for Teams and other workloads in the [Office 365 Security & Compliance Center](https://protection.office.com/) or by using the Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="63613-109">您可以将团队保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="63613-109">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span>

> [!NOTE]
> <span data-ttu-id="63613-110">我们尚不支持保留专用频道消息的配置。</span><span class="sxs-lookup"><span data-stu-id="63613-110">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="63613-111">支持在专用频道中共享的文件的保留。</span><span class="sxs-lookup"><span data-stu-id="63613-111">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="63613-112">若要了解有关 Office 365 的保留策略的详细信息，请参阅[保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="63613-112">To learn more about retention policies for Office 365, see [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="what-are-retention-policies-for-teams"></a><span data-ttu-id="63613-113">团队的保留策略是什么？</span><span class="sxs-lookup"><span data-stu-id="63613-113">What are retention policies for Teams?</span></span>

<span data-ttu-id="63613-114">为团队或任何其他工作负荷设置保留策略时，可以将其设置为：</span><span class="sxs-lookup"><span data-stu-id="63613-114">When you set up a retention policy for Teams or any other workload, you can set them up to:</span></span>

- <span data-ttu-id="63613-115">**保留数据**：使用保留策略确保数据在指定时间段内保留，无论用户应用中发生了什么情况。</span><span class="sxs-lookup"><span data-stu-id="63613-115">**Retain data**: Use a retention policy to ensure that your data is retained for a specified period of time, regardless of what happens in the user app.</span></span> <span data-ttu-id="63613-116">出于合规性原因，将保留数据，并且电子数据展示在保留期到期之前可用，之后你的策略指示是不执行任何操作，还是删除数据。</span><span class="sxs-lookup"><span data-stu-id="63613-116">Data is retained for compliance reasons and is available for eDiscovery until the retention period expires, after which your policy indicates whether to do nothing or delete the data.</span></span> <span data-ttu-id="63613-117">例如，如果创建团队保留策略以将频道消息保留7年，则邮件将在7年后保留，即使用户在团队中删除了他们的邮件也是如此。</span><span class="sxs-lookup"><span data-stu-id="63613-117">For example, if you create a Teams retention policy to retain channel messages for 7 years, the messages are retained for eDiscovery for 7 years, even if users delete their messages in Teams.</span></span>
- <span data-ttu-id="63613-118">**删除数据**：使用保留策略删除数据，以确保它不是你的组织的责任。</span><span class="sxs-lookup"><span data-stu-id="63613-118">**Delete data**: Use a retention policy to delete data to ensure that it's not a liability for your organization.</span></span> <span data-ttu-id="63613-119">使用团队保留策略，删除数据时，将从团队服务上的所有存储位置中永久删除该数据。</span><span class="sxs-lookup"><span data-stu-id="63613-119">With a Teams retention policy, when you delete data, it's permanently deleted from all storage locations on the Teams service.</span></span>

<span data-ttu-id="63613-120">利用团队的保留策略，您可以：</span><span class="sxs-lookup"><span data-stu-id="63613-120">With retention policies for Teams, you can:</span></span>

- <span data-ttu-id="63613-121">保留特定工期的团队聊天和/或频道消息，然后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="63613-121">Retain Teams chats and/or channel messages for a specified duration and then do nothing.</span></span>
- <span data-ttu-id="63613-122">在指定工期内保留团队聊天和/或频道消息，然后删除数据。</span><span class="sxs-lookup"><span data-stu-id="63613-122">Retain Teams chats and/or channel messages for a specified duration and then delete the data.</span></span>
- <span data-ttu-id="63613-123">在指定的持续时间后删除团队聊天和/或频道消息。</span><span class="sxs-lookup"><span data-stu-id="63613-123">Delete Teams chats and/or channel messages after a specified duration.</span></span>

> [!NOTE]
> <span data-ttu-id="63613-124">请记住，在团队中，用户在私人聊天中共享的文件存储在共享该文件的用户的 OneDrive for Business 帐户中。</span><span class="sxs-lookup"><span data-stu-id="63613-124">Remember that in Teams, files that users share in private chats are stored in the OneDrive for Business account of the user who shared the file.</span></span> <span data-ttu-id="63613-125">以及团队成员上载到频道对话的文件存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="63613-125">And, files that team members upload to a channel conversation are stored in the team's SharePoint site.</span></span> <span data-ttu-id="63613-126">因此，若要在团队中保留或删除文件，请创建适用于 OneDrive for business 和 SharePoint Online 的保留策略。</span><span class="sxs-lookup"><span data-stu-id="63613-126">Therefore, to retain or delete files in Teams, create retention policies that apply to OneDrive for Business and SharePoint Online.</span></span>

<span data-ttu-id="63613-127">当数据受保留策略制约时，用户可以继续使用它，因为数据保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="63613-127">When data is subject to a retention policy, users can continue to work with it because the data is retained in place, in its original location.</span></span> <span data-ttu-id="63613-128">如果用户编辑或删除受策略制约的数据，则会将副本保存到在策略生效时保留的安全位置。</span><span class="sxs-lookup"><span data-stu-id="63613-128">If a user edits or deletes data that's subject to the policy, a copy is saved to a secure location where it's retained while the policy is in effect.</span></span>

<span data-ttu-id="63613-129">保留策略的最低许可要求是 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="63613-129">The minimum licensing requirement for retention policies is Office 365 E3.</span></span> <span data-ttu-id="63613-130">若要了解有关许可的详细信息，请参阅[适用于团队的 Office 365 许可](Office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="63613-130">To learn more about licensing, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="63613-131">团队保留策略的工作原理</span><span class="sxs-lookup"><span data-stu-id="63613-131">How Teams retention policies work</span></span>

<span data-ttu-id="63613-132">团队聊天存储在聊天中每个用户的邮箱的隐藏 SubstrateHolds 文件夹中，而团队频道消息存储在团队的组邮箱中的隐藏 SubstratesHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="63613-132">Teams chats are stored in a hidden SubstrateHolds folder in the mailbox of each user in the chat, and Teams channel messages are stored in a hidden SubstratesHolds folder in the group mailbox for a team.</span></span> <span data-ttu-id="63613-133">团队使用同时存储此数据的 Azure 支持的聊天服务，并且默认情况下，此服务会永久存储数据。</span><span class="sxs-lookup"><span data-stu-id="63613-133">Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever.</span></span> <span data-ttu-id="63613-134">使用团队保留策略，删除数据时，将从 Exchange 邮箱和基础聊天服务中永久删除数据。</span><span class="sxs-lookup"><span data-stu-id="63613-134">With a Teams retention policy, when you delete data, the data is permanently deleted from both the Exchange mailboxes and the underlying chat service.</span></span>

<span data-ttu-id="63613-135">将保留策略应用到团队聊天和频道消息时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="63613-135">When you apply a retention policy to Teams chats and channel messages, here's what happens:</span></span>

- <span data-ttu-id="63613-136">如果在保留期间用户在保留期间内编辑或删除了聊天或频道消息，则会将邮件复制（如果已编辑）或移动（如果它已被删除）到 SubstrateHolds 文件夹，并在保留期到期之前存储在该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="63613-136">If a chat or channel message is edited or deleted by a user during the retention period, the message is copied (if it was edited) or moved (if it was deleted) to the SubstrateHolds folder and stored there until the retention period expires.</span></span> <span data-ttu-id="63613-137">如果在保留期到期时将策略配置为删除数据，则邮件将在保留期过期的那一天被永久删除。</span><span class="sxs-lookup"><span data-stu-id="63613-137">If the policy is configured to delete data when the retention period expires, messages are permanently deleted on the day the retention period expires.</span></span>
- <span data-ttu-id="63613-138">如果在保留期间用户未删除聊天或频道消息，则邮件将在保留期到期后的一天内移动到 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="63613-138">If a chat or channel message isn't deleted by a user during the retention period, the message is moved to the SubstrateHolds folder within one day after the retention period expires.</span></span> <span data-ttu-id="63613-139">如果在保留期到期时将策略配置为删除数据，邮件将在移动到文件夹后被永久删除一天。</span><span class="sxs-lookup"><span data-stu-id="63613-139">If the policy is configured to delete data when the retention period expires, the message is permanently deleted one day after it's moved to the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="63613-140">相同的流程适用于 Skype for Business Online 和团队互操作聊天。</span><span class="sxs-lookup"><span data-stu-id="63613-140">The same flow works for Skype for Business Online and Teams interop chats.</span></span> <span data-ttu-id="63613-141">当将 Skype for Business Online 聊天加入团队时，它将成为团队聊天线索中的一条消息，并 ingested 到相应的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="63613-141">When a Skype for Business Online chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="63613-142">团队保留策略将从团队线程中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="63613-142">Teams retention policies will delete these messages from the Teams thread.</span></span> <span data-ttu-id="63613-143">但是，如果为 Skype for business Online 和 Skype for business Online 客户端中的 Skype for business Online 客户端启用了对话历史记录，则不会由团队保留策略处理聊天数据。</span><span class="sxs-lookup"><span data-stu-id="63613-143">However, if conversation history is turned on for Skype for Business Online and from the Skype for Business Online client side those are being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

<span data-ttu-id="63613-144">团队中的保留策略基于创建聊天或频道消息的日期以及 retroactive。</span><span class="sxs-lookup"><span data-stu-id="63613-144">Retention policies in Teams are based on the date the chat or channel messages were created and are retroactive.</span></span> <span data-ttu-id="63613-145">换句话说，如果创建保留策略以删除超过90天的数据，则将删除工作组数据创建超过90天前的数据。</span><span class="sxs-lookup"><span data-stu-id="63613-145">In other words, if you create a retention policy to delete data older than 90 days, Teams data created more than 90 days ago is deleted.</span></span>

<span data-ttu-id="63613-146">在 SharePoint Online 或 OneDrive for business 中应用的保留策略可能会删除在团队聊天或频道消息中引用的文件，然后再删除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="63613-146">It's possible that a retention policy that's applied to SharePoint Online or OneDrive for Business could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="63613-147">在此方案中，文件仍将显示在 "团队" 消息中，但当用户单击该文件时，将收到 "找不到文件" 错误。</span><span class="sxs-lookup"><span data-stu-id="63613-147">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="63613-148">如果有人手动从 SharePoint Online 或 OneDrive for business 中删除文件，则在缺少策略时也可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="63613-148">This can also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business.</span></span>

### <a name="considerations-and-limitations"></a><span data-ttu-id="63613-149">注意事项和限制</span><span class="sxs-lookup"><span data-stu-id="63613-149">Considerations and limitations</span></span>

<span data-ttu-id="63613-150">下面是使用团队保留策略时应注意的一些注意事项和限制：</span><span class="sxs-lookup"><span data-stu-id="63613-150">Here's some considerations and limitations to be aware of when working with Teams retention policies:</span></span>

- <span data-ttu-id="63613-151">团队需要与其他工作负荷分开的保留策略。</span><span class="sxs-lookup"><span data-stu-id="63613-151">Teams requires a retention policy that's separate from other workloads.</span></span> <span data-ttu-id="63613-152">换句话说，你必须为团队聊天和/或频道消息创建特定的保留策略。</span><span class="sxs-lookup"><span data-stu-id="63613-152">In other words, you have to create specific retention policies for Teams chats and/or channel messages.</span></span> <span data-ttu-id="63613-153">因此，您不能在组织范围的保留策略中包含团队。</span><span class="sxs-lookup"><span data-stu-id="63613-153">For this reason, you can't include Teams in org-wide retention policies.</span></span>

- <span data-ttu-id="63613-154">不支持专用信道消息。</span><span class="sxs-lookup"><span data-stu-id="63613-154">Private channel messages aren't supported.</span></span> <span data-ttu-id="63613-155">此时，团队的保留策略仅适用于标准频道消息。</span><span class="sxs-lookup"><span data-stu-id="63613-155">At this time, retention policies for Teams only apply to standard channel messages.</span></span>

- <span data-ttu-id="63613-156">团队不支持高级保留设置，如将策略应用于包含关键字或敏感信息的内容的功能。</span><span class="sxs-lookup"><span data-stu-id="63613-156">Teams doesn't support advanced retention settings, such as the ability to apply a policy to content that contains keywords or sensitive information.</span></span> <span data-ttu-id="63613-157">目前，团队中的保留策略适用于所有聊天和/或频道消息内容。</span><span class="sxs-lookup"><span data-stu-id="63613-157">Currently, retention policies in Teams apply to all chat and/or channel message content.</span></span>

- <span data-ttu-id="63613-158">团队最多可能需要三天的时间来清理已过期的消息。</span><span class="sxs-lookup"><span data-stu-id="63613-158">Teams may take up to three days to clean up expired messages.</span></span> <span data-ttu-id="63613-159">团队保留策略将在保留期到期时删除聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="63613-159">A Teams retention policy will delete chat and channel messages when the retention period expires.</span></span> <span data-ttu-id="63613-160">但是，可能需要长达三天的时间来清理这些邮件并永久删除它们。</span><span class="sxs-lookup"><span data-stu-id="63613-160">However, it may take up to three days to clean up these messages and permanently delete them.</span></span> <span data-ttu-id="63613-161">此外，聊天和频道消息将在保留期到期后和邮件永久删除的时间之间通过电子数据展示工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="63613-161">Also, chat and channel messages will be searchable with eDiscovery tools between the time after the retention period expires and when messages are permanently deleted.</span></span>

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a><span data-ttu-id="63613-162">多个保留策略和保留原则</span><span class="sxs-lookup"><span data-stu-id="63613-162">Multiple retention policies and the principles of retention</span></span>

<span data-ttu-id="63613-163">如果您使用不同的工期设置多个团队保留策略，则应用[保留策略原则](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)。</span><span class="sxs-lookup"><span data-stu-id="63613-163">If you set up multiple Teams retention policies with varying durations, the [principles of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) apply.</span></span> <span data-ttu-id="63613-164">下面概述了优先顺序：</span><span class="sxs-lookup"><span data-stu-id="63613-164">Here's an overview of what takes precedence:</span></span>

- <span data-ttu-id="63613-165">保留的 wins 始终超过删除</span><span class="sxs-lookup"><span data-stu-id="63613-165">Preservation always wins over deletion</span></span>
- <span data-ttu-id="63613-166">保留最长期限始终为 "wins"</span><span class="sxs-lookup"><span data-stu-id="63613-166">Longest preservation period always wins</span></span>
- <span data-ttu-id="63613-167">在位置的隐式包含中显式包含 wins</span><span class="sxs-lookup"><span data-stu-id="63613-167">Explicit inclusion wins over implicit inclusion in terms of locations</span></span>
- <span data-ttu-id="63613-168">Wins 最短删除周期</span><span class="sxs-lookup"><span data-stu-id="63613-168">Shortest deletion period wins</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="63613-169">何时使用团队的保留策略</span><span class="sxs-lookup"><span data-stu-id="63613-169">When to use retention policies for Teams</span></span>

<span data-ttu-id="63613-170">在许多情况下，组织会将私人聊天数据视为比频道消息更多的责任，这通常是更多与项目相关的对话。</span><span class="sxs-lookup"><span data-stu-id="63613-170">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="63613-171">你可以为私人聊天（1:1 或1：许多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="63613-171">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="63613-172">您还可以配置应用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="63613-172">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="63613-173">对于团队聊天，你可以选择要应用该策略的用户。</span><span class="sxs-lookup"><span data-stu-id="63613-173">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="63613-174">对于团队频道消息，你可以选择应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="63613-174">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="63613-175">例如，对于频道消息，你可以将一年的删除策略应用到组织中的特定团队，并向所有其他团队应用三年删除策略。</span><span class="sxs-lookup"><span data-stu-id="63613-175">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="manage-retention-policies-for-teams"></a><span data-ttu-id="63613-176">管理团队的保留策略</span><span class="sxs-lookup"><span data-stu-id="63613-176">Manage retention policies for Teams</span></span>

### <a name="using-the-security--compliance-center"></a><span data-ttu-id="63613-177">使用安全 & 合规中心</span><span class="sxs-lookup"><span data-stu-id="63613-177">Using the Security & Compliance Center</span></span>

#### <a name="create-a-retention-policy"></a><span data-ttu-id="63613-178">创建保留策略</span><span class="sxs-lookup"><span data-stu-id="63613-178">Create a retention policy</span></span>

<span data-ttu-id="63613-179">若要为团队聊天和频道消息创建保留策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="63613-179">To create a retention policy for Teams chats and channel messages, do the following:</span></span>

1. <span data-ttu-id="63613-180">在安全 & 合规中心的左侧导航中，转到 "**信息管理** > **保留**"。</span><span class="sxs-lookup"><span data-stu-id="63613-180">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="63613-181">选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="63613-181">Select **Create**.</span></span>
3. <span data-ttu-id="63613-182">在 "为**你的策略命名**" 页面上，输入你的策略的名称和说明，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="63613-182">On the **Name your policy** page, enter a name and description for your policy, and then click **Next**.</span></span>
4. <span data-ttu-id="63613-183">在 "**设置**" 页面上，指定是要保留数据、删除数据还是同时保留时间，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="63613-183">On the **Settings** page, specify whether you want to retain data, delete it, or both, the retention period, and then click **Next**.</span></span>
5. <span data-ttu-id="63613-184">在 "**选择位置**" 页上，执行下列操作，然后单击 "**下一步**"：</span><span class="sxs-lookup"><span data-stu-id="63613-184">On the **Choose locations** page, do the following, and then click **Next**:</span></span>

    - <span data-ttu-id="63613-185">若要将策略应用到信道消息，请打开**团队频道消息**。</span><span class="sxs-lookup"><span data-stu-id="63613-185">To apply the policy to channel messages, turn on **Teams channel messages**.</span></span>  <span data-ttu-id="63613-186">如果要将策略应用到组织中的特定团队，请选择 "**选择团队**"，然后选择所需团队。</span><span class="sxs-lookup"><span data-stu-id="63613-186">If you want to apply the policy to specific teams in your organization, select **Choose teams**, and then select the teams that you want.</span></span>
    - <span data-ttu-id="63613-187">若要将策略应用于聊天，请打开**团队聊天**。</span><span class="sxs-lookup"><span data-stu-id="63613-187">To apply the policy to chats, turn on **Teams chats**.</span></span> <span data-ttu-id="63613-188">如果要将策略应用到组织中的特定用户，请选择 "**选择用户**"，然后选择所需的用户。</span><span class="sxs-lookup"><span data-stu-id="63613-188">If you want to apply the policy to specific users in your organization, select **Choose users**, and then select the users that you want.</span></span>
      > [!NOTE]
      > <span data-ttu-id="63613-189">当您打开**团队频道消息**和/或**团队聊天**时，所有其他位置将自动关闭。</span><span class="sxs-lookup"><span data-stu-id="63613-189">When you turn on **Teams channel messages** and/or **Teams chats**, all other locations are  automatically turned off.</span></span> <span data-ttu-id="63613-190">团队保留策略只能包含团队位置。</span><span class="sxs-lookup"><span data-stu-id="63613-190">A Teams retention policy can only include Teams locations.</span></span>

        !["选择位置" 页上的团队频道消息和团队聊天选项的屏幕截图](media/retention-policies-create.png)

      > [!IMPORTANT]
      > <span data-ttu-id="63613-192">团队聊天和频道消息不受应用于**Exchange 电子邮件**或**Office 365 组**位置中的用户或组邮箱的保留策略的影响。</span><span class="sxs-lookup"><span data-stu-id="63613-192">Teams chats and channel messages aren't affected by retention policies applied to user or group mailboxes in the **Exchange email** or **Office 365 groups** locations.</span></span> <span data-ttu-id="63613-193">尽管团队聊天和频道邮件存储在 Exchange 中，但它们仅受应用于团队位置的保留策略的影响。</span><span class="sxs-lookup"><span data-stu-id="63613-193">Even though Teams chats and channel messages are stored in Exchange, they're only affected by retention policies applied to the Teams locations.</span></span>

6. <span data-ttu-id="63613-194">查看您的设置，然后在准备就绪后，选择 "**创建此策略**"。</span><span class="sxs-lookup"><span data-stu-id="63613-194">Review your settings, and then when you're ready, select **Create this policy**.</span></span>

#### <a name="edit-a-retention-policy"></a><span data-ttu-id="63613-195">编辑保留策略</span><span class="sxs-lookup"><span data-stu-id="63613-195">Edit a retention policy</span></span>

<span data-ttu-id="63613-196">若要编辑团队保留策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="63613-196">To edit a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="63613-197">在安全 & 合规中心的左侧导航中，转到 "**信息管理** > **保留**"。</span><span class="sxs-lookup"><span data-stu-id="63613-197">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="63613-198">在 "保留策略" 列表中，选中要编辑的保留策略旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="63613-198">In the list of retention policies, select the check box next to the retention policy you want to edit.</span></span>
3. <span data-ttu-id="63613-199">选择要编辑的内容旁边的 "**编辑**"，进行所需的更改，单击 "**保存**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="63613-199">Select **Edit** next to what you want to edit, make your changes, click **Save**, and then click **Close**.</span></span>

    !["选择位置" 页上的团队频道消息和团队聊天选项的屏幕截图](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a><span data-ttu-id="63613-201">删除保留策略</span><span class="sxs-lookup"><span data-stu-id="63613-201">Delete a retention policy</span></span>

<span data-ttu-id="63613-202">若要删除团队保留策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="63613-202">To delete a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="63613-203">在安全 & 合规中心的左侧导航中，转到 "**信息管理** > **保留**"。</span><span class="sxs-lookup"><span data-stu-id="63613-203">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="63613-204">在 "保留策略" 列表中，选中要删除的保留策略旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="63613-204">In the list of retention policies, select the check box next to the retention policy you want to delete.</span></span>
3. <span data-ttu-id="63613-205">选择 "**删除策略**"。</span><span class="sxs-lookup"><span data-stu-id="63613-205">Select **Delete policy**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="63613-206">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="63613-206">Using PowerShell</span></span>

<span data-ttu-id="63613-207">若要使用 PowerShell 创建和管理团队保留策略，请使用以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63613-207">To create and manage Teams retention policies by using PowerShell, use the following cmdlets.</span></span>

|<span data-ttu-id="63613-208">设置</span><span class="sxs-lookup"><span data-stu-id="63613-208">Policy</span></span>|<span data-ttu-id="63613-209">规则</span><span class="sxs-lookup"><span data-stu-id="63613-209">Rule</span></span>|
|---|---|
|[<span data-ttu-id="63613-210">新-TeamsRetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="63613-210">New-TeamsRetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="63613-211">新-TeamsRetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="63613-211">New-TeamsRetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="63613-212">TeamsRetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="63613-212">Get-TeamsRetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="63613-213">TeamsRetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="63613-213">Get-TeamsRetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="63613-214">Set-TeamsRetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="63613-214">Set-TeamsRetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="63613-215">Set-TeamsRetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="63613-215">Set-TeamsRetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="63613-216">Remove-TeamsRetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="63613-216">Remove-TeamsRetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="63613-217">Remove-TeamsRetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="63613-217">Remove-TeamsRetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a><span data-ttu-id="63613-218">已知问题</span><span class="sxs-lookup"><span data-stu-id="63613-218">Known issues</span></span>

<span data-ttu-id="63613-219">以下是正在跟踪和调查的团队中的保留策略的已知问题。</span><span class="sxs-lookup"><span data-stu-id="63613-219">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="63613-220">在 "**团队频道消息**位置" 行中的 "**选择团队**" 下，你可能会看到也不是团队的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="63613-220">Under **Choose teams** in the **Teams channel messages** location row, you may see Office 365 Groups that aren't also Teams.</span></span> <span data-ttu-id="63613-221">未来将对此进行寻址。</span><span class="sxs-lookup"><span data-stu-id="63613-221">This will be addressed in the future.</span></span>

- <span data-ttu-id="63613-222">在 "**团队聊天**位置" 行中的 "**选择用户**" 下，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="63613-222">Under **Choose users** in the **Teams chats** location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="63613-223">保留策略不适于为来宾设置，我们正在努力从列表中删除这些保留策略。</span><span class="sxs-lookup"><span data-stu-id="63613-223">Retention policies aren't meant to be set for guests, and we're working to remove these from the list.</span></span>

- <span data-ttu-id="63613-224">Exchange 生命周期助理（ELC）每天运行，但其 SLA 为7天。</span><span class="sxs-lookup"><span data-stu-id="63613-224">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="63613-225">因此，如果你有一个团队保留策略来删除超过60天的项目，这些项目最多可持续67天。</span><span class="sxs-lookup"><span data-stu-id="63613-225">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="63613-226">这不是一种新情况-它遵循 Exchange 模型。</span><span class="sxs-lookup"><span data-stu-id="63613-226">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="63613-227">当然，在大多数情况下，没有延迟。</span><span class="sxs-lookup"><span data-stu-id="63613-227">Of course, in most cases, there's no delay.</span></span>

## <a name="related-topics"></a><span data-ttu-id="63613-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="63613-228">Related topics</span></span>

- [<span data-ttu-id="63613-229">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="63613-229">Overview of retention policies</span></span>](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
