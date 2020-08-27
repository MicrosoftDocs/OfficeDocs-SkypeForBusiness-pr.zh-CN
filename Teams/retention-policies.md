---
title: Microsoft Teams 中的保留策略
author: cabailey
ms.author: cabailey
ms.reviewer: prvijay
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
ms.openlocfilehash: 0db8b037bdf67f920e1089ae8f67f477e85e3e06
ms.sourcegitcommit: 39fa1aee7a5e067097b126aa619be5aa099888ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903801"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="35c61-103">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="35c61-104">保留策略可帮助你更高效地管理组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="35c61-104">Retention policies help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="35c61-105">使用保留策略可以保留满足组织的内部政策、行业法规或法律要求所需的数据，以及删除被视为负担、不再需要保留或没有法律或业务价值的数据。</span><span class="sxs-lookup"><span data-stu-id="35c61-105">Use retention policies to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs, and to delete data that's considered a liability, that you're no longer required to keep, or has no legal or business value.</span></span>

<span data-ttu-id="35c61-106">默认情况下，团队聊天、频道和文件数据将无限期保留，除非有尝试通过保留策略、用户删除、管理员删除等删除内容。作为管理员，你可以为聊天和频道消息设置团队保留策略，并提前确定是保留数据、删除数据还是在特定时间段内保留数据，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="35c61-106">By default, Teams chat, channel, and files data are retained indefinitely, unless there is an attempt to delete the content via retention policies, user deletes, admin deletes etc. As an admin, you can set up Teams retention policies for chat and channel messages and decide proactively whether to retain the data, delete it, or retain it for a specific period of time and then delete it.</span></span>

<span data-ttu-id="35c61-107">在 [Microsoft 365 合规中心](https://protection.office.com/) 中创建和管理团队和其他工作负荷的保留策略，或者使用安全 & 合规性中心 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="35c61-107">You create and manage retention policies for Teams and other workloads in the [Microsoft 365 compliance center](https://protection.office.com/) or by using the Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="35c61-108">可将 Teams 保留策略应用于整个组织或特定用户和团队。</span><span class="sxs-lookup"><span data-stu-id="35c61-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span>

> [!NOTE]
> <span data-ttu-id="35c61-109">我们尚不支持保留专用频道消息的配置。</span><span class="sxs-lookup"><span data-stu-id="35c61-109">We don't yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="35c61-110">支持保留在私人渠道中共享的文件。</span><span class="sxs-lookup"><span data-stu-id="35c61-110">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="35c61-111">若要了解有关 Microsoft 365 或 Office 365 的保留策略的详细信息，请参阅 [保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="35c61-111">To learn more about retention policies for Microsoft 365 or Office 365, see [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="what-are-retention-policies-for-teams"></a><span data-ttu-id="35c61-112">什么是团队的保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-112">What are retention policies for Teams</span></span>

<span data-ttu-id="35c61-113">在为 Teams 或任何其他工作负载设置保留策略时，可将其设置为：</span><span class="sxs-lookup"><span data-stu-id="35c61-113">When you set up a retention policy for Teams or any other workload, you can set them up to:</span></span>

- <span data-ttu-id="35c61-114">**保留数据**：使用保留策略确保将数据保留一段指定的时间，无论用户应用中发生什么情况都是如此。</span><span class="sxs-lookup"><span data-stu-id="35c61-114">**Retain data**: Use a retention policy to ensure that your data is retained for a specified period of time, regardless of what happens in the user app.</span></span> <span data-ttu-id="35c61-115">出于合规性原因而保留数据，并且可用于电子数据展示，直到保留期到期为止，之后，策略会指示是不执行任何操作还是删除数据。</span><span class="sxs-lookup"><span data-stu-id="35c61-115">Data is retained for compliance reasons and is available for eDiscovery until the retention period expires, after which your policy indicates whether to do nothing or delete the data.</span></span> <span data-ttu-id="35c61-116">例如，如果创建 Teams 保留策略以将频道消息保留 7 年，则会将用于电子数据展示的消息保留 7 年，即便用户在 Teams 中删除了这些消息也是如此。</span><span class="sxs-lookup"><span data-stu-id="35c61-116">For example, if you create a Teams retention policy to retain channel messages for 7 years, the messages are retained for eDiscovery for 7 years, even if users delete their messages in Teams.</span></span>
- <span data-ttu-id="35c61-117">**删除数据**：使用保留策略删除数据，以确保它不会对你的组织造成负担。</span><span class="sxs-lookup"><span data-stu-id="35c61-117">**Delete data**: Use a retention policy to delete data to ensure that it's not a liability for your organization.</span></span> <span data-ttu-id="35c61-118">借助 Teams 保留策略，当你删除数据时，它将从 Teams 服务上的所有存储位置永久删除。</span><span class="sxs-lookup"><span data-stu-id="35c61-118">With a Teams retention policy, when you delete data, it's permanently deleted from all storage locations on the Teams service.</span></span>

<span data-ttu-id="35c61-119">借助 Teams 保留策略，你可以：</span><span class="sxs-lookup"><span data-stu-id="35c61-119">With retention policies for Teams, you can:</span></span>

- <span data-ttu-id="35c61-120">将 Teams 聊天和/或频道消息保留一段指定的时间，并且在此期限后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="35c61-120">Retain Teams chats and/or channel messages for a specified duration and then do nothing.</span></span>
- <span data-ttu-id="35c61-121">将 Teams 聊天和/或频道消息保留一段指定的时间，并在此期限后删除数据。</span><span class="sxs-lookup"><span data-stu-id="35c61-121">Retain Teams chats and/or channel messages for a specified duration and then delete the data.</span></span>
- <span data-ttu-id="35c61-122">在指定的时间段后删除 Teams 聊天和/或频道消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-122">Delete Teams chats and/or channel messages after a specified duration.</span></span>

> [!NOTE]
> <span data-ttu-id="35c61-123">请记住，在 Teams 中，用户在私人聊天中共享的文件存储在共享该文件的用户的 OneDrive for Business 帐户中。</span><span class="sxs-lookup"><span data-stu-id="35c61-123">Remember that in Teams, files that users share in private chats are stored in the OneDrive for Business account of the user who shared the file.</span></span> <span data-ttu-id="35c61-124">由团队成员上传到频道对话的文件则存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="35c61-124">And, files that team members upload to a channel conversation are stored in the team's SharePoint site.</span></span> <span data-ttu-id="35c61-125">因此，若要保留或删除 Teams 中的文件，请创建适用于 OneDrive for Business 和 SharePoint Online 的保留策略。</span><span class="sxs-lookup"><span data-stu-id="35c61-125">Therefore, to retain or delete files in Teams, create retention policies that apply to OneDrive for Business and SharePoint Online.</span></span>

<span data-ttu-id="35c61-126">如果数据受保留策略的约束，用户可以继续使用它，因为该数据将保留在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="35c61-126">When data is subject to a retention policy, users can continue to work with it because the data is retained in place, in its original location.</span></span> <span data-ttu-id="35c61-127">如果用户编辑或删除受策略约束的数据，则副本将保存到该策略生效时保留该副本的安全位置。</span><span class="sxs-lookup"><span data-stu-id="35c61-127">If a user edits or deletes data that's subject to the policy, a copy is saved to a secure location where it's retained while the policy is in effect.</span></span>

<span data-ttu-id="35c61-128">保留策略的最低许可要求是 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="35c61-128">The minimum licensing requirement for retention policies is Office 365 E3.</span></span> <span data-ttu-id="35c61-129">若要了解有关许可的详细信息，请参阅 [Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="35c61-129">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="35c61-130">Teams 保留策略的工作方式</span><span class="sxs-lookup"><span data-stu-id="35c61-130">How Teams retention policies work</span></span>

<span data-ttu-id="35c61-131">团队聊天内容存储在 Teamschat 中每个用户的隐藏文件夹中 () 在聊天中的每个用户的邮箱中，而团队频道消息存储在团队的组邮箱中的隐藏文件夹中 () Teamschat。</span><span class="sxs-lookup"><span data-stu-id="35c61-131">Teams chats are stored in a hidden folder (Teamschat) in the mailbox of each user in the chat, and Teams channel messages are stored in a hidden folder (Teamschat) in the group mailbox for a team.</span></span> <span data-ttu-id="35c61-132">Teams 使用由 Azure 支持的聊天服务，该服务也会存储此数据，并且默认永久存储。</span><span class="sxs-lookup"><span data-stu-id="35c61-132">Teams uses an Azure-powered chat service that also stores this data, and by default this service stores the data forever.</span></span> <span data-ttu-id="35c61-133">借助 Teams 保留策略，当你删除数据时，将从 Exchange 邮箱和基础聊天服务中永久删除该数据。</span><span class="sxs-lookup"><span data-stu-id="35c61-133">With a Teams retention policy, when you delete data, the data is permanently deleted from both the Exchange mailboxes and the underlying chat service.</span></span>

<span data-ttu-id="35c61-134">将 **保留保留** 策略应用到团队聊天或频道邮件时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="35c61-134">When you apply a **retention-hold** policy to Teams chats or channel messages, here's what happens:</span></span>

- <span data-ttu-id="35c61-135">如果在保留期间用户在保留期间内编辑或删除了聊天或频道消息，则会将邮件复制 (如果已编辑，则) 或移动 (如果已将其删除) 到 SubstrateHolds 文件夹并存储在保留期。</span><span class="sxs-lookup"><span data-stu-id="35c61-135">If a chat or channel message is edited or deleted by a user during the retention-hold period, the message is copied (if it was edited) or moved (if it was deleted) to the SubstrateHolds folder and stored there until the retention period expires.</span></span> <span data-ttu-id="35c61-136">如果将策略配置为在保留期到期时删除数据，则将在保留期到期的当天永久删除消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-136">If the policy is configured to delete data when the retention period expires, messages are permanently deleted on the day the retention period expires.</span></span>
- <span data-ttu-id="35c61-137">如果 **保留** 期间用户未删除聊天或频道消息，则邮件将在保留期到期后的一天内移动到 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="35c61-137">If a chat or channel message isn't deleted by a user during the **retention-hold** period, the message is moved to the SubstrateHolds folder within one day after the retention period expires.</span></span> <span data-ttu-id="35c61-138">如果将策略配置为在保留期到期时删除数据，则将在消息移至文件夹的一天后永久删除该消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-138">If the policy is configured to delete data when the retention period expires, the message is permanently deleted one day after it's moved to the folder.</span></span>

<span data-ttu-id="35c61-139">将 **保留期间删除** 策略应用到团队聊天和频道消息时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="35c61-139">When you apply a **retention-delete** policy to Teams chats and channel messages, here's what happens:</span></span>

- <span data-ttu-id="35c61-140">当聊天或频道消息到期时，如果保留消息的年龄超过了 **保留-删除** 策略，后端服务标识已过期消息并开始在后端存储 (用户或组邮箱) 中删除它们。</span><span class="sxs-lookup"><span data-stu-id="35c61-140">When a chat or channel message expires i.e. age of message is more than allowed by **retention-delete** policy, a back-end service, identifies expired messages and starts deleting them in the backend storage (user or group mailbox).</span></span>
- <span data-ttu-id="35c61-141">在后端存储中删除一条消息后，将触发一个过程，以便在 Azure 已通电的聊天服务和用户的团队应用中删除相同的消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-141">Once a message is deleted in back-end storage, a process is triggered to delete the same message in the Azure-powered chat service and user’s Teams app.</span></span> <span data-ttu-id="35c61-142">对于要在 "团队" 应用中删除的邮件，应用需要连接到 internet 并处于空闲状态 (无用户活动) ，因此删除过程不会影响用户体验。</span><span class="sxs-lookup"><span data-stu-id="35c61-142">For the messages to be deleted in Teams app, the app needs to be connected to internet and to be in idle state (no user activity), so that the deletion process would not interfere in user experience.</span></span> <span data-ttu-id="35c61-143">由于用户可能有多个设备（可能处于不同状态），因此保留删除不会完全与这些设备同步。</span><span class="sxs-lookup"><span data-stu-id="35c61-143">Since a user might have multiple devices, which might be in different states, retention deletes would not sync up with those devices at exactly same time.</span></span>
- <span data-ttu-id="35c61-144">在后端存储中的消息删除完成后，这些消息将在合规性搜索报告（如电子数据展示）中停止显示。</span><span class="sxs-lookup"><span data-stu-id="35c61-144">Once the deletion of messages in backend storage is complete, those messages will stop showing up in compliance search reports such as eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="35c61-145">相同的流程适用于 Skype for Business Online 和 Teams 互操作聊天。</span><span class="sxs-lookup"><span data-stu-id="35c61-145">The same flow works for Skype for Business Online and Teams interop chats.</span></span> <span data-ttu-id="35c61-146">当 Skype for Business Online 聊天进入 Teams 时，它将成为 Teams 聊天线程中的消息，并接收到相应的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="35c61-146">When a Skype for Business Online chat comes into Teams, it becomes a message in a Teams chat thread and is ingested into the appropriate mailbox.</span></span> <span data-ttu-id="35c61-147">Teams 保留策略将从 Teams 线程中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-147">Teams retention policies will delete these messages from the Teams thread.</span></span> <span data-ttu-id="35c61-148">但是，如果已为 Skype for Business Online 开启对话历史记录，并且从 Skype for Business Online 客户端将会话历史记录保存到邮箱中，则 Teams 保留策略不会处理该聊天数据。</span><span class="sxs-lookup"><span data-stu-id="35c61-148">However, if conversation history is turned on for Skype for Business Online and from the Skype for Business Online client side those are being saved into a mailbox, that chat data isn't handled by a Teams retention policy.</span></span>

> [!NOTE]
> <span data-ttu-id="35c61-149">邮件的删除是永久性和不可逆的。</span><span class="sxs-lookup"><span data-stu-id="35c61-149">The deletion of messages is permanent and irreversible.</span></span>

<span data-ttu-id="35c61-150">Teams 中的保留策略基于聊天或频道消息的创建日期，并且具有追溯性。</span><span class="sxs-lookup"><span data-stu-id="35c61-150">Retention policies in Teams are based on the date the chat or channel messages were created and are retroactive.</span></span> <span data-ttu-id="35c61-151">换言之，如果你创建保留策略来删除 90 天之前的数据，则在 90 天之前创建的 Teams 数据将被删除。</span><span class="sxs-lookup"><span data-stu-id="35c61-151">In other words, if you create a retention policy to delete data older than 90 days, Teams data created more than 90 days ago is deleted.</span></span>

<span data-ttu-id="35c61-152">应用于 SharePoint Online 或 OneDrive for Business 的保留策略可能会先删除在 Teams 聊天或频道消息中引用的文件，然后再删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-152">It's possible that a retention policy that's applied to SharePoint Online or OneDrive for Business could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="35c61-153">在这种情况下，该文件仍将显示在 Teams 消息中，但当用户单击文件时，将收到“找不到文件”错误。</span><span class="sxs-lookup"><span data-stu-id="35c61-153">In this scenario, the file will still show up in the Teams message, but when users click the file, they'll get a "File not found" error.</span></span> <span data-ttu-id="35c61-154">如果某人手动从 SharePoint Online 或 OneDrive for Business 中删除文件，则在没有应用策略的情况下也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="35c61-154">This can also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business.</span></span>

### <a name="considerations-and-limitations"></a><span data-ttu-id="35c61-155">注意事项和限制</span><span class="sxs-lookup"><span data-stu-id="35c61-155">Considerations and limitations</span></span>

<span data-ttu-id="35c61-156">以下是在使用 Teams 保留策略时需要注意的一些事项和限制：</span><span class="sxs-lookup"><span data-stu-id="35c61-156">Here's some considerations and limitations to be aware of when working with Teams retention policies:</span></span>

- <span data-ttu-id="35c61-157">Teams 需要与其他工作负载分开的保留策略。</span><span class="sxs-lookup"><span data-stu-id="35c61-157">Teams requires a retention policy that's separate from other workloads.</span></span> <span data-ttu-id="35c61-158">换言之，你必须为 Teams 聊天和/或频道消息创建特定保留策略。</span><span class="sxs-lookup"><span data-stu-id="35c61-158">In other words, you have to create specific retention policies for Teams chats and/or channel messages.</span></span> <span data-ttu-id="35c61-159">因此，你不能在组织范围的保留策略中包括 Teams。</span><span class="sxs-lookup"><span data-stu-id="35c61-159">For this reason, you can't include Teams in org-wide retention policies.</span></span>

- <span data-ttu-id="35c61-160">不支持私有频道消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-160">Private channel messages aren't supported.</span></span> <span data-ttu-id="35c61-161">目前，Teams 的保留策略仅适用于标准频道消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-161">At this time, retention policies for Teams only apply to standard channel messages.</span></span>

- <span data-ttu-id="35c61-162">Teams 不支持高级保留设置，例如，用于为包含关键字或敏感信息的内容应用策略的功能。</span><span class="sxs-lookup"><span data-stu-id="35c61-162">Teams doesn't support advanced retention settings, such as the ability to apply a policy to content that contains keywords or sensitive information.</span></span> <span data-ttu-id="35c61-163">目前，Teams 中的保留策略适用于所有聊天和/或频道消息内容。</span><span class="sxs-lookup"><span data-stu-id="35c61-163">Currently, retention policies in Teams apply to all chat and/or channel message content.</span></span>

- <span data-ttu-id="35c61-164">当这些邮件过期时，团队保留策略将触发删除聊天和频道消息的过程， (基于邮件创建日期) 。</span><span class="sxs-lookup"><span data-stu-id="35c61-164">A Teams retention policy will trigger a process to delete chat and channel messages when those messages expire (based on message creation date).</span></span> <span data-ttu-id="35c61-165">但是，根据服务负载，可能需要长达7天才能永久删除后端存储和团队应用中的这些消息。</span><span class="sxs-lookup"><span data-stu-id="35c61-165">However, depending on service load, it may take up-to seven days to permanently delete these messages from backend storage and Teams app.</span></span> <span data-ttu-id="35c61-166">此外，这些邮件可以使用合规性工具 (电子数据展示、最终用户搜索) ，直至它们被从后端存储中永久删除。</span><span class="sxs-lookup"><span data-stu-id="35c61-166">Also, these messages will be searchable with compliance tools (eDiscovery, end user search) till they are permanently deleted from backend storage.</span></span>

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a><span data-ttu-id="35c61-167">多个保留策略和保留原则</span><span class="sxs-lookup"><span data-stu-id="35c61-167">Multiple retention policies and the principles of retention</span></span>

<span data-ttu-id="35c61-168">如果设置多个具有不同期限的 Teams 保留策略，则[保留策略原则](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)适用。</span><span class="sxs-lookup"><span data-stu-id="35c61-168">If you set up multiple Teams retention policies with varying durations, the [principles of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) apply.</span></span> <span data-ttu-id="35c61-169">以下是关于优先级的概述：</span><span class="sxs-lookup"><span data-stu-id="35c61-169">Here's an overview of what takes precedence:</span></span>

- <span data-ttu-id="35c61-170">保留始终优先于删除</span><span class="sxs-lookup"><span data-stu-id="35c61-170">Preservation always wins over deletion</span></span>
- <span data-ttu-id="35c61-171">优选最长的保留期</span><span class="sxs-lookup"><span data-stu-id="35c61-171">Longest preservation period always wins</span></span>
- <span data-ttu-id="35c61-172">显式添加的位置优先于隐式添加的位置</span><span class="sxs-lookup"><span data-stu-id="35c61-172">Explicit inclusion wins over implicit inclusion in terms of locations</span></span>
- <span data-ttu-id="35c61-173">优选最短删除期</span><span class="sxs-lookup"><span data-stu-id="35c61-173">Shortest deletion period wins</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="35c61-174">何时使用 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-174">When to use retention policies for Teams</span></span>

<span data-ttu-id="35c61-175">在许多情况下，组织认为与频道消息相比，私人聊天数据将造成更大的负担，因为频道消息通常是与项目更为相关的会话。</span><span class="sxs-lookup"><span data-stu-id="35c61-175">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="35c61-176">你可以为私人聊天（一对一或一对多聊天）和频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="35c61-176">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="35c61-177">你还可以配置适用于组织中特定用户或团队的唯一策略。</span><span class="sxs-lookup"><span data-stu-id="35c61-177">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="35c61-178">对于 Teams 聊天，可选择要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="35c61-178">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="35c61-179">对于 Teams 频道消息，可选择要为其应用策略的团队。</span><span class="sxs-lookup"><span data-stu-id="35c61-179">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="35c61-180">例如，对于频道消息，可以将一年删除策略应用于组织中的特定团队，并将三年删除策略应用于所有其他团队。</span><span class="sxs-lookup"><span data-stu-id="35c61-180">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="manage-retention-policies-for-teams"></a><span data-ttu-id="35c61-181">管理 Teams 的保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-181">Manage retention policies for Teams</span></span>

### <a name="using-the-security--compliance-center"></a><span data-ttu-id="35c61-182">使用安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="35c61-182">Using the Security & Compliance Center</span></span>

#### <a name="create-a-retention-policy"></a><span data-ttu-id="35c61-183">创建保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-183">Create a retention policy</span></span>

<span data-ttu-id="35c61-184">若要为 Teams 聊天和频道消息创建保留策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="35c61-184">To create a retention policy for Teams chats and channel messages, do the following:</span></span>

1. <span data-ttu-id="35c61-185">在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-185">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="35c61-186">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-186">Select **Create**.</span></span>
3. <span data-ttu-id="35c61-187">在“**为你的策略命名**”页面上，为你的策略输入名称和说明，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-187">On the **Name your policy** page, enter a name and description for your policy, and then click **Next**.</span></span>
4. <span data-ttu-id="35c61-188">在“**设置**”页上，指定是保留数据、删除数据还是先保留后删除，指定保留期，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-188">On the **Settings** page, specify whether you want to retain data, delete it, or both, the retention period, and then click **Next**.</span></span>
5. <span data-ttu-id="35c61-189">在“**选择位置**”页面上，执行以下操作，然后单击“**下一步**”：</span><span class="sxs-lookup"><span data-stu-id="35c61-189">On the **Choose locations** page, do the following, and then click **Next**:</span></span>

    - <span data-ttu-id="35c61-190">若要将策略应用于频道消息，请开启“**Teams 频道消息**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-190">To apply the policy to channel messages, turn on **Teams channel messages**.</span></span>  <span data-ttu-id="35c61-191">如果要将策略应用于组织中的特定团队，请选择“**选择团队**”，然后选择所需的团队。</span><span class="sxs-lookup"><span data-stu-id="35c61-191">If you want to apply the policy to specific teams in your organization, select **Choose teams**, and then select the teams that you want.</span></span>
    - <span data-ttu-id="35c61-192">若要将策略应用于聊天，请开启“**Teams 聊天**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-192">To apply the policy to chats, turn on **Teams chats**.</span></span> <span data-ttu-id="35c61-193">如果要将策略应用于组织中的特定用户，请选择“**选择用户**”，然后选择所需的用户。</span><span class="sxs-lookup"><span data-stu-id="35c61-193">If you want to apply the policy to specific users in your organization, select **Choose users**, and then select the users that you want.</span></span>
      > [!NOTE]
      > <span data-ttu-id="35c61-194">当开启“**Teams 频道消息**”和/或“**Teams 聊天**”时，所有其他位置都会自动关闭。</span><span class="sxs-lookup"><span data-stu-id="35c61-194">When you turn on **Teams channel messages** and/or **Teams chats**, all other locations are  automatically turned off.</span></span> <span data-ttu-id="35c61-195">Teams 保留策略只能包含 Teams 位置。</span><span class="sxs-lookup"><span data-stu-id="35c61-195">A Teams retention policy can only include Teams locations.</span></span>

        ![“选择位置”页面上的“Teams 频道消息”和“Teams 聊天”选项的屏幕截图](media/retention-policies-create.png)

      > [!IMPORTANT]
      > <span data-ttu-id="35c61-197">团队聊天和频道消息不受应用于 **Exchange 电子邮件** 或 **Microsoft 365 组** 位置中的用户或组邮箱的保留策略的影响。</span><span class="sxs-lookup"><span data-stu-id="35c61-197">Teams chats and channel messages aren't affected by retention policies applied to user or group mailboxes in the **Exchange email** or **Microsoft 365 groups** locations.</span></span> <span data-ttu-id="35c61-198">即使 Teams 聊天和频道消息存储在 Exchange 中，它们也仅受到应用于 Teams 位置的保留策略的影响。</span><span class="sxs-lookup"><span data-stu-id="35c61-198">Even though Teams chats and channel messages are stored in Exchange, they're only affected by retention policies applied to the Teams locations.</span></span>

6. <span data-ttu-id="35c61-199">查看设置，在准备就绪后，选择“**创建此策略**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-199">Review your settings, and then when you're ready, select **Create this policy**.</span></span>

#### <a name="edit-a-retention-policy"></a><span data-ttu-id="35c61-200">编辑保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-200">Edit a retention policy</span></span>

<span data-ttu-id="35c61-201">若要编辑 Teams 保留策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="35c61-201">To edit a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="35c61-202">在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-202">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="35c61-203">在保留策略列表中，选中要编辑的保留策略旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="35c61-203">In the list of retention policies, select the check box next to the retention policy you want to edit.</span></span>
3. <span data-ttu-id="35c61-204">选择要编辑的策略旁边的“**编辑**”，进行更改，单击“**保存**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-204">Select **Edit** next to what you want to edit, make your changes, click **Save**, and then click **Close**.</span></span>

    ![“选择位置”页面上的“Teams 频道消息”和“Teams 聊天”选项的屏幕截图](media/retention-policies-edit.png)

> [!WARNING]
> <span data-ttu-id="35c61-206">如果你已配置特定团队或特定用户以包含团队频道消息或团队聊天的内容，并编辑这些内容以删除该位置的最后一个，则该位置的配置将恢复为 " **全部**"。</span><span class="sxs-lookup"><span data-stu-id="35c61-206">If you have configured specific teams or specific users to include for Teams channel messages or Teams chats, and edit these to remove the last one for the location, the configuration for that location reverts to **All**.</span></span> <span data-ttu-id="35c61-207">请确保这是你希望在保存策略之前执行的配置。</span><span class="sxs-lookup"><span data-stu-id="35c61-207">Make sure this is the configuration that you intend before you save the policy.</span></span>
> 
> <span data-ttu-id="35c61-208">例如，如果你指定了一个团队聊天用户以包含在配置为删除数据的保留策略中，然后编辑策略以删除此用户，则默认情况下，所有用户都将遵守永久删除其团队聊天消息的保留策略。</span><span class="sxs-lookup"><span data-stu-id="35c61-208">For example, if you have specified one Teams chat user to include in your retention policy that's configured to delete data, and then edit the policy to remove this user, by default all users will then be subject to the retention policy that permanently deletes their Teams chat messages.</span></span> <span data-ttu-id="35c61-209">对于团队频道消息，这同样适用于包含。</span><span class="sxs-lookup"><span data-stu-id="35c61-209">The same applies to includes for Teams channel messages.</span></span>
> 
> <span data-ttu-id="35c61-210">在这种情况下，如果你不希望团队频道消息或团队的 **所有设置均** 受保留策略制约，请将位置切换为 "关"。</span><span class="sxs-lookup"><span data-stu-id="35c61-210">In this scenario, toggle the location off if you don't want the **All** setting for the Teams channel messages or Teams chat messages to be subject to the retention policy.</span></span> <span data-ttu-id="35c61-211">或者，将 "排除" 指定为不受策略阻止。</span><span class="sxs-lookup"><span data-stu-id="35c61-211">Alternatively, specify excludes to be exempt from the policy.</span></span>


#### <a name="delete-a-retention-policy"></a><span data-ttu-id="35c61-212">删除保留策略</span><span class="sxs-lookup"><span data-stu-id="35c61-212">Delete a retention policy</span></span>

<span data-ttu-id="35c61-213">若要删除 Teams 保留策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="35c61-213">To delete a Teams retention policy, do the following:</span></span>

1. <span data-ttu-id="35c61-214">在安全与合规中心的左窗格中，转到“**信息管理**” > “**保留**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-214">In the left navigation of the Security & Compliance Center, go to **Information governance** > **Retention**.</span></span>
2. <span data-ttu-id="35c61-215">在保留策略列表中，选中要删除的保留策略旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="35c61-215">In the list of retention policies, select the check box next to the retention policy you want to delete.</span></span>
3. <span data-ttu-id="35c61-216">选择“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="35c61-216">Select **Delete policy**.</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="35c61-217">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="35c61-217">End user experience</span></span>

<span data-ttu-id="35c61-218">对于私人聊天 (1:1 聊天) 或群组聊天，最终用户将看到早于保留策略配置的聊天已删除，并显示一条控制消息，显示 "我们已删除较早的 messaged，因为您的组织的保留策略" 已在尚未删除的邮件上显示。</span><span class="sxs-lookup"><span data-stu-id="35c61-218">For private chats (1:1 chats) or group chats, the end users will see that chats older than the retention policy configuration are deleted and a control message stating" We've deleted older messaged due to your org's retention policy" is shown on top of yet undeleted messages.</span></span>
:::image type="content" source="media/retention-policies-image1.png" alt-text="聊天保留屏幕截图":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="群组聊天保留屏幕截图":::

<span data-ttu-id="35c61-221">对于频道消息， (频道成员) 的最终用户将看到邮件过期后，已删除的邮件会从视图中消失。</span><span class="sxs-lookup"><span data-stu-id="35c61-221">For Channel messages, the end users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="35c61-222">如果已删除邮件是串接对话的父邮件，则在替换父消息时，将显示一条消息，指出 "此消息已被删除，因为保留策略已删除"。</span><span class="sxs-lookup"><span data-stu-id="35c61-222">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前频道的屏幕截图":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留后频道的屏幕截图":::

> [!NOTE]
> <span data-ttu-id="35c61-225">最终用户消息目前不能由用户或管理员修改。</span><span class="sxs-lookup"><span data-stu-id="35c61-225">End user messaging is not user or admin modifiable at this time.</span></span>


### <a name="using-powershell"></a><span data-ttu-id="35c61-226">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="35c61-226">Using PowerShell</span></span>

<span data-ttu-id="35c61-227">若要使用 [安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)创建和管理团队保留策略，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="35c61-227">To create and manage Teams retention policies by using [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell), use the following cmdlets:</span></span>

|<span data-ttu-id="35c61-228">策略</span><span class="sxs-lookup"><span data-stu-id="35c61-228">Policy</span></span>|<span data-ttu-id="35c61-229">规则</span><span class="sxs-lookup"><span data-stu-id="35c61-229">Rule</span></span>|
|---|---|
|[<span data-ttu-id="35c61-230">新-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="35c61-230">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="35c61-231">新-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="35c61-231">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="35c61-232">RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="35c61-232">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="35c61-233">RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="35c61-233">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="35c61-234">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="35c61-234">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="35c61-235">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="35c61-235">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[<span data-ttu-id="35c61-236">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="35c61-236">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [<span data-ttu-id="35c61-237">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="35c61-237">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a><span data-ttu-id="35c61-238">已知问题</span><span class="sxs-lookup"><span data-stu-id="35c61-238">Known issues</span></span>

<span data-ttu-id="35c61-239">以下是正在跟踪和调查的 Teams 中的已知保留策略问题。</span><span class="sxs-lookup"><span data-stu-id="35c61-239">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="35c61-240">在 "**团队频道消息**位置" 行中的 "**选择团队**" 下，你可能会看到还不是团队的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="35c61-240">Under **Choose teams** in the **Teams channel messages** location row, you may see Microsoft 365 Groups that aren't also Teams.</span></span> <span data-ttu-id="35c61-241">此问题将在未来得到解决。</span><span class="sxs-lookup"><span data-stu-id="35c61-241">This will be addressed in the future.</span></span>

- <span data-ttu-id="35c61-242">在“**Teams 聊天**”位置行中的“**选择用户**”下，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="35c61-242">Under **Choose users** in the **Teams chats** location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="35c61-243">保留策略不是为来宾设置的，我们正致力于从列表中删除来宾。</span><span class="sxs-lookup"><span data-stu-id="35c61-243">Retention policies aren't meant to be set for guests, and we're working to remove these from the list.</span></span>

- <span data-ttu-id="35c61-244">Exchange 生命周期助理 (的 ELC) 每天运行，但在某些情况下，时间延迟已运行最长7天。</span><span class="sxs-lookup"><span data-stu-id="35c61-244">Exchange Life Cycle assistant (ELC) runs daily, but the latency is known to have run upto 7 days, in some cases.</span></span> <span data-ttu-id="35c61-245">因此，如果你创建了 Teams 保留策略来删除 60 天之前的项目，则这些项目最长可保留 67 天。</span><span class="sxs-lookup"><span data-stu-id="35c61-245">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="35c61-246">这不是新情况 - 它遵循 Exchange 模型。</span><span class="sxs-lookup"><span data-stu-id="35c61-246">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="35c61-247">当然，在大多数情况下，不会出现延迟。</span><span class="sxs-lookup"><span data-stu-id="35c61-247">Of course, in most cases, there's no delay.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35c61-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="35c61-248">Related topics</span></span>

- [<span data-ttu-id="35c61-249">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="35c61-249">Overview of retention policies</span></span>](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
