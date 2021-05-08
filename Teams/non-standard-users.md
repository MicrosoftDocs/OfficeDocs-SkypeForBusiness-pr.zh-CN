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
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617845"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="d7c68-103">Microsoft Teams标准用户的应用行为</span><span class="sxs-lookup"><span data-stu-id="d7c68-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="d7c68-104">本文介绍当来宾Teams外部用户 (联合用户) 和匿名用户时，Teams的行为。</span><span class="sxs-lookup"><span data-stu-id="d7c68-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="d7c68-105">**来宾用户** 不是组织的员工、学生或成员。</span><span class="sxs-lookup"><span data-stu-id="d7c68-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="d7c68-106">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="d7c68-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="d7c68-107">外部 **(联合)** 用户属于另一个域，无法访问组织的团队或团队资源。</span><span class="sxs-lookup"><span data-stu-id="d7c68-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="d7c68-108">有关来宾用户与外部用户的详细比较， [请参阅与其他组织的用户通信](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="d7c68-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="d7c68-109">匿名 **用户** 是用户通过Teams加入会议的会议中的概念。</span><span class="sxs-lookup"><span data-stu-id="d7c68-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="d7c68-110">用户尚未使用其 Microsoft 或组织的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d7c68-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="d7c68-111">来宾用户访问</span><span class="sxs-lookup"><span data-stu-id="d7c68-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="d7c68-112">为来宾用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="d7c68-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="d7c68-113">来宾无法安装、更新或删除共享上下文中的应用，例如聊天、频道或会议。</span><span class="sxs-lookup"><span data-stu-id="d7c68-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="d7c68-114">他们可以使用消息扩展和直接链接在个人范围内安装、更新或删除应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="d7c68-115">来宾无法访问应用商店Teams应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7c68-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="d7c68-116">来宾用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="d7c68-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="d7c68-117">如果应用是由本机用户安装的，则来宾可以使用应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="d7c68-118">机器人可以主动向来宾用户发送消息，但来宾无法与机器人交互。</span><span class="sxs-lookup"><span data-stu-id="d7c68-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="d7c68-119">来宾无法向机器人发送消息 1：1、@ 提及机器人，或与与机器人通信的自适应卡交互。</span><span class="sxs-lookup"><span data-stu-id="d7c68-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="d7c68-120">来宾将遵循为任何应用的主机租户设置的全局和组织范围权限策略。</span><span class="sxs-lookup"><span data-stu-id="d7c68-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="d7c68-121">换言之，如果整个宿主组织阻止了应用，则来宾也不可能使用该应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="d7c68-122">设置策略不适用于来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d7c68-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="d7c68-123">这意味着默认策略中的管理员固定应用不会影响来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d7c68-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="d7c68-124">联合 (外部) 用户访问权限</span><span class="sxs-lookup"><span data-stu-id="d7c68-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="d7c68-125">为外部用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="d7c68-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="d7c68-126">外部用户无法在任何上下文中安装、更新或删除应用，例如个人、聊天、频道或会议。</span><span class="sxs-lookup"><span data-stu-id="d7c68-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="d7c68-127">他们无法访问应用商店Teams应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="d7c68-128">外部用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="d7c68-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="d7c68-129">外部用户不能使用任何Teams，并且当将外部用户添加到具有本机用户的上下文中时，所有用户（本机用户和外部用户）都无法再使用应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="d7c68-130">外部用户不会受到应用策略的影响，因为他们不能Teams应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="d7c68-131">会议访问中的匿名用户</span><span class="sxs-lookup"><span data-stu-id="d7c68-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="d7c68-132">为匿名用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="d7c68-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="d7c68-133">匿名用户无法安装、更新或删除会议中的应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="d7c68-134">匿名用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="d7c68-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="d7c68-135">匿名用户不能直接在会议中使用应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="d7c68-136">如果存在匿名用户，本机用户可以继续使用会议应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="d7c68-137">如果应用在聊天中发送自适应卡片，匿名用户可以与卡交互。有关详细信息，请参阅允许匿名 [用户加入会议](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。</span><span class="sxs-lookup"><span data-stu-id="d7c68-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card For more information, see [Allow anonymous users to join meetings](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="d7c68-138">匿名用户将继承用户级全局默认权限策略。</span><span class="sxs-lookup"><span data-stu-id="d7c68-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="d7c68-139">如果用户级权限策略已启用Teams，他们可以与会议中的应用交互。</span><span class="sxs-lookup"><span data-stu-id="d7c68-139">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="d7c68-140">匿名用户只能与已在会议中可用的应用交互，并且无法获取和/或管理这些应用。</span><span class="sxs-lookup"><span data-stu-id="d7c68-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
