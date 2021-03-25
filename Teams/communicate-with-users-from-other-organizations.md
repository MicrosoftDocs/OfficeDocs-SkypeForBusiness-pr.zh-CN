---
title: 使用来宾访问权限和外部访问权限与组织外部的人员进行协作
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
ms.openlocfilehash: e4aea581af73e69512e8ab55f87faa0602219575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115990"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a><span data-ttu-id="30d6d-103">使用来宾访问权限和外部访问权限与组织外部的人员进行协作</span><span class="sxs-lookup"><span data-stu-id="30d6d-103">Use guest access and external access to collaborate with people outside your organization</span></span>

<span data-ttu-id="30d6d-104">当需要与组织外部的人员进行通信和协作时，Microsoft Teams 可为你提供两种选择：</span><span class="sxs-lookup"><span data-stu-id="30d6d-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="30d6d-105">**外部访问** - 一种联盟，允许用户查找其他组织中的人员以及与其通话和聊天。</span><span class="sxs-lookup"><span data-stu-id="30d6d-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="30d6d-106">除非作为来宾受到邀请，否则这些人员无法添加到团队。</span><span class="sxs-lookup"><span data-stu-id="30d6d-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="30d6d-107">**来宾访问** - 来宾访问允许邀请组织外部人员加入团队。</span><span class="sxs-lookup"><span data-stu-id="30d6d-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="30d6d-108">受邀人员将在 Azure Active Directory 中获得来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="30d6d-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="30d6d-109">请注意，Teams 允许邀请组织外部人员参加会议。</span><span class="sxs-lookup"><span data-stu-id="30d6d-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="30d6d-110">这不需要配置外部或来宾访问。</span><span class="sxs-lookup"><span data-stu-id="30d6d-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="30d6d-111">外部访问（联盟）</span><span class="sxs-lookup"><span data-stu-id="30d6d-111">External access (federation)</span></span>

<span data-ttu-id="30d6d-112">针对组织外部使用 Teams、Skype for Business（联机或本地）或 Skype 的人员，如果需要查找此类人员、与其通话和聊天以及设置与此类人员的会议，可设置外部访问。</span><span class="sxs-lookup"><span data-stu-id="30d6d-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="30d6d-113">默认情况下，将针对所有域启用外部访问。</span><span class="sxs-lookup"><span data-stu-id="30d6d-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="30d6d-114">你可以通过允许或阻止特定域或者通过关闭该设置来限制外部访问。</span><span class="sxs-lookup"><span data-stu-id="30d6d-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![外部访问设置的屏幕截图](media/external-access-federation-settings.png)

<span data-ttu-id="30d6d-116">若要配置外部访问，请参阅[管理外部访问](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="30d6d-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

>[!NOTE]
><span data-ttu-id="30d6d-117">Microsoft Teams 免费许可证不支持外部访问。</span><span class="sxs-lookup"><span data-stu-id="30d6d-117">Microsoft Teams free licenses do not support external access.</span></span>

## <a name="guest-access"></a><span data-ttu-id="30d6d-118">来宾访问</span><span class="sxs-lookup"><span data-stu-id="30d6d-118">Guest access</span></span>

<span data-ttu-id="30d6d-119">使用来宾访问将组织外部人员添加到团队，他们可在其中聊天、通话、开会和协作处理文件。</span><span class="sxs-lookup"><span data-stu-id="30d6d-119">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="30d6d-120">来宾可以获得几乎与本地团队成员相同的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="30d6d-120">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="30d6d-121">来宾将作为 B2B 用户添加到组织的 Azure Active Directory，且必须使用他们的来宾帐户登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="30d6d-121">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="30d6d-122">这意味着，他们可能需要从自己的组织注销才能登录到你的组织。</span><span class="sxs-lookup"><span data-stu-id="30d6d-122">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="30d6d-123">若要为 Teams 配置来宾访问，请参阅[在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="30d6d-123">To configure guest access for Teams, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="30d6d-124">比较外部访问和来宾访问</span><span class="sxs-lookup"><span data-stu-id="30d6d-124">Compare external and guest access</span></span>

<span data-ttu-id="30d6d-125">下表显示了使用外部访问（联盟）和来宾访问的区别。</span><span class="sxs-lookup"><span data-stu-id="30d6d-125">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="30d6d-126">在这两种情况下，组织外部人员均被标识为外部用户。</span><span class="sxs-lookup"><span data-stu-id="30d6d-126">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="30d6d-127">你的用户可以进行的一些操作</span><span class="sxs-lookup"><span data-stu-id="30d6d-127">Things your users can do</span></span>

| <span data-ttu-id="30d6d-128">用户可以</span><span class="sxs-lookup"><span data-stu-id="30d6d-128">Users can</span></span> | <span data-ttu-id="30d6d-129">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="30d6d-129">External access users</span></span> | <span data-ttu-id="30d6d-130">来宾</span><span class="sxs-lookup"><span data-stu-id="30d6d-130">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="30d6d-131">与其他组织中的人聊天</span><span class="sxs-lookup"><span data-stu-id="30d6d-131">Chat with someone in another organization</span></span> | <span data-ttu-id="30d6d-132">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-132">Yes</span></span> | <span data-ttu-id="30d6d-133">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-133">Yes</span></span> |
| <span data-ttu-id="30d6d-134">呼叫其他组织中的人</span><span class="sxs-lookup"><span data-stu-id="30d6d-134">Call someone in another organization</span></span> | <span data-ttu-id="30d6d-135">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-135">Yes</span></span> | <span data-ttu-id="30d6d-136">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-136">Yes</span></span> |
| <span data-ttu-id="30d6d-137">查看其他组织中的人是否可接受呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="30d6d-137">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="30d6d-138">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-138">Yes</span></span> | <span data-ttu-id="30d6d-139">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-139">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="30d6d-140">搜索其他组织中的人员</span><span class="sxs-lookup"><span data-stu-id="30d6d-140">Search for people in other organizations</span></span> | <span data-ttu-id="30d6d-141">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-141">Yes<sup>2</sup></span></span> | <span data-ttu-id="30d6d-142">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-142">No</span></span> |
| <span data-ttu-id="30d6d-143">共享文件</span><span class="sxs-lookup"><span data-stu-id="30d6d-143">Share files</span></span> | <span data-ttu-id="30d6d-144">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-144">No</span></span> | <span data-ttu-id="30d6d-145">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-145">Yes</span></span> |
| <span data-ttu-id="30d6d-146">查看另一个组织中某人外出期间的邮件</span><span class="sxs-lookup"><span data-stu-id="30d6d-146">See the out-of-office message of someone in another organization</span></span> | <span data-ttu-id="30d6d-147">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-147">No</span></span> | <span data-ttu-id="30d6d-148">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-148">Yes</span></span> |
| <span data-ttu-id="30d6d-149">组织其他组织中的某个人</span><span class="sxs-lookup"><span data-stu-id="30d6d-149">Block someone in another organization</span></span>  | <span data-ttu-id="30d6d-150">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-150">No</span></span> | <span data-ttu-id="30d6d-151">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-151">Yes</span></span> |
| <span data-ttu-id="30d6d-152">使用 @提及</span><span class="sxs-lookup"><span data-stu-id="30d6d-152">Use @mentions</span></span> | <span data-ttu-id="30d6d-153">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-153">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-154">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-154">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="30d6d-155">组织外部的人员可以进行的一些操作</span><span class="sxs-lookup"><span data-stu-id="30d6d-155">Things people outside your organization can do</span></span>

| <span data-ttu-id="30d6d-156">组织外部的人员可以</span><span class="sxs-lookup"><span data-stu-id="30d6d-156">People outside your organization can</span></span> | <span data-ttu-id="30d6d-157">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="30d6d-157">External access users</span></span> | <span data-ttu-id="30d6d-158">来宾</span><span class="sxs-lookup"><span data-stu-id="30d6d-158">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="30d6d-159">访问 Teams 资源</span><span class="sxs-lookup"><span data-stu-id="30d6d-159">Access Teams resources</span></span> | <span data-ttu-id="30d6d-160">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-160">No</span></span> | <span data-ttu-id="30d6d-161">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-161">Yes</span></span> |
| <span data-ttu-id="30d6d-162">被添加到群聊</span><span class="sxs-lookup"><span data-stu-id="30d6d-162">Be added to a group chat</span></span> | <span data-ttu-id="30d6d-163">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-163">No</span></span> | <span data-ttu-id="30d6d-164">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-164">Yes</span></span> |
| <span data-ttu-id="30d6d-165">受邀加入会议</span><span class="sxs-lookup"><span data-stu-id="30d6d-165">Be invited to a meeting</span></span> | <span data-ttu-id="30d6d-166">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-166">Yes</span></span> | <span data-ttu-id="30d6d-167">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-167">Yes</span></span> |
| <span data-ttu-id="30d6d-168">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="30d6d-168">Make private calls</span></span> | <span data-ttu-id="30d6d-169">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-169">Yes</span></span> | <span data-ttu-id="30d6d-170">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-170">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-171">查看拨入会议参与者的电话号码</span><span class="sxs-lookup"><span data-stu-id="30d6d-171">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="30d6d-172">否<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-172">No<sup>4</sup></span></span> | <span data-ttu-id="30d6d-173">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-173">Yes</span></span> |
| <span data-ttu-id="30d6d-174">使用 IP 视频</span><span class="sxs-lookup"><span data-stu-id="30d6d-174">Use IP video</span></span> | <span data-ttu-id="30d6d-175">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-175">Yes</span></span> | <span data-ttu-id="30d6d-176">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-176">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-177">使用屏幕共享</span><span class="sxs-lookup"><span data-stu-id="30d6d-177">Use screen sharing</span></span> | <span data-ttu-id="30d6d-178">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-178">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-179">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-179">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-180">使用立即开会</span><span class="sxs-lookup"><span data-stu-id="30d6d-180">Use meet now</span></span> | <span data-ttu-id="30d6d-181">否</span><span class="sxs-lookup"><span data-stu-id="30d6d-181">No</span></span> | <span data-ttu-id="30d6d-182">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-182">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-183">编辑已发送的消息</span><span class="sxs-lookup"><span data-stu-id="30d6d-183">Edit sent messages</span></span> | <span data-ttu-id="30d6d-184">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-184">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-185">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-186">删除已发送的消息</span><span class="sxs-lookup"><span data-stu-id="30d6d-186">Delete sent messages</span></span> | <span data-ttu-id="30d6d-187">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-187">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-188">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-188">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-189">在对话中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="30d6d-189">Use Giphy in conversation</span></span> | <span data-ttu-id="30d6d-190">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-190">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-191">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-191">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-192">在对话中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="30d6d-192">Use memes in conversation</span></span> | <span data-ttu-id="30d6d-193">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-193">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-194">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-194">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-195">在对话中使用贴纸</span><span class="sxs-lookup"><span data-stu-id="30d6d-195">Use stickers in conversation</span></span> | <span data-ttu-id="30d6d-196">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-196">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-197">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-197">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="30d6d-198">将显示状态</span><span class="sxs-lookup"><span data-stu-id="30d6d-198">Presence is displayed</span></span> | <span data-ttu-id="30d6d-199">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-199">Yes</span></span> | <span data-ttu-id="30d6d-200">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-200">Yes</span></span> |
| <span data-ttu-id="30d6d-201">使用 @提及</span><span class="sxs-lookup"><span data-stu-id="30d6d-201">Use @mentions</span></span> | <span data-ttu-id="30d6d-202">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="30d6d-202">Yes<sup>3</sup></span></span> | <span data-ttu-id="30d6d-203">是</span><span class="sxs-lookup"><span data-stu-id="30d6d-203">Yes</span></span> |

<br>

<span data-ttu-id="30d6d-204"><sup>1</sup> 前提是已将用户添加为来宾，并且对方已使用来宾帐户登录。</span><span class="sxs-lookup"><span data-stu-id="30d6d-204"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="30d6d-205"><sup>2</sup> 仅通过电子邮件或会话初始协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="30d6d-205"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="30d6d-206"><sup>3</sup> 支持来自不同组织的仅 Teams 对仅 Teams 用户的一对一聊天。</span><span class="sxs-lookup"><span data-stu-id="30d6d-206"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="30d6d-207"><sup>4</sup> 默认情况下，外部参与者看不到拨入参与者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="30d6d-207"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="30d6d-208">如果想要保持这些电话号码的隐私，请选择“**进入/退出公告类型**”的“**提示音**”（这会阻止 Teams 读出电话号码）。</span><span class="sxs-lookup"><span data-stu-id="30d6d-208">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="30d6d-209">若要了解详细信息，请参阅[在 Microsoft Teams 中打开或关闭会议的进入和退出公告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="30d6d-209">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="30d6d-210"><sup>5</sup> 默认允许，但可由 Teams 管理员禁用</span><span class="sxs-lookup"><span data-stu-id="30d6d-210"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="30d6d-211">相关主题</span><span class="sxs-lookup"><span data-stu-id="30d6d-211">Related topics</span></span>

[<span data-ttu-id="30d6d-212">Teams 中的外部访问</span><span class="sxs-lookup"><span data-stu-id="30d6d-212">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="30d6d-213">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="30d6d-213">Guest access in Teams</span></span>](guest-access.md)