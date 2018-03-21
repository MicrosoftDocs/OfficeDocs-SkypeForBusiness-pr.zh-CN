---
title: "设置会议迁移服务 (MMS)"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "会议迁移服务 (MMS) 是为业务服务，在后台运行并自动更新用户的业务和 Microsoft 小组会议 Skype Skype。 MMS 旨在消除用户运行会议迁移工具需要更新其 Skype 业务和 Microsoft 小组会议。"
ms.openlocfilehash: 0d33efb2f60a06853ba26cd6e525f624114c95a5
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="bfd13-104">设置会议迁移服务 (MMS)</span><span class="sxs-lookup"><span data-stu-id="bfd13-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="bfd13-105">会议迁移服务 (MMS) 是为业务服务，在后台运行并自动更新用户的业务和 Microsoft 小组会议 Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="bfd13-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="bfd13-106">MMS 旨在消除用户运行会议迁移工具需要更新其 Skype 业务和 Microsoft 小组会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>
  
 <span data-ttu-id="bfd13-107">**要求**</span><span class="sxs-lookup"><span data-stu-id="bfd13-107">**Requirements**</span></span>
  
<span data-ttu-id="bfd13-108">MMS 要求会议组织者使用 Exchange Online 上的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bfd13-108">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="bfd13-109">**主要场景**</span><span class="sxs-lookup"><span data-stu-id="bfd13-109">**Primary scenarios**</span></span>
  
<span data-ttu-id="bfd13-110">MMS 会在下列两种主要场景中为用户更新 Skype 会议：</span><span class="sxs-lookup"><span data-stu-id="bfd13-110">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="bfd13-111">当用户被迁移从内部 Skype 业务服务器到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="bfd13-111">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="bfd13-112">当管理员将需要更新该用户的会议中的音频会议信息的用户的音频会议设置进行了更改。</span><span class="sxs-lookup"><span data-stu-id="bfd13-112">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="bfd13-113">**无法使用 MMS 的一般场景**</span><span class="sxs-lookup"><span data-stu-id="bfd13-113">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="bfd13-p103">我们在此处列出了可能适用于你的一般场景。这些场景都支持迁移。但是，MMS 不在这些场景中运行，你需要改为使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="bfd13-117">用户的邮箱在本地 Exchange Server 上</span><span class="sxs-lookup"><span data-stu-id="bfd13-117">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="bfd13-118">使用第三方音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="bfd13-118">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="bfd13-119">到内部部署 Skype 服务器迁移用户 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="bfd13-119">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="bfd13-120">将本地用户迁移至 Skype for Business Online 时更新会议</span><span class="sxs-lookup"><span data-stu-id="bfd13-120">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="bfd13-121">这是 MMS 可以帮助你的用户顺利过渡的最常见的场景。</span><span class="sxs-lookup"><span data-stu-id="bfd13-121">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="bfd13-122">当迁移用户从内部 Skype 业务服务器到 Skype 的在线业务时，MMS 将检测到新的用户，并且将扫描该用户的日历 Skype 业务和 Microsoft 小组会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-122">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="bfd13-123">任何将来的会议将与该用户的新信息更新。</span><span class="sxs-lookup"><span data-stu-id="bfd13-123">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="bfd13-124">如果您当前使用的音频会议的 Skype 服务器 2015</span><span class="sxs-lookup"><span data-stu-id="bfd13-124">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="bfd13-125">我们建议你在此场景中使用 MMS 时遵循下列最佳做法以获得最佳体验：</span><span class="sxs-lookup"><span data-stu-id="bfd13-125">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="bfd13-126">由于 MMS 要求用户使用 Exchange Online 上的邮箱，如果你也将迁离本地 Exchange Server，请先将用户的邮箱迁移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="bfd13-126">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="bfd13-127">**音频会议**许可证分配给用户，在运行之前`Move-CSUser`cmdlet 迁移用户。</span><span class="sxs-lookup"><span data-stu-id="bfd13-127">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="bfd13-128">这是因为 MMS 还更新会议时音频会议设置的更改的用户。</span><span class="sxs-lookup"><span data-stu-id="bfd13-128">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="bfd13-129">如果你没有先分配许可证，在你分配许可证后 MMS 会再次更新所有会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-129">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="bfd13-130">如果你当前使用的是第三方音频会议提供商 (ACP)</span><span class="sxs-lookup"><span data-stu-id="bfd13-130">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="bfd13-131">与第三方 ACP，MMS 的运行取决于组织的音频会议设置。</span><span class="sxs-lookup"><span data-stu-id="bfd13-131">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="bfd13-132">您可以选择当您为用户分配**音频会议**许可自动替换从您 ACP 的拨入号码。</span><span class="sxs-lookup"><span data-stu-id="bfd13-132">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="bfd13-133">另一方面，你可能需要阻止自动替换发生，保留你的 ACP 提供的拨入号码。</span><span class="sxs-lookup"><span data-stu-id="bfd13-133">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="bfd13-134">要查看您的组织的设置，请运行下面的 Windows PowerShell 命令并检查参数的值`AutomaticallyReplaceAcpProvider`。</span><span class="sxs-lookup"><span data-stu-id="bfd13-134">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="bfd13-135">如果需要有关 PowerShell 的帮助，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。</span><span class="sxs-lookup"><span data-stu-id="bfd13-135">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="bfd13-136">如果此参数的值是 $true，然后将运行时为用户分配**音频会议**许可 MMS 并更新他们的会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-136">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="bfd13-137">从您 ACP 的拨入号码保留直到**音频会议**许可分配。</span><span class="sxs-lookup"><span data-stu-id="bfd13-137">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="bfd13-138">如果此参数的值是 $false，MMS 不会更新会议，如果为用户分派的**音频会议**许可。</span><span class="sxs-lookup"><span data-stu-id="bfd13-138">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="bfd13-139">从您 ACP 的拨入号码将保留，直到用户手动设置为在 Skype 业务管理中心或使用 Windows PowerShell 的音频会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-139">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="bfd13-140">当用户的音频会议设置更改时，更新会议</span><span class="sxs-lookup"><span data-stu-id="bfd13-140">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="bfd13-141">MMS 将更新现有的 Skype 业务和 Microsoft 小组会议在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="bfd13-141">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="bfd13-142">当分配或删除**音频会议**许可。</span><span class="sxs-lookup"><span data-stu-id="bfd13-142">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="bfd13-143">当您启用或禁用音频会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-143">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="bfd13-144">当您更改或重置用户配置为使用公共会议会议 ID。</span><span class="sxs-lookup"><span data-stu-id="bfd13-144">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="bfd13-145">当将用户移动到新的音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="bfd13-145">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="bfd13-146">一个电话号码时从音频会议桥未分配。</span><span class="sxs-lookup"><span data-stu-id="bfd13-146">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="bfd13-147">这个场景比较复杂，需要执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="bfd13-147">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="bfd13-148">有关详细信息，请参阅[更改收费或免费电话号码在您的音频会议桥上](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-148">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="bfd13-149">[!重要信息] 仅当你使用的是 Microsoft 网桥时 MMS 才会更新会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-149">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="bfd13-150">如果您正在使用第三方音频会议提供商，用户将需要更新其会议手动。</span><span class="sxs-lookup"><span data-stu-id="bfd13-150">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="bfd13-151">在这种情况下，你可以使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-151">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="bfd13-152">不是所有用户的音频会议设置更改都触发 MMS。</span><span class="sxs-lookup"><span data-stu-id="bfd13-152">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="bfd13-153">具体地说，下列两种更改不会使 MMS 更新会议：</span><span class="sxs-lookup"><span data-stu-id="bfd13-153">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="bfd13-154">当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时</span><span class="sxs-lookup"><span data-stu-id="bfd13-154">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="bfd13-155">当你使用 [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) 命令更改你的组织的会议 URL 时。</span><span class="sxs-lookup"><span data-stu-id="bfd13-155">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="bfd13-156">MMS 更新会议时会发生什么？</span><span class="sxs-lookup"><span data-stu-id="bfd13-156">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="bfd13-157">当 MMS 检测到用户的会议需要更新时，它会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bfd13-157">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="bfd13-158">确定所有的 Skype 用户已计划在将来的业务和 Microsoft 小组会议</span><span class="sxs-lookup"><span data-stu-id="bfd13-158">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="bfd13-159">任何 Skype 业务或 Microsoft 小组的会议发生之前，MMS 在运行时将被跳过。</span><span class="sxs-lookup"><span data-stu-id="bfd13-159">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="bfd13-160">仅会更新该用户为组织者的会议</span><span class="sxs-lookup"><span data-stu-id="bfd13-160">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="bfd13-161">替换会议详情中的联机会议信息块</span><span class="sxs-lookup"><span data-stu-id="bfd13-161">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="bfd13-162">代表会议组织者将更新发送给会议所有的收件人</span><span class="sxs-lookup"><span data-stu-id="bfd13-162">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="bfd13-163">**MMS 运行需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="bfd13-163">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="bfd13-164">MMS 迁移会议时间的时间量取决于多少用户受到影响，和 Skype 在他们的日历上的每个用户拥有的业务或 Microsoft 小组会议的总次数。</span><span class="sxs-lookup"><span data-stu-id="bfd13-164">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="bfd13-165">运行至少需要 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="bfd13-165">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="bfd13-166">一些大型迁移需要的时间可能长达 12 小时，大多数迁移应该可以在 1 小时内完成。</span><span class="sxs-lookup"><span data-stu-id="bfd13-166">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="bfd13-167">**限制和潜在问题**</span><span class="sxs-lookup"><span data-stu-id="bfd13-167">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="bfd13-168">只通过单击在 Web 上的 Outlook 中的**添加 Skype 会议**按钮或通过 Skype 会议外接使用 Outlook 的计划的业务或 Microsoft 小组会议 Skype 被迁移。</span><span class="sxs-lookup"><span data-stu-id="bfd13-168">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="bfd13-169">换言之，如果用户将一个会议中的 Skype 联机会议信息复制并粘贴到另一个新会议中，该新会议不会更新。</span><span class="sxs-lookup"><span data-stu-id="bfd13-169">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="bfd13-p114">MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="bfd13-p115">在 MMS 运行后，所有之前创建的或附加到会议的会议内容（白板、投票等）将不会保留。如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="bfd13-p116">日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。请注意，存储在 OneNote 中的实际会议笔记会被保留，只会覆盖共享笔记的链接。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="bfd13-178">与会者超过 250（包括组织者）的会议不会迁移。</span><span class="sxs-lookup"><span data-stu-id="bfd13-178">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="bfd13-179">邀请正文中的一些 UNICODE 字符可能会被错误地更新为以下特殊字符之一：ï、¿、½、�。</span><span class="sxs-lookup"><span data-stu-id="bfd13-179">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="bfd13-180">MMS 更新会议时用户会为用户显示什么？</span><span class="sxs-lookup"><span data-stu-id="bfd13-180">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="bfd13-181">MMS 会像会议迁移工具一样代表用户发送会议更新。</span><span class="sxs-lookup"><span data-stu-id="bfd13-181">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="bfd13-182">因此，只会再次向用户显示其会议的会议接受通知。</span><span class="sxs-lookup"><span data-stu-id="bfd13-182">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="bfd13-183">这可能是令人困惑的用户，所以我们建议您事先不只当您迁移从内部到 Skype 的在线业务，但当您更改音频会议，还将触发 MMS 时通知用户。</span><span class="sxs-lookup"><span data-stu-id="bfd13-183">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="bfd13-184">管理 MMS</span><span class="sxs-lookup"><span data-stu-id="bfd13-184">Managing MMS</span></span>

<span data-ttu-id="bfd13-p118">你需要使用 Windows PowerShell 管理 MMS 并检查进行中的迁移的状态。本部分信息的前提是你了解如何使用 PowerShell 管理你的 Skype for Business 组织。如果你不了解如何使用 PowerShell，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="bfd13-188">我应该如何检查会议迁移的状态？</span><span class="sxs-lookup"><span data-stu-id="bfd13-188">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="bfd13-p119">你可以使用  `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。下面列出了一些示例。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="bfd13-191">要获取所有 MMS 迁移的汇总状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfd13-191">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="bfd13-192">这样会显示所有迁移状态的表格视图，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfd13-192">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="bfd13-193">州的 UserCount--</span><span class="sxs-lookup"><span data-stu-id="bfd13-193">State UserCount---------------</span></span><br/> <span data-ttu-id="bfd13-194">挂起 21</span><span class="sxs-lookup"><span data-stu-id="bfd13-194">Pending 21</span></span><br/><span data-ttu-id="bfd13-195">正在进行 6</span><span class="sxs-lookup"><span data-stu-id="bfd13-195">InProgress 6</span></span><br/> <span data-ttu-id="bfd13-196">失败的 2</span><span class="sxs-lookup"><span data-stu-id="bfd13-196">Failed 2</span></span> <br/> <span data-ttu-id="bfd13-197">成功的 131</span><span class="sxs-lookup"><span data-stu-id="bfd13-197">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="bfd13-p120">[!重要信息] 如果看到任何失败的迁移，请尽快解决这些问题。在你解决这些问题之前，其他人将无法拨入这些用户组织的会议。有关详细信息，请参阅[出错了应该怎么办？](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)部分。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="bfd13-p121">要获取一定时间段内所有迁移的完整详细信息，你可以使用  `StartTime` 和 `EndTime` 参数。例如，运行以下命令会返回 2016 年 10 月 1 日到 2016 年 10 月 8 日之间发生的所有迁移的完整详细信息。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="bfd13-p122">你可能也会想要检查特定用户的迁移状态，你可以使用  `UserId` 参数。例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：</span><span class="sxs-lookup"><span data-stu-id="bfd13-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="bfd13-205">出错了应该怎么办？</span><span class="sxs-lookup"><span data-stu-id="bfd13-205">What do I do if there is an error?</span></span>
<span data-ttu-id="bfd13-206"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd13-206"></span></span>

<span data-ttu-id="bfd13-207">在运行  `Get-CsMeetingMigrationStatus` cmdlet 获取汇总视图时，你发现有的迁移处于 已失败状态，下面列出了你需要执行的操作：</span><span class="sxs-lookup"><span data-stu-id="bfd13-207">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="bfd13-p123">确定受影响的用户。运行以下命令获取受影响的用户列表，以及报告的具体错误：</span><span class="sxs-lookup"><span data-stu-id="bfd13-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="bfd13-210">为其中的每个用户运行[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)以手动迁移他们的会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-210">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="bfd13-211">如果使用会议迁移工具还是无法完成迁移，你有两个选择：</span><span class="sxs-lookup"><span data-stu-id="bfd13-211">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="bfd13-212">让用户创建新的 Skype 会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-212">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="bfd13-213">[联系支持人员](https://go.microsoft.com/fwlink/p/?LinkID=518322)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-213">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="bfd13-214">启用和禁用 MMS</span><span class="sxs-lookup"><span data-stu-id="bfd13-214">Enabling and disabling MMS</span></span>
<span data-ttu-id="bfd13-215"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd13-215"></span></span>

<span data-ttu-id="bfd13-216">所有组织默认均已启用 MMS，但可以根据需要将其禁用。</span><span class="sxs-lookup"><span data-stu-id="bfd13-216">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="bfd13-217">例如，如果您想手动迁移所有会议或使用第三方音频会议提供商，可能不需要运行的 MMS。</span><span class="sxs-lookup"><span data-stu-id="bfd13-217">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="bfd13-218">你也可以选择暂时禁用 MMS。</span><span class="sxs-lookup"><span data-stu-id="bfd13-218">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="bfd13-219">例如，您可能会进行大量更改的音频会议设置为您的组织并不希望运行，直到完成所有更改的 MMS。</span><span class="sxs-lookup"><span data-stu-id="bfd13-219">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="bfd13-p125">要查看你的组织是否启用了 MMS，请运行以下命令并检查  `MeetingMigrationEnabled` 参数的值。如果此参数设置为$true，则启用了 MMS。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="bfd13-222">要禁用 MMS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfd13-222">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="bfd13-223">要启用 MMS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfd13-223">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="bfd13-224">启用和禁用多媒体短消息仅用于音频会议更改</span><span class="sxs-lookup"><span data-stu-id="bfd13-224">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="bfd13-225"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd13-225"></span></span>

<span data-ttu-id="bfd13-226">您还可以仅对音频会议更改禁用 MMS。</span><span class="sxs-lookup"><span data-stu-id="bfd13-226">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="bfd13-227">它仍将运行时迁移用户从 Skype 的业务部署到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="bfd13-227">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="bfd13-228">若要检查音频会议更新当前的 MMS 状态，运行以下命令，检查的值`AutomaticallyMigrateUserMeetings`参数。</span><span class="sxs-lookup"><span data-stu-id="bfd13-228">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="bfd13-229">如果此参数设置为 $true，MMS 设置音频会议设置发生更改时更新用户会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-229">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="bfd13-230">要禁用 MMS 的音频会议，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfd13-230">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="bfd13-231">若要启用 MMS 的音频会议，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfd13-231">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="bfd13-232">我如何手动为用户运行会议迁移？</span><span class="sxs-lookup"><span data-stu-id="bfd13-232">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="bfd13-233"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd13-233"></span></span>

<span data-ttu-id="bfd13-234">除了自动会议迁移之外，你还可以通过运行 cmdlet **Start-CsExMeetingMigration** 手动为用户运行会议迁移。</span><span class="sxs-lookup"><span data-stu-id="bfd13-234">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="bfd13-235">此 cmdlet 会议迁移队列中添加用户。</span><span class="sxs-lookup"><span data-stu-id="bfd13-235">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="bfd13-236">会议迁移服务将读取用户请求并迁移其会议。</span><span class="sxs-lookup"><span data-stu-id="bfd13-236">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="bfd13-237">你可以通过 cmdlet **Get-CsMeetingMigrationStatus** 检查会议迁移的状态。</span><span class="sxs-lookup"><span data-stu-id="bfd13-237">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="bfd13-238">下面是为用户 ashaw@contoso.com 启动会议迁移的示例：</span><span class="sxs-lookup"><span data-stu-id="bfd13-238">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="bfd13-239">使用 PowerShell 管理你的 Skype for Business 组织</span><span class="sxs-lookup"><span data-stu-id="bfd13-239">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="bfd13-240"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="bfd13-240"></span></span>

 <span data-ttu-id="bfd13-241">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="bfd13-241">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="bfd13-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bfd13-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bfd13-243">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="bfd13-243">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="bfd13-p128">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="bfd13-p129">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="bfd13-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="bfd13-250">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-250">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="bfd13-251">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="bfd13-251">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="bfd13-252">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bfd13-252">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bfd13-253">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="bfd13-253">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bfd13-254">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="bfd13-254">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="bfd13-255">如果想要深入了解如何启动 Windows PowerShell，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[使用 Windows PowerShell 连接到 Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-255">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="bfd13-p130">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="bfd13-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bfd13-259">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="bfd13-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bfd13-260">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfd13-260">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bfd13-p131">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="bfd13-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bfd13-263">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="bfd13-263">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bfd13-264">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bfd13-264">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bfd13-265">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="bfd13-265">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bfd13-266">相关主题</span><span class="sxs-lookup"><span data-stu-id="bfd13-266">Related topics</span></span>

[<span data-ttu-id="bfd13-267">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="bfd13-267">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
