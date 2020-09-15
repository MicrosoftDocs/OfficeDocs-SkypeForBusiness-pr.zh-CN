---
title: '使用会议迁移服务 (MMS) '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 会议迁移服务 (MMS) 是一种在后台运行的服务，可自动更新用户的 Skype for business 和 Microsoft 团队会议。 MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 9223102ef9c264fdafdb9f52ec74d6edb383f987
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47765344"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="006fa-104">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="006fa-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="006fa-105"> (MMS) 的会议迁移服务是在以下情况下更新用户现有会议的服务：</span><span class="sxs-lookup"><span data-stu-id="006fa-105">The Meeting Migration Service (MMS) is a service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="006fa-106">当用户从本地迁移到云时 (是 Skype for Business Online 还是 TeamsOnly) 。</span><span class="sxs-lookup"><span data-stu-id="006fa-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="006fa-107">管理员对用户的音频会议设置进行更改时</span><span class="sxs-lookup"><span data-stu-id="006fa-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="006fa-108">当联机用户仅升级到团队时，或者当 TeamsUpgradePolicy 中的用户模式设置为 SfBwithTeamsCollabAndMeetings 时</span><span class="sxs-lookup"><span data-stu-id="006fa-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="006fa-109">使用 PowerShell 时</span><span class="sxs-lookup"><span data-stu-id="006fa-109">When you use PowerShell</span></span> 


<span data-ttu-id="006fa-110">默认情况下，在这些情况下，MMS 会自动触发，尽管管理员可以在租户级别禁用它。</span><span class="sxs-lookup"><span data-stu-id="006fa-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="006fa-111">此外，管理员可以使用 PowerShell cmdlet 为给定用户手动触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="006fa-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="006fa-112">**限制**：如果满足以下任一条件，则无法使用会议迁移服务：</span><span class="sxs-lookup"><span data-stu-id="006fa-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="006fa-113">用户的邮箱托管在本地 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="006fa-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="006fa-114">用户正在从云迁移到本地 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="006fa-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="006fa-115">在这些情况下，最终用户可以使用 [会议迁移工具](https://www.microsoft.com/download/details.aspx?id=51659) 来迁移其自己的会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="006fa-116">MMS 的工作原理</span><span class="sxs-lookup"><span data-stu-id="006fa-116">How MMS works</span></span>

<span data-ttu-id="006fa-117">为给定用户触发 MMS 时，将向队列中放置该用户的迁移请求。</span><span class="sxs-lookup"><span data-stu-id="006fa-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="006fa-118">为了避免任何争用条件，已对排队的请求进行有意处理，直到至少90分钟后才会被处理。</span><span class="sxs-lookup"><span data-stu-id="006fa-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="006fa-119">MMS 处理请求后，它会执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="006fa-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="006fa-120">它将在该用户的邮箱中搜索该用户组织的所有现有会议，将来安排该用户。</span><span class="sxs-lookup"><span data-stu-id="006fa-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="006fa-121">根据用户邮箱中的信息，在团队或 Skype for Business Online 中为该用户更新或安排新会议，具体取决于具体的方案。</span><span class="sxs-lookup"><span data-stu-id="006fa-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="006fa-122">在电子邮件中，它将替换会议详细信息中的联机会议阻止。</span><span class="sxs-lookup"><span data-stu-id="006fa-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="006fa-123">它代表会议组织者将该会议的更新版本发送给所有会议收件人。</span><span class="sxs-lookup"><span data-stu-id="006fa-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="006fa-124">会议被邀请者将通过其电子邮件中的已更新会议坐标接收会议更新。</span><span class="sxs-lookup"><span data-stu-id="006fa-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="006fa-126">从 MMS 触发时起，通常需要大约2小时才会迁移用户的会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="006fa-127">但是，如果用户拥有大量的会议，可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="006fa-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="006fa-128">如果 MMS 在为用户迁移一个或多个会议时遇到错误，将在24小时范围内定期重试最多9次。</span><span class="sxs-lookup"><span data-stu-id="006fa-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="006fa-129">**备注**：</span><span class="sxs-lookup"><span data-stu-id="006fa-129">**Notes**:</span></span>

- <span data-ttu-id="006fa-130">MMS 在迁移会议时会替换联机会议信息块中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="006fa-130">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="006fa-131">因此，如果用户编辑了信息块，它们的更改会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="006fa-131">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="006fa-132">用户拥有的所有联机会议信息块以外的内容不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="006fa-132">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span> <span data-ttu-id="006fa-133">这意味着将仍包括附加到会议邀请的任何文件。</span><span class="sxs-lookup"><span data-stu-id="006fa-133">This means any files attached to the meeting invite will still be included.</span></span> 
- <span data-ttu-id="006fa-134">只有通过在 Outlook 网页版中单击 " **添加 skype 会议** " 按钮或使用 Outlook 的 skype 会议外接程序进行安排的 Skype for Business 或 Microsoft 团队会议才会被迁移。</span><span class="sxs-lookup"><span data-stu-id="006fa-134">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="006fa-135">如果用户将一个会议中的 Skype online 会议信息复制并粘贴到新会议中，则不会更新新会议，因为原始服务中没有会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-135">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="006fa-136">创建或附加到会议的会议内容 (白板、投票等) 在 MMS 运行后不会保留。</span><span class="sxs-lookup"><span data-stu-id="006fa-136">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="006fa-137">如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。</span><span class="sxs-lookup"><span data-stu-id="006fa-137">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="006fa-138">日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="006fa-138">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="006fa-139">请注意，OneNote 中存储的实际会议笔记仍将保留在其中。只有指向共享笔记的链接被覆盖。</span><span class="sxs-lookup"><span data-stu-id="006fa-139">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="006fa-140">与会者超过 250（包括组织者）的会议不会迁移。</span><span class="sxs-lookup"><span data-stu-id="006fa-140">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="006fa-141">邀请正文中的一些 UNICODE 字符可能会错误地更新为下列特殊字符之一：ï、¿、1/2、。</span><span class="sxs-lookup"><span data-stu-id="006fa-141">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="006fa-142">为用户触发 MMS</span><span class="sxs-lookup"><span data-stu-id="006fa-142">Triggering MMS for a user</span></span>

<span data-ttu-id="006fa-143">本部分介绍在以下每种情况下会触发 MMS 的情况：</span><span class="sxs-lookup"><span data-stu-id="006fa-143">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="006fa-144">用户从本地迁移到云时</span><span class="sxs-lookup"><span data-stu-id="006fa-144">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="006fa-145">管理员对用户的音频会议设置进行更改时</span><span class="sxs-lookup"><span data-stu-id="006fa-145">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="006fa-146">当 TeamsUpgradePolicy 中的用户模式使用 Powershell 或团队管理门户设置为 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (时) </span><span class="sxs-lookup"><span data-stu-id="006fa-146">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="006fa-147">使用 PowerShell cmdlet 时，Start-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="006fa-147">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="006fa-148">将本地用户移动到云时更新会议</span><span class="sxs-lookup"><span data-stu-id="006fa-148">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="006fa-149">这是一种最常见的情况，MMS 可帮助用户创建更流畅的切换效果。</span><span class="sxs-lookup"><span data-stu-id="006fa-149">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="006fa-150">如果没有会议迁移，在用户联机移动后，在本地 Skype for business 服务器中由用户组织的现有会议将不再有效。</span><span class="sxs-lookup"><span data-stu-id="006fa-150">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="006fa-151">因此，当你使用本地管理员工具 (`Move-CsUser` 或 "管理员控制面板") 将用户移动到云时，现有会议将自动移到云，如下所示：</span><span class="sxs-lookup"><span data-stu-id="006fa-151">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="006fa-152">如果 `MoveToTeams` 指定了开关 `Move-CsUser` ，会议将直接迁移到团队，并且用户将处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="006fa-152">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="006fa-153">使用此开关需要使用 CU8 或更高版本的 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="006fa-153">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="006fa-154">通过使用 Skype for business 客户端或 Skype 会议应用，这些用户仍然可以加入任何受邀参加的 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-154">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="006fa-155">否则，会议将迁移到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="006fa-155">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="006fa-156">在任何一种情况下，如果用户在被移动到云之前已分配了音频会议许可证，则将使用拨入坐标创建会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-156">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="006fa-157">如果你将用户从本地移动到云，并且希望该用户使用音频会议，我们建议你在移动用户之前先分配音频会议，以便仅触发1个会议迁移。</span><span class="sxs-lookup"><span data-stu-id="006fa-157">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="006fa-158">当用户的音频会议设置更改时更新会议</span><span class="sxs-lookup"><span data-stu-id="006fa-158">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="006fa-159">在以下情况下，MMS 将更新现有 Skype for Business 和 Microsoft 团队会议以添加、删除或修改拨入坐标：</span><span class="sxs-lookup"><span data-stu-id="006fa-159">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="006fa-160">向用户分配或删除 Microsoft 音频会议服务许可证时，该用户未启用第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="006fa-160">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="006fa-161">如果将用户的音频会议提供商从任何其他提供商更改为 Microsoft，前提是该用户分配有 Microsoft 音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="006fa-161">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="006fa-162">有关详细信息，请参阅 [将 Microsoft 分配为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="006fa-162">For more information, see [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span> <span data-ttu-id="006fa-163">另请注意，第三方音频会议提供商 [ACP] 的支持计划于2019年4月1日（如 [以前宣布](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)）的生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="006fa-163">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).</span></span>
- <span data-ttu-id="006fa-164">启用或禁用用户的音频会议时。</span><span class="sxs-lookup"><span data-stu-id="006fa-164">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="006fa-165">当您更改或重置配置为使用公共会议的用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="006fa-165">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="006fa-166">将用户移动到新的音频会议桥时。</span><span class="sxs-lookup"><span data-stu-id="006fa-166">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="006fa-167">当音频会议桥的电话号码未分配时。</span><span class="sxs-lookup"><span data-stu-id="006fa-167">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="006fa-168">这是一个需要额外步骤的复杂方案。</span><span class="sxs-lookup"><span data-stu-id="006fa-168">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="006fa-169">有关详细信息，请参阅 [更改音频会议桥中的电话号码](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="006fa-169">For more information, see [Change the phone numbers on your audio conferencing bridge](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="006fa-170">对用户的音频会议设置的所有更改都不会触发 MMS。</span><span class="sxs-lookup"><span data-stu-id="006fa-170">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="006fa-171">具体地说，下列两种更改不会使 MMS 更新会议：</span><span class="sxs-lookup"><span data-stu-id="006fa-171">Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="006fa-172">当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时</span><span class="sxs-lookup"><span data-stu-id="006fa-172">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="006fa-173">使用命令更改组织的会议 URL 时 `Update-CsTenantMeetingUrl` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-173">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="006fa-174">分配 TeamsUpgradePolicy 时更新会议</span><span class="sxs-lookup"><span data-stu-id="006fa-174">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="006fa-175">默认情况下，当向用户授予 with 或的实例时，将自动触发会议迁移 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode= SfBWithTeamsCollabAndMeetings` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-175">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="006fa-176">如果你不希望在授予其中任一种模式时迁移会议，请 `MigrateMeetingsToTeams $false` 在 (中指定 `Grant-CsTeamsUpgradePolicy` 如果使用 PowerShell) 或取消选中在设置用户的共存模式时迁移会议的框 (如果使用团队管理门户) 。</span><span class="sxs-lookup"><span data-stu-id="006fa-176">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="006fa-177">另请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="006fa-177">Also note the following:</span></span>

- <span data-ttu-id="006fa-178">仅当你授予特定用户时，才会调用会议迁移 `TeamsUpgradePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-178">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="006fa-179">如果你在 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` *租户范围内* 授予或，则不会调用会议迁移。</span><span class="sxs-lookup"><span data-stu-id="006fa-179">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="006fa-180">如果用户处于联机状态，则仅可向用户授予 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="006fa-180">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="006fa-181">必须按照前面所述，使用托管内部部署的用户进行移动 `Move-CsUser` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-181">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="006fa-182">授予除 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 以外的其他模式时，不会将现有团队会议转换为 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-182">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="006fa-183">通过 PowerShell cmdlet 手动触发会议迁移</span><span class="sxs-lookup"><span data-stu-id="006fa-183">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="006fa-184">除了自动会议迁移之外，管理员还可以通过运行 cmdlet 手动为用户触发会议迁移 `Start-CsExMeetingMigration` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-184">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="006fa-185">此 cmdlet 将针对指定用户的迁移请求排队。</span><span class="sxs-lookup"><span data-stu-id="006fa-185">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="006fa-186">除了所需参数之外 `Identity` ，它还带有两个可选参数， `SourceMeetingType` 并 `TargetMeetingType` 允许你指定如何迁移会议：</span><span class="sxs-lookup"><span data-stu-id="006fa-186">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="006fa-187">**TargetMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="006fa-187">**TargetMeetingType:**</span></span>

- <span data-ttu-id="006fa-188">使用 `TargetMeetingType Current` 指定 skype for business 会议保持 skype for business 会议和团队会议保持团队会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-188">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="006fa-189">但是音频会议坐标可能会更改，并且任何本地 Skype for business 会议都将迁移到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="006fa-189">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="006fa-190">这是 TargetMeetingType 的默认值。</span><span class="sxs-lookup"><span data-stu-id="006fa-190">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="006fa-191">使用 `TargetMeetingType Teams` 指定无论是否需要进行任何音频会议更新，任何现有会议都必须迁移到团队，无论该会议是托管在 Skype For business online 还是内部部署中。</span><span class="sxs-lookup"><span data-stu-id="006fa-191">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="006fa-192">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="006fa-192">**SourceMeetingType:**</span></span>
- <span data-ttu-id="006fa-193">`SourceMeetingType SfB`"使用" 表示只有 Skype For business 会议 (是否应更新内部部署或联机) 。</span><span class="sxs-lookup"><span data-stu-id="006fa-193">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="006fa-194">使用 `SourceMeetingType Teams` 指示仅应更新团队会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-194">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="006fa-195">"使用" `SourceMeetingType All` 表示应更新 Skype for business 会议和团队会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-195">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="006fa-196">这是 SourceMeetingType 的默认值。</span><span class="sxs-lookup"><span data-stu-id="006fa-196">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="006fa-197">下面的示例演示了如何为用户 ashaw@contoso.com 启动会议迁移，以便将所有会议迁移到团队：</span><span class="sxs-lookup"><span data-stu-id="006fa-197">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="006fa-198">管理 MMS</span><span class="sxs-lookup"><span data-stu-id="006fa-198">Managing MMS</span></span>

<span data-ttu-id="006fa-199">使用 Windows PowerShell，你可以检查正在进行的迁移的状态，手动触发会议迁移，并完全禁用迁移。</span><span class="sxs-lookup"><span data-stu-id="006fa-199">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="006fa-200">检查会议迁移的状态</span><span class="sxs-lookup"><span data-stu-id="006fa-200">Check the status of meeting migrations</span></span>

<span data-ttu-id="006fa-201">使用 `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。</span><span class="sxs-lookup"><span data-stu-id="006fa-201">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="006fa-202">下面列出了一些示例。</span><span class="sxs-lookup"><span data-stu-id="006fa-202">Below are some examples.</span></span>

- <span data-ttu-id="006fa-203">若要获取所有 MMS 迁移的摘要状态，请运行以下命令，其中提供了所有迁移状态的表格视图：</span><span class="sxs-lookup"><span data-stu-id="006fa-203">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="006fa-204">若要获取特定时间段内所有迁移的完整详细信息，请使用 " `StartTime` 和" `EndTime` 参数。</span><span class="sxs-lookup"><span data-stu-id="006fa-204">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="006fa-205">例如，以下命令将返回从2018年10月1日到2018年10月8日的所有迁移的完整详细信息。</span><span class="sxs-lookup"><span data-stu-id="006fa-205">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="006fa-206">若要检查特定用户的迁移状态，请使用该 `Identity` 参数。</span><span class="sxs-lookup"><span data-stu-id="006fa-206">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="006fa-207">例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：</span><span class="sxs-lookup"><span data-stu-id="006fa-207">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="006fa-208">如果你看到任何失败的迁移，请尽快采取措施解决这些问题，因为用户无法在你解决这些问题之前使用这些用户进行组织。</span><span class="sxs-lookup"><span data-stu-id="006fa-208">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="006fa-209">如果 `Get-CsMeetingMigrationStatus` 显示处于失败状态的任何迁移，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="006fa-209">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="006fa-210">确定受影响的用户。</span><span class="sxs-lookup"><span data-stu-id="006fa-210">Determine which users are affected.</span></span> <span data-ttu-id="006fa-211">运行以下命令获取受影响的用户列表，以及报告的具体错误：</span><span class="sxs-lookup"><span data-stu-id="006fa-211">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="006fa-212">对于每个受影响的用户，运行会议迁移工具以手动迁移其会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-212">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="006fa-213">如果使用会议迁移工具还是无法完成迁移，你有两个选择：</span><span class="sxs-lookup"><span data-stu-id="006fa-213">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="006fa-214">让用户创建新的 Skype 会议。</span><span class="sxs-lookup"><span data-stu-id="006fa-214">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="006fa-215">[联系支持人员](https://go.microsoft.com/fwlink/p/?LinkID=518322)。</span><span class="sxs-lookup"><span data-stu-id="006fa-215">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="006fa-216">启用和禁用 MMS</span><span class="sxs-lookup"><span data-stu-id="006fa-216">Enabling and disabling MMS</span></span>

<span data-ttu-id="006fa-217">默认情况下，将为所有组织启用 MMS，但可以禁用它，如下所示：</span><span class="sxs-lookup"><span data-stu-id="006fa-217">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="006fa-218">完全禁用租户。</span><span class="sxs-lookup"><span data-stu-id="006fa-218">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="006fa-219">仅针对与音频会议相关的更改禁用。</span><span class="sxs-lookup"><span data-stu-id="006fa-219">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="006fa-220">在这种情况下，当用户从本地迁移到云或在中授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式时，MMS 仍将运行 `TeamsUpgradePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-220">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="006fa-221">例如，你可能希望手动迁移所有会议或暂时禁用 MMS，同时对你的组织的音频会议设置进行重大更改</span><span class="sxs-lookup"><span data-stu-id="006fa-221">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="006fa-222">若要查看你的组织是否已启用 MMS，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="006fa-222">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="006fa-223">如果参数为，则启用 MMS `MeetingMigrationEnabled` `$true` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-223">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="006fa-224">若要完全启用或禁用 MMS，请使用 `Set-CsTenantMigrationConfiguration` 命令。</span><span class="sxs-lookup"><span data-stu-id="006fa-224">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="006fa-225">例如，若要禁用 MMS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="006fa-225">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="006fa-226">如果组织中已启用 MMS，并且你想要检查它是否已启用音频会议更新，请 `AutomaticallyMigrateUserMeetings` 在的 "输出" 中检查该参数的值 `Get-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-226">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="006fa-227">若要启用或禁用音频会议的 MMS，请使用 `Set-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="006fa-227">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="006fa-228">例如，若要为音频会议禁用 MMS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="006fa-228">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="006fa-229">相关主题</span><span class="sxs-lookup"><span data-stu-id="006fa-229">Related topics</span></span>

[<span data-ttu-id="006fa-230">在 Microsoft 365 或 Office 365 中试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="006fa-230">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="006fa-231">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="006fa-231">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
