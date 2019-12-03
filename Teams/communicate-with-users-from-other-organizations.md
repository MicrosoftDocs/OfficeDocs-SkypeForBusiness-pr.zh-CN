---
title: 与 Microsoft Teams 中其他组织的用户通信
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 了解如何使用外部访问（联合身份验证）和来宾访问，与 Microsoft Teams 中其他组织的用户进行通信。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 39fa50868b60ce78da360d97a2fad5dff9fee09b
ms.sourcegitcommit: 486eaa85042670edec2231efaf7dae8fa329e852
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2019
ms.locfileid: "39665445"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a><span data-ttu-id="87556-103">与 Microsoft Teams 中其他组织的用户通信</span><span class="sxs-lookup"><span data-stu-id="87556-103">Communicate with users from other organizations in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="87556-104">当需要与组织外部的人员进行通信和协作时，Microsoft Teams 为你提供了两种不同的方法来实现这一目的。</span><span class="sxs-lookup"><span data-stu-id="87556-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams gives you two different ways to make that happen.</span></span> <span data-ttu-id="87556-105">第一个 – **外部访问**（联合身份验证）– 可用于查找、呼叫和与其他域（例如 contoso.com）中的用户进行聊天。</span><span class="sxs-lookup"><span data-stu-id="87556-105">The first – **external access** (federation) – lets  you find, call, and chat with users in other domains (for example, contoso.com).</span></span> <span data-ttu-id="87556-106">第二个 – **来宾访问** – 允许你使用个人的电子邮件地址将其作为来宾添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="87556-106">The second – **guest access** – lets you add individuals to your teams, as guests, using their email address.</span></span> <span data-ttu-id="87556-107">你可以像与组织中的其他任何用户一样与来宾协作。</span><span class="sxs-lookup"><span data-stu-id="87556-107">You can collaborate with guests as you would with any other users in your organization.</span></span>

<span data-ttu-id="87556-108">如果需要，可同时使用外部访问和来宾访问（它们彼此之间不相排斥）。</span><span class="sxs-lookup"><span data-stu-id="87556-108">You can use both external access and guest access if you want - one doesn't preclude the other.</span></span>

<span data-ttu-id="87556-109">下面大体介绍了选择方法（要进行详细比较，请跳转到[比较外部和来宾访问](#compare-external-and-guest-access)）：</span><span class="sxs-lookup"><span data-stu-id="87556-109">At a high level, here’s how to choose (for a detailed comparison, jump down to [Compare external and guest access](#compare-external-and-guest-access)):</span></span>

## <a name="external-access"></a><span data-ttu-id="87556-110">外部访问</span><span class="sxs-lookup"><span data-stu-id="87556-110">External access</span></span>

<span data-ttu-id="87556-111">当需要允许其他域中的外部用户查找、呼叫你、与你聊天和安排会议的解决方案时，可使用**外部访问**（联合身份验证）。</span><span class="sxs-lookup"><span data-stu-id="87556-111">Use **external access** (federation) when you need a solution that lets external users in other domains find, call, chat, and set up meetings with you.</span></span> <span data-ttu-id="87556-112">外部用户无权访问贵组织的团队或团队资源。</span><span class="sxs-lookup"><span data-stu-id="87556-112">External users have no access to your organization's teams or team resources.</span></span> <span data-ttu-id="87556-113">当你要与仍在 Skype for Business（在线或本地）或 Skype（将在 2020 年初推出）上的外部用户进行通信时，请选择外部访问。</span><span class="sxs-lookup"><span data-stu-id="87556-113">Choose external access when you want to communicate with external users who are still on Skype for Business (online or on premises) or Skype (coming in early 2020).</span></span> 

<span data-ttu-id="87556-114">默认情况下，Teams 中的外部访问处于启用状态，这意味着你的组织可以与所有外部域进行通信。</span><span class="sxs-lookup"><span data-stu-id="87556-114">External access is turned on by default in Teams, which means your org can communicate with all external domains.</span></span> <span data-ttu-id="87556-115">Teams 管理员可以将其关闭，也可以指定要包含（或排除）的域。</span><span class="sxs-lookup"><span data-stu-id="87556-115">The Teams admin can turn it off or specify which domains to include (or exclude).</span></span> <span data-ttu-id="87556-116">要了解详细信息，请参阅[管理外部访问](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="87556-116">To learn more, read [Manage external access](manage-external-access.md).</span></span> 

<span data-ttu-id="87556-117">如果希望外部用户拥有访问团队和频道的权限，则选择使用[来宾访问](#guest-access)可能是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="87556-117">If you want external users to have access to teams and channels, [guest access](#guest-access) might be a better way to go.</span></span> 


## <a name="guest-access"></a><span data-ttu-id="87556-118">来宾访问</span><span class="sxs-lookup"><span data-stu-id="87556-118">Guest access</span></span>

<span data-ttu-id="87556-119">使用**来宾访问**将单个用户（无论来自哪个域）添加到团队，以便他们可以聊天、呼叫、召开会议和使用 Office 365 应用（如 Word、Excel 或 PowerPoint）就组织文件（存储在 SharePoint 或 OneDrive for Business）进行协作。</span><span class="sxs-lookup"><span data-stu-id="87556-119">Use **guest access** to add an individual user (regardless of domain) to a team, where they can chat, call, meet, and collaborate on organization files (stored in SharePoint or OneDrive for Business), using Office 365 apps such as Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="87556-120">可以为来宾用户提供与本机团队成员几乎所有相同的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="87556-120">A guest user can be given nearly all the same Teams capabilities as a native team member.</span></span> <span data-ttu-id="87556-121">要了解详细信息，请阅读 [Teams 中的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="87556-121">To learn more, read [Guest access in Teams](guest-access.md).</span></span>

- <span data-ttu-id="87556-122">来宾已添加到组织的 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="87556-122">Guests are added to your organization’s Active Directory.</span></span>
- <span data-ttu-id="87556-123">要与来宾通信，来宾必须使用其来宾帐户登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="87556-123">To communicate with a guest, the guest has to be signed in to Teams using their guest account.</span></span> <span data-ttu-id="87556-124">这意味着，来宾可能必须注销自己的 Teams 帐户才能登录到 Teams 帐户。</span><span class="sxs-lookup"><span data-stu-id="87556-124">This means that a guest may have to sign out of their own Teams account to sign in to your Teams account.</span></span>
- <span data-ttu-id="87556-125">与外部访问（联合）用户相比，来宾用户有权访问 Teams 中的更多资源（例如文件、团队和频道）。</span><span class="sxs-lookup"><span data-stu-id="87556-125">Guest users have access to more resources in Teams - such as files, teams, and channels - than external-access (federated) users.</span></span>
- <span data-ttu-id="87556-126">Teams 管理员在 Teams 管理中心中控制来宾可以（或不可）执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="87556-126">The Teams admin controls everything that a guest can (or can’t) do in the Teams admin center.</span></span> <span data-ttu-id="87556-127">要了解详细信息，请阅读[管理来宾访问](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="87556-127">To learn more, read [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="87556-128">如果你已准备好在组织中启用来宾访问，请从[来宾访问清单](guest-access-checklist.md)开始。</span><span class="sxs-lookup"><span data-stu-id="87556-128">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>


## <a name="compare-external-and-guest-access"></a><span data-ttu-id="87556-129">比较外部访问和来宾访问</span><span class="sxs-lookup"><span data-stu-id="87556-129">Compare external and guest access</span></span>

| <span data-ttu-id="87556-130">功能</span><span class="sxs-lookup"><span data-stu-id="87556-130">Feature</span></span> | <span data-ttu-id="87556-131">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="87556-131">External access users</span></span> | <span data-ttu-id="87556-132">来宾访问用户</span><span class="sxs-lookup"><span data-stu-id="87556-132">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="87556-133">用户可与其他公司的人聊天</span><span class="sxs-lookup"><span data-stu-id="87556-133">User can chat with someone in another company</span></span> | <span data-ttu-id="87556-134">是</span><span class="sxs-lookup"><span data-stu-id="87556-134">Yes</span></span> |<span data-ttu-id="87556-135">是</span><span class="sxs-lookup"><span data-stu-id="87556-135">Yes</span></span> |
| <span data-ttu-id="87556-136">用户可呼叫其他公司的人员</span><span class="sxs-lookup"><span data-stu-id="87556-136">User can call someone in another company</span></span> | <span data-ttu-id="87556-137">是</span><span class="sxs-lookup"><span data-stu-id="87556-137">Yes</span></span> | <span data-ttu-id="87556-138">是</span><span class="sxs-lookup"><span data-stu-id="87556-138">Yes</span></span> |
| <span data-ttu-id="87556-139">用户可查看其他公司是否有人可供呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="87556-139">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="87556-140">是</span><span class="sxs-lookup"><span data-stu-id="87556-140">Yes</span></span> | <span data-ttu-id="87556-141">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="87556-141">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="87556-142">用户可以跨外部租户搜索用户</span><span class="sxs-lookup"><span data-stu-id="87556-142">User can search for users across external tenants</span></span> | <span data-ttu-id="87556-143">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="87556-143">Yes<sup>2</sup></span></span> | <span data-ttu-id="87556-144">否</span><span class="sxs-lookup"><span data-stu-id="87556-144">No</span></span> |
| <span data-ttu-id="87556-145">用户可以共享文件</span><span class="sxs-lookup"><span data-stu-id="87556-145">User can share files</span></span> | <span data-ttu-id="87556-146">否</span><span class="sxs-lookup"><span data-stu-id="87556-146">No</span></span> | <span data-ttu-id="87556-147">是</span><span class="sxs-lookup"><span data-stu-id="87556-147">Yes</span></span> |
| <span data-ttu-id="87556-148">用户可访问 Teams 资源</span><span class="sxs-lookup"><span data-stu-id="87556-148">User can access Teams resources</span></span> | <span data-ttu-id="87556-149">否</span><span class="sxs-lookup"><span data-stu-id="87556-149">No</span></span> | <span data-ttu-id="87556-150">是</span><span class="sxs-lookup"><span data-stu-id="87556-150">Yes</span></span> |
| <span data-ttu-id="87556-151">可将用户添加到群聊</span><span class="sxs-lookup"><span data-stu-id="87556-151">User can be added to a group chat</span></span> | <span data-ttu-id="87556-152">否</span><span class="sxs-lookup"><span data-stu-id="87556-152">No</span></span> | <span data-ttu-id="87556-153">是</span><span class="sxs-lookup"><span data-stu-id="87556-153">Yes</span></span> |
| <span data-ttu-id="87556-154">可邀请用户加入会议</span><span class="sxs-lookup"><span data-stu-id="87556-154">User can be invited to a meeting</span></span> | <span data-ttu-id="87556-155">是</span><span class="sxs-lookup"><span data-stu-id="87556-155">Yes</span></span> | <span data-ttu-id="87556-156">是</span><span class="sxs-lookup"><span data-stu-id="87556-156">Yes</span></span> |
| <span data-ttu-id="87556-157">可以将其他用户添加到与外部用户的聊天中</span><span class="sxs-lookup"><span data-stu-id="87556-157">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="87556-158">否<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="87556-158">No<sup>3</sup></span></span> | <span data-ttu-id="87556-159">不适用</span><span class="sxs-lookup"><span data-stu-id="87556-159">N/A</span></span> |
| <span data-ttu-id="87556-160">用户被标识为外部方</span><span class="sxs-lookup"><span data-stu-id="87556-160">User is identified as an external party</span></span> | <span data-ttu-id="87556-161">是</span><span class="sxs-lookup"><span data-stu-id="87556-161">Yes</span></span> | <span data-ttu-id="87556-162">是</span><span class="sxs-lookup"><span data-stu-id="87556-162">Yes</span></span> |
| <span data-ttu-id="87556-163">将显示状态</span><span class="sxs-lookup"><span data-stu-id="87556-163">Presence is displayed</span></span> | <span data-ttu-id="87556-164">是</span><span class="sxs-lookup"><span data-stu-id="87556-164">Yes</span></span> | <span data-ttu-id="87556-165">是</span><span class="sxs-lookup"><span data-stu-id="87556-165">Yes</span></span> |
| <span data-ttu-id="87556-166">将显示外出消息</span><span class="sxs-lookup"><span data-stu-id="87556-166">Out of office message is shown</span></span> | <span data-ttu-id="87556-167">否</span><span class="sxs-lookup"><span data-stu-id="87556-167">No</span></span> | <span data-ttu-id="87556-168">是</span><span class="sxs-lookup"><span data-stu-id="87556-168">Yes</span></span> |
| <span data-ttu-id="87556-169">可阻止单个用户</span><span class="sxs-lookup"><span data-stu-id="87556-169">Individual user can be blocked</span></span> | <span data-ttu-id="87556-170">否</span><span class="sxs-lookup"><span data-stu-id="87556-170">No</span></span> | <span data-ttu-id="87556-171">是</span><span class="sxs-lookup"><span data-stu-id="87556-171">Yes</span></span> |
| <span data-ttu-id="87556-172">支持 @提及</span><span class="sxs-lookup"><span data-stu-id="87556-172">@mentions are supported</span></span> | <span data-ttu-id="87556-173">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-173">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-174">是</span><span class="sxs-lookup"><span data-stu-id="87556-174">Yes</span></span> |
| <span data-ttu-id="87556-175">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="87556-175">Make private calls</span></span> | <span data-ttu-id="87556-176">是</span><span class="sxs-lookup"><span data-stu-id="87556-176">Yes</span></span> | <span data-ttu-id="87556-177">是</span><span class="sxs-lookup"><span data-stu-id="87556-177">Yes</span></span> |
| <span data-ttu-id="87556-178">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87556-178">Allow IP video</span></span> | <span data-ttu-id="87556-179">是</span><span class="sxs-lookup"><span data-stu-id="87556-179">Yes</span></span> | <span data-ttu-id="87556-180">是</span><span class="sxs-lookup"><span data-stu-id="87556-180">Yes</span></span> |
| <span data-ttu-id="87556-181">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87556-181">Screen sharing mode</span></span> | <span data-ttu-id="87556-182">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-182">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-183">是</span><span class="sxs-lookup"><span data-stu-id="87556-183">Yes</span></span> |
| <span data-ttu-id="87556-184">允许立即召开会议</span><span class="sxs-lookup"><span data-stu-id="87556-184">Allow meet now</span></span> | <span data-ttu-id="87556-185">否</span><span class="sxs-lookup"><span data-stu-id="87556-185">No</span></span> | <span data-ttu-id="87556-186">是</span><span class="sxs-lookup"><span data-stu-id="87556-186">Yes</span></span> |
| <span data-ttu-id="87556-187">编辑已发送的消息</span><span class="sxs-lookup"><span data-stu-id="87556-187">Edit sent messages</span></span> | <span data-ttu-id="87556-188">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-188">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-189">是</span><span class="sxs-lookup"><span data-stu-id="87556-189">Yes</span></span> |
| <span data-ttu-id="87556-190">可以删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="87556-190">Can delete sent messages</span></span> | <span data-ttu-id="87556-191">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-191">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-192">是</span><span class="sxs-lookup"><span data-stu-id="87556-192">Yes</span></span> |
| <span data-ttu-id="87556-193">在对话中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="87556-193">Use Giphy in conversation</span></span> | <span data-ttu-id="87556-194">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-194">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-195">是</span><span class="sxs-lookup"><span data-stu-id="87556-195">Yes</span></span> |
| <span data-ttu-id="87556-196">在对话中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="87556-196">Use memes in conversation</span></span> | <span data-ttu-id="87556-197">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-197">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-198">是</span><span class="sxs-lookup"><span data-stu-id="87556-198">Yes</span></span> |
| <span data-ttu-id="87556-199">在对话中使用贴纸</span><span class="sxs-lookup"><span data-stu-id="87556-199">Use stickers in conversation</span></span> | <span data-ttu-id="87556-200">是<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="87556-200">Yes<sup>4</sup></span></span> | <span data-ttu-id="87556-201">是</span><span class="sxs-lookup"><span data-stu-id="87556-201">Yes</span></span> |
||||

<span data-ttu-id="87556-202"><sup>1</sup> 前提是已将用户添加为来宾，并且已作为来宾登录到来宾租户。</span><span class="sxs-lookup"><span data-stu-id="87556-202"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="87556-203"><sup>2</sup> 仅通过电子邮件或会话初始协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="87556-203"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="87556-204"><sup>3</sup> 外部（联合）聊天仅可为一对一。</span><span class="sxs-lookup"><span data-stu-id="87556-204"><sup>3</sup> External (federated) chat is 1:1 only.</span></span><br>
<span data-ttu-id="87556-205"><sup>4</sup> 支持来自两个不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。</span><span class="sxs-lookup"><span data-stu-id="87556-205"><sup>4</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <span data-ttu-id="87556-206">*这是预览版或早期版本功能。*</span><span class="sxs-lookup"><span data-stu-id="87556-206">*This is a preview or early release feature.*</span></span>

## <a name="related-topics"></a><span data-ttu-id="87556-207">相关主题</span><span class="sxs-lookup"><span data-stu-id="87556-207">Related topics</span></span>

[<span data-ttu-id="87556-208">Teams 中的外部访问</span><span class="sxs-lookup"><span data-stu-id="87556-208">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="87556-209">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="87556-209">Guest access in Teams</span></span>](guest-access.md)

