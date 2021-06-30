---
title: 对非教育租户使用监督式聊天
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
description: 了解非教育性租户在会议中进行Microsoft Teams聊天。
ms.openlocfilehash: 9d3e7707632a384f82a89a965f6db51f786f9d66
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203722"
---
# <a name="supervised-chats-for-non-educational-tenants"></a><span data-ttu-id="21bff-103">非教育租户的监督式聊天</span><span class="sxs-lookup"><span data-stu-id="21bff-103">Supervised chats for non-educational tenants</span></span>

<span data-ttu-id="21bff-104">监督式聊天允许指定的主管启动与组织中任何人的聊天，并阻止受限用户启动新聊天，除非有合适的主管。</span><span class="sxs-lookup"><span data-stu-id="21bff-104">Supervised chat allows designated supervisors to initiate chats with anyone in their organization and blocks restricted users from starting new chats unless an appropriate supervisor is present.</span></span> <span data-ttu-id="21bff-105">启用聊天监督后，主管不允许离开聊天，不允许其他参与者删除聊天，从而确保涉及受限用户的聊天受到适当的监管。</span><span class="sxs-lookup"><span data-stu-id="21bff-105">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving restricted users are properly supervised.</span></span>

<span data-ttu-id="21bff-106">这些限制仅适用于在完全启用监督聊天后创建的新私人聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-106">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="21bff-107">它们不适用于现有私人聊天、会议聊天或频道。</span><span class="sxs-lookup"><span data-stu-id="21bff-107">They don't apply to existing private chats, meetings chats, or channels.</span></span>

<span data-ttu-id="21bff-108">监督式聊天是专门针对教育机构需求定制的，但也可供非教育租户使用。</span><span class="sxs-lookup"><span data-stu-id="21bff-108">Supervised chat is tailored for educational institution needs, but it is also available to non-educational tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="21bff-109">监督聊天保护在强制实施该功能后创建的新聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-109">Supervised chat protects new chats created after the feature is enforced.</span></span> <span data-ttu-id="21bff-110">它不会保护现有聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-110">It doesn't protect existing chats.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="21bff-111">启用监督聊天</span><span class="sxs-lookup"><span data-stu-id="21bff-111">Enable supervised chat</span></span>

> [!NOTE]
> <span data-ttu-id="21bff-112">在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不需要的受限用户访问不受监督的聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-112">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted restricted user access to unsupervised chats.</span></span>

<span data-ttu-id="21bff-113">**为环境中每个用户定义聊天权限角色**</span><span class="sxs-lookup"><span data-stu-id="21bff-113">**Define chat permission roles for each user in your environment**</span></span>

<span data-ttu-id="21bff-114">要正常使用监督聊天，需要为环境中每个用户分配正确的聊天权限角色。</span><span class="sxs-lookup"><span data-stu-id="21bff-114">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="21bff-115">用户可以分配三个角色：</span><span class="sxs-lookup"><span data-stu-id="21bff-115">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="21bff-116">完全权限：此角色应分配给环境中聊天主管。</span><span class="sxs-lookup"><span data-stu-id="21bff-116">Full permissions: This role should be assigned to the chat supervisors in your environment.</span></span> <span data-ttu-id="21bff-117">他们可以开始与环境中的任何用户聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-117">They can start chats with any user within your environment.</span></span> <span data-ttu-id="21bff-118">具有完全权限的用户应监督他们参与的聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-118">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="21bff-119">他们不能离开或从他们启动的聊天或他们在联合租户中监督的聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="21bff-119">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="21bff-120">受限权限：此角色非常适合仅对受限用户拥有监督访问权限的员工成员。</span><span class="sxs-lookup"><span data-stu-id="21bff-120">Limited permissions: This role is ideal for staff members who should only have supervised access to restricted users.</span></span> <span data-ttu-id="21bff-121">他们可以开始与任何完整或受限用户聊天，但不能开始与受限用户聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-121">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="21bff-122">如果具有完全权限的用户开始与受限用户聊天，可以将受限用户带到对话中。</span><span class="sxs-lookup"><span data-stu-id="21bff-122">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="21bff-123">发生此访问的原因是具有完全权限的用户可以监督受限和受限用户之间的协作。</span><span class="sxs-lookup"><span data-stu-id="21bff-123">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="21bff-124">受限权限：此角色非常适合需要监督的用户。</span><span class="sxs-lookup"><span data-stu-id="21bff-124">Restricted permissions: This role is ideal for users who need to be supervised.</span></span> <span data-ttu-id="21bff-125">他们只能与具有完全权限的用户开始聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-125">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="21bff-126">他们可以参与具有完全权限的用户邀请他们参与的任何对话。</span><span class="sxs-lookup"><span data-stu-id="21bff-126">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="21bff-127">在联合聊天案例中，只有具有完全权限的用户（来自受限用户的租户）才能将受限用户添加到聊天中。</span><span class="sxs-lookup"><span data-stu-id="21bff-127">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="21bff-128">若要设置用户的聊天权限角色，请使用管理员门户中消息策略选项内找到的聊天权限Teams策略。</span><span class="sxs-lookup"><span data-stu-id="21bff-128">To set your users’ chat permission role, use the **Chat permissions role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="21bff-129">可以使用 PowerShell 通过 ChatPermissionRole 策略定义角色，其值为 Full、Limited 或 Restricted。</span><span class="sxs-lookup"><span data-stu-id="21bff-129">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="21bff-130">此策略位于 [CsTeamsMessagingPolicy 下](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="21bff-130">This policy is under [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>

<span data-ttu-id="21bff-131">无法将角色分配给租户中的来宾。</span><span class="sxs-lookup"><span data-stu-id="21bff-131">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="21bff-132">为来宾分配受限角色。</span><span class="sxs-lookup"><span data-stu-id="21bff-132">Guests are assigned the limited role.</span></span>

## <a name="allow-supervised-chat"></a><span data-ttu-id="21bff-133">允许监督聊天</span><span class="sxs-lookup"><span data-stu-id="21bff-133">Allow supervised chat</span></span>

<span data-ttu-id="21bff-134">默认情况下，你的租户禁用了监督聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-134">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="21bff-135">为用户设置聊天权限角色后，可以通过访问组织范围的设置 Teams 设置 将基于角色的聊天权限策略设置为"开  >  **"，** 在租户中启用监督式 **聊天**。</span><span class="sxs-lookup"><span data-stu-id="21bff-135">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** > **Teams Settings** and setting **Role-based chat permissions** policy to **On**.</span></span> <span data-ttu-id="21bff-136">还可将 AllowRoleBasedChatPermissions 设置为 True，使用 PowerShell 启用监督式聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-136">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="21bff-137">此 cmdlet 位于 [CsTeamsClientConfiguration 下](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="21bff-137">This cmdlet is under [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).</span></span>

<span data-ttu-id="21bff-138">必须为租户中的所有用户启用监督聊天，并且不能仅为部分用户启用。</span><span class="sxs-lookup"><span data-stu-id="21bff-138">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

<span data-ttu-id="21bff-139">**启用聊天**</span><span class="sxs-lookup"><span data-stu-id="21bff-139">**Enable chat**</span></span>

<span data-ttu-id="21bff-140">使用管理中心内提供的现有聊天策略为所有用户Teams聊天。</span><span class="sxs-lookup"><span data-stu-id="21bff-140">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

<span data-ttu-id="21bff-141">**维护监督聊天**</span><span class="sxs-lookup"><span data-stu-id="21bff-141">**Maintain supervised chats**</span></span>

<span data-ttu-id="21bff-142">最初启用监督聊天后，需要执行一些操作以确保环境中聊天保持监督状态：</span><span class="sxs-lookup"><span data-stu-id="21bff-142">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="21bff-143">向加入租户的任何新用户分配相应的角色。</span><span class="sxs-lookup"><span data-stu-id="21bff-143">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="21bff-144">默认情况下，将为用户分配受限角色。</span><span class="sxs-lookup"><span data-stu-id="21bff-144">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="21bff-145">如果拥有完全权限的用户离开或从租户中删除，他们监督的聊天将无人参与。</span><span class="sxs-lookup"><span data-stu-id="21bff-145">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="21bff-146">删除原始用户之前，请确保向这些对话添加具有完全权限的另一个用户，以便聊天可以保持监督状态。</span><span class="sxs-lookup"><span data-stu-id="21bff-146">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="21bff-147">删除原始监督者后，无法将新参与者添加到对话中，但当前参与者可以继续通信。</span><span class="sxs-lookup"><span data-stu-id="21bff-147">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>
