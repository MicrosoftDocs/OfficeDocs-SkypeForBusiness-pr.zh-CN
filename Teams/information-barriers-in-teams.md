---
title: Microsoft 团队中的信息障碍
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: 本文介绍 Microsoft 团队中的哪些信息障碍以及他们如何影响团队。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce71f0c0f2621253698cd250372624ded638dcec
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083182"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="2a463-103">Microsoft 团队中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="2a463-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="2a463-104">信息障碍（IB）是管理员可以配置以防止个人或组相互通信的策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-104">Information barriers (IB) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="2a463-105">例如，如果一个部门处理的信息不应与其他部门共享，或者需要防止或独立地与该组外的任何人进行通信，则这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="2a463-105">This is useful if, for example, one department is handling information that shouldn't be shared with other departments or a group needs to be prevented, or isolated, from communicating with anyone outside of that group.</span></span>

> [!NOTE]
> - <span data-ttu-id="2a463-106">不能跨租户创建信息障碍组。</span><span class="sxs-lookup"><span data-stu-id="2a463-106">Information barrier groups cannot be created across tenants.</span></span>
> - <span data-ttu-id="2a463-107">版本1不支持使用机器人添加用户。</span><span class="sxs-lookup"><span data-stu-id="2a463-107">Using bots to add users is not supported in version 1.</span></span>
> - <span data-ttu-id="2a463-108">专用频道符合您配置的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-108">Private channels are compliant to information barrier policies that you configure.</span></span>
> - <span data-ttu-id="2a463-109">新增：连接到团队的 SharePoint 网站的信息屏障支持现在处于私人预览版中。</span><span class="sxs-lookup"><span data-stu-id="2a463-109">New: Information barrier support for SharePoint site connected to Teams is now in Private Preview.</span></span> <span data-ttu-id="2a463-110">单击[此处](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u)参与私人预览版。</span><span class="sxs-lookup"><span data-stu-id="2a463-110">Click [here](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) to participate in the private preview.</span></span>

<span data-ttu-id="2a463-111">信息屏障策略还可防止查找和发现。</span><span class="sxs-lookup"><span data-stu-id="2a463-111">Information barrier policies also prevent lookups and discovery.</span></span> <span data-ttu-id="2a463-112">这意味着，如果你尝试与不应与之通信的人员进行通信，你将在人员选取器中找不到该用户。</span><span class="sxs-lookup"><span data-stu-id="2a463-112">This means that if you attempt to communicate with someone you should not be communicating with, you will not find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="2a463-113">背景</span><span class="sxs-lookup"><span data-stu-id="2a463-113">Background</span></span>

<span data-ttu-id="2a463-114">信息障碍的主要驱动因素来自金融服务行业。</span><span class="sxs-lookup"><span data-stu-id="2a463-114">The primary driver for information barriers comes from the financial services industry.</span></span> <span data-ttu-id="2a463-115">金融行业监管机构（[FINRA]( http://www.finra.org)）检查成员公司内的信息障碍和利益冲突，并提供有关如何管理此类冲突（FINRA 2241、[债务研究机构声明 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)）的指导。</span><span class="sxs-lookup"><span data-stu-id="2a463-115">The Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) reviews information barriers and conflicts of interest within member firms and provides guidance as to how to manage such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>  

<span data-ttu-id="2a463-116">但是，由于信息障碍的推出，许多其他方面发现它们非常有用。</span><span class="sxs-lookup"><span data-stu-id="2a463-116">However, since introducing information barriers, many other areas have found them to be useful.</span></span> <span data-ttu-id="2a463-117">其他常见方案包括：</span><span class="sxs-lookup"><span data-stu-id="2a463-117">Other common scenarios include:</span></span>

- <span data-ttu-id="2a463-118">教育：一学校学生无法查找其他学校的学生的联系人详情。</span><span class="sxs-lookup"><span data-stu-id="2a463-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>
- <span data-ttu-id="2a463-119">法律：保留由一位客户的律师为同一事务所获取的不同客户的律师所获得的数据的机密性。</span><span class="sxs-lookup"><span data-stu-id="2a463-119">Legal: Maintaining confidentiality of data obtained by the lawyer of one client from being accessed by a lawyer for the same firm representing a different client.</span></span>
- <span data-ttu-id="2a463-120">政府：信息访问和控制限制在部门和群组之间。</span><span class="sxs-lookup"><span data-stu-id="2a463-120">Government: Information access and control is limited across departments and groups.</span></span>
- <span data-ttu-id="2a463-121">专业服务：公司中的一组人员只能在客户服务期间通过联盟或来宾访问与客户或特定客户聊天。</span><span class="sxs-lookup"><span data-stu-id="2a463-121">Professional services: A group of people in a company is only able to chat with a client or specific customer via federation or guest access during a customer engagement.</span></span>

<span data-ttu-id="2a463-122">例如，Enrico 属于 "银行" 段，Pradeep 属于财务顾问段。</span><span class="sxs-lookup"><span data-stu-id="2a463-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="2a463-123">Enrico 和 Pradeep 无法互相通信，因为组织的 IB 策略阻止这两个网段之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="2a463-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="2a463-124">但是，Enrico 和 Pradeep 可以与 HR 中的和进行通信。</span><span class="sxs-lookup"><span data-stu-id="2a463-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![示例显示信息障碍，阻止在分段之间进行通信](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="2a463-126">何时使用信息障碍</span><span class="sxs-lookup"><span data-stu-id="2a463-126">When to use information barriers</span></span>

<span data-ttu-id="2a463-127">您可能希望在类似情况下使用信息障碍：</span><span class="sxs-lookup"><span data-stu-id="2a463-127">You might want to use information barriers in situations like these:</span></span>

- <span data-ttu-id="2a463-128">必须阻止团队与特定其他团队进行通信或共享数据。</span><span class="sxs-lookup"><span data-stu-id="2a463-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="2a463-129">团队不得与团队外部的任何人通信或与之共享数据。</span><span class="sxs-lookup"><span data-stu-id="2a463-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="2a463-130">信息屏障策略评估服务确定通信是否符合信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with information barrier policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="2a463-131">管理信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="2a463-131">Managing information barrier policies</span></span>

<span data-ttu-id="2a463-132">信息屏障策略在 Microsoft 365 合规性中心（SCC）中使用 PowerShell cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="2a463-132">Information barrier policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="2a463-133">有关详细信息，请参阅[定义信息障碍策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="2a463-133">For more information, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a463-134">在设置或定义策略之前，**必须在 Microsoft 团队中启用范围的目录搜索**。</span><span class="sxs-lookup"><span data-stu-id="2a463-134">Before you set up or define policies, **you must enable scoped directory search in Microsoft Teams**.</span></span> <span data-ttu-id="2a463-135">在设置或定义信息障碍策略之前，请至少等待几小时后再启用范围目录搜索。</span><span class="sxs-lookup"><span data-stu-id="2a463-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="2a463-136">[了解有关信息障碍的先决条件的详细信息](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2a463-136">[Learn more about prerequisites for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="2a463-137">信息障碍管理员角色</span><span class="sxs-lookup"><span data-stu-id="2a463-137">Information barriers administrator role</span></span>

<span data-ttu-id="2a463-138">IB 合规性管理角色负责管理信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-138">The IB Compliance Management role is responsible for managing information barrier policies.</span></span> <span data-ttu-id="2a463-139">有关此角色的详细信息，请参阅[Microsoft 365 合规性中心中的权限](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="2a463-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="2a463-140">信息障碍触发器</span><span class="sxs-lookup"><span data-stu-id="2a463-140">Information barrier triggers</span></span>

<span data-ttu-id="2a463-141">当以下团队事件发生时，将激活信息屏障策略：</span><span class="sxs-lookup"><span data-stu-id="2a463-141">Information barrier policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="2a463-142">将**成员添加到团队**-每当您将用户添加到团队时，用户的策略必须根据其他团队成员的信息屏障策略进行评估。</span><span class="sxs-lookup"><span data-stu-id="2a463-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the information barrier policies of other team members.</span></span> <span data-ttu-id="2a463-143">成功添加用户后，用户可以执行团队中的所有功能，而无需进一步检查。</span><span class="sxs-lookup"><span data-stu-id="2a463-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="2a463-144">如果用户的策略阻止将他们添加到团队，则该用户将不会显示在 "搜索" 中。</span><span class="sxs-lookup"><span data-stu-id="2a463-144">If the user's policy blocks them from being added to the team, the user will not show up in search.</span></span>

    ![显示群组聊天的屏幕截图](media/information-barriers-add-members.png)

- <span data-ttu-id="2a463-146">**请求新的聊天**-每次在两个或更多用户之间请求新的聊天时，将对聊天进行评估以确保它不违反任何信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-146">**A new chat is requested** - Each time a new chat is requested between two or more users, the chat is evaluated to make sure that it isn't violating any information barrier policies.</span></span> <span data-ttu-id="2a463-147">如果对话违反了 "信息屏障" 策略，则不会启动对话。</span><span class="sxs-lookup"><span data-stu-id="2a463-147">If the conversation violates an information barrier policy, then the conversation isn't initiated.</span></span>

    <span data-ttu-id="2a463-148">下面是1:1 聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-148">Here's an example of a 1:1 chat.</span></span>

     ![显示1:1 聊天中阻止的通信的屏幕截图](media/information-barriers-one-one-chat.png)

    <span data-ttu-id="2a463-150">下面是群组聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-150">Here's an example of a group chat.</span></span>

    ![显示群组聊天的屏幕截图](media/information-barriers-group-chat.png)

- <span data-ttu-id="2a463-152">**邀请用户加入会议**-当用户被邀请加入会议时，将根据其他团队成员的策略评估用户的策略，如果发生冲突，则不允许用户加入会议中。。</span><span class="sxs-lookup"><span data-stu-id="2a463-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the user's policy is evaluated against the policies of other team members, and if there's a violation, the user will not be allowed to join the meeting.</span></span>

    ![显示用户已阻止会议的屏幕截图](media/information-barriers-meeting.png)

- <span data-ttu-id="2a463-154">**在两个或更多用户之间共享屏幕**-无论何时在两个或更多用户之间共享屏幕，都必须评估屏幕共享以确保它不违反其他用户的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-154">**A screen is shared between two or more users** - Any time a screen is shared between two or more users, the screen share must be evaluated to make sure that it doesn't violate the information barrier policies of other users.</span></span> <span data-ttu-id="2a463-155">如果违反了信息障碍策略，则不允许使用屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="2a463-155">If an information barrier policy is violated, the screen share won't be allowed.</span></span> 
 
    <span data-ttu-id="2a463-156">下面是应用策略前的屏幕共享示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-156">Here's an example of screen share before the policy is applied.</span></span> 

    ![显示用户聊天的屏幕截图](media/ib-before-screen-share-policy.png)

    <span data-ttu-id="2a463-158">下面是应用策略后的屏幕共享示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-158">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="2a463-159">屏幕共享和呼叫图标不可见。</span><span class="sxs-lookup"><span data-stu-id="2a463-159">The screen share and call icons aren't visible.</span></span>

    ![显示具有阻止的设置的用户 char 的屏幕截图](media/ib-after-screen-share-policy.png)

- <span data-ttu-id="2a463-161">**用户在团队中放置电话呼叫（VOIP）** -只要用户向另一个用户或一组用户发起语音呼叫，就会评估呼叫以确保它不违反其他团队成员的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-161">**A user places a phone call (VOIP) in Teams** - Any time a voice call is initiated by a user to another user or group of users, the call is evaluated to make sure that it doesn't violate the information barrier policies of other team members.</span></span> <span data-ttu-id="2a463-162">如果存在任何冲突，将阻止语音通话。</span><span class="sxs-lookup"><span data-stu-id="2a463-162">If there is any violation, the voice call is blocked.</span></span>
- <span data-ttu-id="2a463-163">**团队中的来宾用户**-信息障碍策略也适用于团队中的来宾用户。</span><span class="sxs-lookup"><span data-stu-id="2a463-163">**Guest users in Teams** - Information barrier policies apply to guest users in Teams too.</span></span> <span data-ttu-id="2a463-164">如果您的组织的全球通讯簿中需要发现来宾用户，请参阅[管理 Microsoft 365 组中的来宾访问](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="2a463-164">If guest users need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="2a463-165">一旦来宾用户可发现，你可以[定义信息障碍策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="2a463-165">Once guest users are discoverable, you can [define information barrier policies](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="2a463-166">策略更改如何影响现有聊天</span><span class="sxs-lookup"><span data-stu-id="2a463-166">How policy changes impact existing chats</span></span>

<span data-ttu-id="2a463-167">当信息屏障策略管理员对策略进行更改，或者由于对用户配置文件的更改（如作业更改或类似原因）而导致策略更改生效时，信息屏障策略评估服务将自动搜索成员以确保团队成员不违反任何策略。</span><span class="sxs-lookup"><span data-stu-id="2a463-167">When the information barrier policy administrator makes changes to a policy, or a policy change kicks into effect because of a change to a user's profile (such as for a job change or a similar reason), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that members of the Team are not violating any policies.</span></span>

<span data-ttu-id="2a463-168">如果用户之间已有聊天或其他通信，并且已设置新策略或更改了现有策略，则该服务将评估现有通信，以确保仍允许进行通信。</span><span class="sxs-lookup"><span data-stu-id="2a463-168">If there is an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="2a463-169">**1:1 聊天**-如果不再允许两个用户之间的通信（如果策略阻止通信被应用到一个或两个用户），则将阻止进一步通信，并且聊天对话将变为只读。</span><span class="sxs-lookup"><span data-stu-id="2a463-169">**1:1 chat** - If communication between the two users is no longer allowed (if a policy blocking communication is applied to one or both users), further communication is blocked and the chat conversation will become read-only.</span></span> 

    <span data-ttu-id="2a463-170">下面是显示聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-170">Here's an example that shows the chat is visible.</span></span>

    ![显示用户聊天的屏幕截图](media/ib-before-1-1chat-policy.png)

    <span data-ttu-id="2a463-172">下面是显示 "聊天" 已禁用的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-172">Here's an example that shows the chat is disabled.</span></span>

    ![显示已禁用用户聊天的屏幕截图](media/ib-after-1-1chat-policy.png)

- <span data-ttu-id="2a463-174">**群组聊天**-如果不再允许从一个用户到组的通信（例如，如果用户更改了作业），则用户和其他违反该策略的用户可能会从群组聊天中删除，并且不允许与组进行进一步通信。</span><span class="sxs-lookup"><span data-stu-id="2a463-174">**Group chat** - If communication from one user to the group is no longer allowed (for example, if a user changes jobs), the user along with the other users who violate the policy may be removed from group chat and further communication with the group will not be allowed.</span></span> <span data-ttu-id="2a463-175">用户仍然可以查看旧对话（该对话将为只读），但无法查看或参与与组的任何新对话。</span><span class="sxs-lookup"><span data-stu-id="2a463-175">The user can still see old conversations (which will be read-only), but will not be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="2a463-176">如果新的或已更改的策略阻止通信被应用到多个用户，则受该策略影响的用户可能会从群组聊天中被删除。</span><span class="sxs-lookup"><span data-stu-id="2a463-176">If the new or changed policy preventing communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="2a463-177">他们仍然可以看到旧的对话。</span><span class="sxs-lookup"><span data-stu-id="2a463-177">They can still see old conversations.</span></span>

<span data-ttu-id="2a463-178">在此示例中，Enrico 移动到组织内的其他部门，并从群组聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="2a463-178">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![显示群组聊天的屏幕截图](media/information-barriers-user-changes-job.png)

<span data-ttu-id="2a463-180">Enrico 无法再向群组聊天发送消息。</span><span class="sxs-lookup"><span data-stu-id="2a463-180">Enrico can no longer send messages to the group chat.</span></span>

  ![显示群组聊天的屏幕截图](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="2a463-182">**团队**-已从组中删除的任何用户都将从团队中删除，并且将无法查看或参与现有对话或新对话。</span><span class="sxs-lookup"><span data-stu-id="2a463-182">**Team** - Any users who have been removed from the group are removed from the team and will not be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="2a463-183">方案：现有聊天中的用户遭到阻止</span><span class="sxs-lookup"><span data-stu-id="2a463-183">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="2a463-184">当前，如果信息屏障策略阻止其他用户，则用户会遇到以下情况：</span><span class="sxs-lookup"><span data-stu-id="2a463-184">Currently, users experience the following if an information barrier policy blocks another user:</span></span>

- <span data-ttu-id="2a463-185">"**人员" 选项卡**-用户在 "**人员**" 选项卡上看不到被阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="2a463-185">**People tab** - A user cannot see blocked users on the **People** tab.</span></span>
- <span data-ttu-id="2a463-186">**人员选取器**-阻止的用户将在人员选取器中不可见。</span><span class="sxs-lookup"><span data-stu-id="2a463-186">**People Picker** - Blocked users will not be visible in the people picker.</span></span>

    ![显示群组聊天的屏幕截图](media/information-barriers-people-picker.png)
    
- <span data-ttu-id="2a463-188">**"活动" 选项卡**-如果用户访问被阻止用户的 "**活动**" 选项卡，则不会显示任何帖子。</span><span class="sxs-lookup"><span data-stu-id="2a463-188">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="2a463-189">（"**活动**" 选项卡仅显示频道发布，在两个用户之间不存在任何公共频道。）</span><span class="sxs-lookup"><span data-stu-id="2a463-189">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="2a463-190">下面是已阻止的 "活动" 选项卡视图的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-190">Here's an example of the activity tab view that is blocked.</span></span>

    ![显示已阻止的 "活动" 选项卡的屏幕截图](media/ib-after-activity-tab-policy.png)


- <span data-ttu-id="2a463-192">**组织结构图**-如果用户访问的组织结构图中出现被阻止的用户，则被阻止的用户将不会显示在组织结构图中，并且将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="2a463-192">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user will not appear on the org chart and an error message will appear instead.</span></span>
- <span data-ttu-id="2a463-193">**人员卡片**-如果用户参与对话，随后被阻止，则其他用户将在其悬停在阻止用户的名称上时看到错误消息，而不是人员卡。</span><span class="sxs-lookup"><span data-stu-id="2a463-193">**People card** - If a user participates in a conversation and the user is subsequently blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="2a463-194">卡片上列出的操作（如通话和聊天）将不可用。</span><span class="sxs-lookup"><span data-stu-id="2a463-194">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>
- <span data-ttu-id="2a463-195">**建议的联系人**-阻止的用户不会显示在 "建议的联系人" 列表中（为新用户显示的初始联系人列表）。</span><span class="sxs-lookup"><span data-stu-id="2a463-195">**Suggested contacts** - Blocked users do not appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>
- <span data-ttu-id="2a463-196">**聊天联系人**-用户可以在聊天联系人列表中看到被阻止的用户，但将标识被阻止的用户，并且用户唯一可以执行的操作是将其删除。</span><span class="sxs-lookup"><span data-stu-id="2a463-196">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span> <span data-ttu-id="2a463-197">用户也可以单击它们以查看其过去的对话。</span><span class="sxs-lookup"><span data-stu-id="2a463-197">The user can also click on them to view their past conversation.</span></span>
- <span data-ttu-id="2a463-198">**呼叫联系人**-用户可以在通话联系人列表中看到被阻止的用户，但将标识被阻止的用户，并且用户唯一可以执行的操作是将其删除。</span><span class="sxs-lookup"><span data-stu-id="2a463-198">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified and the only action the user can perform is to delete them.</span></span>

    <span data-ttu-id="2a463-199">下面是 "通话联系人" 列表中被阻止的用户的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-199">Here's an example of a blocked user in the calls contact list.</span></span>

    ![显示用户用户聊天的屏幕截图](media/ib-before-chat-contacts-policy.png)

    <span data-ttu-id="2a463-201">下面是对 "通话内容" 列表中的用户禁用聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2a463-201">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    ![显示用户已阻止聊天的屏幕截图](media/ib-after-chat-contacts-policy.png)

- <span data-ttu-id="2a463-203">**Skype 到团队迁移**-在 Skype for Business 到团队迁移期间，所有用户（甚至是信息屏障策略阻止的用户）都将迁移到团队，然后按照上述说明进行处理。</span><span class="sxs-lookup"><span data-stu-id="2a463-203">**Skype to Teams migration** - During a Skype for Business to Teams migration, all users, even those blocked by information barrier policies, will be migrated to Teams and then will be handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="2a463-204">团队策略和 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="2a463-204">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="2a463-205">创建团队时，将预配 SharePoint 网站并将其与团队相关联以实现文件体验。</span><span class="sxs-lookup"><span data-stu-id="2a463-205">When a team is created, a SharePoint site is provisioned and associated with the Team for the files experience.</span></span> <span data-ttu-id="2a463-206">对此 SharePoint 网站和文件的访问将接受组织的 IB，即，只有其 IB 段匹配每个 IB 策略的用户才可以访问。</span><span class="sxs-lookup"><span data-stu-id="2a463-206">Access to this SharePoint site and files honors the organization's IB, i.e., only the users whose IB segment matches per IB policy are allowed access.</span></span> <span data-ttu-id="2a463-207">即使在文件共享时，IB 策略也会生效。</span><span class="sxs-lookup"><span data-stu-id="2a463-207">Even at the time of file sharing, the IB policy is honored.</span></span>

<span data-ttu-id="2a463-208">例如：在 Contoso Bank corporation 中，用户 "Sesha@contosobank.onmicrosoft.com" 属于 "投资银行" 段，而用户 "Nikita@contosobank.onmicrosoft.com" 属于 "部门咨询"。</span><span class="sxs-lookup"><span data-stu-id="2a463-208">For example: In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to segment Advisory.</span></span> <span data-ttu-id="2a463-209">组织的 IB 策略阻止这两个网段之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="2a463-209">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="2a463-210">当用户 Sesha 为投资银行段创建团队时，团队和支持它的 SharePoint 网站将仅供投资银行段用户访问。</span><span class="sxs-lookup"><span data-stu-id="2a463-210">When user Sesha creates a team for Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking segment users.</span></span> <span data-ttu-id="2a463-211">用户 Nikita 无法访问该网站，即使她拥有网站链接也是如此。</span><span class="sxs-lookup"><span data-stu-id="2a463-211">User Nikita can't access that site even if she has the site link.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="2a463-212">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="2a463-212">Required licenses and permissions</span></span>

<span data-ttu-id="2a463-213">有关详细信息（包括计划和定价），请参阅[许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="2a463-213">For more details, including plans and pricing, see [Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="more-information"></a><span data-ttu-id="2a463-214">更多信息</span><span class="sxs-lookup"><span data-stu-id="2a463-214">More information</span></span>

- <span data-ttu-id="2a463-215">若要了解有关信息障碍的详细信息，请参阅[信息障碍](https://docs.microsoft.com/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="2a463-215">To learn more about information barriers, see [Information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="2a463-216">若要设置信息障碍策略，请参阅[定义信息障碍策略](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="2a463-216">To set up information barrier policies, see [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="2a463-217">若要编辑或删除信息障碍策略，请参阅[编辑（或删除）信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="2a463-217">To edit or remove information barrier policies, see [Edit (or remove) information barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>
