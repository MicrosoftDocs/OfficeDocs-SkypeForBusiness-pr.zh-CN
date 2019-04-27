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
description: 您的 IT 管理员可以配置外部访问的其他域 （联合身份验证），以使用户可以从这些域参与团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98dc47ec66861d2f0c77c0eff45851c09e8bc353
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33356185"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="fe829-103">在 Microsoft Teams 中管理外部访问权限（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="fe829-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="fe829-104">与 Microsoft 团队外部访问来自其他域的用户可以参加您聊天和呼叫。</span><span class="sxs-lookup"><span data-stu-id="fe829-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="fe829-105">您还可以允许外部用户仍在使用 Skype 业务联机或业务 prem 的 Skype 参与。</span><span class="sxs-lookup"><span data-stu-id="fe829-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="fe829-106">外部访问 （联合身份验证） 和来宾访问是不同：</span><span class="sxs-lookup"><span data-stu-id="fe829-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="fe829-107">来宾访问向个人授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="fe829-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="fe829-108">外部访问提供对整个域访问权限。</span><span class="sxs-lookup"><span data-stu-id="fe829-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="fe829-109">来宾授予访问权限，一次的团队所有者，允许[访问资源](guest-experience.md)，如通道讨论和文件，为来宾特定团队，以及与其他用户被邀请参加的团队中的聊天。</span><span class="sxs-lookup"><span data-stu-id="fe829-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="fe829-110">外部访问 （联合聊天），与外部聊天参与者均没有访问权邀请组织的团队或工作组资源。</span><span class="sxs-lookup"><span data-stu-id="fe829-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="fe829-111">他们只能参与一对一联盟聊天。</span><span class="sxs-lookup"><span data-stu-id="fe829-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="fe829-112">租户管理员可以选择之间的两个通信选项，具体取决于哪个级别的协作是理想与外部方。</span><span class="sxs-lookup"><span data-stu-id="fe829-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="fe829-113">管理员可以选择方法或同时，具体取决于其组织的需求，但建议启用更完整、 协作式团队体验的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="fe829-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="fe829-114">请参阅下面的有关外部的比较的表和来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="fe829-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="fe829-115">功能</span><span class="sxs-lookup"><span data-stu-id="fe829-115">Feature</span></span> | <span data-ttu-id="fe829-116">外部访问用户</span><span class="sxs-lookup"><span data-stu-id="fe829-116">External access users</span></span> | <span data-ttu-id="fe829-117">来宾访问用户</span><span class="sxs-lookup"><span data-stu-id="fe829-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="fe829-118">用户可以与另一家公司中的某个人聊天</span><span class="sxs-lookup"><span data-stu-id="fe829-118">User can chat with someone in another company</span></span> | <span data-ttu-id="fe829-119">是</span><span class="sxs-lookup"><span data-stu-id="fe829-119">Yes</span></span> |<span data-ttu-id="fe829-120">是 </span><span class="sxs-lookup"><span data-stu-id="fe829-120">Yes</span></span> |
| <span data-ttu-id="fe829-121">用户可以在另一家公司呼叫某人</span><span class="sxs-lookup"><span data-stu-id="fe829-121">User can call someone in another company</span></span> | <span data-ttu-id="fe829-122">是</span><span class="sxs-lookup"><span data-stu-id="fe829-122">Yes</span></span> | <span data-ttu-id="fe829-123">是 </span><span class="sxs-lookup"><span data-stu-id="fe829-123">Yes</span></span> |
| <span data-ttu-id="fe829-124">用户可以看到另一家公司的某个人是否可用于调用或聊天</span><span class="sxs-lookup"><span data-stu-id="fe829-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="fe829-125">是</span><span class="sxs-lookup"><span data-stu-id="fe829-125">Yes</span></span> | <span data-ttu-id="fe829-126">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fe829-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="fe829-127">用户可以搜索外部租户的用户</span><span class="sxs-lookup"><span data-stu-id="fe829-127">User can search for users across external tenants</span></span> | <span data-ttu-id="fe829-128">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fe829-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="fe829-129">否</span><span class="sxs-lookup"><span data-stu-id="fe829-129">No</span></span> |
| <span data-ttu-id="fe829-130">用户可以共享文件</span><span class="sxs-lookup"><span data-stu-id="fe829-130">User can share files</span></span> | <span data-ttu-id="fe829-131">否</span><span class="sxs-lookup"><span data-stu-id="fe829-131">No</span></span> | <span data-ttu-id="fe829-132">是</span><span class="sxs-lookup"><span data-stu-id="fe829-132">Yes</span></span> |
| <span data-ttu-id="fe829-133">用户可以访问团队资源</span><span class="sxs-lookup"><span data-stu-id="fe829-133">User can access Teams resources</span></span> | <span data-ttu-id="fe829-134">否</span><span class="sxs-lookup"><span data-stu-id="fe829-134">No</span></span> | <span data-ttu-id="fe829-135">是</span><span class="sxs-lookup"><span data-stu-id="fe829-135">Yes</span></span> |
| <span data-ttu-id="fe829-136">可以将用户添加到群聊</span><span class="sxs-lookup"><span data-stu-id="fe829-136">User can be added to a group chat</span></span> | <span data-ttu-id="fe829-137">否</span><span class="sxs-lookup"><span data-stu-id="fe829-137">No</span></span> | <span data-ttu-id="fe829-138">是</span><span class="sxs-lookup"><span data-stu-id="fe829-138">Yes</span></span> |
| <span data-ttu-id="fe829-139">可以将用户添加到会议</span><span class="sxs-lookup"><span data-stu-id="fe829-139">User can be added to a meeting</span></span> | <span data-ttu-id="fe829-140">是</span><span class="sxs-lookup"><span data-stu-id="fe829-140">Yes</span></span> | <span data-ttu-id="fe829-141">是 </span><span class="sxs-lookup"><span data-stu-id="fe829-141">Yes</span></span> |
| <span data-ttu-id="fe829-142">其他用户可以与外部用户添加到聊天</span><span class="sxs-lookup"><span data-stu-id="fe829-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="fe829-143">没有<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="fe829-143">No<sup>3</sup></span></span> | <span data-ttu-id="fe829-144">不适用</span><span class="sxs-lookup"><span data-stu-id="fe829-144">N/A</span></span> |
| <span data-ttu-id="fe829-145">用户被标识为外部方</span><span class="sxs-lookup"><span data-stu-id="fe829-145">User is identified as an external party</span></span> | <span data-ttu-id="fe829-146">是</span><span class="sxs-lookup"><span data-stu-id="fe829-146">Yes</span></span> | <span data-ttu-id="fe829-147">是 </span><span class="sxs-lookup"><span data-stu-id="fe829-147">Yes</span></span> |
| <span data-ttu-id="fe829-148">显示状态</span><span class="sxs-lookup"><span data-stu-id="fe829-148">Presence is displayed</span></span> | <span data-ttu-id="fe829-149">是</span><span class="sxs-lookup"><span data-stu-id="fe829-149">Yes</span></span> | <span data-ttu-id="fe829-150">是 </span><span class="sxs-lookup"><span data-stu-id="fe829-150">Yes</span></span> |
| <span data-ttu-id="fe829-151">显示邮件是外出</span><span class="sxs-lookup"><span data-stu-id="fe829-151">Out of office message is shown</span></span> | <span data-ttu-id="fe829-152">否</span><span class="sxs-lookup"><span data-stu-id="fe829-152">No</span></span> | <span data-ttu-id="fe829-153">是</span><span class="sxs-lookup"><span data-stu-id="fe829-153">Yes</span></span> |
| <span data-ttu-id="fe829-154">单个用户可以被阻止</span><span class="sxs-lookup"><span data-stu-id="fe829-154">Individual user can be blocked</span></span> | <span data-ttu-id="fe829-155">否</span><span class="sxs-lookup"><span data-stu-id="fe829-155">No</span></span> | <span data-ttu-id="fe829-156">是</span><span class="sxs-lookup"><span data-stu-id="fe829-156">Yes</span></span> |
| <span data-ttu-id="fe829-157">支持 @mentions</span><span class="sxs-lookup"><span data-stu-id="fe829-157">@mentions are supported</span></span> | <span data-ttu-id="fe829-158">否</span><span class="sxs-lookup"><span data-stu-id="fe829-158">No</span></span> | <span data-ttu-id="fe829-159">是</span><span class="sxs-lookup"><span data-stu-id="fe829-159">Yes</span></span> |
||||

<span data-ttu-id="fe829-160"><sup>1</sup>提供用户已添加以来宾身份，并作为来宾到来宾租户登录。</span><span class="sxs-lookup"><span data-stu-id="fe829-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="fe829-161"><sup>2</sup>仅通过电子邮件或会话初始协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="fe829-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="fe829-162"><sup>3</sup>外部 （联盟） 聊天是仅 1:1。</span><span class="sxs-lookup"><span data-stu-id="fe829-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="fe829-163">打开或关闭 （用户能与其通信 Skype 的业务和团队用户） 的外部访问</span><span class="sxs-lookup"><span data-stu-id="fe829-163">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="fe829-164">Microsoft 团队 & Business Admin Center 的 Skype 可用于管理外部访问。</span><span class="sxs-lookup"><span data-stu-id="fe829-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="fe829-165">在 Microsoft 团队 & Skype 的业务管理中心中，选择**组织范围的设置** > **外部访问**。</span><span class="sxs-lookup"><span data-stu-id="fe829-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![组织范围设置外部访问的屏幕截图](media/manage-external-access-1.png)<span data-ttu-id="fe829-167">.</span><span class="sxs-lookup"><span data-stu-id="fe829-167"></span></span>

2. <span data-ttu-id="fe829-168">切换**用户可以与 Skype 的业务和团队用户通信**切换到**打开**或**关闭**。</span><span class="sxs-lookup"><span data-stu-id="fe829-168">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![外部访问开关开启的屏幕截图](media/manage-external-access-2.png)<span data-ttu-id="fe829-170">.</span><span class="sxs-lookup"><span data-stu-id="fe829-170"></span></span>

3. <span data-ttu-id="fe829-171">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fe829-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="fe829-172">添加或阻止域</span><span class="sxs-lookup"><span data-stu-id="fe829-172">Add or block a domain</span></span>

<span data-ttu-id="fe829-173">按照以下步骤添加域或关闭外部访问域。</span><span class="sxs-lookup"><span data-stu-id="fe829-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="fe829-174">在 Microsoft 团队 & Skype 的业务管理中心中，选择**组织范围的设置** > **外部访问**。</span><span class="sxs-lookup"><span data-stu-id="fe829-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="fe829-175">选择“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="fe829-175">Select **Add a domain**.</span></span> 
 
    ![使用的屏幕快照的外部访问页添加域链接](media/manage-external-access-3.png)<span data-ttu-id="fe829-177">.</span><span class="sxs-lookup"><span data-stu-id="fe829-177"></span></span>

   <span data-ttu-id="fe829-178">**添加域**窗格中显示。</span><span class="sxs-lookup"><span data-stu-id="fe829-178">The **Add a domain** pane appears.</span></span>

    ![添加域窗格中的屏幕截图](media/manage-external-access-4.png)<span data-ttu-id="fe829-180">.</span><span class="sxs-lookup"><span data-stu-id="fe829-180"></span></span>


3. <span data-ttu-id="fe829-181">在**添加域**，下键入域名;例如，键入 Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fe829-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="fe829-182">选择“**已允许**”或“**已阻止**”。</span><span class="sxs-lookup"><span data-stu-id="fe829-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="fe829-183">您可以更改此设置在任何时间。</span><span class="sxs-lookup"><span data-stu-id="fe829-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="fe829-184">选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="fe829-184">Select **Done**.</span></span>

<span data-ttu-id="fe829-185">添加域之后，您将看到的域名和状态添加到外部访问页上的域的列表。</span><span class="sxs-lookup"><span data-stu-id="fe829-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="fe829-186">更多信息</span><span class="sxs-lookup"><span data-stu-id="fe829-186">More information</span></span>

<span data-ttu-id="fe829-187">有关来宾访问中的 Microsoft 团队的信息，请参阅[管理中的 Microsoft 团队的来宾访问](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="fe829-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
