---
title: 非标准用户的 Teams 应用行为
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解 Microsoft Teams 中的应用对于非标准用户的行为方式。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66754565737929ec9d34125ca421c7e3eed9fe65
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278542"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="736f6-103">非标准用户的 Microsoft Teams 应用行为</span><span class="sxs-lookup"><span data-stu-id="736f6-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="736f6-104">本文介绍 Teams 中的应用在来宾、外部 (联合) 和匿名用户存在于 Teams 上下文中时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="736f6-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="736f6-105">**来宾用户** 不是组织的员工、学生或成员。</span><span class="sxs-lookup"><span data-stu-id="736f6-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="736f6-106">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="736f6-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="736f6-107">联合 **(用户)** 属于另一个域，并且无法访问组织的团队或团队资源。</span><span class="sxs-lookup"><span data-stu-id="736f6-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="736f6-108">有关来宾与外部用户的更详细比较， [请参阅与其他组织的用户进行通信](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)。</span><span class="sxs-lookup"><span data-stu-id="736f6-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations).</span></span>

- <span data-ttu-id="736f6-109">匿名 **用户** 是 Teams 会议中用户通过链接加入会议的概念。</span><span class="sxs-lookup"><span data-stu-id="736f6-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="736f6-110">用户尚未使用其 Microsoft 或组织的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="736f6-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="736f6-111">来宾用户访问</span><span class="sxs-lookup"><span data-stu-id="736f6-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="736f6-112">为来宾用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="736f6-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="736f6-113">来宾无法安装、更新或删除共享上下文中的应用，例如聊天、频道或会议。</span><span class="sxs-lookup"><span data-stu-id="736f6-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="736f6-114">他们可以使用消息扩展和直接链接在个人范围内安装、更新或删除应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="736f6-115">来宾无法访问 Teams 应用商店。</span><span class="sxs-lookup"><span data-stu-id="736f6-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="736f6-116">来宾用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="736f6-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="736f6-117">如果应用是由本机用户安装的，则来宾可以使用应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="736f6-118">机器人可以主动向来宾用户发送消息，但来宾无法与机器人交互。</span><span class="sxs-lookup"><span data-stu-id="736f6-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="736f6-119">来宾无法 1：1 向机器人发送消息、@ 提及机器人，或者无法与与机器人通信的自适应卡交互。</span><span class="sxs-lookup"><span data-stu-id="736f6-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="736f6-120">来宾将遵循为任何应用的主机租户设置的全局和组织范围权限策略。</span><span class="sxs-lookup"><span data-stu-id="736f6-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="736f6-121">换言之，如果整个宿主组织阻止了应用，则来宾也不可能使用该应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="736f6-122">设置策略不适用于来宾用户。</span><span class="sxs-lookup"><span data-stu-id="736f6-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="736f6-123">这意味着默认策略中的管理员固定应用不会影响来宾用户。</span><span class="sxs-lookup"><span data-stu-id="736f6-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="736f6-124">外部 (联合) 用户访问</span><span class="sxs-lookup"><span data-stu-id="736f6-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="736f6-125">为外部用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="736f6-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="736f6-126">外部用户无法在任何上下文中安装、更新或删除应用，例如个人、聊天、频道或会议。</span><span class="sxs-lookup"><span data-stu-id="736f6-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="736f6-127">他们无法访问 Teams 应用商店。</span><span class="sxs-lookup"><span data-stu-id="736f6-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="736f6-128">外部用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="736f6-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="736f6-129">外部用户不能使用任何 Teams 应用，当将外部用户添加到具有本机用户的上下文中时，所有用户（本机用户和外部用户）都无法再使用应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="736f6-130">外部用户不会受到应用策略的影响，因为他们不能使用 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="736f6-131">会议访问中的匿名用户</span><span class="sxs-lookup"><span data-stu-id="736f6-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="736f6-132">为匿名用户安装、更新和删除</span><span class="sxs-lookup"><span data-stu-id="736f6-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="736f6-133">匿名用户无法安装、更新或删除会议中的应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="736f6-134">匿名用户的使用行为和策略</span><span class="sxs-lookup"><span data-stu-id="736f6-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="736f6-135">匿名用户不能直接在会议中使用应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="736f6-136">如果存在匿名用户，本机用户可以继续使用会议应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="736f6-137">如果应用在聊天中发送自适应卡，匿名用户可以与该卡交互。</span><span class="sxs-lookup"><span data-stu-id="736f6-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="736f6-138">匿名用户将继承用户级全局默认权限策略。</span><span class="sxs-lookup"><span data-stu-id="736f6-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="736f6-139">如果用户级别的权限策略已启用应用，此控件允许匿名用户与 Teams 会议中的应用交互。</span><span class="sxs-lookup"><span data-stu-id="736f6-139">This control allows anonymous users to interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="736f6-140">匿名用户只能与已在会议中可用的应用交互，并且无法获取和/或管理这些应用。</span><span class="sxs-lookup"><span data-stu-id="736f6-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
