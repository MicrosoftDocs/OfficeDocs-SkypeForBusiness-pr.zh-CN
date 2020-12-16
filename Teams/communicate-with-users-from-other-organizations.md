---
title: 与其他组织中的用户通话和聊天
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用外部访问（联合身份验证）和来宾访问在 Microsoft Teams 中与组织外部的用户进行通话、聊天、查找和添加这些用户。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031808"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a><span data-ttu-id="867d7-103">在 Microsoft Teams 中与其他组织的用户进行通话和聊天</span><span class="sxs-lookup"><span data-stu-id="867d7-103">Call and chat with users from other organizations in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="867d7-p101">当你需要与组织外部人员进行沟通和协作时，Microsoft Teams 提供了两种不同的方法来实现这一目的。第一 – **外部访问** （联合身份验证） – 可用于查找、呼叫和与其他域（例如 contoso.com）中的用户聊天。第二 – **访客访问** – 使你可以使用其电子邮件地址将个人作为来并添加到你的团队中。可以像与组织中的其他任何用户一样与访客协作。</span><span class="sxs-lookup"><span data-stu-id="867d7-p101">When you need to communicate and collaborate with people outside your organization, Microsoft Teams gives you two different ways to make that happen. The first – **external access** (federation) – lets  you find, call, and chat with users in other domains (for example, contoso.com). The second – **guest access** – lets you add individuals to your teams, as guests, using their email address. You can collaborate with guests as you would with any other users in your organization.</span></span>

<span data-ttu-id="867d7-108">如果需要，可同时使用外部访问和来宾访问（它们彼此之间不相排斥）。</span><span class="sxs-lookup"><span data-stu-id="867d7-108">You can use both external access and guest access if you want - one doesn't preclude the other.</span></span>

<span data-ttu-id="867d7-109">下面大体介绍了选择方法（要进行详细比较，请跳转到[比较外部和来宾访问](#compare-external-and-guest-access)）：</span><span class="sxs-lookup"><span data-stu-id="867d7-109">At a high level, here’s how to choose (for a detailed comparison, jump down to [Compare external and guest access](#compare-external-and-guest-access)):</span></span>

## <a name="external-access"></a><span data-ttu-id="867d7-110">外部访问</span><span class="sxs-lookup"><span data-stu-id="867d7-110">External access</span></span>

<span data-ttu-id="867d7-p102">当需要允许其他域中的外部用户查找、呼叫、聊天和安排会议的解决方案时，可使用 **外部访问** （联盟）。外部用户无法访问你组织的团队或团队资源。当你想要与仍在使用 Skype for Business（在线或本地）或 Skype （将于2020年年初推出）的组织外部用户进行沟通时，请选择外部访问。</span><span class="sxs-lookup"><span data-stu-id="867d7-p102">Use **external access** (federation) when you need a solution that lets external users in other domains find, call, chat, and set up meetings with you. External users have no access to your organization's teams or team resources. Choose external access when you want to communicate with users outside your organization who are still on Skype for Business (online or on premises) or Skype (coming in early 2020).</span></span> 

<span data-ttu-id="867d7-p103">外部访问在 Teams 中默认为开启，这意味着你的组织可以与所有外部域进行通信。Teams 管理员可以将其关闭或指定要包括（或排除）的域。若要了解更多信息，请参阅[管理外部访问](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="867d7-p103">External access is turned on by default in Teams, which means your org can communicate with all external domains. The Teams admin can turn it off or specify which domains to include (or exclude). To learn more, read [Manage external access](manage-external-access.md).</span></span> 

<span data-ttu-id="867d7-117">如果希望外部用户拥有访问团队和频道的权限，则选择使用[来宾访问](#guest-access)可能是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="867d7-117">If you want external users to have access to teams and channels, [guest access](#guest-access) might be a better way to go.</span></span> 


## <a name="guest-access"></a><span data-ttu-id="867d7-118">来宾访问</span><span class="sxs-lookup"><span data-stu-id="867d7-118">Guest access</span></span>

<span data-ttu-id="867d7-p104">使用 **来宾访问** 将个人用户（无论域）添加到团队中，以便他们可以使用 Microsoft 365 或者 Office 365 应用程序（例如 Word、Excel 或 PowerPoint）就组织文件（存储在 SharePoint 或 OneDrive for Business中）进行聊天、通话、开会和协作。来宾用户可以获得与本地团队成员几乎相同的所有团队功能。要了解更多信息，请阅读 [Teams 中的访客访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="867d7-p104">Use **guest access** to add an individual user (regardless of domain) to a team, where they can chat, call, meet, and collaborate on organization files (stored in SharePoint or OneDrive for Business), using Microsoft 365 or Office 365 apps such as Word, Excel, or PowerPoint. A guest user can be given nearly all the same Teams capabilities as a native team member. To learn more, read [Guest access in Teams](guest-access.md).</span></span>

- <span data-ttu-id="867d7-122">来宾已添加到组织的 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="867d7-122">Guests are added to your organization’s Active Directory.</span></span>
- <span data-ttu-id="867d7-p105">要与访客沟通，访客必须使用他们的访客账户登录到 Teams。这意味着访客可能需要从自己的 Teams 账户中注销才能登录到你的 Teams 账户，如果是同一个账户，则需要切换组织。</span><span class="sxs-lookup"><span data-stu-id="867d7-p105">To communicate with a guest, the guest has to be signed in to Teams using their guest account. This means that a guest may have to sign out of their own Teams account to sign in to your Teams account, or switch organizations if it's the same account.</span></span>
- <span data-ttu-id="867d7-125">与外部访问（联合）用户相比，来宾用户有权访问 Teams 中的更多资源（例如文件、团队和频道）。</span><span class="sxs-lookup"><span data-stu-id="867d7-125">Guest users have access to more resources in Teams - such as files, teams, and channels - than external-access (federated) users.</span></span>
- <span data-ttu-id="867d7-p106">Teams 管理员在 Teams 管理中心中控制来宾可以（或无法）执行的所有操作。要了解更多信息，请阅读[管理访客访问](manage-guests.md)。 </span><span class="sxs-lookup"><span data-stu-id="867d7-p106">The Teams admin controls everything that a guest can (or can’t) do in the Teams admin center. To learn more, read [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="867d7-128">如果你已准备好在组织中启用来宾访问，请从[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)开始。</span><span class="sxs-lookup"><span data-stu-id="867d7-128">If you're ready to turn on guest access in your organization, start with the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>


## <a name="compare-external-and-guest-access"></a><span data-ttu-id="867d7-129">比较外部访问和来宾访问</span><span class="sxs-lookup"><span data-stu-id="867d7-129">Compare external and guest access</span></span>

| <span data-ttu-id="867d7-130">功能</span><span class="sxs-lookup"><span data-stu-id="867d7-130">Feature</span></span> | <span data-ttu-id="867d7-131">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="867d7-131">External access users</span></span> | <span data-ttu-id="867d7-132">来宾访问用户</span><span class="sxs-lookup"><span data-stu-id="867d7-132">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="867d7-133">用户可与其他公司的人聊天</span><span class="sxs-lookup"><span data-stu-id="867d7-133">User can chat with someone in another company</span></span> | <span data-ttu-id="867d7-134">是</span><span class="sxs-lookup"><span data-stu-id="867d7-134">Yes</span></span> |<span data-ttu-id="867d7-135">是</span><span class="sxs-lookup"><span data-stu-id="867d7-135">Yes</span></span> |
| <span data-ttu-id="867d7-136">用户可呼叫其他公司的人员</span><span class="sxs-lookup"><span data-stu-id="867d7-136">User can call someone in another company</span></span> | <span data-ttu-id="867d7-137">是</span><span class="sxs-lookup"><span data-stu-id="867d7-137">Yes</span></span> | <span data-ttu-id="867d7-138">是</span><span class="sxs-lookup"><span data-stu-id="867d7-138">Yes</span></span> |
| <span data-ttu-id="867d7-139">用户可查看其他公司是否有人可供呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="867d7-139">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="867d7-140">是</span><span class="sxs-lookup"><span data-stu-id="867d7-140">Yes</span></span> | <span data-ttu-id="867d7-141">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-141">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="867d7-142">用户可以跨外部租户搜索用户</span><span class="sxs-lookup"><span data-stu-id="867d7-142">User can search for users across external tenants</span></span> | <span data-ttu-id="867d7-143">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-143">Yes<sup>2</sup></span></span> | <span data-ttu-id="867d7-144">否</span><span class="sxs-lookup"><span data-stu-id="867d7-144">No</span></span> |
| <span data-ttu-id="867d7-145">用户可以共享文件</span><span class="sxs-lookup"><span data-stu-id="867d7-145">User can share files</span></span> | <span data-ttu-id="867d7-146">否</span><span class="sxs-lookup"><span data-stu-id="867d7-146">No</span></span> | <span data-ttu-id="867d7-147">是</span><span class="sxs-lookup"><span data-stu-id="867d7-147">Yes</span></span> |
| <span data-ttu-id="867d7-148">用户可访问 Teams 资源</span><span class="sxs-lookup"><span data-stu-id="867d7-148">User can access Teams resources</span></span> | <span data-ttu-id="867d7-149">否</span><span class="sxs-lookup"><span data-stu-id="867d7-149">No</span></span> | <span data-ttu-id="867d7-150">是</span><span class="sxs-lookup"><span data-stu-id="867d7-150">Yes</span></span> |
| <span data-ttu-id="867d7-151">可将用户添加到群聊</span><span class="sxs-lookup"><span data-stu-id="867d7-151">User can be added to a group chat</span></span> | <span data-ttu-id="867d7-152">否</span><span class="sxs-lookup"><span data-stu-id="867d7-152">No</span></span> | <span data-ttu-id="867d7-153">是</span><span class="sxs-lookup"><span data-stu-id="867d7-153">Yes</span></span> |
| <span data-ttu-id="867d7-154">可邀请用户加入会议</span><span class="sxs-lookup"><span data-stu-id="867d7-154">User can be invited to a meeting</span></span> | <span data-ttu-id="867d7-155">是</span><span class="sxs-lookup"><span data-stu-id="867d7-155">Yes</span></span> | <span data-ttu-id="867d7-156">是</span><span class="sxs-lookup"><span data-stu-id="867d7-156">Yes</span></span> |
| <span data-ttu-id="867d7-157">可以将其他用户添加到与外部用户的聊天中</span><span class="sxs-lookup"><span data-stu-id="867d7-157">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="867d7-158">否<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-158">No<sup>3</sup></span></span> | <span data-ttu-id="867d7-159">不适用</span><span class="sxs-lookup"><span data-stu-id="867d7-159">N/A</span></span> |
| <span data-ttu-id="867d7-160">用户被标识为外部方</span><span class="sxs-lookup"><span data-stu-id="867d7-160">User is identified as an external party</span></span> | <span data-ttu-id="867d7-161">是</span><span class="sxs-lookup"><span data-stu-id="867d7-161">Yes</span></span> | <span data-ttu-id="867d7-162">是</span><span class="sxs-lookup"><span data-stu-id="867d7-162">Yes</span></span> |
| <span data-ttu-id="867d7-163">将显示状态</span><span class="sxs-lookup"><span data-stu-id="867d7-163">Presence is displayed</span></span> | <span data-ttu-id="867d7-164">是</span><span class="sxs-lookup"><span data-stu-id="867d7-164">Yes</span></span> | <span data-ttu-id="867d7-165">是</span><span class="sxs-lookup"><span data-stu-id="867d7-165">Yes</span></span> |
| <span data-ttu-id="867d7-166">将显示外出消息</span><span class="sxs-lookup"><span data-stu-id="867d7-166">Out of office message is shown</span></span> | <span data-ttu-id="867d7-167">否</span><span class="sxs-lookup"><span data-stu-id="867d7-167">No</span></span> | <span data-ttu-id="867d7-168">是</span><span class="sxs-lookup"><span data-stu-id="867d7-168">Yes</span></span> |
| <span data-ttu-id="867d7-169">可阻止单个用户</span><span class="sxs-lookup"><span data-stu-id="867d7-169">Individual user can be blocked</span></span> | <span data-ttu-id="867d7-170">否</span><span class="sxs-lookup"><span data-stu-id="867d7-170">No</span></span> | <span data-ttu-id="867d7-171">是</span><span class="sxs-lookup"><span data-stu-id="867d7-171">Yes</span></span> |
| <span data-ttu-id="867d7-172">支持 @提及</span><span class="sxs-lookup"><span data-stu-id="867d7-172">@mentions are supported</span></span> | <span data-ttu-id="867d7-173">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-173">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-174">是</span><span class="sxs-lookup"><span data-stu-id="867d7-174">Yes</span></span> |
| <span data-ttu-id="867d7-175">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="867d7-175">Make private calls</span></span> | <span data-ttu-id="867d7-176">是</span><span class="sxs-lookup"><span data-stu-id="867d7-176">Yes</span></span> | <span data-ttu-id="867d7-177">是</span><span class="sxs-lookup"><span data-stu-id="867d7-177">Yes</span></span> |
| <span data-ttu-id="867d7-178">查看适用于拨入会议参加者的电话号码</span><span class="sxs-lookup"><span data-stu-id="867d7-178">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="867d7-179">否<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-179">No<sup>5</sup></span></span> | <span data-ttu-id="867d7-180">是</span><span class="sxs-lookup"><span data-stu-id="867d7-180">Yes</span></span> |
| <span data-ttu-id="867d7-181">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="867d7-181">Allow IP video</span></span> | <span data-ttu-id="867d7-182">是</span><span class="sxs-lookup"><span data-stu-id="867d7-182">Yes</span></span> | <span data-ttu-id="867d7-183">是</span><span class="sxs-lookup"><span data-stu-id="867d7-183">Yes</span></span> |
| <span data-ttu-id="867d7-184">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="867d7-184">Screen sharing mode</span></span> | <span data-ttu-id="867d7-185">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-185">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-186">是</span><span class="sxs-lookup"><span data-stu-id="867d7-186">Yes</span></span> |
| <span data-ttu-id="867d7-187">允许立即召开会议</span><span class="sxs-lookup"><span data-stu-id="867d7-187">Allow meet now</span></span> | <span data-ttu-id="867d7-188">否</span><span class="sxs-lookup"><span data-stu-id="867d7-188">No</span></span> | <span data-ttu-id="867d7-189">是</span><span class="sxs-lookup"><span data-stu-id="867d7-189">Yes</span></span> |
| <span data-ttu-id="867d7-190">编辑已发送的消息</span><span class="sxs-lookup"><span data-stu-id="867d7-190">Edit sent messages</span></span> | <span data-ttu-id="867d7-191">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-191">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-192">是</span><span class="sxs-lookup"><span data-stu-id="867d7-192">Yes</span></span> |
| <span data-ttu-id="867d7-193">可以删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="867d7-193">Can delete sent messages</span></span> | <span data-ttu-id="867d7-194">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-194">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-195">是</span><span class="sxs-lookup"><span data-stu-id="867d7-195">Yes</span></span> |
| <span data-ttu-id="867d7-196">在对话中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="867d7-196">Use Giphy in conversation</span></span> | <span data-ttu-id="867d7-197">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-197">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-198">是</span><span class="sxs-lookup"><span data-stu-id="867d7-198">Yes</span></span> |
| <span data-ttu-id="867d7-199">在对话中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="867d7-199">Use memes in conversation</span></span> | <span data-ttu-id="867d7-200">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-200">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-201">是</span><span class="sxs-lookup"><span data-stu-id="867d7-201">Yes</span></span> |
| <span data-ttu-id="867d7-202">在对话中使用贴纸</span><span class="sxs-lookup"><span data-stu-id="867d7-202">Use stickers in conversation</span></span> | <span data-ttu-id="867d7-203">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="867d7-203">Yes<sup>4</sup></span></span> | <span data-ttu-id="867d7-204">是</span><span class="sxs-lookup"><span data-stu-id="867d7-204">Yes</span></span> |
||||

<span data-ttu-id="867d7-205"><sup>1</sup> 前提是已将用户添加为来宾，并且已作为来宾登录到来宾租户。</span><span class="sxs-lookup"><span data-stu-id="867d7-205"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="867d7-206"><sup>2</sup> 仅通过电子邮件或会话初始协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="867d7-206"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="867d7-207"><sup>3</sup> 外部（联合）聊天仅可为一对一。</span><span class="sxs-lookup"><span data-stu-id="867d7-207"><sup>3</sup> External (federated) chat is 1:1 only.</span></span><br>
<span data-ttu-id="867d7-208"><sup>4</sup> 支持来自两个不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。</span><span class="sxs-lookup"><span data-stu-id="867d7-208"><sup>4</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="867d7-p107"><sup>5</sup> 默认情况下，外部参与者无法看到已拨入的参与者的电话号码。如果想要维持这些电话号码的隐私，请选择 **进入/退出公告类型** （这会阻止Teams读取号码）的 **音调**。若要了解更多详细信息，请参阅 [在Microsoft Teams中打开或关闭会议的进入和退出公告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="867d7-p107"><sup>5</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="867d7-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="867d7-212">Related topics</span></span>

[<span data-ttu-id="867d7-213">Teams 中的外部访问</span><span class="sxs-lookup"><span data-stu-id="867d7-213">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="867d7-214">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="867d7-214">Guest access in Teams</span></span>](guest-access.md)

