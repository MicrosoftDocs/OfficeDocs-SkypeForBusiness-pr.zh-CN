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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会议迁移服务 (MMS) 是在后台运行，并为用户的业务和 Microsoft 团队会议将自动更新 Skype 的服务。 MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: da1b21b65794354a023632e785c463b494cc38f5
ms.sourcegitcommit: ee05fe02fe68b5bd6ee38dd4a3ad69da3d37c492
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34106171"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="c0491-104">使用会议迁移服务 (MMS)</span><span class="sxs-lookup"><span data-stu-id="c0491-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="c0491-105">会议迁移服务 (MMS) 是更新以下方案中的用户的现有会议的服务：</span><span class="sxs-lookup"><span data-stu-id="c0491-105">The Meeting Migration Service (MMS) is service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="c0491-106">当迁移用户从内部部署到云 （是否业务 online Skype 或 TeamsOnly）。</span><span class="sxs-lookup"><span data-stu-id="c0491-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="c0491-107">当管理员对用户的音频会议设置进行了更改</span><span class="sxs-lookup"><span data-stu-id="c0491-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="c0491-108">在向仅，工作组或 TeamsUpgradePolicy 中的用户的模式设置为 SfBwithTeamsCollabAndMeetings 升级 online 用户</span><span class="sxs-lookup"><span data-stu-id="c0491-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="c0491-109">当您使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0491-109">When you use PowerShell</span></span> 


<span data-ttu-id="c0491-110">默认情况下 MMS 是自动触发中每种情况下，尽管管理员可以禁用它在租户级别。</span><span class="sxs-lookup"><span data-stu-id="c0491-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="c0491-111">此外，管理员可以使用 PowerShell cmdlet 以手动触发给定用户的会议迁移。</span><span class="sxs-lookup"><span data-stu-id="c0491-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="c0491-112">**限制**： 会议如果以下任一情况，不能使用迁移服务：</span><span class="sxs-lookup"><span data-stu-id="c0491-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="c0491-113">用户邮箱位于 Exchange 内部部署中。</span><span class="sxs-lookup"><span data-stu-id="c0491-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="c0491-114">用户正在迁移从云到 Skype 的业务 Server 内部部署。</span><span class="sxs-lookup"><span data-stu-id="c0491-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="c0491-115">在这些情况下，最终用户可以使用[会议迁移工具](https://www.microsoft.com/en-us/download/details.aspx?id=51659)来迁移他们自己的会议而。</span><span class="sxs-lookup"><span data-stu-id="c0491-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/en-us/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="c0491-116">MMS 的工作原理</span><span class="sxs-lookup"><span data-stu-id="c0491-116">How MMS works</span></span>

<span data-ttu-id="c0491-117">指定用户的触发 MMS 时，为该用户的迁移请求位于队列中。</span><span class="sxs-lookup"><span data-stu-id="c0491-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="c0491-118">若要避免任何问题的竞争条件，排队有意未处理请求之前，至少 90 分钟过去的。</span><span class="sxs-lookup"><span data-stu-id="c0491-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="c0491-119">一旦 MMS 处理请求，则它将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c0491-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="c0491-120">搜索所有现有会议的用户组织的和计划将来的该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c0491-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="c0491-121">根据用户的邮箱中找到的信息，其更新或计划新会议中团队或 Skype 业务 online 为该用户，具体取决于具体的情况。</span><span class="sxs-lookup"><span data-stu-id="c0491-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="c0491-122">在电子邮件中，它取代了会议详细信息中的联机会议块。</span><span class="sxs-lookup"><span data-stu-id="c0491-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="c0491-123">代表会议组织者向所有会议收件人发送的会议的更新的版本。</span><span class="sxs-lookup"><span data-stu-id="c0491-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="c0491-124">会议受邀者将其电子邮件中收到与更新后的会议坐标为会议更新。</span><span class="sxs-lookup"><span data-stu-id="c0491-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="c0491-126">从触发 MMS 的时间，它通常需要大约 2 小时，直到都将迁移用户的会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="c0491-127">但是，如果用户具有大量的会议，则可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="c0491-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="c0491-128">如果 MMS 遇到错误迁移用户的一个或多个会议，它将定期重试达 9 倍 24 小时的范围内。</span><span class="sxs-lookup"><span data-stu-id="c0491-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="c0491-129">**说明**：</span><span class="sxs-lookup"><span data-stu-id="c0491-129">**Notes**:</span></span>

- <span data-ttu-id="c0491-p106">MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="c0491-p106">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
- <span data-ttu-id="c0491-133">仅 Skype 业务或 Microsoft 团队通过单击**添加 Skype 会议**按钮在 Web 上的 Outlook 或 outlook 使用 Skype Meeting 外接程序安排的会议都将迁移。</span><span class="sxs-lookup"><span data-stu-id="c0491-133">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="c0491-134">如果用户复制和粘贴到新的会议的 Skype 联机会议信息从一个会议，则不会更新该新的会议，由于没有原始服务中的没有会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-134">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="c0491-135">MMS 运行后，不会保留会议内容已创建或连接到会议 （白板、 投票，等等）。</span><span class="sxs-lookup"><span data-stu-id="c0491-135">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="c0491-136">如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。</span><span class="sxs-lookup"><span data-stu-id="c0491-136">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="c0491-137">日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="c0491-137">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="c0491-138">请注意，仍将存储在 OneNote 中的实际会议备注是存在;它是仅链接到共享便笺的都将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="c0491-138">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="c0491-139">与会者超过 250（包括组织者）的会议不会迁移。</span><span class="sxs-lookup"><span data-stu-id="c0491-139">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="c0491-140">邀请的正文中的某些 UNICODE 字符可能会错误地更新下列特殊字符之一： ï，¿，½。</span><span class="sxs-lookup"><span data-stu-id="c0491-140">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="c0491-141">用户的触发 MMS</span><span class="sxs-lookup"><span data-stu-id="c0491-141">Triggering MMS for a user</span></span>

<span data-ttu-id="c0491-142">本节介绍在以下情况下触发 MMS 时，会发生什么情况：</span><span class="sxs-lookup"><span data-stu-id="c0491-142">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="c0491-143">到云时从内部部署迁移用户</span><span class="sxs-lookup"><span data-stu-id="c0491-143">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="c0491-144">当管理员对用户的音频会议设置进行了更改</span><span class="sxs-lookup"><span data-stu-id="c0491-144">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="c0491-145">当 TeamsUpgradePolicy 中的用户的模式设置为 TeamsOnly 或 SfBWithTeamsCollabAndMeetings （使用 Powershell 或团队管理门户）</span><span class="sxs-lookup"><span data-stu-id="c0491-145">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="c0491-146">当您使用 PowerShell cmdlet，开始 CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="c0491-146">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="c0491-147">更新会议的内部部署用户移到云中时</span><span class="sxs-lookup"><span data-stu-id="c0491-147">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="c0491-148">这是其中 MMS 帮助创建更平稳转换为您的用户的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="c0491-148">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="c0491-149">但不会议迁移现有会议按 Skype 中为 Business Server 内部部署的用户将不再起作用后联机移动该用户。</span><span class="sxs-lookup"><span data-stu-id="c0491-149">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="c0491-150">因此，当您使用的内部部署管理工具 (是`Move-CsUser`或管理控制面板) 以将用户移动到云，现有会议将自动移动到云，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0491-150">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="c0491-151">如果`MoveToTeams`中切换`Move-CsUser`会议都将迁移到团队直接和用户将处于 TeamsOnly 模式指定。</span><span class="sxs-lookup"><span data-stu-id="c0491-151">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="c0491-152">使用此开关需要 Skype 业务服务器 2015 CU8 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c0491-152">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="c0491-153">这些用户仍可以加入任何 Skype 的业务它们可能会邀请参加会议，使用业务客户端 Skype 或 Skype 会议应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0491-153">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="c0491-154">否则会议都将迁移到 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="c0491-154">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="c0491-155">在任一情况下，如果用户已分配的音频会议许可证之前被移动到云，会议将创建使用电话拨入式坐标。</span><span class="sxs-lookup"><span data-stu-id="c0491-155">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="c0491-156">如果用户从内部部署迁移到云，并且想要使用音频会议的用户，我们建议您首先分配音频会议，移动用户，以便触发仅 1 会议迁移之前。</span><span class="sxs-lookup"><span data-stu-id="c0491-156">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="c0491-157">更新会议用户的音频会议设置更改时</span><span class="sxs-lookup"><span data-stu-id="c0491-157">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="c0491-158">在以下情况下，MMS 会更新现有 Skype 业务和 Microsoft 团队会议添加、 删除或修改电话拨入式坐标：</span><span class="sxs-lookup"><span data-stu-id="c0491-158">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="c0491-159">第三方音频会议提供商未启用时，您可以分配或删除用户和该用户的 Microsoft 音频会议服务许可证。</span><span class="sxs-lookup"><span data-stu-id="c0491-159">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="c0491-160">当您更改用户的音频会议提供商从任何其他提供程序为 Microsoft，提供用户分配 Microsoft 音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="c0491-160">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="c0491-161">有关详细信息，请参阅[分配 Microsoft 作为音频会议提供商](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="c0491-161">For more information, see [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span> <span data-ttu-id="c0491-162">另请注意，支持第三方音频会议提供商 [ACP] 已安排生命周期结束上 2019，年 4 月 1，为[以前宣布](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)。</span><span class="sxs-lookup"><span data-stu-id="c0491-162">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).</span></span>
- <span data-ttu-id="c0491-163">当您启用或禁用的用户的音频会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-163">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="c0491-164">当您更改或重置用户配置为使用公开会议的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="c0491-164">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="c0491-165">当您将用户移动到新的音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="c0491-165">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="c0491-166">当从音频会议桥的电话号码时未分配。</span><span class="sxs-lookup"><span data-stu-id="c0491-166">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="c0491-167">这是一个复杂的方案，需要执行附加步骤。</span><span class="sxs-lookup"><span data-stu-id="c0491-167">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="c0491-168">有关详细信息，请参阅[Change 音频会议网桥上的电话号码](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="c0491-168">For more information, see [Change the phone numbers on your audio conferencing bridge](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="c0491-169">并非所有更改用户的音频会议设置都触发 MMS。</span><span class="sxs-lookup"><span data-stu-id="c0491-169">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="c0491-170">具体地说，下列两种更改不会使 MMS 更新会议：</span><span class="sxs-lookup"><span data-stu-id="c0491-170">Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="c0491-171">当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时</span><span class="sxs-lookup"><span data-stu-id="c0491-171">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="c0491-172">当您更改您的组织的会议 URL 使用`Update-CsTenantMeetingUrl`命令。</span><span class="sxs-lookup"><span data-stu-id="c0491-172">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="c0491-173">更新会议分配 TeamsUpgradePolicy 时</span><span class="sxs-lookup"><span data-stu-id="c0491-173">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="c0491-174">默认情况下，会议迁移自动时将触发向用户授予实例`TeamsUpgradePolicy`与`mode=TeamsOnly`或`mode= SfBWithTeamsCollabAndMeetings`。</span><span class="sxs-lookup"><span data-stu-id="c0491-174">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="c0491-175">如果您不希望将会议迁移授予这些模式，之一时，然后指定`MigrateMeetingsToTeams $false`中`Grant-CsTeamsUpgradePolicy`（如果使用 PowerShell） 或取消选中迁移会议 （如果使用团队管理门户） 设置用户的共存模式时框。</span><span class="sxs-lookup"><span data-stu-id="c0491-175">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="c0491-176">此外请注意以下情况：</span><span class="sxs-lookup"><span data-stu-id="c0491-176">Also note the following:</span></span>

- <span data-ttu-id="c0491-177">会议迁移时才会激活您授予`TeamsUpgradePolicy`为某个特定用户。</span><span class="sxs-lookup"><span data-stu-id="c0491-177">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="c0491-178">如果您授予`TeamsUpgradePolicy`与`mode=TeamsOnly`或`mode=SfBWithTeamsCollabAndMeetings`在*租户范围*内，会议迁移不调用。</span><span class="sxs-lookup"><span data-stu-id="c0491-178">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="c0491-179">用户只能授予 TeamsOnly 模式如果用户驻留联机。</span><span class="sxs-lookup"><span data-stu-id="c0491-179">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="c0491-180">必须使用移动用户驻留在内部部署的`Move-CsUser`如上文所述。</span><span class="sxs-lookup"><span data-stu-id="c0491-180">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="c0491-181">授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 模式不转换现有团队会议为 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-181">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="c0491-182">通过 PowerShell cmdlet 手动触发会议迁移</span><span class="sxs-lookup"><span data-stu-id="c0491-182">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="c0491-183">除了自动会议迁移，管理员可以手动触发会议迁移的用户通过运行 cmdlet `Start-CsExMeetingMigration`。</span><span class="sxs-lookup"><span data-stu-id="c0491-183">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="c0491-184">此 cmdlet 队列中指定的用户的迁移请求。</span><span class="sxs-lookup"><span data-stu-id="c0491-184">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="c0491-185">除了需要`Identity`参数，它采用两个可选的参数，`SourceMeetingType`和`TargetMeetingType`，它允许您指定如何迁移会议：</span><span class="sxs-lookup"><span data-stu-id="c0491-185">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="c0491-186">**TargetMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="c0491-186">**TargetMeetingType:**</span></span>

- <span data-ttu-id="c0491-187">使用`TargetMeetingType Current`指定的业务会议的 Skype 能够 Skype 业务会议并团队会议保持团队会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-187">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="c0491-188">可能更改但是音频会议协调，和业务会议的任何本地 Skype 将业务 online 迁移到 Skype。</span><span class="sxs-lookup"><span data-stu-id="c0491-188">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="c0491-189">这是 TargetMeetingType 的默认值。</span><span class="sxs-lookup"><span data-stu-id="c0491-189">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="c0491-190">使用`TargetMeetingType Teams`指定必须将任何现有会议迁移到团队，无论是否会议位于 Skype 中适用于商务联机或本地和无论是否需要的任何音频会议更新如下。</span><span class="sxs-lookup"><span data-stu-id="c0491-190">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="c0491-191">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="c0491-191">**SourceMeetingType:**</span></span>
- <span data-ttu-id="c0491-192">使用`SourceMeetingType SfB`指示业务会议的唯一 Skype (是否在本地或联机) 应更新。</span><span class="sxs-lookup"><span data-stu-id="c0491-192">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="c0491-193">使用`SourceMeetingType Teams`指示应仅团队会议进行了更新。</span><span class="sxs-lookup"><span data-stu-id="c0491-193">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="c0491-194">使用`SourceMeetingType All`指示应更新为业务会议和团队会议这两个 Skyep。</span><span class="sxs-lookup"><span data-stu-id="c0491-194">Using `SourceMeetingType All` indicates that both Skyep for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="c0491-195">这是 SourceMeetingType 的默认值。</span><span class="sxs-lookup"><span data-stu-id="c0491-195">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="c0491-196">下面的示例演示如何启动会议迁移用户 ashaw@contoso.com，以便所有会议都将都迁移到团队：</span><span class="sxs-lookup"><span data-stu-id="c0491-196">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="c0491-197">管理 MMS</span><span class="sxs-lookup"><span data-stu-id="c0491-197">Managing MMS</span></span>

<span data-ttu-id="c0491-198">使用 Windows PowerShell，可以检查持续迁移的状态、 手动触发会议迁移和完全禁用迁移。</span><span class="sxs-lookup"><span data-stu-id="c0491-198">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="c0491-199">检查会议迁移的状态</span><span class="sxs-lookup"><span data-stu-id="c0491-199">Check the status of meeting migrations</span></span>

<span data-ttu-id="c0491-200">您使用`Get-CsMeetingMigrationStatus`cmdlet 来检查会议迁移的状态。</span><span class="sxs-lookup"><span data-stu-id="c0491-200">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="c0491-201">下面列出了一些示例。</span><span class="sxs-lookup"><span data-stu-id="c0491-201">Below are some examples.</span></span>

- <span data-ttu-id="c0491-202">要获取所有 MMS 迁移摘要状态，请运行以下命令提供所有迁移状态的表格视图：</span><span class="sxs-lookup"><span data-stu-id="c0491-202">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="c0491-203">若要获取特定时间段内的所有迁移的完整详细信息，请使用`StartTime`和`EndTime`参数。</span><span class="sxs-lookup"><span data-stu-id="c0491-203">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="c0491-204">例如，以下命令将返回完整详细信息发生的所有迁移 2018 年 10 月 1，从到 2018 年 10 月 8。</span><span class="sxs-lookup"><span data-stu-id="c0491-204">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="c0491-205">若要检查的特定用户迁移状态，请使用`Identity`参数。</span><span class="sxs-lookup"><span data-stu-id="c0491-205">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="c0491-206">例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：</span><span class="sxs-lookup"><span data-stu-id="c0491-206">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="c0491-207">如果您看到任何已失败的迁移，采取操作来解决这些问题尽快，因为用户将能够电话拨入式会议按这些用户，直到您解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="c0491-207">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="c0491-208">如果`Get-CsMeetingMigrationStatus`显示任何迁移在故障状态，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c0491-208">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="c0491-209">确定受影响的用户。</span><span class="sxs-lookup"><span data-stu-id="c0491-209">Determine which users are affected.</span></span> <span data-ttu-id="c0491-210">运行以下命令获取受影响的用户列表，以及报告的具体错误：</span><span class="sxs-lookup"><span data-stu-id="c0491-210">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. <span data-ttu-id="c0491-211">对于每个受影响的用户，运行会议迁移工具以手动将迁移其会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-211">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="c0491-212">如果使用会议迁移工具还是无法完成迁移，你有两个选择：</span><span class="sxs-lookup"><span data-stu-id="c0491-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="c0491-213">让用户创建新的 Skype 会议。</span><span class="sxs-lookup"><span data-stu-id="c0491-213">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="c0491-214">[联系支持人员](https://go.microsoft.com/fwlink/p/?LinkID=518322)。</span><span class="sxs-lookup"><span data-stu-id="c0491-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="c0491-215">启用和禁用 MMS</span><span class="sxs-lookup"><span data-stu-id="c0491-215">Enabling and disabling MMS</span></span>

<span data-ttu-id="c0491-216">所有组织，默认情况下启用 MMS，但可以禁用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0491-216">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="c0491-217">完全禁用租户。</span><span class="sxs-lookup"><span data-stu-id="c0491-217">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="c0491-218">只禁用与音频会议相关的更改。</span><span class="sxs-lookup"><span data-stu-id="c0491-218">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="c0491-219">在这种情况下，MMS 将用户从内部部署到云或授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式中的迁移时仍运行`TeamsUpgradePolicy`。</span><span class="sxs-lookup"><span data-stu-id="c0491-219">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="c0491-220">例如，您可能想要手动迁移所有会议或更改您的组织的音频会议设置的大量时暂时禁用 MMS</span><span class="sxs-lookup"><span data-stu-id="c0491-220">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="c0491-221">若要查看 MMS 启用您的组织，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c0491-221">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="c0491-222">如果启用 MMS `MeetingMigrationEnabled` ，则参数`$true`。</span><span class="sxs-lookup"><span data-stu-id="c0491-222">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="c0491-223">若要启用或禁用 MMS 完全，使用`Set-CsTenantMigrationConfiguration`命令。</span><span class="sxs-lookup"><span data-stu-id="c0491-223">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="c0491-224">例如，若要禁用 MMS，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c0491-224">For example, to disable MMS, run the following command:</span></span>

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="c0491-225">如果您想检查它是否已启用音频会议更新 MMS 启用组织中，检查的值`AutomaticallyMigrateUserMeetings`中的输出参数`Get-CsOnlineDialInConferencingTenantSettings`。</span><span class="sxs-lookup"><span data-stu-id="c0491-225">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="c0491-226">若要启用或禁用 MMS 为音频会议，请使用`Set-CsOnlineDialInConferencingTenantSettings`。</span><span class="sxs-lookup"><span data-stu-id="c0491-226">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="c0491-227">例如，若要禁用 MMS 为音频会议，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c0491-227">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="c0491-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="c0491-228">Related topics</span></span>

[<span data-ttu-id="c0491-229">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="c0491-229">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="c0491-230">内部部署和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="c0491-230">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
