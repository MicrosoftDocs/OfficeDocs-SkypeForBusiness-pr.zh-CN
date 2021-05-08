---
title: 使用会议迁移服务 (MMS)
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
description: 会议迁移 (MMS) 是在后台运行的服务，可Skype for Business Microsoft Teams会议。 MMS 旨在消除用户运行会议迁移工具以更新其会议Skype for Business Microsoft Teams的需求。
ms.openlocfilehash: 3866a11144ef6566422f4e7478b3e0e63ed4a0c5
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237608"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="0feb1-104">使用会议迁移服务 (MMS)</span><span class="sxs-lookup"><span data-stu-id="0feb1-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="0feb1-105">会议迁移服务 (MMS) 是一种在下列情况下更新用户现有会议的服务：</span><span class="sxs-lookup"><span data-stu-id="0feb1-105">The Meeting Migration Service (MMS) is a service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="0feb1-106">当用户从本地迁移到云环境时 (是Skype for Business Online 还是 TeamsOnly) 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="0feb1-107">当管理员更改用户的音频会议设置时</span><span class="sxs-lookup"><span data-stu-id="0feb1-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="0feb1-108">将联机用户升级到Teams，或者 TeamsUpgradePolicy 中的用户模式设置为 SfBwithTeamsCollabAndMeetings 时</span><span class="sxs-lookup"><span data-stu-id="0feb1-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="0feb1-109">使用 PowerShell 时</span><span class="sxs-lookup"><span data-stu-id="0feb1-109">When you use PowerShell</span></span> 


<span data-ttu-id="0feb1-110">默认情况下，MMS 会在每种情况下自动触发，尽管管理员可以在租户级别禁用 MMS。</span><span class="sxs-lookup"><span data-stu-id="0feb1-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="0feb1-111">此外，管理员可以使用 PowerShell cmdlet 为给定用户手动触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="0feb1-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="0feb1-112">**限制**：如果满足以下任一条件，将不能使用会议迁移服务：</span><span class="sxs-lookup"><span data-stu-id="0feb1-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="0feb1-113">用户的邮箱托管在本地Exchange中。</span><span class="sxs-lookup"><span data-stu-id="0feb1-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="0feb1-114">用户正在从云迁移到Skype for Business Server本地。</span><span class="sxs-lookup"><span data-stu-id="0feb1-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="0feb1-115">在这些情况下，最终用户可以使用会议迁移 [工具来](https://www.microsoft.com/download/details.aspx?id=51659) 迁移自己的会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="0feb1-116">MMS 的工作原理</span><span class="sxs-lookup"><span data-stu-id="0feb1-116">How MMS works</span></span>

<span data-ttu-id="0feb1-117">为给定用户触发 MMS 时，该用户的迁移请求将置于队列中。</span><span class="sxs-lookup"><span data-stu-id="0feb1-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="0feb1-118">为避免出现任何竞争情况，在至少 90 分钟之前，特意不处理排队的请求。</span><span class="sxs-lookup"><span data-stu-id="0feb1-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="0feb1-119">MMS 处理请求后，会执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0feb1-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="0feb1-120">它会在用户的邮箱中搜索该用户组织的所有现有会议，并计划在将来。</span><span class="sxs-lookup"><span data-stu-id="0feb1-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="0feb1-121">根据在用户的邮箱中发现的信息，它会在 Teams 或 Skype for Business Online 中为该用户更新或安排新会议，具体取决于具体方案。</span><span class="sxs-lookup"><span data-stu-id="0feb1-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="0feb1-122">在电子邮件中，它将替换会议详细信息中的联机会议块。</span><span class="sxs-lookup"><span data-stu-id="0feb1-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="0feb1-123">它代表会议组织者将会议的更新版本发送给所有会议收件人。</span><span class="sxs-lookup"><span data-stu-id="0feb1-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="0feb1-124">会议被邀请者将收到其电子邮件中更新的会议坐标的会议更新。</span><span class="sxs-lookup"><span data-stu-id="0feb1-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="0feb1-126">从 MMS 触发起，通常需要大约 2 小时，直到用户的会议迁移完成。</span><span class="sxs-lookup"><span data-stu-id="0feb1-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="0feb1-127">但是，如果用户具有大量会议，可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="0feb1-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="0feb1-128">如果 MMS 在迁移用户的一个或多个会议时遇到错误，它将在 24 小时内定期重试最多 9 次。</span><span class="sxs-lookup"><span data-stu-id="0feb1-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="0feb1-129">**注意**：</span><span class="sxs-lookup"><span data-stu-id="0feb1-129">**Notes**:</span></span>

- <span data-ttu-id="0feb1-130">MMS 在迁移会议时会替换联机会议信息块中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="0feb1-130">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="0feb1-131">因此，如果用户编辑了信息块，它们的更改会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="0feb1-131">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="0feb1-132">用户拥有的所有联机会议信息块以外的内容不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="0feb1-132">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span> <span data-ttu-id="0feb1-133">这意味着，附加到会议邀请的任何文件仍将包含在内。</span><span class="sxs-lookup"><span data-stu-id="0feb1-133">This means any files attached to the meeting invite will still be included.</span></span> 
- <span data-ttu-id="0feb1-134">仅Skype for Business Microsoft Teams Web 上单击 Outlook 中的"添加 Skype 会议"按钮或者使用 Outlook 的 Skype 会议 加载项安排的 Outlook 会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-134">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="0feb1-135">如果用户将联机会议信息Skype粘贴到新会议，则新会议不会更新，因为原始服务中没有任何会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-135">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="0feb1-136">创建或附加到会议的会议内容 (白板、投票等) MMS 运行后不会保留。</span><span class="sxs-lookup"><span data-stu-id="0feb1-136">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="0feb1-137">如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。</span><span class="sxs-lookup"><span data-stu-id="0feb1-137">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="0feb1-138">日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="0feb1-138">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="0feb1-139">请注意，存储在会议记录中OneNote会议笔记仍将存在;它是唯一覆盖的共享笔记的链接。</span><span class="sxs-lookup"><span data-stu-id="0feb1-139">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="0feb1-140">与会者超过 250（包括组织者）的会议不会迁移。</span><span class="sxs-lookup"><span data-stu-id="0feb1-140">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="0feb1-141">邀请正文中的某些 UNICODE 字符可能会错误地更新为以下特殊字符之一：ï、-、1/2、 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-141">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="0feb1-142">为用户触发 MMS</span><span class="sxs-lookup"><span data-stu-id="0feb1-142">Triggering MMS for a user</span></span>

<span data-ttu-id="0feb1-143">本部分介绍以下情况中触发 MMS 时会发生什么情况：</span><span class="sxs-lookup"><span data-stu-id="0feb1-143">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="0feb1-144">当用户从本地迁移到云时</span><span class="sxs-lookup"><span data-stu-id="0feb1-144">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="0feb1-145">当管理员更改用户的音频会议设置时</span><span class="sxs-lookup"><span data-stu-id="0feb1-145">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="0feb1-146">当用户在 TeamsUpgradePolicy 中的模式设置为 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (使用 Powershell 或 Teams 管理门户) </span><span class="sxs-lookup"><span data-stu-id="0feb1-146">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="0feb1-147">使用 PowerShell cmdlet 时，Start-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="0feb1-147">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="0feb1-148">将本地用户移动到云时更新会议</span><span class="sxs-lookup"><span data-stu-id="0feb1-148">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="0feb1-149">这是 MMS 可帮助为用户创建更平滑过渡的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="0feb1-149">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="0feb1-150">如果不进行会议迁移，则由本地用户Skype for Business Server的现有会议在用户联机移动后将不再有效。</span><span class="sxs-lookup"><span data-stu-id="0feb1-150">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="0feb1-151">因此，使用本地管理工具 (管理控制面板) 将用户移动到云时，现有会议会自动移动到 `Move-CsUser` 云，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0feb1-151">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="0feb1-152">如果指定了 中的开关，会议将直接迁移到Teams `MoveToTeams` `Move-CsUser` 用户将进入 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0feb1-152">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="0feb1-153">此开关的使用要求在 2015 Skype for Business Server CU8 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0feb1-153">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="0feb1-154">这些用户仍可使用 Skype for Business Skype for Business 客户端或 Skype 会议 App 加入他们受邀参加的任何Skype 会议会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-154">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="0feb1-155">否则，会议将迁移到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="0feb1-155">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="0feb1-156">在任一情况下，如果在将用户移动到云之前为用户分配了音频会议许可证，则使用拨入坐标创建会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-156">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="0feb1-157">如果将用户从本地移动到云，并且希望该用户使用音频会议，我们建议在移动用户之前先分配音频会议，以便仅触发 1 个会议迁移。</span><span class="sxs-lookup"><span data-stu-id="0feb1-157">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="0feb1-158">当用户的音频会议设置更改时更新会议</span><span class="sxs-lookup"><span data-stu-id="0feb1-158">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="0feb1-159">在下列情况下，MMS 将更新Skype for Business Microsoft Teams会议以添加、删除或修改拨入坐标：</span><span class="sxs-lookup"><span data-stu-id="0feb1-159">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="0feb1-160">向用户分配或删除 Microsoft 音频会议服务许可证时，并且未为该用户启用第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="0feb1-160">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="0feb1-161">将用户的音频会议提供商从任何其他提供商更改为 Microsoft 时，只要为该用户分配了 Microsoft 音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="0feb1-161">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="0feb1-162">有关详细信息，请参阅将 [Microsoft 分配为音频会议提供商](./assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="0feb1-162">For more information, see [Assign Microsoft as the audio conferencing provider](./assign-microsoft-as-the-audio-conferencing-provider.md).</span></span> <span data-ttu-id="0feb1-163">另请注意，对第三方音频会议提供商 [ACP] 的支持计划于 2019 年 4 月 1 日结束，正如之前 [宣布的](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="0feb1-163">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).</span></span>
- <span data-ttu-id="0feb1-164">为用户启用或禁用音频会议时。</span><span class="sxs-lookup"><span data-stu-id="0feb1-164">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="0feb1-165">更改或重置配置为使用公用会议的用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="0feb1-165">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="0feb1-166">将用户移动到新的音频会议网桥时。</span><span class="sxs-lookup"><span data-stu-id="0feb1-166">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="0feb1-167">取消分配来自音频会议网桥的电话号码时。</span><span class="sxs-lookup"><span data-stu-id="0feb1-167">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="0feb1-168">这是一个复杂的方案，需要其他步骤。</span><span class="sxs-lookup"><span data-stu-id="0feb1-168">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="0feb1-169">有关详细信息，请参阅 [更改音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="0feb1-169">For more information, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="0feb1-170">并非用户的音频会议设置的所有更改都触发 MMS。</span><span class="sxs-lookup"><span data-stu-id="0feb1-170">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="0feb1-171">具体地说，下列两种更改不会使 MMS 更新会议：</span><span class="sxs-lookup"><span data-stu-id="0feb1-171">Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="0feb1-172">当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时</span><span class="sxs-lookup"><span data-stu-id="0feb1-172">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="0feb1-173">使用 命令更改组织的会议 URL `Update-CsTenantMeetingUrl` 时。</span><span class="sxs-lookup"><span data-stu-id="0feb1-173">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="0feb1-174">分配 TeamsUpgradePolicy 时更新会议</span><span class="sxs-lookup"><span data-stu-id="0feb1-174">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="0feb1-175">默认情况下，当向用户授予 具有 或 的实例时，会自动 `TeamsUpgradePolicy` 触发 `mode=TeamsOnly` 会议迁移 `mode= SfBWithTeamsCollabAndMeetings` 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-175">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="0feb1-176">如果在授予上述任一模式时不想迁移会议，则使用 PowerShell) 时，在 (中指定 ，或者取消选中用于迁移会议的框（如果使用 Teams 管理门户) ，则设置用户的共存模式 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` (）。</span><span class="sxs-lookup"><span data-stu-id="0feb1-176">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="0feb1-177">另请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="0feb1-177">Also note the following:</span></span>

- <span data-ttu-id="0feb1-178">只有当为特定用户授予权限时， `TeamsUpgradePolicy` 才调用会议迁移。</span><span class="sxs-lookup"><span data-stu-id="0feb1-178">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="0feb1-179">如果在租户范围内使用 或 进行授权，则不 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` 调用会议迁移。 </span><span class="sxs-lookup"><span data-stu-id="0feb1-179">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="0feb1-180">如果用户是在线家庭用户，则只能向用户授予 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0feb1-180">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="0feb1-181">必须如前所述使用 移动本地 `Move-CsUser` 用户。</span><span class="sxs-lookup"><span data-stu-id="0feb1-181">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="0feb1-182">授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings Teams模式不会将现有会议Skype for Business会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-182">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="0feb1-183">通过 PowerShell cmdlet 手动触发会议迁移</span><span class="sxs-lookup"><span data-stu-id="0feb1-183">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="0feb1-184">除了自动会议迁移外，管理员可以通过运行 cmdlet 手动为用户触发会议迁移 `Start-CsExMeetingMigration` 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-184">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="0feb1-185">此 cmdlet 将指定用户的迁移请求排队。</span><span class="sxs-lookup"><span data-stu-id="0feb1-185">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="0feb1-186">除了所需的参数外，它还采用两个可选参数 和 ，这允许你 `Identity` `SourceMeetingType` `TargetMeetingType` 指定如何迁移会议：</span><span class="sxs-lookup"><span data-stu-id="0feb1-186">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="0feb1-187">**TargetMeetingType：**</span><span class="sxs-lookup"><span data-stu-id="0feb1-187">**TargetMeetingType:**</span></span>

- <span data-ttu-id="0feb1-188">使用 `TargetMeetingType Current` 指定Skype for Business保留Skype for Business，Teams保留Teams会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-188">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="0feb1-189">但是，音频会议坐标可能会更改，任何本地会议Skype for Business迁移到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="0feb1-189">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="0feb1-190">这是 TargetMeetingType 的默认值。</span><span class="sxs-lookup"><span data-stu-id="0feb1-190">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="0feb1-191">使用 指定必须将任何现有会议迁移到 Teams，无论会议是托管在 Skype for Business 在线还是本地，也无论是否需要任何音频会议更新 `TargetMeetingType Teams` 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-191">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="0feb1-192">**SourceMeetingType：**</span><span class="sxs-lookup"><span data-stu-id="0feb1-192">**SourceMeetingType:**</span></span>
- <span data-ttu-id="0feb1-193">`SourceMeetingType SfB`使用 指示仅Skype for Business会议 (是本地还是联机) 更新。</span><span class="sxs-lookup"><span data-stu-id="0feb1-193">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="0feb1-194">`SourceMeetingType Teams`使用 指示仅Teams更新会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-194">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="0feb1-195">`SourceMeetingType All`使用 指示应Skype for Business会议Teams会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-195">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="0feb1-196">这是 SourceMeetingType 的默认值。</span><span class="sxs-lookup"><span data-stu-id="0feb1-196">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="0feb1-197">以下示例演示如何为用户启动会议迁移 ashaw@contoso.com 以便所有会议迁移到Teams：</span><span class="sxs-lookup"><span data-stu-id="0feb1-197">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="0feb1-198">管理 MMS</span><span class="sxs-lookup"><span data-stu-id="0feb1-198">Managing MMS</span></span>

<span data-ttu-id="0feb1-199">使用Windows PowerShell，可以检查正在进行的迁移的状态、手动触发会议迁移，以及完全禁用迁移。</span><span class="sxs-lookup"><span data-stu-id="0feb1-199">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="0feb1-200">检查会议迁移的状态</span><span class="sxs-lookup"><span data-stu-id="0feb1-200">Check the status of meeting migrations</span></span>

<span data-ttu-id="0feb1-201">使用 `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。</span><span class="sxs-lookup"><span data-stu-id="0feb1-201">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="0feb1-202">下面列出了一些示例。</span><span class="sxs-lookup"><span data-stu-id="0feb1-202">Below are some examples.</span></span>

- <span data-ttu-id="0feb1-203">若要获取所有 MMS 迁移的摘要状态，请运行以下命令，该命令提供所有迁移状态的表格视图：</span><span class="sxs-lookup"><span data-stu-id="0feb1-203">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="0feb1-204">若要获取特定时段内所有迁移的完整详细信息，请使用 `StartTime` 和 `EndTime` 参数。</span><span class="sxs-lookup"><span data-stu-id="0feb1-204">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="0feb1-205">例如，以下命令将返回 2018 年 10 月 1 日到 2018 年 10 月 8 日发生的所有迁移的完整详细信息。</span><span class="sxs-lookup"><span data-stu-id="0feb1-205">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="0feb1-206">若要检查特定用户的迁移状态，请使用 `Identity` 参数。</span><span class="sxs-lookup"><span data-stu-id="0feb1-206">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="0feb1-207">例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：</span><span class="sxs-lookup"><span data-stu-id="0feb1-207">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="0feb1-208">如果看到任何迁移失败，请尽快采取措施解决这些问题，因为用户无法拨入由这些用户组织的会议，直到你解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="0feb1-208">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="0feb1-209">如果 `Get-CsMeetingMigrationStatus` 显示任何迁移都为失败状态，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0feb1-209">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="0feb1-p126">确定受影响的用户。运行以下命令获取受影响的用户列表，以及报告的具体错误：</span><span class="sxs-lookup"><span data-stu-id="0feb1-p126">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="0feb1-212">对于每个受影响的用户，请运行会议迁移工具以手动迁移其会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-212">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="0feb1-213">如果使用会议迁移工具还是无法完成迁移，你有两个选择：</span><span class="sxs-lookup"><span data-stu-id="0feb1-213">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="0feb1-214">让用户创建新的 Skype 会议。</span><span class="sxs-lookup"><span data-stu-id="0feb1-214">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="0feb1-215">[联系支持人员](/microsoft-365/Admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="0feb1-215">[Contact support](/microsoft-365/Admin/contact-support-for-business-products).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="0feb1-216">启用和禁用 MMS</span><span class="sxs-lookup"><span data-stu-id="0feb1-216">Enabling and disabling MMS</span></span>

<span data-ttu-id="0feb1-217">MMS 默认为所有组织启用，但可禁用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0feb1-217">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="0feb1-218">完全禁用租户。</span><span class="sxs-lookup"><span data-stu-id="0feb1-218">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="0feb1-219">仅对与音频会议相关的更改禁用。</span><span class="sxs-lookup"><span data-stu-id="0feb1-219">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="0feb1-220">在这种情况下，当用户从本地迁移到云时，或者当你在 中授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式时，MMS 仍将运行 `TeamsUpgradePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-220">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="0feb1-221">例如，你可能希望手动迁移所有会议或暂时禁用 MMS，同时对组织的音频会议设置进行重大更改</span><span class="sxs-lookup"><span data-stu-id="0feb1-221">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="0feb1-222">若要查看是否为组织启用了 MMS，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0feb1-222">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="0feb1-223">如果参数为 ，则启用 `MeetingMigrationEnabled` `$true` MMS。</span><span class="sxs-lookup"><span data-stu-id="0feb1-223">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="0feb1-224">若要完全启用或禁用 MMS，请使用 `Set-CsTenantMigrationConfiguration` 命令。</span><span class="sxs-lookup"><span data-stu-id="0feb1-224">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="0feb1-225">例如，若要禁用 MMS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0feb1-225">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="0feb1-226">如果在组织中启用了 MMS，并且你想要检查是否为音频会议更新启用了 MMS，请检查 的输出中的 `AutomaticallyMigrateUserMeetings` 参数值 `Get-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-226">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="0feb1-227">若要为音频会议启用或禁用 MMS，请使用 `Set-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="0feb1-227">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="0feb1-228">例如，若要为音频会议禁用 MMS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0feb1-228">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="0feb1-229">相关主题</span><span class="sxs-lookup"><span data-stu-id="0feb1-229">Related topics</span></span>

[<span data-ttu-id="0feb1-230">尝试或购买音频会议Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="0feb1-230">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="0feb1-231">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="0feb1-231">Move users between on-premises and cloud</span></span>](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
