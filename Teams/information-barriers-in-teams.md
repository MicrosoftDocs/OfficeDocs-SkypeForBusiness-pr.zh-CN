---
title: 在 Microsoft 团队预览中的信息障碍
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: 了解信息障碍及其如何影响团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71c547ac13f63c9357dfb6e8a0cbe34d748646d3
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827785"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a><span data-ttu-id="d1564-103">在 Microsoft 团队预览中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="d1564-103">Information barriers in Microsoft Teams preview</span></span>

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

<span data-ttu-id="d1564-104">信息的障碍是管理员可以配置为阻止个人或组进行相互进行通信的策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-104">Information barriers are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="d1564-105">如果，例如，一个部门处理不应与其他部门共享信息或一组需要被阻止与任何外部的联系人进行通信，这很有用。</span><span class="sxs-lookup"><span data-stu-id="d1564-105">This is useful if, for example, one department is handling information that shouldn’t be shared with other departments or a group needs to be prevented from communicating with any outside contacts.</span></span>

> [!NOTE]
> - <span data-ttu-id="d1564-106">不能跨租户创建信息障碍组。</span><span class="sxs-lookup"><span data-stu-id="d1564-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="d1564-107">版本 1 不支持使用自动程序添加用户。</span><span class="sxs-lookup"><span data-stu-id="d1564-107">Using bots to add users is not supported for version 1.</span></span>

<span data-ttu-id="d1564-108">信息障碍策略也阻止查找和发现。</span><span class="sxs-lookup"><span data-stu-id="d1564-108">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="d1564-109">这意味着，如果您尝试与某人不应与通信您进行通信，您将找不到该用户在人员选取器。</span><span class="sxs-lookup"><span data-stu-id="d1564-109">This means that if you attempt to communicate with someone you should not be communicating with, you will not find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="d1564-110">背景</span><span class="sxs-lookup"><span data-stu-id="d1564-110">Background</span></span>

<span data-ttu-id="d1564-111">信息的障碍的主驱动程序来自金融服务行业。</span><span class="sxs-lookup"><span data-stu-id="d1564-111">The primary driver for Information Barriers comes from the financial services industry.</span></span> <span data-ttu-id="d1564-112">金融行业监管机构 ([FINRA]( http://www.finra.org/)) 介绍信息障碍和利益冲突成员公司内，并提供了有关如何管理 （FINRA 2241，[偿还研究法规通知 15 31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)此类冲突指南。</span><span class="sxs-lookup"><span data-stu-id="d1564-112">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org/)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

## <a name="when-should-i-use-information-barriers"></a><span data-ttu-id="d1564-113">何时应使用信息障碍？</span><span class="sxs-lookup"><span data-stu-id="d1564-113">When should I use information barriers?</span></span>

<span data-ttu-id="d1564-114">您可能需要在以下情况下使用信息障碍：</span><span class="sxs-lookup"><span data-stu-id="d1564-114">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="d1564-115">团队必须防止通信或与某个特定共享数据其他团队。</span><span class="sxs-lookup"><span data-stu-id="d1564-115">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="d1564-116">团队必须不进行通信，或与团队之外的任何人共享数据。</span><span class="sxs-lookup"><span data-stu-id="d1564-116">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="d1564-117">信息障碍策略评估服务确定通信是否符合信息限制策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-117">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span> 

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="d1564-118">管理信息限制策略</span><span class="sxs-lookup"><span data-stu-id="d1564-118">Managing information barrier policies</span></span>

<span data-ttu-id="d1564-119">使用安全 & 合规性中心 (SCC) PowerShell cmdlet 管理信息限制策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-119">Information barrier policies are managed with Security & Compliance Center (SCC) PowerShell cmdlets.</span></span> <span data-ttu-id="d1564-120">有关使用这些 cmdlet，[此处注册](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d1564-120">For more information about using these cmdlets, [sign up here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1564-121">在设置或定义策略，**您必须启用的 Microsoft 团队中的作用域的目录搜索**。</span><span class="sxs-lookup"><span data-stu-id="d1564-121">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="d1564-122">等待至少 24 小时后启用作用域的目录搜索之前设置或定义信息障碍的策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-122">Wait at least 24 hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="d1564-123">信息的障碍管理员角色</span><span class="sxs-lookup"><span data-stu-id="d1564-123">Information barriers administrator role</span></span>

<span data-ttu-id="d1564-124">信息的障碍管理员角色负责管理信息限制策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-124">The information barriers administrator role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="d1564-125">有关此角色以及参与预览，[此处注册](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d1564-125">For more information about this role and to participate in the preview, [sign up here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).</span></span>

## <a name="when-are-information-barrier-policies-checked"></a><span data-ttu-id="d1564-126">何时检查信息障碍策略？</span><span class="sxs-lookup"><span data-stu-id="d1564-126">When are information barrier policies checked?</span></span>

<span data-ttu-id="d1564-127">以下团队事件发生时，会检查信息障碍策略：</span><span class="sxs-lookup"><span data-stu-id="d1564-127">Information barrier policies are checked when the following Teams events take place:</span></span>

- <span data-ttu-id="d1564-128">必须根据其他小组成员的信息限制策略来计算**成员添加到团队**-每当将用户添加到团队，用户的策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-128">**Members are added to a team** - Whenever you add a user to a team, the user’s policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="d1564-129">成功添加用户后，用户可以执行无进一步的检查团队中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="d1564-129">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="d1564-130">如果用户的策略阻止它们的添加到团队，用户不将会在搜索中显示。</span><span class="sxs-lookup"><span data-stu-id="d1564-130">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>
- <span data-ttu-id="d1564-131">**请求新的聊天**-每次新的聊天请求两个或多个用户之间聊天进行评估，以确保其不违反信息障碍的任何策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-131">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn’t violating any Information barrier policies.</span></span> <span data-ttu-id="d1564-132">如果对话违反信息障碍策略，然后对话未启动，并出现错误消息。</span><span class="sxs-lookup"><span data-stu-id="d1564-132">If the conversation violates an information barrier policy, then the conversation isn’t initiated, and an error message appears.</span></span>
- <span data-ttu-id="d1564-133">**邀请用户加入会议**的邀请用户加入会议、 计算用户的策略所依据的策略的其他小组成员，以及如果没有冲突，用户将不允许加入会议，并将看到一条错误消息时。</span><span class="sxs-lookup"><span data-stu-id="d1564-133">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there’s a violation, the user will not be allowed to join the meeting and will see an error message.</span></span>
- <span data-ttu-id="d1564-134">**两个或多个用户之间共享屏幕**的任何时间屏幕共享两个或多个用户之间，必须计算的屏幕共享以确保其不违反信息限制策略的其他用户。</span><span class="sxs-lookup"><span data-stu-id="d1564-134">**A screen is shared between two or more users** - Any time a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn’t violate the information barrier policies of other users.</span></span> <span data-ttu-id="d1564-135">如果违反了信息障碍策略，将不允许的屏幕共享，并显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="d1564-135">If an information barrier policy is violated, the screen share won’t be allowed, and an error message will appear.</span></span>
- <span data-ttu-id="d1564-136">**团队中的用户发出电话呼叫 (VOIP)** -语音呼叫由另一个用户或用户组，呼叫用户启动的任何时间计算以确保其不违反 oher 小组成员的信息限制策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-136">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn’t violate the information barrier policies of oher team members.</span></span> <span data-ttu-id="d1564-137">如果没有任何冲突，语音呼叫被阻止。</span><span class="sxs-lookup"><span data-stu-id="d1564-137">If there is any violation, the voice call is blocked.</span></span>

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a><span data-ttu-id="d1564-138">如果更改策略到现有聊天线程的怎么办？</span><span class="sxs-lookup"><span data-stu-id="d1564-138">What happens to existing chat threads when a policy is changed?</span></span>

<span data-ttu-id="d1564-139">当信息障碍策略管理对该策略进行更改或策略更改用于启动生效由于更改用户的作业或类似的原因，信息障碍策略评估服务自动搜索确保的成员团队成员没有违反的任何策略。</span><span class="sxs-lookup"><span data-stu-id="d1564-139">When the information  barrier policy admin makes changes to the policy or a policy change kicks into effect because of a user’s job changing or a similar reason, the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span> 

<span data-ttu-id="d1564-140">如果没有现有聊天或其他用户之间的通信和新的策略设置或更改现有策略，该服务将评估现有的通信，以确保，它们不"感染保留"（不再允许）：</span><span class="sxs-lookup"><span data-stu-id="d1564-140">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that they aren’t “poisoned” (no longer allowed):</span></span> 

- <span data-ttu-id="d1564-141">**1:1 聊天**-如果 （如果阻止通信的策略应用于一个或两个用户） 不再允许两个用户之间的通信、 进一步通信将被阻止和聊天会话将变为只读。</span><span class="sxs-lookup"><span data-stu-id="d1564-141">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span>
- <span data-ttu-id="d1564-142">**群聊**-如果 （例如，如果用户更改作业） 不再允许向组从一个用户的通信、 可能从群聊中删除违反策略的其他用户以及用户和组与进一步通信不会允许。</span><span class="sxs-lookup"><span data-stu-id="d1564-142">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="d1564-143">用户仍可以看到旧对话 （这将为只读），但不是能以查看或参与与组的任何新的对话。</span><span class="sxs-lookup"><span data-stu-id="d1564-143">The user can still see old conversations (which will be read-only), but will not be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="d1564-144">如果阻止了通信的新的或更改策略应用于多个用户，可能会影响该策略的用户删除从群聊。</span><span class="sxs-lookup"><span data-stu-id="d1564-144">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="d1564-145">他们仍可以看到旧的对话。</span><span class="sxs-lookup"><span data-stu-id="d1564-145">They can still see old conversations.</span></span> 
- <span data-ttu-id="d1564-146">**团队**-已从组中删除任何用户删除来自团队，并将不能查看或参与现有或新的对话。</span><span class="sxs-lookup"><span data-stu-id="d1564-146">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="d1564-147">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="d1564-147">Required licenses and permissions</span></span>

<span data-ttu-id="d1564-148">目前，信息障碍功能处于公共预览。</span><span class="sxs-lookup"><span data-stu-id="d1564-148">Currently, the information barrier features are in public preview.</span></span> <span data-ttu-id="d1564-149">这些功能通常可用时，它们将包含在订阅，例如：</span><span class="sxs-lookup"><span data-stu-id="d1564-149">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="d1564-150">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d1564-150">Microsoft 365 E5</span></span>
- <span data-ttu-id="d1564-151">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="d1564-151">Office 365 E5</span></span>
- <span data-ttu-id="d1564-152">Office 365 高级合规性</span><span class="sxs-lookup"><span data-stu-id="d1564-152">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="d1564-153">Microsoft 365 E5 合规性</span><span class="sxs-lookup"><span data-stu-id="d1564-153">Microsoft 365 E5 Compliance</span></span>

<span data-ttu-id="d1564-154">有关详细信息，包括计划和定价，请参阅[法规遵从性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="d1564-154">For more details, including plans and pricing, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).</span></span>
