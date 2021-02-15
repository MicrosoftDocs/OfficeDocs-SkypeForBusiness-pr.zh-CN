---
title: 与其他组织中的用户通话和聊天
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: 了解如何使用外部访问（联盟）和来宾访问在 Microsoft Teams 中与组织外部的人员进行通话和聊天以及查找和添加这些人员。
ms.openlocfilehash: 5c5eecf5ceb2228f981a7cd06b52f3b5a1b787d7
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145830"
---
# <a name="call-chat-and-collaborate-with-people-outside-your-organization-in-microsoft-teams"></a><span data-ttu-id="784bd-103">在 Microsoft Teams 中与组织外部的人员通话、聊天和协作</span><span class="sxs-lookup"><span data-stu-id="784bd-103">Call, chat, and collaborate with people outside your organization in Microsoft Teams</span></span>

<span data-ttu-id="784bd-104">当需要与组织外部的人员进行通信和协作时，Microsoft Teams 可为你提供两种选择：</span><span class="sxs-lookup"><span data-stu-id="784bd-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="784bd-105">**外部访问** - 一种联盟，允许用户查找其他组织中的人员以及与其通话和聊天。</span><span class="sxs-lookup"><span data-stu-id="784bd-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="784bd-106">除非作为来宾受到邀请，否则这些人员无法添加到团队。</span><span class="sxs-lookup"><span data-stu-id="784bd-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="784bd-107">**来宾访问** - 来宾访问允许邀请组织外部人员加入团队。</span><span class="sxs-lookup"><span data-stu-id="784bd-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="784bd-108">受邀人员将在 Azure Active Directory 中获得来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="784bd-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="784bd-109">请注意，Teams 允许邀请组织外部人员参加会议。</span><span class="sxs-lookup"><span data-stu-id="784bd-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="784bd-110">这不需要配置外部或来宾访问。</span><span class="sxs-lookup"><span data-stu-id="784bd-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="784bd-111">外部访问（联盟）</span><span class="sxs-lookup"><span data-stu-id="784bd-111">External access (federation)</span></span>

<span data-ttu-id="784bd-112">针对组织外部使用 Teams、Skype for Business（联机或本地）或 Skype 的人员，如果需要查找此类人员、与其通话和聊天以及设置与此类人员的会议，可设置外部访问。</span><span class="sxs-lookup"><span data-stu-id="784bd-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="784bd-113">默认情况下，将针对所有域启用外部访问。</span><span class="sxs-lookup"><span data-stu-id="784bd-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="784bd-114">你可以通过允许或阻止特定域或者通过关闭该设置来限制外部访问。</span><span class="sxs-lookup"><span data-stu-id="784bd-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![外部访问设置的屏幕截图](media/external-access-federation-settings.png)

<span data-ttu-id="784bd-116">若要配置外部访问，请参阅[管理外部访问](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="784bd-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

## <a name="guest-access"></a><span data-ttu-id="784bd-117">来宾访问</span><span class="sxs-lookup"><span data-stu-id="784bd-117">Guest access</span></span>

<span data-ttu-id="784bd-118">使用来宾访问将组织外部人员添加到团队，他们可在其中聊天、通话、开会和协作处理文件。</span><span class="sxs-lookup"><span data-stu-id="784bd-118">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="784bd-119">来宾可以获得几乎与本地团队成员相同的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="784bd-119">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="784bd-120">来宾将作为 B2B 用户添加到组织的 Azure Active Directory，且必须使用他们的来宾帐户登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="784bd-120">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="784bd-121">这意味着，他们可能需要从自己的组织注销才能登录到你的组织。</span><span class="sxs-lookup"><span data-stu-id="784bd-121">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="784bd-122">若要为 Teams 配置来宾访问，请参阅[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="784bd-122">To configure guest access for Teams, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="784bd-123">比较外部访问和来宾访问</span><span class="sxs-lookup"><span data-stu-id="784bd-123">Compare external and guest access</span></span>

<span data-ttu-id="784bd-124">下表显示了使用外部访问（联盟）和来宾访问的区别。</span><span class="sxs-lookup"><span data-stu-id="784bd-124">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="784bd-125">在这两种情况下，组织外部人员均被标识为外部用户。</span><span class="sxs-lookup"><span data-stu-id="784bd-125">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="784bd-126">你的用户可以进行的一些操作</span><span class="sxs-lookup"><span data-stu-id="784bd-126">Things your users can do</span></span>

| <span data-ttu-id="784bd-127">用户可以</span><span class="sxs-lookup"><span data-stu-id="784bd-127">Users can</span></span> | <span data-ttu-id="784bd-128">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="784bd-128">External access users</span></span> | <span data-ttu-id="784bd-129">来宾</span><span class="sxs-lookup"><span data-stu-id="784bd-129">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="784bd-130">与其他组织中的人聊天</span><span class="sxs-lookup"><span data-stu-id="784bd-130">Chat with someone in another organization</span></span> | <span data-ttu-id="784bd-131">是</span><span class="sxs-lookup"><span data-stu-id="784bd-131">Yes</span></span> | <span data-ttu-id="784bd-132">是</span><span class="sxs-lookup"><span data-stu-id="784bd-132">Yes</span></span> |
| <span data-ttu-id="784bd-133">呼叫其他组织中的人</span><span class="sxs-lookup"><span data-stu-id="784bd-133">Call someone in another organization</span></span> | <span data-ttu-id="784bd-134">是</span><span class="sxs-lookup"><span data-stu-id="784bd-134">Yes</span></span> | <span data-ttu-id="784bd-135">是</span><span class="sxs-lookup"><span data-stu-id="784bd-135">Yes</span></span> |
| <span data-ttu-id="784bd-136">查看其他组织中的人是否可接受呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="784bd-136">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="784bd-137">是</span><span class="sxs-lookup"><span data-stu-id="784bd-137">Yes</span></span> | <span data-ttu-id="784bd-138">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-138">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="784bd-139">搜索其他组织中的人员</span><span class="sxs-lookup"><span data-stu-id="784bd-139">Search for people in other organizations</span></span> | <span data-ttu-id="784bd-140">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-140">Yes<sup>2</sup></span></span> | <span data-ttu-id="784bd-141">否</span><span class="sxs-lookup"><span data-stu-id="784bd-141">No</span></span> |
| <span data-ttu-id="784bd-142">共享文件</span><span class="sxs-lookup"><span data-stu-id="784bd-142">Share files</span></span> | <span data-ttu-id="784bd-143">否</span><span class="sxs-lookup"><span data-stu-id="784bd-143">No</span></span> | <span data-ttu-id="784bd-144">是</span><span class="sxs-lookup"><span data-stu-id="784bd-144">Yes</span></span> |
| <span data-ttu-id="784bd-145">查看以下人员的外出消息</span><span class="sxs-lookup"><span data-stu-id="784bd-145">See the out-of-office message of</span></span> | <span data-ttu-id="784bd-146">否</span><span class="sxs-lookup"><span data-stu-id="784bd-146">No</span></span> | <span data-ttu-id="784bd-147">是</span><span class="sxs-lookup"><span data-stu-id="784bd-147">Yes</span></span> |
| <span data-ttu-id="784bd-148">阻止其他组织中的人</span><span class="sxs-lookup"><span data-stu-id="784bd-148">Block someone in another organization someone in another organization</span></span> | <span data-ttu-id="784bd-149">否</span><span class="sxs-lookup"><span data-stu-id="784bd-149">No</span></span> | <span data-ttu-id="784bd-150">是</span><span class="sxs-lookup"><span data-stu-id="784bd-150">Yes</span></span> |
| <span data-ttu-id="784bd-151">使用 @提及</span><span class="sxs-lookup"><span data-stu-id="784bd-151">Use @mentions</span></span> | <span data-ttu-id="784bd-152">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-152">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-153">是</span><span class="sxs-lookup"><span data-stu-id="784bd-153">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="784bd-154">组织外部的人员可以进行的一些操作</span><span class="sxs-lookup"><span data-stu-id="784bd-154">Things people outside your organization can do</span></span>

| <span data-ttu-id="784bd-155">组织外部的人员可以</span><span class="sxs-lookup"><span data-stu-id="784bd-155">People outside your organization can</span></span> | <span data-ttu-id="784bd-156">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="784bd-156">External access users</span></span> | <span data-ttu-id="784bd-157">来宾</span><span class="sxs-lookup"><span data-stu-id="784bd-157">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="784bd-158">访问 Teams 资源</span><span class="sxs-lookup"><span data-stu-id="784bd-158">Access Teams resources</span></span> | <span data-ttu-id="784bd-159">否</span><span class="sxs-lookup"><span data-stu-id="784bd-159">No</span></span> | <span data-ttu-id="784bd-160">是</span><span class="sxs-lookup"><span data-stu-id="784bd-160">Yes</span></span> |
| <span data-ttu-id="784bd-161">被添加到群聊</span><span class="sxs-lookup"><span data-stu-id="784bd-161">Be added to a group chat</span></span> | <span data-ttu-id="784bd-162">否</span><span class="sxs-lookup"><span data-stu-id="784bd-162">No</span></span> | <span data-ttu-id="784bd-163">是</span><span class="sxs-lookup"><span data-stu-id="784bd-163">Yes</span></span> |
| <span data-ttu-id="784bd-164">受邀加入会议</span><span class="sxs-lookup"><span data-stu-id="784bd-164">Be invited to a meeting</span></span> | <span data-ttu-id="784bd-165">是</span><span class="sxs-lookup"><span data-stu-id="784bd-165">Yes</span></span> | <span data-ttu-id="784bd-166">是</span><span class="sxs-lookup"><span data-stu-id="784bd-166">Yes</span></span> |
| <span data-ttu-id="784bd-167">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="784bd-167">Make private calls</span></span> | <span data-ttu-id="784bd-168">是</span><span class="sxs-lookup"><span data-stu-id="784bd-168">Yes</span></span> | <span data-ttu-id="784bd-169">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-169">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-170">查看拨入会议参与者的电话号码</span><span class="sxs-lookup"><span data-stu-id="784bd-170">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="784bd-171">否<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-171">No<sup>4</sup></span></span> | <span data-ttu-id="784bd-172">是</span><span class="sxs-lookup"><span data-stu-id="784bd-172">Yes</span></span> |
| <span data-ttu-id="784bd-173">使用 IP 视频</span><span class="sxs-lookup"><span data-stu-id="784bd-173">Use IP video</span></span> | <span data-ttu-id="784bd-174">是</span><span class="sxs-lookup"><span data-stu-id="784bd-174">Yes</span></span> | <span data-ttu-id="784bd-175">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-175">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-176">使用屏幕共享</span><span class="sxs-lookup"><span data-stu-id="784bd-176">Use screen sharing</span></span> | <span data-ttu-id="784bd-177">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-177">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-178">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-178">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-179">使用立即开会</span><span class="sxs-lookup"><span data-stu-id="784bd-179">Use meet now</span></span> | <span data-ttu-id="784bd-180">否</span><span class="sxs-lookup"><span data-stu-id="784bd-180">No</span></span> | <span data-ttu-id="784bd-181">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-181">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-182">编辑已发送的消息</span><span class="sxs-lookup"><span data-stu-id="784bd-182">Edit sent messages</span></span> | <span data-ttu-id="784bd-183">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-183">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-184">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-185">删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="784bd-185">Delete sent messages</span></span> | <span data-ttu-id="784bd-186">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-186">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-187">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-188">在对话中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="784bd-188">Use Giphy in conversation</span></span> | <span data-ttu-id="784bd-189">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-189">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-190">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-191">在对话中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="784bd-191">Use memes in conversation</span></span> | <span data-ttu-id="784bd-192">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-192">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-193">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-193">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-194">在对话中使用贴纸</span><span class="sxs-lookup"><span data-stu-id="784bd-194">Use stickers in conversation</span></span> | <span data-ttu-id="784bd-195">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-195">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-196">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-196">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="784bd-197">将显示状态</span><span class="sxs-lookup"><span data-stu-id="784bd-197">Presence is displayed</span></span> | <span data-ttu-id="784bd-198">是</span><span class="sxs-lookup"><span data-stu-id="784bd-198">Yes</span></span> | <span data-ttu-id="784bd-199">是</span><span class="sxs-lookup"><span data-stu-id="784bd-199">Yes</span></span> |
| <span data-ttu-id="784bd-200">使用 @提及</span><span class="sxs-lookup"><span data-stu-id="784bd-200">Use @mentions</span></span> | <span data-ttu-id="784bd-201">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="784bd-201">Yes<sup>3</sup></span></span> | <span data-ttu-id="784bd-202">是</span><span class="sxs-lookup"><span data-stu-id="784bd-202">Yes</span></span> |

<br>

<span data-ttu-id="784bd-203"><sup>1</sup> 前提是已将用户添加为来宾，并且对方已使用来宾帐户登录。</span><span class="sxs-lookup"><span data-stu-id="784bd-203"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="784bd-204"><sup>2</sup> 仅通过电子邮件或会话初始协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="784bd-204"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="784bd-205"><sup>3</sup> 支持来自不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。</span><span class="sxs-lookup"><span data-stu-id="784bd-205"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="784bd-206"><sup>4</sup> 默认情况下，外部参与者看不到拨入参与者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="784bd-206"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="784bd-207">如果想要保持这些电话号码的隐私，请选择“**进入/退出公告类型**”的“**提示音**”（这会阻止 Teams 读出电话号码）。</span><span class="sxs-lookup"><span data-stu-id="784bd-207">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="784bd-208">若要了解详细信息，请参阅[在 Microsoft Teams 中打开或关闭会议的进入和退出公告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="784bd-208">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="784bd-209"><sup>5</sup> 默认允许，但可由 Teams 管理员禁用</span><span class="sxs-lookup"><span data-stu-id="784bd-209"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="784bd-210">相关主题</span><span class="sxs-lookup"><span data-stu-id="784bd-210">Related topics</span></span>

[<span data-ttu-id="784bd-211">Teams 中的外部访问</span><span class="sxs-lookup"><span data-stu-id="784bd-211">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="784bd-212">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="784bd-212">Guest access in Teams</span></span>](guest-access.md)

