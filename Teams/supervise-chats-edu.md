---
title: 使用监督聊天
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解 Microsoft Teams 会议中监督聊天。
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506675"
---
# <a name="supervised-chats-in-microsoft-teams"></a><span data-ttu-id="683ba-103">Microsoft Teams 中的监督聊天</span><span class="sxs-lookup"><span data-stu-id="683ba-103">Supervised chats in Microsoft Teams</span></span>

<span data-ttu-id="683ba-104">教育机构为学生提供安全、健康的数字空间。</span><span class="sxs-lookup"><span data-stu-id="683ba-104">Education institutions provide a safe and healthy digital space for students.</span></span> <span data-ttu-id="683ba-105">数字空间包括 Teams 中的电子邮件、联机会议和呼叫以及消息传递。</span><span class="sxs-lookup"><span data-stu-id="683ba-105">The digital space includes emails, online meetings and calls, and messaging in Teams.</span></span> <span data-ttu-id="683ba-106">为了防止不适当的消息传递行为，许多学校在 Teams 中禁用私人聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-106">To prevent inappropriate messaging behavior, many schools disable private chat in Teams.</span></span> <span data-ttu-id="683ba-107">遗憾的是，禁用聊天也会阻止教师私下联系学生进行个性化学习。</span><span class="sxs-lookup"><span data-stu-id="683ba-107">Unfortunately, disabling chat also blocks the opportunity for teachers to reach out to students privately for personalized learning.</span></span> <span data-ttu-id="683ba-108">禁用聊天后，学生不希望在课堂团队中公开发布消息时，无法与教师联系。</span><span class="sxs-lookup"><span data-stu-id="683ba-108">With chat disabled, students can't reach out to teachers when they prefer not to post the messages publicly in class teams.</span></span>

<span data-ttu-id="683ba-109">监督式聊天允许指定的教师发起与学生的聊天，并阻止学生开始新聊天，除非有合适的教师。</span><span class="sxs-lookup"><span data-stu-id="683ba-109">Supervised chat allows designated educators to initiate chats with students and blocks students from starting new chats unless an appropriate educator is present.</span></span> <span data-ttu-id="683ba-110">启用聊天监督后，主管不允许离开聊天，不允许其他参与者删除聊天，从而确保涉及学生的聊天受到适当的监督。</span><span class="sxs-lookup"><span data-stu-id="683ba-110">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving students are properly supervised.</span></span>

<span data-ttu-id="683ba-111">这些限制仅适用于在完全启用监督聊天后创建的新私人聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-111">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="683ba-112">它们不适用于现有私人聊天、会议聊天或频道。</span><span class="sxs-lookup"><span data-stu-id="683ba-112">They don't apply to existing private chats, meetings chats, or channels.</span></span> <span data-ttu-id="683ba-113">若要详细了解会议聊天、频道安全和确保学生安全的最佳做法，请观看使用 Teams 时确保 [学生安全](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)。</span><span class="sxs-lookup"><span data-stu-id="683ba-113">To learn more about best practices for meeting chat, channel safety, and keeping students safe, view [Keeping students safe while using Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).</span></span>

> [!Note]
> <span data-ttu-id="683ba-114">监督聊天保护在强制实施该功能后创建的新聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-114">Supervised chat protects new chats created after the feature is enforced.</span></span>  <span data-ttu-id="683ba-115">它不会保护现有聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-115">It doesn't protect existing chats.</span></span>

## <a name="review-use-cases-for-supervised-chats"></a><span data-ttu-id="683ba-116">查看监督聊天的用例</span><span class="sxs-lookup"><span data-stu-id="683ba-116">Review use cases for supervised chats</span></span>

<span data-ttu-id="683ba-117">以下示例介绍何时需要监督聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-117">The following examples are descriptions of when a supervised chat is necessary.</span></span>

- <span data-ttu-id="683ba-118">当学生不喜欢共享或公开提问时，与教师进行 1.1 跟进。</span><span class="sxs-lookup"><span data-stu-id="683ba-118">A 1.1 follow-up with an educator when students aren't comfortable sharing or asking questions publicly.</span></span>

- <span data-ttu-id="683ba-119">教师通过 1.1 向学生介绍作业、最近的课堂 (或缺少) 或其他主题。</span><span class="sxs-lookup"><span data-stu-id="683ba-119">Educators reaching out 1.1 to a student about an assignment, recent class interaction (or lack of), or other topic.</span></span>

- <span data-ttu-id="683ba-120">教师监视的学生组讨论。</span><span class="sxs-lookup"><span data-stu-id="683ba-120">Student group discussions monitored by an educator.</span></span>

- <span data-ttu-id="683ba-121">允许非教职员工在受监督的环境中与学生聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-121">Allow non-teaching staff to chat with student in a supervised environment.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="683ba-122">启用监督聊天</span><span class="sxs-lookup"><span data-stu-id="683ba-122">Enable supervised chat</span></span>

> [!Note]
> <span data-ttu-id="683ba-123">在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不需要的学生访问不受监督的聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-123">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted student access to unsupervised chats.</span></span>

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a><span data-ttu-id="683ba-124">为环境中每个用户定义聊天权限角色</span><span class="sxs-lookup"><span data-stu-id="683ba-124">Define chat permission roles for each user in your environment</span></span>

<span data-ttu-id="683ba-125">要正常使用监督聊天，需要为环境中每个用户分配正确的聊天权限角色。</span><span class="sxs-lookup"><span data-stu-id="683ba-125">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="683ba-126">用户可以分配三个角色：</span><span class="sxs-lookup"><span data-stu-id="683ba-126">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="683ba-127">*完全权限* - 此角色非常适合应具有学生和其他教职员工成员的完全访问权限的教师。</span><span class="sxs-lookup"><span data-stu-id="683ba-127">*Full permissions* – This role is ideal for educators who should have full access to students and other staff members.</span></span> <span data-ttu-id="683ba-128">他们可以开始与环境中的任何用户聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-128">They can start chats with any user within your environment.</span></span> <span data-ttu-id="683ba-129">具有完全权限的用户应监督他们参与的聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-129">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="683ba-130">他们不能离开或从他们启动的聊天或他们在联合租户中监督的聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="683ba-130">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="683ba-131">*受限权限* - 此角色非常适合仅对学生拥有监督访问权限且对其他教职员工和教师具有完全访问权限的员工。</span><span class="sxs-lookup"><span data-stu-id="683ba-131">*Limited permissions* – This role is ideal for staff members who should only have supervised access to students and have full access to other staff and educators.</span></span> <span data-ttu-id="683ba-132">他们可以开始与任何完整或受限用户聊天，但不能开始与受限用户聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-132">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="683ba-133">如果具有完全权限的用户开始与受限用户聊天，可以将受限用户带到对话中。</span><span class="sxs-lookup"><span data-stu-id="683ba-133">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="683ba-134">发生此访问的原因是具有完全权限的用户可以监督受限和受限用户之间的协作。</span><span class="sxs-lookup"><span data-stu-id="683ba-134">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="683ba-135">*受限权限* - 此角色非常适合需要监督的学生。</span><span class="sxs-lookup"><span data-stu-id="683ba-135">*Restricted permissions* – This role is ideal for students who need to be supervised.</span></span> <span data-ttu-id="683ba-136">他们只能与具有完全权限的用户开始聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-136">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="683ba-137">他们可以参与具有完全权限的用户邀请他们参与的任何对话。</span><span class="sxs-lookup"><span data-stu-id="683ba-137">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="683ba-138">在联合聊天案例中，只有具有完全权限的用户（来自受限用户的租户）才能将受限用户添加到聊天中。</span><span class="sxs-lookup"><span data-stu-id="683ba-138">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="683ba-139">若要设置用户的聊天权限角色，请使用在 Teams管理门户的消息策略选项内找到的"聊天权限"角色策略。</span><span class="sxs-lookup"><span data-stu-id="683ba-139">To set your users’ chat permission role, use the **Chat permissions** **role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="683ba-140">可以使用 PowerShell 通过 ChatPermissionRole 策略定义角色，其值为 Full、Limited 或 Restricted。</span><span class="sxs-lookup"><span data-stu-id="683ba-140">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="683ba-141">此策略位于 CsTeamsMessagingPolicy 下。</span><span class="sxs-lookup"><span data-stu-id="683ba-141">This policy is under CsTeamsMessagingPolicy.</span></span>

<span data-ttu-id="683ba-142">详细了解设置。</span><span class="sxs-lookup"><span data-stu-id="683ba-142">To learn more about setting.</span></span> <span data-ttu-id="683ba-143">Teams 策略请参阅适用于教育的 Teams 策略和策略包和向大量用户分配策略指南。</span><span class="sxs-lookup"><span data-stu-id="683ba-143">Teams policies see Teams policies and policy packages for Education and Assign policies to large sets of users guides.</span></span>

<span data-ttu-id="683ba-144">无法将角色分配给租户中的来宾。</span><span class="sxs-lookup"><span data-stu-id="683ba-144">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="683ba-145">为来宾分配受限角色。</span><span class="sxs-lookup"><span data-stu-id="683ba-145">Guests are assigned the limited role.</span></span>

### <a name="allow-supervised-chat"></a><span data-ttu-id="683ba-146">允许监督聊天</span><span class="sxs-lookup"><span data-stu-id="683ba-146">Allow supervised chat</span></span>

<span data-ttu-id="683ba-147">默认情况下，你的租户禁用了监督聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-147">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="683ba-148">为用户设置聊天权限角色后，可以通过访问"组织范围的设置""Teams 设置"，将"基于角色的聊天权限策略"设置为"开"，在租户中启用监督式 &gt; *聊天。* </span><span class="sxs-lookup"><span data-stu-id="683ba-148">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** &gt; **Teams Settings** and setting **Role-based chat permissions** policy to *On.*</span></span> <span data-ttu-id="683ba-149">还可将 AllowRoleBasedChatPermissions 设置为 True，使用 PowerShell 启用监督式聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-149">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="683ba-150">此 cmdlet 位于 CsTeamsClientConfiguration 下。</span><span class="sxs-lookup"><span data-stu-id="683ba-150">This cmdlet is under CsTeamsClientConfiguration.</span></span>

<span data-ttu-id="683ba-151">必须为租户中的所有用户启用监督聊天，并且不能仅为部分用户启用。</span><span class="sxs-lookup"><span data-stu-id="683ba-151">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

### <a name="enable-chat"></a><span data-ttu-id="683ba-152">启用聊天</span><span class="sxs-lookup"><span data-stu-id="683ba-152">Enable chat</span></span>

<span data-ttu-id="683ba-153">使用 Teams 管理中心提供的现有聊天策略为所有用户启用聊天。</span><span class="sxs-lookup"><span data-stu-id="683ba-153">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

## <a name="maintain-supervised-chats"></a><span data-ttu-id="683ba-154">维护监督聊天</span><span class="sxs-lookup"><span data-stu-id="683ba-154">Maintain supervised chats</span></span>

<span data-ttu-id="683ba-155">最初启用监督聊天后，需要执行一些操作以确保环境中聊天保持监督状态：</span><span class="sxs-lookup"><span data-stu-id="683ba-155">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="683ba-156">向加入租户的任何新用户分配相应的角色。</span><span class="sxs-lookup"><span data-stu-id="683ba-156">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="683ba-157">默认情况下，将为用户分配受限角色。</span><span class="sxs-lookup"><span data-stu-id="683ba-157">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="683ba-158">如果拥有完全权限的用户离开或从租户中删除，他们监督的聊天将无人参与。</span><span class="sxs-lookup"><span data-stu-id="683ba-158">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="683ba-159">删除原始用户之前，请确保向这些对话添加具有完全权限的另一个用户，以便聊天可以保持监督状态。</span><span class="sxs-lookup"><span data-stu-id="683ba-159">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="683ba-160">删除原始监督者后，无法将新参与者添加到对话中，但当前参与者可以继续通信。</span><span class="sxs-lookup"><span data-stu-id="683ba-160">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="683ba-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="683ba-161">Related topics</span></span>

[<span data-ttu-id="683ba-162">教育中 Teams 的监督聊天</span><span class="sxs-lookup"><span data-stu-id="683ba-162">Supervised chats for Teams in education</span></span>](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
