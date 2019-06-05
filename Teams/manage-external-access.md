---
title: 在 Microsoft Teams 中管理外部访问权限（联合身份验证）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: IT 管理员可以为其他域 (联盟) 配置外部访问以允许这些域中的用户参与团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702717"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="56d09-103">在 Microsoft Teams 中管理外部访问权限（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="56d09-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="56d09-104">通过 Microsoft 团队外部访问, 其他域中的用户可以参与您的聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="56d09-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="56d09-105">您还可以允许仍在使用 Skype for Business Online 或 Skype for business 本地的外部用户参与。</span><span class="sxs-lookup"><span data-stu-id="56d09-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="56d09-106">外部访问 (联盟) 和来宾访问不同:</span><span class="sxs-lookup"><span data-stu-id="56d09-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="56d09-107">来宾访问提供对个人的访问权限。</span><span class="sxs-lookup"><span data-stu-id="56d09-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="56d09-108">外部访问提供对整个域的访问权限。</span><span class="sxs-lookup"><span data-stu-id="56d09-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="56d09-109">来宾访问权限由团队所有者授权后, 允许来宾访问特定团队的[资源](guest-experience.md)(如频道讨论和文件), 并与他们被邀请的团队中的其他用户进行聊天。</span><span class="sxs-lookup"><span data-stu-id="56d09-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="56d09-110">通过外部访问 (联合聊天), 外部聊天参与者不能访问邀请组织的团队或团队资源。</span><span class="sxs-lookup"><span data-stu-id="56d09-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="56d09-111">他们只能参与一对一联合聊天。</span><span class="sxs-lookup"><span data-stu-id="56d09-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="56d09-112">租户管理员可以在两种通信选项之间进行选择, 具体取决于外部方需要的协作级别。</span><span class="sxs-lookup"><span data-stu-id="56d09-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="56d09-113">管理员可以选择两种方法或两者之一, 具体取决于它们的组织需求, 但我们建议启用来宾访问以实现更完整的协作团队体验。</span><span class="sxs-lookup"><span data-stu-id="56d09-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="56d09-114">有关外部和来宾访问功能的比较, 请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="56d09-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="56d09-115">功能</span><span class="sxs-lookup"><span data-stu-id="56d09-115">Feature</span></span> | <span data-ttu-id="56d09-116">外部 access 用户</span><span class="sxs-lookup"><span data-stu-id="56d09-116">External access users</span></span> | <span data-ttu-id="56d09-117">来宾访问用户</span><span class="sxs-lookup"><span data-stu-id="56d09-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="56d09-118">用户可以与其他公司的人员进行聊天</span><span class="sxs-lookup"><span data-stu-id="56d09-118">User can chat with someone in another company</span></span> | <span data-ttu-id="56d09-119">是</span><span class="sxs-lookup"><span data-stu-id="56d09-119">Yes</span></span> |<span data-ttu-id="56d09-120">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-120">Yes</span></span> |
| <span data-ttu-id="56d09-121">用户可以呼叫其他公司中的人员</span><span class="sxs-lookup"><span data-stu-id="56d09-121">User can call someone in another company</span></span> | <span data-ttu-id="56d09-122">是</span><span class="sxs-lookup"><span data-stu-id="56d09-122">Yes</span></span> | <span data-ttu-id="56d09-123">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-123">Yes</span></span> |
| <span data-ttu-id="56d09-124">用户可以查看其他公司的人员是否可以进行呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="56d09-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="56d09-125">是</span><span class="sxs-lookup"><span data-stu-id="56d09-125">Yes</span></span> | <span data-ttu-id="56d09-126">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="56d09-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="56d09-127">用户可以跨外部租户搜索用户</span><span class="sxs-lookup"><span data-stu-id="56d09-127">User can search for users across external tenants</span></span> | <span data-ttu-id="56d09-128">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="56d09-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="56d09-129">否</span><span class="sxs-lookup"><span data-stu-id="56d09-129">No</span></span> |
| <span data-ttu-id="56d09-130">用户可以共享文件</span><span class="sxs-lookup"><span data-stu-id="56d09-130">User can share files</span></span> | <span data-ttu-id="56d09-131">否</span><span class="sxs-lookup"><span data-stu-id="56d09-131">No</span></span> | <span data-ttu-id="56d09-132">是</span><span class="sxs-lookup"><span data-stu-id="56d09-132">Yes</span></span> |
| <span data-ttu-id="56d09-133">用户可以访问团队资源</span><span class="sxs-lookup"><span data-stu-id="56d09-133">User can access Teams resources</span></span> | <span data-ttu-id="56d09-134">否</span><span class="sxs-lookup"><span data-stu-id="56d09-134">No</span></span> | <span data-ttu-id="56d09-135">是</span><span class="sxs-lookup"><span data-stu-id="56d09-135">Yes</span></span> |
| <span data-ttu-id="56d09-136">用户可以添加到群组聊天</span><span class="sxs-lookup"><span data-stu-id="56d09-136">User can be added to a group chat</span></span> | <span data-ttu-id="56d09-137">否</span><span class="sxs-lookup"><span data-stu-id="56d09-137">No</span></span> | <span data-ttu-id="56d09-138">是</span><span class="sxs-lookup"><span data-stu-id="56d09-138">Yes</span></span> |
| <span data-ttu-id="56d09-139">可将用户添加到会议</span><span class="sxs-lookup"><span data-stu-id="56d09-139">User can be added to a meeting</span></span> | <span data-ttu-id="56d09-140">是</span><span class="sxs-lookup"><span data-stu-id="56d09-140">Yes</span></span> | <span data-ttu-id="56d09-141">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-141">Yes</span></span> |
| <span data-ttu-id="56d09-142">可将其他用户添加到与外部用户的聊天</span><span class="sxs-lookup"><span data-stu-id="56d09-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="56d09-143">无<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="56d09-143">No<sup>3</sup></span></span> | <span data-ttu-id="56d09-144">不适用</span><span class="sxs-lookup"><span data-stu-id="56d09-144">N/A</span></span> |
| <span data-ttu-id="56d09-145">用户被标识为外部当事方</span><span class="sxs-lookup"><span data-stu-id="56d09-145">User is identified as an external party</span></span> | <span data-ttu-id="56d09-146">是</span><span class="sxs-lookup"><span data-stu-id="56d09-146">Yes</span></span> | <span data-ttu-id="56d09-147">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-147">Yes</span></span> |
| <span data-ttu-id="56d09-148">显示状态</span><span class="sxs-lookup"><span data-stu-id="56d09-148">Presence is displayed</span></span> | <span data-ttu-id="56d09-149">是</span><span class="sxs-lookup"><span data-stu-id="56d09-149">Yes</span></span> | <span data-ttu-id="56d09-150">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-150">Yes</span></span> |
| <span data-ttu-id="56d09-151">显示 "外出" 消息</span><span class="sxs-lookup"><span data-stu-id="56d09-151">Out of office message is shown</span></span> | <span data-ttu-id="56d09-152">否</span><span class="sxs-lookup"><span data-stu-id="56d09-152">No</span></span> | <span data-ttu-id="56d09-153">是</span><span class="sxs-lookup"><span data-stu-id="56d09-153">Yes</span></span> |
| <span data-ttu-id="56d09-154">可以阻止单个用户</span><span class="sxs-lookup"><span data-stu-id="56d09-154">Individual user can be blocked</span></span> | <span data-ttu-id="56d09-155">否</span><span class="sxs-lookup"><span data-stu-id="56d09-155">No</span></span> | <span data-ttu-id="56d09-156">是</span><span class="sxs-lookup"><span data-stu-id="56d09-156">Yes</span></span> |
| <span data-ttu-id="56d09-157">支持 @mentions</span><span class="sxs-lookup"><span data-stu-id="56d09-157">@mentions are supported</span></span> | <span data-ttu-id="56d09-158">否</span><span class="sxs-lookup"><span data-stu-id="56d09-158">No</span></span> | <span data-ttu-id="56d09-159">是</span><span class="sxs-lookup"><span data-stu-id="56d09-159">Yes</span></span> |
| <span data-ttu-id="56d09-160">拨打私人电话</span><span class="sxs-lookup"><span data-stu-id="56d09-160">Make Private Calls</span></span> | <span data-ttu-id="56d09-161">是</span><span class="sxs-lookup"><span data-stu-id="56d09-161">Yes</span></span> | <span data-ttu-id="56d09-162">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-162">Yes</span></span> |
| <span data-ttu-id="56d09-163">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="56d09-163">Allow IP Video</span></span> | <span data-ttu-id="56d09-164">是</span><span class="sxs-lookup"><span data-stu-id="56d09-164">Yes</span></span> | <span data-ttu-id="56d09-165">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-165">Yes</span></span> |
| <span data-ttu-id="56d09-166">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="56d09-166">Screen Sharing Mode</span></span> | <span data-ttu-id="56d09-167">是</span><span class="sxs-lookup"><span data-stu-id="56d09-167">Yes</span></span> | <span data-ttu-id="56d09-168">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-168">Yes</span></span> |
| <span data-ttu-id="56d09-169">允许立即开会</span><span class="sxs-lookup"><span data-stu-id="56d09-169">Allow Meet Now</span></span> | <span data-ttu-id="56d09-170">否</span><span class="sxs-lookup"><span data-stu-id="56d09-170">No</span></span> | <span data-ttu-id="56d09-171">是</span><span class="sxs-lookup"><span data-stu-id="56d09-171">Yes</span></span> |
| <span data-ttu-id="56d09-172">编辑已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="56d09-172">Edit Sent Messages</span></span> | <span data-ttu-id="56d09-173">是</span><span class="sxs-lookup"><span data-stu-id="56d09-173">Yes</span></span> | <span data-ttu-id="56d09-174">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-174">Yes</span></span> |
| <span data-ttu-id="56d09-175">可以删除已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="56d09-175">Can Delete Sent Messages</span></span> | <span data-ttu-id="56d09-176">是</span><span class="sxs-lookup"><span data-stu-id="56d09-176">Yes</span></span> | <span data-ttu-id="56d09-177">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-177">Yes</span></span> |
| <span data-ttu-id="56d09-178">在对话中使用 Giphy</span><span class="sxs-lookup"><span data-stu-id="56d09-178">Use Giphy In Conversation</span></span> | <span data-ttu-id="56d09-179">是</span><span class="sxs-lookup"><span data-stu-id="56d09-179">Yes</span></span> | <span data-ttu-id="56d09-180">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-180">Yes</span></span> |
| <span data-ttu-id="56d09-181">在对话中使用 Meme</span><span class="sxs-lookup"><span data-stu-id="56d09-181">Use Memes In Conversation</span></span> | <span data-ttu-id="56d09-182">是</span><span class="sxs-lookup"><span data-stu-id="56d09-182">Yes</span></span> | <span data-ttu-id="56d09-183">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-183">Yes</span></span> |
| <span data-ttu-id="56d09-184">在对话中使用贴纸</span><span class="sxs-lookup"><span data-stu-id="56d09-184">Use Stickers In Conversation</span></span> | <span data-ttu-id="56d09-185">是</span><span class="sxs-lookup"><span data-stu-id="56d09-185">Yes</span></span> | <span data-ttu-id="56d09-186">是 </span><span class="sxs-lookup"><span data-stu-id="56d09-186">Yes</span></span> |
||||

<span data-ttu-id="56d09-187"><sup>1</sup>假设已将用户添加为来宾, 并以来宾身份登录到来宾租户。</span><span class="sxs-lookup"><span data-stu-id="56d09-187"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="56d09-188"><sup>2</sup>仅通过电子邮件或会话初始协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="56d09-188"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="56d09-189"><sup>3</sup>仅限1:1 的外部 (联合) 聊天。</span><span class="sxs-lookup"><span data-stu-id="56d09-189"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

> [!NOTE]
> <span data-ttu-id="56d09-190">有关来宾功能和来宾体验的详细信息, 请参阅[打开或关闭来宾对 Microsoft 团队的访问权限](https://docs.microsoft.com/microsoftteams/set-up-guests)和[来宾体验等](https://docs.microsoft.com/microsoftteams/guest-experience)。</span><span class="sxs-lookup"><span data-stu-id="56d09-190">For more information on guest features and the guest experience, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) and [What the guest experience is like](https://docs.microsoft.com/microsoftteams/guest-experience).</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="56d09-191">打开或关闭外部访问 (用户可以与 Skype for Business 和团队用户通信)</span><span class="sxs-lookup"><span data-stu-id="56d09-191">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="56d09-192">你可以使用 Microsoft 团队 & Skype for Business 管理中心来管理外部访问。</span><span class="sxs-lookup"><span data-stu-id="56d09-192">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="56d09-193">在 "Microsoft 团队 & Skype for business 管理中心" 中, 选择 "**组织范围的设置** > **外部访问**"。</span><span class="sxs-lookup"><span data-stu-id="56d09-193">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![组织范围设置外部访问的屏幕截图](media/manage-external-access-1.png)<span data-ttu-id="56d09-195">.</span><span class="sxs-lookup"><span data-stu-id="56d09-195"></span></span>

2. <span data-ttu-id="56d09-196">切换**用户可以与 Skype For business 和团队用户进行通信**切换到 **"打开" 或 "** **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="56d09-196">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![打开了外部访问切换器的屏幕截图](media/manage-external-access-2.png)<span data-ttu-id="56d09-198">.</span><span class="sxs-lookup"><span data-stu-id="56d09-198"></span></span>

3. <span data-ttu-id="56d09-199">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56d09-199">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="56d09-200">添加或阻止域</span><span class="sxs-lookup"><span data-stu-id="56d09-200">Add or block a domain</span></span>

<span data-ttu-id="56d09-201">请按照以下步骤添加域或关闭域的外部访问。</span><span class="sxs-lookup"><span data-stu-id="56d09-201">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="56d09-202">在 "Microsoft 团队 & Skype for business 管理中心" 中, 选择 "**组织范围的设置** > **外部访问**"。</span><span class="sxs-lookup"><span data-stu-id="56d09-202">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="56d09-203">选择“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="56d09-203">Select **Add a domain**.</span></span> 
 
    ![带有 "添加域" 链接的外部访问页面的屏幕截图](media/manage-external-access-3.png)<span data-ttu-id="56d09-205">.</span><span class="sxs-lookup"><span data-stu-id="56d09-205"></span></span>

   <span data-ttu-id="56d09-206">将显示 "**添加域**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="56d09-206">The **Add a domain** pane appears.</span></span>

    !["添加域" 窗格的屏幕截图](media/manage-external-access-4.png)<span data-ttu-id="56d09-208">.</span><span class="sxs-lookup"><span data-stu-id="56d09-208"></span></span>


3. <span data-ttu-id="56d09-209">在 "**添加域**" 下, 键入域的名称;例如, 键入 Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="56d09-209">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="56d09-210">选择“**已允许**”或“**已阻止**”。</span><span class="sxs-lookup"><span data-stu-id="56d09-210">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="56d09-211">您可以随时更改此设置。</span><span class="sxs-lookup"><span data-stu-id="56d09-211">You can change this setting at any time.</span></span>

2. <span data-ttu-id="56d09-212">选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="56d09-212">Select **Done**.</span></span>

<span data-ttu-id="56d09-213">添加域后, 您将看到添加到外部访问页面上的域列表中的域名和状态。</span><span class="sxs-lookup"><span data-stu-id="56d09-213">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="56d09-214">详细信息</span><span class="sxs-lookup"><span data-stu-id="56d09-214">More information</span></span>

<span data-ttu-id="56d09-215">有关 Microsoft 团队中的来宾访问的信息, 请参阅[管理 Microsoft 团队中的来宾访问](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="56d09-215">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
