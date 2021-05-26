---
title: Teams标准用户的应用行为
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解应用Microsoft Teams标准用户的行为方式。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50ab15d188f2f8a198f59446a0bd5fd8015d0c74
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656025"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="9ce67-103">Microsoft Teams标准用户的应用行为</span><span class="sxs-lookup"><span data-stu-id="9ce67-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="9ce67-104">本文介绍当来宾Teams外部用户 (联合用户) 和匿名用户时，Teams的行为。</span><span class="sxs-lookup"><span data-stu-id="9ce67-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="9ce67-105">**来宾用户** 不是组织的员工、学生或成员。</span><span class="sxs-lookup"><span data-stu-id="9ce67-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="9ce67-106">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="9ce67-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="9ce67-107">外部 **(联合)** 用户属于另一个域，无法访问组织的团队或团队资源。</span><span class="sxs-lookup"><span data-stu-id="9ce67-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="9ce67-108">有关来宾用户与外部用户的详细比较， [请参阅与其他组织的用户通信](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="9ce67-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="9ce67-109">匿名 **用户** 是用户通过Teams加入会议的会议中的概念。</span><span class="sxs-lookup"><span data-stu-id="9ce67-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="9ce67-110">用户尚未使用其 Microsoft 或组织的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9ce67-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="9ce67-111">来宾用户</span><span class="sxs-lookup"><span data-stu-id="9ce67-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="9ce67-112">为来宾用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="9ce67-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="9ce67-113">来宾无法安装、更新或删除应用到共享上下文（如聊天、频道或会议）中，但他们可以使用消息扩展和直接链接访问其个人范围。</span><span class="sxs-lookup"><span data-stu-id="9ce67-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="9ce67-114">来宾无法从桌面Teams访问 Teams应用商店，但可以使用直接链接访问它。</span><span class="sxs-lookup"><span data-stu-id="9ce67-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="9ce67-115">来宾用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="9ce67-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="9ce67-116">如果应用是由本机用户安装的，则来宾可以使用应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="9ce67-117">安装到通道的机器人</span><span class="sxs-lookup"><span data-stu-id="9ce67-117">Bots installed to a channel</span></span>

<span data-ttu-id="9ce67-118">机器人可以主动向来宾用户发送消息，但来宾无法与机器人交互。</span><span class="sxs-lookup"><span data-stu-id="9ce67-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="9ce67-119">来宾无法一对一地向机器人发送消息、提及机器人，或与与机器人通信的自适应卡交互。</span><span class="sxs-lookup"><span data-stu-id="9ce67-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="9ce67-120">使用策略安装的个人机器人</span><span class="sxs-lookup"><span data-stu-id="9ce67-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="9ce67-121">来宾将遵循为任何应用的主机租户设置的全局和组织范围权限策略。</span><span class="sxs-lookup"><span data-stu-id="9ce67-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="9ce67-122">如果整个主机组织阻止了应用，则来宾也不可能使用该应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="9ce67-123">还会为来宾安装全局默认应用设置策略中包含的任何机器人。</span><span class="sxs-lookup"><span data-stu-id="9ce67-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="9ce67-124">安装机器人后，机器人可以主动与来宾通信，来宾可以与机器人重新通信。</span><span class="sxs-lookup"><span data-stu-id="9ce67-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="9ce67-125">无法从全局默认应用设置策略中删除来宾。</span><span class="sxs-lookup"><span data-stu-id="9ce67-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="9ce67-126">若要避免来宾访问机器人，可以创建更多应用设置策略，将其分配给内部用户，然后使用自定义策略安装机器人。</span><span class="sxs-lookup"><span data-stu-id="9ce67-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="9ce67-127">外部 (联合) 用户</span><span class="sxs-lookup"><span data-stu-id="9ce67-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="9ce67-128">为外部用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="9ce67-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="9ce67-129">外部用户无法在任何上下文中安装、更新或删除应用，例如个人、聊天、频道或会议。</span><span class="sxs-lookup"><span data-stu-id="9ce67-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="9ce67-130">他们无法访问应用商店Teams应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="9ce67-131">外部用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="9ce67-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="9ce67-132">其他组织中的人员遵守托管组织的默认用户权限策略和组织范围的设置。</span><span class="sxs-lookup"><span data-stu-id="9ce67-132">People from other organizations adhere to the hosting organization's default user permission policy and org-wide settings.</span></span>
- <span data-ttu-id="9ce67-133">托管组织中的用户可以在与其他组织人员的会议聊天中添加应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="9ce67-134">其他组织中的人员不能在会议聊天中添加应用，但一旦添加到聊天中，就可以与机器人和选项卡进行交互。</span><span class="sxs-lookup"><span data-stu-id="9ce67-134">People from other organizations cannot add apps in meeting chats but can interact with bots and tabs once added to the chat.</span></span>
- <span data-ttu-id="9ce67-135">在聊天中安装机器人后，它可以主动与来自该聊天中其他组织的人通信，并且这些用户可以与机器人通信。</span><span class="sxs-lookup"><span data-stu-id="9ce67-135">After a bot is installed in a chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="9ce67-136">将应用托管组织的数据策略，以及该用户的组织共享的任何第三方应用的数据共享做法。</span><span class="sxs-lookup"><span data-stu-id="9ce67-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="9ce67-137">匿名用户</span><span class="sxs-lookup"><span data-stu-id="9ce67-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="9ce67-138">为匿名用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="9ce67-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="9ce67-139">匿名用户无法安装、更新或删除会议中的应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="9ce67-140">匿名用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="9ce67-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="9ce67-141">匿名用户不能直接在会议中使用应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="9ce67-142">如果存在匿名用户，本机用户可以继续使用会议应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="9ce67-143">如果应用在聊天中发送自适应卡，匿名用户可以与该卡交互。</span><span class="sxs-lookup"><span data-stu-id="9ce67-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="9ce67-144">有关详细信息，请阅读 [允许匿名用户加入会议](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。</span><span class="sxs-lookup"><span data-stu-id="9ce67-144">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="9ce67-145">匿名用户将继承用户级全局默认权限策略。</span><span class="sxs-lookup"><span data-stu-id="9ce67-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="9ce67-146">如果用户级权限策略已启用Teams，他们可以与会议中的应用交互。</span><span class="sxs-lookup"><span data-stu-id="9ce67-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="9ce67-147">匿名用户只能与已在会议中可用的应用交互，并且无法获取和/或管理这些应用。</span><span class="sxs-lookup"><span data-stu-id="9ce67-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
