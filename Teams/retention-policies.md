---
title: Microsoft Teams 中的保留策略
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
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
ms.openlocfilehash: dde12e5197031cd768cecf539ae2213f2a5b4d92
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905464"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="b41f3-103">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="b41f3-104">保留策略可帮助你更高效地管理组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-104">Retention policies help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="b41f3-105">使用保留策略可以保留满足组织的内部政策、行业法规或法律要求所需的数据，以及删除被视为负担、不再需要保留或没有法律或业务价值的数据。</span><span class="sxs-lookup"><span data-stu-id="b41f3-105">Use retention policies to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs, and to delete data that's considered a liability, that you're no longer required to keep, or has no legal or business value.</span></span>

<span data-ttu-id="b41f3-106">默认情况下，Teams 聊天、频道和文件数据将永久保留。</span><span class="sxs-lookup"><span data-stu-id="b41f3-106">By default, Teams chat, channel, and files data are retained forever.</span></span> <span data-ttu-id="b41f3-107">作为管理员，你可以为聊天和频道消息设置 Teams 保留策略，并主动决定是保留数据、删除数据还是将其保留一段时间后再删除。</span><span class="sxs-lookup"><span data-stu-id="b41f3-107">As an admin, you can set up Teams retention policies for chat and channel messages and decide proactively whether to retain the data, delete it, or retain it for a specific period of time and then delete it.</span></span>

<span data-ttu-id="b41f3-108">在[Microsoft 365 合规中心](https://protection.office.com/)中创建和管理团队和其他工作负荷的保留策略，或者使用安全 & 合规性中心 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b41f3-108">You create and manage retention policies for Teams and other workloads in the [Microsoft 365 Compliance Center](https://protection.office.com/) or by using the Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="b41f3-109">可将 Teams 保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="b41f3-109">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span>

> [!NOTE]
> <span data-ttu-id="b41f3-110">我们尚不支持保留专用频道消息的配置。</span><span class="sxs-lookup"><span data-stu-id="b41f3-110">We don't yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="b41f3-111">支持保留在私人渠道中共享的文件。</span><span class="sxs-lookup"><span data-stu-id="b41f3-111">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="b41f3-112">若要了解有关 Office 365 的保留策略的详细信息，请参阅[保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="b41f3-112">To learn more about retention policies for Office 365, see [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="what-are-retention-policies-for-teams"></a><span data-ttu-id="b41f3-113">Teams 的保留策略是什么？</span><span class="sxs-lookup"><span data-stu-id="b41f3-113">What are retention policies for Teams?</span></span>

<span data-ttu-id="b41f3-114">在为 Teams 或任何其他工作负载设置保留策略时，可将其设置为：</span><span class="sxs-lookup"><span data-stu-id="b41f3-114">When you set up a retention policy for Teams or any other workload, you can set them up to:</span></span>

- <span data-ttu-id="b41f3-115">**保留数据**：使用保留策略确保将数据保留一段指定的时间，无论用户应用中发生什么情况都是如此。</span><span class="sxs-lookup"><span data-stu-id="b41f3-115">**Retain data**: Use a retention policy to ensure that your data is retained for a specified period of time, regardless of what happens in the user app.</span></span> <span data-ttu-id="b41f3-116">出于合规性原因而保留数据，并且可用于电子数据展示，直到保留期到期为止，之后，策略会指示是不执行任何操作还是删除数据。</span><span class="sxs-lookup"><span data-stu-id="b41f3-116">Data is retained for compliance reasons and is available for eDiscovery until the retention period expires, after which your policy indicates whether to do nothing or delete the data.</span></span> <span data-ttu-id="b41f3-117">例如，如果创建 Teams 保留策略以将频道消息保留 7 年，则会将用于电子数据展示的消息保留 7 年，即便用户在 Teams 中删除了这些消息也是如此。</span><span class="sxs-lookup"><span data-stu-id="b41f3-117">For example, if you create a Teams retention policy to retain channel messages for 7 years, the messages are retained for eDiscovery for 7 years, even if users delete their messages in Teams.</span></span>
- <span data-ttu-id="b41f3-118">**删除数据**：使用保留策略删除数据，以确保它不会对你的组织造成负担。</span><span class="sxs-lookup"><span data-stu-id="b41f3-118">**Delete data**: Use a retention policy to delete data to ensure that it's not a liability for your organization.</span></span> <span data-ttu-id="b41f3-119">借助 Teams 保留策略，当你删除数据时，它将从 Teams 服务上的所有存储位置永久删除。</span><span class="sxs-lookup"><span data-stu-id="b41f3-119">With a Teams retention policy, when you delete data, it's permanently deleted from all storage locations on the Teams service.</span></span>

<span data-ttu-id="b41f3-120">借助 Teams 保留策略，你可以：</span><span class="sxs-lookup"><span data-stu-id="b41f3-120">With retention policies for Teams, you can:</span></span>

- <span data-ttu-id="b41f3-121">将 Teams 聊天和/或频道消息保留一段指定的时间，并且在此期限后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b41f3-121">Retain Teams chats and/or channel messages for a specified duration and then do nothing.</span></span>
- <span data-ttu-id="b41f3-122">将 Teams 聊天和/或频道消息保留一段指定的时间，并在此期限后删除数据。</span><span class="sxs-lookup"><span data-stu-id="b41f3-122">Retain Teams chats and/or channel messages for a specified duration and then delete the data.</span></span>
- <span data-ttu-id="b41f3-123">在指定的时间段后删除 Teams 聊天和/或频道消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-123">Delete Teams chats and/or channel messages after a specified duration.</span></span>

> [!NOTE]
> <span data-ttu-id="b41f3-124">请记住，在 Teams 中，用户在私人聊天中共享的文件存储在共享该文件的用户的 OneDrive for Business 帐户中。</span><span class="sxs-lookup"><span data-stu-id="b41f3-124">Remember that in Teams, files that users share in private chats are stored in the OneDrive for Business account of the user who shared the file.</span></span> <span data-ttu-id="b41f3-125">由团队成员上传到频道对话的文件则存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="b41f3-125">And, files that team members upload to a channel conversation are stored in the team's SharePoint site.</span></span> <span data-ttu-id="b41f3-126">因此，若要保留或删除 Teams 中的文件，请创建适用于 OneDrive for Business 和 SharePoint Online 的保留策略。</span><span class="sxs-lookup"><span data-stu-id="b41f3-126">Therefore, to retain or delete files in Teams, create retention policies that apply to OneDrive for Business and SharePoint Online.</span></span>

<span data-ttu-id="b41f3-127">如果数据受保留策略的约束，用户可以继续使用它，因为该数据将保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="b41f3-127">When data is subject to a retention policy, users can continue to work with it because the data is retained in place, in its original location.</span></span> <span data-ttu-id="b41f3-128">如果用户编辑或删除受策略约束的数据，则副本将保存到该策略生效时保留该副本的安全位置。</span><span class="sxs-lookup"><span data-stu-id="b41f3-128">If a user edits or deletes data that's subject to the policy, a copy is saved to a secure location where it's retained while the policy is in effect.</span></span>

<span data-ttu-id="b41f3-129">保留策略的最低许可要求是 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="b41f3-129">The minimum licensing requirement for retention policies is Office 365 E3.</span></span> <span data-ttu-id="b41f3-130">若要了解有关许可的详细信息，请参阅[适用于 Teams 的 Office 365 许可](Office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="b41f3-130">To learn more about licensing, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="b41f3-131">Teams 保留策略的工作方式</span><span class="sxs-lookup"><span data-stu-id="b41f3-131">How Teams retention policies work</span></span>

<span data-ttu-id="b41f3-132">Teams 聊天存储在参与聊天的每个用户的邮箱中的隐藏 SubstrateHolds 文件夹内，Teams 频道消息存储在团队组邮箱中的隐藏 SubstratesHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b41f3-132">Teams chats are stored in a hidden SubstrateHolds folder in the mailbox of each user in the chat, and Teams channel messages are stored in a hidden SubstratesHolds folder in the group mailbox for a team.</span></span> <span data-ttu-id="b41f3-133">Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。</span><span class="sxs-lookup"><span data-stu-id="b41f3-133">Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever.</span></span> <span data-ttu-id="b41f3-134">借助 Teams 保留策略，当你删除数据时，将从 Exchange 邮箱和基础聊天服务中永久删除该数据。</span><span class="sxs-lookup"><span data-stu-id="b41f3-134">With a Teams retention policy, when you delete data, the data is permanently deleted from both the Exchange mailboxes and the underlying chat service.</span></span>

<span data-ttu-id="b41f3-135">将保留策略应用于 Teams 聊天和频道消息后，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="b41f3-135">When you apply a retention policy to Teams chats and channel messages, here's what happens:</span></span>

- <span data-ttu-id="b41f3-136">如果用户在保留期内编辑或删除了聊天或频道消息，则该消息将复制（如果已编辑）或移动（如果已删除）到 SubstrateHolds 文件夹中，并存储在该文件夹中，直到保留期到期为止。</span><span class="sxs-lookup"><span data-stu-id="b41f3-136">If a chat or channel message is edited or deleted by a user during the retention period, the message is copied (if it was edited) or moved (if it was deleted) to the SubstrateHolds folder and stored there until the retention period expires.</span></span> <span data-ttu-id="b41f3-137">如果将策略配置为在保留期到期时删除数据，则将在保留期到期的当天永久删除消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-137">If the policy is configured to delete data when the retention period expires, messages are permanently deleted on the day the retention period expires.</span></span>
- <span data-ttu-id="b41f3-138">如果用户在保留期内未删除聊天或频道消息，则该消息将在保留期到期后的一天内移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b41f3-138">If a chat or channel message isn't deleted by a user during the retention period, the message is moved to the SubstrateHolds folder within one day after the retention period expires.</span></span> <span data-ttu-id="b41f3-139">如果将策略配置为在保留期到期时删除数据，则将在消息移至文件夹的一天后永久删除该消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-139">If the policy is configured to delete data when the retention period expires, the message is permanently deleted one day after it's moved to the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="b41f3-140">相同的流程适用于 Skype for Business Online 和 Teams 互操作聊天。</span><span class="sxs-lookup"><span data-stu-id="b41f3-140">The same flow works for Skype for Business Online and Teams interop chats.</span></span> <span data-ttu-id="b41f3-141">当 Skype for Business Online 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="b41f3-141">When a Skype for Business Online chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="b41f3-142">Teams 保留策略将从 Teams 线程中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-142">Teams retention policies will delete these messages from the Teams thread.</span></span> <span data-ttu-id="b41f3-143">但是，如果已为 Skype for Business Online 开启对话历史记录，并且从 Skype for Business Online 客户端将会话历史记录保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。</span><span class="sxs-lookup"><span data-stu-id="b41f3-143">However, if conversation history is turned on for Skype for Business Online and from the Skype for Business Online client side those are being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

<span data-ttu-id="b41f3-144">Teams 中的保留策略基于聊天或频道消息的创建日期，并且具有追溯性。</span><span class="sxs-lookup"><span data-stu-id="b41f3-144">Retention policies in Teams are based on the date the chat or channel messages were created and are retroactive.</span></span> <span data-ttu-id="b41f3-145">换言之，如果你创建保留策略来删除 90 天之前的数据，则在 90 天之前创建的 Teams 数据将被删除。</span><span class="sxs-lookup"><span data-stu-id="b41f3-145">In other words, if you create a retention policy to delete data older than 90 days, Teams data created more than 90 days ago is deleted.</span></span>

<span data-ttu-id="b41f3-146">应用于 SharePoint Online 或 OneDrive for Business 的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-146">It's possible that a retention policy that's applied to SharePoint Online or OneDrive for Business could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="b41f3-147">在这种情况下，该文件仍将显示在 Teams 消息中，但当用户单击文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="b41f3-147">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="b41f3-148">如果某人手动从 SharePoint Online 或 OneDrive for Business 中删除文件，则在没有应用策略的情况下也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b41f3-148">This can also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business.</span></span>

### <a name="considerations-and-limitations"></a><span data-ttu-id="b41f3-149">注意事项和限制</span><span class="sxs-lookup"><span data-stu-id="b41f3-149">Considerations and limitations</span></span>

<span data-ttu-id="b41f3-150">以下是在使用 Teams 保留策略时需要注意的一些事项和限制：</span><span class="sxs-lookup"><span data-stu-id="b41f3-150">Here's some considerations and limitations to be aware of when working with Teams retention policies:</span></span>

- <span data-ttu-id="b41f3-151">Teams 需要与其他工作负载分开的保留策略。</span><span class="sxs-lookup"><span data-stu-id="b41f3-151">Teams requires a retention policy that's separate from other workloads.</span></span> <span data-ttu-id="b41f3-152">换言之，你必须为 Teams 聊天和/或频道消息创建特定保留策略。</span><span class="sxs-lookup"><span data-stu-id="b41f3-152">In other words, you have to create specific retention policies for Teams chats and/or channel messages.</span></span> <span data-ttu-id="b41f3-153">因此，你不能在组织范围的保留策略中包括 Teams。</span><span class="sxs-lookup"><span data-stu-id="b41f3-153">For this reason, you can't include Teams in org-wide retention policies.</span></span>

- <span data-ttu-id="b41f3-154">不支持私有频道消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-154">Private channel messages aren't supported.</span></span> <span data-ttu-id="b41f3-155">目前，Teams 的保留策略仅适用于标准频道消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-155">At this time, retention policies for Teams only apply to standard channel messages.</span></span>

- <span data-ttu-id="b41f3-156">Teams 不支持高级保留设置，例如，用于为包含关键字或敏感信息的内容应用策略的功能。</span><span class="sxs-lookup"><span data-stu-id="b41f3-156">Teams doesn't support advanced retention settings, such as the ability to apply a policy to content that contains keywords or sensitive information.</span></span> <span data-ttu-id="b41f3-157">目前，Teams 中的保留策略适用于所有聊天和/或频道消息内容。</span><span class="sxs-lookup"><span data-stu-id="b41f3-157">Currently, retention policies in Teams apply to all chat and/or channel message content.</span></span>

- <span data-ttu-id="b41f3-158">团队最多可能需要3到7天的时间来清理已过期的消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-158">Teams may take up to three to seven days to clean up expired messages.</span></span> <span data-ttu-id="b41f3-159">Teams 保留策略将在保留期到期时删除聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-159">A Teams retention policy will delete chat and channel messages when the retention period expires.</span></span> <span data-ttu-id="b41f3-160">但是，可能需要长达3至7天的时间来清理这些邮件并永久删除它们。</span><span class="sxs-lookup"><span data-stu-id="b41f3-160">However, it may take up to three to seven days to clean up these messages and permanently delete them.</span></span> <span data-ttu-id="b41f3-161">此外，在保留期到期后和永久删除消息之间的时间段内，可以使用电子数据展示工具搜索聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="b41f3-161">Also, chat and channel messages will be searchable with eDiscovery tools between the time after the retention period expires and when messages are permanently deleted.</span></span>

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a><span data-ttu-id="b41f3-162">多个保留策略和保留原则</span><span class="sxs-lookup"><span data-stu-id="b41f3-162">Multiple retention policies and the principles of retention</span></span>

<span data-ttu-id="b41f3-163">如果设置多个具有不同期限的 Teams 保留策略，则[保留策略原则](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)适用。</span><span class="sxs-lookup"><span data-stu-id="b41f3-163">If you set up multiple Teams retention policies with varying durations, the [principles of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) apply.</span></span> <span data-ttu-id="b41f3-164">以下是关于优先级的概述：</span><span class="sxs-lookup"><span data-stu-id="b41f3-164">Here's an overview of what takes precedence:</span></span>

- <span data-ttu-id="b41f3-165">保留始终优先于删除</span><span class="sxs-lookup"><span data-stu-id="b41f3-165">Preservation always wins over deletion</span></span>
- <span data-ttu-id="b41f3-166">优选最长的保留期</span><span class="sxs-lookup"><span data-stu-id="b41f3-166">Longest preservation period always wins</span></span>
- <span data-ttu-id="b41f3-167">显式添加的位置优先于隐式添加的位置</span><span class="sxs-lookup"><span data-stu-id="b41f3-167">Explicit inclusion wins over implicit inclusion in terms of locations</span></span>
- <span data-ttu-id="b41f3-168">优选最短删除期</span><span class="sxs-lookup"><span data-stu-id="b41f3-168">Shortest deletion period wins</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="b41f3-169">何时使用 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-169">When to use retention policies for Teams</span></span>

<span data-ttu-id="b41f3-170">在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。</span><span class="sxs-lookup"><span data-stu-id="b41f3-170">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="b41f3-171">你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="b41f3-171">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="b41f3-172">你还可以配置适用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="b41f3-172">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="b41f3-173">对于 Teams 聊天，可选择要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="b41f3-173">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="b41f3-174">对于 Teams 频道消息，可选择要为其应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="b41f3-174">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="b41f3-175">例如，对于频道消息，可以将一年删除策略应用于组织中的特定团队，并将三年删除策略应用于所有其他团队。</span><span class="sxs-lookup"><span data-stu-id="b41f3-175">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="manage-retention-policies-for-teams"></a><span data-ttu-id="b41f3-176">管理 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-176">Manage retention policies for Teams</span></span>

### <a name="using-the-security--compliance-center"></a><span data-ttu-id="b41f3-177">使用安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="b41f3-177">Using the Security & Compliance Center</span></span>

#### <a name="create-a-retention-policy"></a><span data-ttu-id="b41f3-178">创建保留策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-178">Create a retention policy</span></span>

<span data-ttu-id="b41f3-179">若要为 Teams 聊天和频道消息创建保留策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b41f3-179">To create a retention policy for Teams chats and channel messages, do the following:</span></span>

1. <span data-ttu-id="b41f3-180">在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-180">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="b41f3-181">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-181">Select **Create**.</span></span>
3. <span data-ttu-id="b41f3-182">在“**为你的策略命名**”页面上，为你的策略输入名称和说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-182">On the **Name your policy** page, enter a name and description for your policy, and then click **Next**.</span></span>
4. <span data-ttu-id="b41f3-183">在“**设置**”页上，指定是保留数据、删除数据还是先保留后删除，指定保留期，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-183">On the **Settings** page, specify whether you want to retain data, delete it, or both, the retention period, and then click **Next**.</span></span>
5. <span data-ttu-id="b41f3-184">在“**选择位置**”页面上，执行以下操作，然后单击“**下一步**”：</span><span class="sxs-lookup"><span data-stu-id="b41f3-184">On the **Choose locations** page, do the following, and then click **Next**:</span></span>

    - <span data-ttu-id="b41f3-185">若要将策略应用于频道消息，请开启“**Teams 频道消息**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-185">To apply the policy to channel messages, turn on **Teams channel messages**.</span></span>  <span data-ttu-id="b41f3-186">如果要将策略应用于组织中的特定团队，请选择“**选择团队**”，然后选择所需的团队。</span><span class="sxs-lookup"><span data-stu-id="b41f3-186">If you want to apply the policy to specific teams in your organization, select **Choose teams**, and then select the teams that you want.</span></span>
    - <span data-ttu-id="b41f3-187">若要将策略应用于聊天，请开启“**Teams 聊天**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-187">To apply the policy to chats, turn on **Teams chats**.</span></span> <span data-ttu-id="b41f3-188">如果要将策略应用于组织中的特定用户，请选择“**选择用户**”，然后选择所需的用户。</span><span class="sxs-lookup"><span data-stu-id="b41f3-188">If you want to apply the policy to specific users in your organization, select **Choose users**, and then select the users that you want.</span></span>
      > [!NOTE]
      > <span data-ttu-id="b41f3-189">当开启“**Teams 频道消息**”和/或“**Teams 聊天**”时，所有其他位置都会自动关闭。</span><span class="sxs-lookup"><span data-stu-id="b41f3-189">When you turn on **Teams channel messages** and/or **Teams chats**, all other locations are  automatically turned off.</span></span> <span data-ttu-id="b41f3-190">Teams 保留策略只能包含 Teams 位置。</span><span class="sxs-lookup"><span data-stu-id="b41f3-190">A Teams retention policy can only include Teams locations.</span></span>

        ![“选择位置”页面上的“Teams 频道消息”和“Teams 聊天”选项的屏幕截图](media/retention-policies-create.png)

      > [!IMPORTANT]
      > <span data-ttu-id="b41f3-192">团队聊天和频道消息不受应用于**Exchange 电子邮件**或**Microsoft 365 组**位置中的用户或组邮箱的保留策略的影响。</span><span class="sxs-lookup"><span data-stu-id="b41f3-192">Teams chats and channel messages aren't affected by retention policies applied to user or group mailboxes in the **Exchange email** or **Microsoft 365 groups** locations.</span></span> <span data-ttu-id="b41f3-193">即使 Teams 聊天和频道消息存储在 Exchange 中，它们也仅受到应用于 Teams 位置的保留策略的影响。</span><span class="sxs-lookup"><span data-stu-id="b41f3-193">Even though Teams chats and channel messages are stored in Exchange, they're only affected by retention policies applied to the Teams locations.</span></span>

6. <span data-ttu-id="b41f3-194">查看设置，在准备就绪后，选择“**创建此策略**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-194">Review your settings, and then when you're ready, select **Create this policy**.</span></span>

#### <a name="edit-a-retention-policy"></a><span data-ttu-id="b41f3-195">编辑保留策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-195">Edit a retention policy</span></span>

<span data-ttu-id="b41f3-196">若要编辑 Teams 保留策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b41f3-196">To edit a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="b41f3-197">在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-197">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="b41f3-198">在保留策略列表中，选中要编辑的保留策略旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b41f3-198">In the list of retention policies, select the check box next to the retention policy you want to edit.</span></span>
3. <span data-ttu-id="b41f3-199">选择要编辑的策略旁边的“**编辑**”，进行更改，单击“**保存**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-199">Select **Edit** next to what you want to edit, make your changes, click **Save**, and then click **Close**.</span></span>

    ![“选择位置”页面上的“Teams 频道消息”和“Teams 聊天”选项的屏幕截图](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a><span data-ttu-id="b41f3-201">删除保留策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-201">Delete a retention policy</span></span>

<span data-ttu-id="b41f3-202">若要删除 Teams 保留策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b41f3-202">To delete a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="b41f3-203">在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-203">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="b41f3-204">在保留策略列表中，选中要删除的保留策略旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b41f3-204">In the list of retention policies, select the check box next to the retention policy you want to delete.</span></span>
3. <span data-ttu-id="b41f3-205">选择“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="b41f3-205">Select **Delete policy**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b41f3-206">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b41f3-206">Using PowerShell</span></span>

<span data-ttu-id="b41f3-207">若要使用[Office 365 安全 & 合规性 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)创建和管理团队保留策略，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b41f3-207">To create and manage Teams retention policies by using [Office 365 Security & Compliance PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell), use the following cmdlets:</span></span>

|<span data-ttu-id="b41f3-208">策略</span><span class="sxs-lookup"><span data-stu-id="b41f3-208">Policy</span></span>|<span data-ttu-id="b41f3-209">规则</span><span class="sxs-lookup"><span data-stu-id="b41f3-209">Rule</span></span>|
|---|---|
|[<span data-ttu-id="b41f3-210">新-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b41f3-210">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="b41f3-211">新-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b41f3-211">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="b41f3-212">RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b41f3-212">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="b41f3-213">RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b41f3-213">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="b41f3-214">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b41f3-214">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="b41f3-215">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b41f3-215">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="b41f3-216">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="b41f3-216">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="b41f3-217">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="b41f3-217">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a><span data-ttu-id="b41f3-218">已知问题</span><span class="sxs-lookup"><span data-stu-id="b41f3-218">Known issues</span></span>

<span data-ttu-id="b41f3-219">以下是正在跟踪和调查的 Teams 中的已知保留策略问题。</span><span class="sxs-lookup"><span data-stu-id="b41f3-219">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="b41f3-220">在 "**团队频道消息**位置" 行中的 "**选择团队**" 下，你可能会看到还不是团队的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="b41f3-220">Under **Choose teams** in the **Teams channel messages** location row, you may see Microsoft 365 Groups that aren't also Teams.</span></span> <span data-ttu-id="b41f3-221">此问题将在未来得到解决。</span><span class="sxs-lookup"><span data-stu-id="b41f3-221">This will be addressed in the future.</span></span>

- <span data-ttu-id="b41f3-222">在“**Teams 聊天**”位置行中的“**选择用户**”下，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="b41f3-222">Under **Choose users** in the **Teams chats** location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="b41f3-223">保留策略不是为来宾设置的，我们正致力于从列表中删除来宾。</span><span class="sxs-lookup"><span data-stu-id="b41f3-223">Retention policies aren't meant to be set for guests, and we're working to remove these from the list.</span></span>

- <span data-ttu-id="b41f3-224">Exchange 生命周期助手 (ELC) 每天运行，但其 SLA 为 7 天。</span><span class="sxs-lookup"><span data-stu-id="b41f3-224">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="b41f3-225">因此，如果你创建了 Teams 保留策略来删除 60 天之前的项目，则这些项目最长可保留 67 天。</span><span class="sxs-lookup"><span data-stu-id="b41f3-225">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="b41f3-226">这不是新情况 - 它遵循 Exchange 模型。</span><span class="sxs-lookup"><span data-stu-id="b41f3-226">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="b41f3-227">当然，在大多数情况下，不会出现延迟。</span><span class="sxs-lookup"><span data-stu-id="b41f3-227">Of course, in most cases, there's no delay.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b41f3-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="b41f3-228">Related topics</span></span>

- [<span data-ttu-id="b41f3-229">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="b41f3-229">Overview of retention policies</span></span>](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
