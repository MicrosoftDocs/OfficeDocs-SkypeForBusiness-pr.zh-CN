---
title: Microsoft Teams 预览中的信息障碍
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/01/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: 了解信息障碍及其对团队的影响。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a9c896e7131dfcd1a510a39712759fd8143fe3f
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418285"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a><span data-ttu-id="d329f-103">Microsoft Teams 预览中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="d329f-103">Information barriers in Microsoft Teams preview</span></span>

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

<span data-ttu-id="d329f-104">信息屏障是管理员可以配置以防止个人或组相互通信的策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-104">Information barriers are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="d329f-105">例如, 如果一个部门处理的信息不应与其他部门共享, 或者需要防止或独立地与该组外的任何人进行通信, 则这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="d329f-105">This is useful if, for example, one department is handling information that shouldn’t be shared with other departments or a group needs to be prevented, or isolated, from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="d329f-106">不能跨租户创建信息障碍组。</span><span class="sxs-lookup"><span data-stu-id="d329f-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="d329f-107">版本1不支持使用机器人添加用户。</span><span class="sxs-lookup"><span data-stu-id="d329f-107">Using bots to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="d329f-108">信息障碍版本1不包括对 SharePoint 和 OneDrive for business 的支持。</span><span class="sxs-lookup"><span data-stu-id="d329f-108">Information barriers version 1 doesn't include support for SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="d329f-109">我们正在努力在 SharePoint 中启用该功能, 并将在其可用后进行通信。</span><span class="sxs-lookup"><span data-stu-id="d329f-109">We are working on enabling the feature in SharePoint and will communicate once it's available.</span></span>

<span data-ttu-id="d329f-110">信息屏障策略还可防止查找和发现。</span><span class="sxs-lookup"><span data-stu-id="d329f-110">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="d329f-111">这意味着, 如果你尝试与不应与之通信的人员进行通信, 你将在人员选取器中找不到该用户。</span><span class="sxs-lookup"><span data-stu-id="d329f-111">This means that if you attempt to communicate with someone you should not be communicating with, you will not find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="d329f-112">背景</span><span class="sxs-lookup"><span data-stu-id="d329f-112">Background</span></span>

<span data-ttu-id="d329f-113">信息障碍的主要驱动因素来自金融服务行业。</span><span class="sxs-lookup"><span data-stu-id="d329f-113">The primary driver for Information Barriers comes from the financial services industry.</span></span> <span data-ttu-id="d329f-114">金融行业监管机构 ([FINRA]( http://www.finra.org)) 检查成员公司内的信息障碍和利益冲突, 并提供有关如何管理此类冲突 (FINRA 2241、[债务研究机构声明 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)) 的指导。</span><span class="sxs-lookup"><span data-stu-id="d329f-114">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

## <a name="when-should-i-use-information-barriers"></a><span data-ttu-id="d329f-115">何时应使用信息障碍？</span><span class="sxs-lookup"><span data-stu-id="d329f-115">When should I use information barriers?</span></span>

<span data-ttu-id="d329f-116">您可能希望在类似情况下使用信息障碍:</span><span class="sxs-lookup"><span data-stu-id="d329f-116">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="d329f-117">必须阻止团队与特定其他团队进行通信或共享数据。</span><span class="sxs-lookup"><span data-stu-id="d329f-117">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="d329f-118">团队不得与团队外部的任何人通信或与之共享数据。</span><span class="sxs-lookup"><span data-stu-id="d329f-118">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="d329f-119">信息屏障策略评估服务确定通信是否符合信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-119">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span> 

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="d329f-120">管理信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="d329f-120">Managing information barrier policies</span></span>

<span data-ttu-id="d329f-121">信息屏障策略通过安全 & 合规性中心 (SCC) PowerShell cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="d329f-121">Information barrier policies are managed with Security & Compliance Center (SCC) PowerShell cmdlets.</span></span> <span data-ttu-id="d329f-122">有关使用这些 cmdlet 的详细信息, 请参阅[定义信息障碍 (预览版) 策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="d329f-122">For more information about using these cmdlets, see [Define policies for information barriers (Preview)](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d329f-123">在设置或定义策略之前,**必须在 Microsoft 团队中启用范围的目录搜索**。</span><span class="sxs-lookup"><span data-stu-id="d329f-123">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="d329f-124">在为信息障碍设置或定义策略之前, 在启用范围目录搜索后至少等待24小时。</span><span class="sxs-lookup"><span data-stu-id="d329f-124">Wait at least 24 hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="d329f-125">信息障碍管理员角色</span><span class="sxs-lookup"><span data-stu-id="d329f-125">Information barriers administrator role</span></span>

<span data-ttu-id="d329f-126">信息屏障管理员角色 (IB 合规性管理) 负责管理信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-126">The information barriers administrator role (IB Compliance Management) is responsible for managing information barrier policies.</span></span> <span data-ttu-id="d329f-127">有关此角色的详细信息, 请参阅[Office 365 安全 & 合规中心中的权限](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="d329f-127">For more information about this role, see [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="when-are-information-barrier-policies-checked"></a><span data-ttu-id="d329f-128">何时检查信息障碍策略？</span><span class="sxs-lookup"><span data-stu-id="d329f-128">When are information barrier policies checked?</span></span>

<span data-ttu-id="d329f-129">当以下团队事件发生时, 将检查信息障碍策略:</span><span class="sxs-lookup"><span data-stu-id="d329f-129">Information barrier policies are checked when the following Teams events take place:</span></span>

- <span data-ttu-id="d329f-130">将**成员添加到团队**-每当您将用户添加到团队时, 用户的策略必须根据其他团队成员的信息屏障策略进行评估。</span><span class="sxs-lookup"><span data-stu-id="d329f-130">**Members are added to a team** - Whenever you add a user to a team, the user’s policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="d329f-131">成功添加用户后, 用户可以执行团队中的所有功能, 而无需进一步检查。</span><span class="sxs-lookup"><span data-stu-id="d329f-131">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="d329f-132">如果用户的策略阻止将他们添加到团队, 则该用户将不会显示在 "搜索" 中。</span><span class="sxs-lookup"><span data-stu-id="d329f-132">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>
- <span data-ttu-id="d329f-133">**请求新的聊天**-每次在两个或更多用户之间请求新的聊天时, 将对聊天进行评估以确保它不违反任何信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-133">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn’t violating any information barrier policies.</span></span> <span data-ttu-id="d329f-134">如果对话违反了 "信息屏障" 策略, 则不会启动对话。</span><span class="sxs-lookup"><span data-stu-id="d329f-134">If the conversation violates an information barrier policy, then the conversation isn’t initiated.</span></span>
- <span data-ttu-id="d329f-135">**邀请用户加入会议**-当用户被邀请加入会议时, 将根据其他团队成员的策略评估用户的策略, 如果发生冲突, 则不允许用户加入会议中。。</span><span class="sxs-lookup"><span data-stu-id="d329f-135">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there’s a violation, the user will not be allowed to join the meeting.</span></span>
- <span data-ttu-id="d329f-136">**在两个或更多用户之间共享屏幕**-无论何时在两个或更多用户之间共享屏幕, 都必须评估屏幕共享以确保它不违反其他用户的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-136">**A screen is shared between two or more users** - Any time a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn’t violate the information barrier policies of other users.</span></span> <span data-ttu-id="d329f-137">如果违反了信息障碍策略, 则不允许使用屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="d329f-137">If an information barrier policy is violated, the screen share won’t be allowed.</span></span>
- <span data-ttu-id="d329f-138">**用户在团队中放置电话呼叫 (VOIP)** -只要用户向另一个用户或一组用户发起语音呼叫, 就会评估呼叫以确保它不违反其他团队成员的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-138">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn’t violate the information barrier policies of other team members.</span></span> <span data-ttu-id="d329f-139">如果存在任何冲突, 将阻止语音通话。</span><span class="sxs-lookup"><span data-stu-id="d329f-139">If there is any violation, the voice call is blocked.</span></span>

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a><span data-ttu-id="d329f-140">更改策略时对现有聊天线程有何影响？</span><span class="sxs-lookup"><span data-stu-id="d329f-140">What happens to existing chat threads when a policy is changed?</span></span>

<span data-ttu-id="d329f-141">当信息屏障策略管理员对策略进行更改, 或者由于对用户配置文件 (如作业更改或类似原因) 的更改而导致策略更改生效时, 信息屏障策略评估服务将自动搜索成员以确保团队成员不违反任何策略。</span><span class="sxs-lookup"><span data-stu-id="d329f-141">When the information barrier policy admin makes changes to a policy, or a policy change kicks into effect because of a change to a user’s profile (such as for a job change or a similar reason), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span>

<span data-ttu-id="d329f-142">如果用户之间已有聊天或其他通信, 并且已设置新策略或更改了现有策略, 则该服务将评估现有通信, 以确保仍允许进行通信。</span><span class="sxs-lookup"><span data-stu-id="d329f-142">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="d329f-143">**1:1 聊天**-如果不再允许两个用户之间的通信 (如果策略阻止通信被应用到一个或两个用户), 则将阻止进一步通信, 并且聊天对话将变为只读。</span><span class="sxs-lookup"><span data-stu-id="d329f-143">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span>
- <span data-ttu-id="d329f-144">**群组聊天**-如果不再允许从一个用户到组的通信 (例如, 如果用户更改了作业), 则用户和其他违反该策略的用户可能会从群组聊天中删除, 而与组的进一步通信将不会被有.</span><span class="sxs-lookup"><span data-stu-id="d329f-144">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="d329f-145">用户仍然可以查看旧对话 (该对话将为只读), 但无法查看或参与与组的任何新对话。</span><span class="sxs-lookup"><span data-stu-id="d329f-145">The user can still see old conversations (which will be read-only), but will not be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="d329f-146">如果新的或已更改的策略阻止通信被应用到多个用户, 则受该策略影响的用户可能会从群组聊天中被删除。</span><span class="sxs-lookup"><span data-stu-id="d329f-146">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="d329f-147">他们仍然可以看到旧的对话。</span><span class="sxs-lookup"><span data-stu-id="d329f-147">They can still see old conversations.</span></span> 
- <span data-ttu-id="d329f-148">**团队**-已从组中删除的任何用户都将从团队中删除, 并且将无法查看或参与现有对话或新对话。</span><span class="sxs-lookup"><span data-stu-id="d329f-148">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="what-will-users-experience-if-another-user-is-blocked"></a><span data-ttu-id="d329f-149">如果其他用户被阻止, 用户会遇到什么情况？</span><span class="sxs-lookup"><span data-stu-id="d329f-149">What will users experience if another user is blocked?</span></span>

<span data-ttu-id="d329f-150">当前, 如果信息屏障策略阻止其他用户, 则用户会遇到以下情况:</span><span class="sxs-lookup"><span data-stu-id="d329f-150">Currently, users experience the following if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="d329f-151">"**人员" 选项卡**-用户可能会在 "**人员**" 选项卡上看到某些被阻止的用户。用户可以选择被阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="d329f-151">**People tab** - A user may see some blocked users on the **People** tab. The user can select the blocked users.</span></span>
- <span data-ttu-id="d329f-152">**"活动" 选项卡**-如果用户访问被阻止用户的 "**活动**" 选项卡, 则不会显示任何帖子。</span><span class="sxs-lookup"><span data-stu-id="d329f-152">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="d329f-153">("**活动**" 选项卡仅显示频道发布, 在两个用户之间不存在任何公共频道。)</span><span class="sxs-lookup"><span data-stu-id="d329f-153">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>
- <span data-ttu-id="d329f-154">**组织结构图**-如果用户访问显示被阻止的用户的组织结构图, 用户将在图表上看到被阻止的用户, 并且可以单击图表上的 "操作", 但操作 (如 "调用") 将不会执行。</span><span class="sxs-lookup"><span data-stu-id="d329f-154">**Org charts** - If a user accesses an org chart on which a blocked user appears, the user will see the blocked user on the chart and can click actions on the chart, but the actions (such as calling) will not go through.</span></span>
- <span data-ttu-id="d329f-155">**人员卡片**-如果用户参与对话, 后来被阻止, 其他用户仍然可以看到被阻止用户看到的人员卡。</span><span class="sxs-lookup"><span data-stu-id="d329f-155">**People card** - If a user participates in a conversation and is subsequently blocked, other users can still see the people card for the blocked user.</span></span> <span data-ttu-id="d329f-156">卡片上列出的所有操作 (如 "通话和聊天") 都将可用, 但操作将不会继续。</span><span class="sxs-lookup"><span data-stu-id="d329f-156">All actions listed on the card (such as calling and chat) will be available, but the actions will not go through.</span></span>
- <span data-ttu-id="d329f-157">**建议的联系人**-在 "建议的联系人" 列表 (为新用户显示的初始联系人列表) 中, 用户可以看到所有建议的联系人 (包括被阻止的用户)。</span><span class="sxs-lookup"><span data-stu-id="d329f-157">**Suggested contacts** - On the suggested contacts list (the initial contact list that appears for new users), users can see all suggested contacts (including blocked users).</span></span> <span data-ttu-id="d329f-158">但是, 如果用户单击被阻止的用户的名称以打开 "聊天" 窗格, 则邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="d329f-158">However, if a user clicks the name of a blocked user to open the Chats pane, the message will be blocked.</span></span>
- <span data-ttu-id="d329f-159">**聊天联系人**-用户可以在聊天联系人列表中看到被阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="d329f-159">**Chat contacts** - A user can see blocked users on the chat contact list.</span></span>
- <span data-ttu-id="d329f-160">**呼叫联系人**-用户可以在呼叫联系人列表中看到被阻止的用户, 并且将显示呼叫和消息等操作, 但当用户尝试呼叫或向被阻止的用户发送消息时, 呼叫或消息将不会发送。</span><span class="sxs-lookup"><span data-stu-id="d329f-160">**Calls contacts** - A user can see blocked users on the calls contact list and actions such as calling and messaging will appear, but when the user tries to call or send a message to the blocked user, the call or message will not go through.</span></span>
- <span data-ttu-id="d329f-161">**Skype 到团队迁移**-在 Skype for Business 到团队迁移期间, 所有用户 (甚至是信息屏障策略阻止的用户) 都将迁移到团队, 然后按照上述说明进行处理。</span><span class="sxs-lookup"><span data-stu-id="d329f-161">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

<span data-ttu-id="d329f-162">即将推出: 如果信息障碍策略阻止另一个用户, 则用户将会遇到以下情况:</span><span class="sxs-lookup"><span data-stu-id="d329f-162">Coming soon: users will experience the following if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="d329f-163">"**人员" 选项卡**-用户在 "**人员**" 选项卡上看不到被阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="d329f-163">**People tab** - A user cannot see blocked users on the **People** tab.</span></span>
- <span data-ttu-id="d329f-164">**"活动" 选项卡**-如果用户访问被阻止用户的 "**活动**" 选项卡, 则不会显示任何帖子。</span><span class="sxs-lookup"><span data-stu-id="d329f-164">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="d329f-165">("**活动**" 选项卡仅显示频道发布, 在两个用户之间不存在任何公共频道。)</span><span class="sxs-lookup"><span data-stu-id="d329f-165">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>
- <span data-ttu-id="d329f-166">**组织结构图**-如果用户访问的组织结构图中出现被阻止的用户, 则被阻止的用户将不会显示在组织结构图中, 并且将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="d329f-166">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user will not appear on the org chart and an error message will appear instead.</span></span>
- <span data-ttu-id="d329f-167">**人员卡片**-如果用户参与对话, 随后被阻止, 则其他用户将在其悬停在阻止用户的名称上时看到错误消息, 而不是人员卡。</span><span class="sxs-lookup"><span data-stu-id="d329f-167">**People card** - If a user participates in a conversation and the user is subsequently blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="d329f-168">卡片上列出的操作 (如通话和聊天) 将不可用。</span><span class="sxs-lookup"><span data-stu-id="d329f-168">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>
- <span data-ttu-id="d329f-169">**建议的联系人**-阻止的用户不会显示在 "建议的联系人" 列表中 (为新用户显示的初始联系人列表)。</span><span class="sxs-lookup"><span data-stu-id="d329f-169">**Suggested contacts** - Blocked users do not appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>
- <span data-ttu-id="d329f-170">**聊天联系人**-用户在聊天联系人列表中看不到被阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="d329f-170">**Chat contacts** - A user cannot see blocked users on the chat contact list.</span></span>
- <span data-ttu-id="d329f-171">**呼叫联系人**-用户可以在通话联系人列表中看到被阻止的用户, 但将标识被阻止的用户, 并且用户唯一可以执行的操作是将其删除。</span><span class="sxs-lookup"><span data-stu-id="d329f-171">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span>
- <span data-ttu-id="d329f-172">**Skype 到团队迁移**-在 Skype for Business 到团队迁移期间, 所有用户 (甚至是信息屏障策略阻止的用户) 都将迁移到团队, 然后按照上述说明进行处理。</span><span class="sxs-lookup"><span data-stu-id="d329f-172">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="d329f-173">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="d329f-173">Required licenses and permissions</span></span>

<span data-ttu-id="d329f-174">目前, 信息障碍功能位于公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="d329f-174">Currently, the information barrier features are in public preview.</span></span> <span data-ttu-id="d329f-175">当这些功能通常可用时, 它们将包含在套餐中, 例如:</span><span class="sxs-lookup"><span data-stu-id="d329f-175">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="d329f-176">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d329f-176">Microsoft 365 E5</span></span>
- <span data-ttu-id="d329f-177">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="d329f-177">Office 365 E5</span></span>
- <span data-ttu-id="d329f-178">Office 365 高级合规性</span><span class="sxs-lookup"><span data-stu-id="d329f-178">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="d329f-179">Microsoft 365 E5 合规性</span><span class="sxs-lookup"><span data-stu-id="d329f-179">Microsoft 365 E5 Compliance</span></span>

<span data-ttu-id="d329f-180">有关详细信息 (包括计划和定价), 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="d329f-180">For more details, including plans and pricing, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).</span></span>

## <a name="more-information"></a><span data-ttu-id="d329f-181">详细信息</span><span class="sxs-lookup"><span data-stu-id="d329f-181">More information</span></span>

- <span data-ttu-id="d329f-182">若要了解有关信息障碍的详细信息, 请参阅[信息障碍 (预览版)](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="d329f-182">To learn more about information barriers, see [Information barriers (Preview)](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="d329f-183">若要设置信息障碍策略, 请参阅[定义信息障碍策略 (预览版)](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="d329f-183">To set up information barrier policies, see [Define policies for information barriers (Preview)](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)</span></span>
