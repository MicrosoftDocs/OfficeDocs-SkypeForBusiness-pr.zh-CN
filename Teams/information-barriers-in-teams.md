---
title: Microsoft Teams 中的信息屏障
description: 本文介绍 Microsoft Teams 中的信息屏障及其如何影响 Teams。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 79a1a416e0d868129e2d78f305cfe32efb527d53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120643"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="ba505-103">Microsoft Teams 中的信息屏障</span><span class="sxs-lookup"><span data-stu-id="ba505-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="ba505-104">IB (信息) 是管理员可以配置的策略，以防止个人或组相互通信。</span><span class="sxs-lookup"><span data-stu-id="ba505-104">Information barriers (IBs) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="ba505-105">例如，如果一个部门正在处理不应与其他部门共享的信息，则 IB 非常有用。</span><span class="sxs-lookup"><span data-stu-id="ba505-105">IBs are useful if, for example, one department is handling information that shouldn't be shared with other departments.</span></span> <span data-ttu-id="ba505-106">当需要隔离或阻止组与该组外部的任何人通信时，数据库也很有用。</span><span class="sxs-lookup"><span data-stu-id="ba505-106">IBs are also useful when a group needs to be isolated or prevented from communicating with anyone outside of that group.</span></span>

>[!NOTE]
>- <span data-ttu-id="ba505-107">无法 (IB) 组的信息屏障。</span><span class="sxs-lookup"><span data-stu-id="ba505-107">Information barrier (IB) groups cannot be created across tenants.</span></span>
>- <span data-ttu-id="ba505-108">版本 1 不支持使用机器人、Azure Active Directory (Azure AD) 应用以及用于添加用户的一些 API。</span><span class="sxs-lookup"><span data-stu-id="ba505-108">Using bots, Azure Active Directory (Azure AD) apps, and some APIs to add users is not supported in version 1.</span></span>
>- <span data-ttu-id="ba505-109">专用通道符合配置的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-109">Private channels are compliant to IB policies that you configure.</span></span>
>- <span data-ttu-id="ba505-110">新增：有关对连接到 Teams 的 SharePoint 网站屏障的支持信息，请参阅与 [Microsoft Teams](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)网站关联的段。</span><span class="sxs-lookup"><span data-stu-id="ba505-110">New: For information about support for barriers for SharePoint sites that are connected to Teams, see [Segments associated with Microsoft Teams sites](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="ba505-111">IB 策略还会阻止查找和发现。</span><span class="sxs-lookup"><span data-stu-id="ba505-111">IB policies also prevent lookups and discovery.</span></span> <span data-ttu-id="ba505-112">如果您尝试与不应通信的某人进行通信，您将在人员选取器中找不到该用户。</span><span class="sxs-lookup"><span data-stu-id="ba505-112">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="ba505-113">背景</span><span class="sxs-lookup"><span data-stu-id="ba505-113">Background</span></span>

<span data-ttu-id="ba505-114">IB 的主要驱动因素来自金融服务行业。</span><span class="sxs-lookup"><span data-stu-id="ba505-114">The primary driver for IBs comes from the financial services industry.</span></span> <span data-ttu-id="ba505-115">金融行业监管局 ([FINRA]( https://www.finra.org)) 评审成员公司内部的数据库和利益冲突，并提供有关管理此类冲突的指导 (FINRA 2241，债务研究法规通知[15-31。](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)</span><span class="sxs-lookup"><span data-stu-id="ba505-115">The Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) reviews IBs and conflicts of interest within member firms and provides guidance about managing such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>

<span data-ttu-id="ba505-116">但是，自引入 IB 以来，许多其他领域发现它们很有用。</span><span class="sxs-lookup"><span data-stu-id="ba505-116">However, since introducing IBs, many other areas have found them to be useful.</span></span> <span data-ttu-id="ba505-117">其他常见方案包括：</span><span class="sxs-lookup"><span data-stu-id="ba505-117">Other common scenarios include:</span></span>

- <span data-ttu-id="ba505-118">教育：一个学校的学生无法查找其他学校学生的联系人详细信息。</span><span class="sxs-lookup"><span data-stu-id="ba505-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>

- <span data-ttu-id="ba505-119">法律：维护由一个客户的律师获取的数据的保密性，防止代表不同客户的同一家公司的律师访问这些数据。</span><span class="sxs-lookup"><span data-stu-id="ba505-119">Legal: Maintaining the confidentiality of data that is obtained by the lawyer of one client and preventing it from being accessed by a lawyer for the same firm who represents a different client.</span></span>

- <span data-ttu-id="ba505-120">政府：信息访问和控制在部门和组中受到限制。</span><span class="sxs-lookup"><span data-stu-id="ba505-120">Government: Information access and control are limited across departments and groups.</span></span>

- <span data-ttu-id="ba505-121">专业服务：公司中的一组人员只能在客户参与期间通过来宾访问与客户或特定客户聊天。</span><span class="sxs-lookup"><span data-stu-id="ba505-121">Professional services: A group of people in a company is only able to chat with a client or a specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="ba505-122">例如，Enrico 属于银行段，Pradeep 属于财务顾问段。</span><span class="sxs-lookup"><span data-stu-id="ba505-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="ba505-123">Enrico 和 Pradeep 无法相互通信，因为组织的 IB 策略阻止这两个段之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="ba505-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="ba505-124">但是，Enrico 和 Pradeep 可以在 HR 中与 Lee 通信。</span><span class="sxs-lookup"><span data-stu-id="ba505-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![显示阻止段之间通信的信息屏障的示例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="ba505-126">何时使用信息屏障</span><span class="sxs-lookup"><span data-stu-id="ba505-126">When to use information barriers</span></span>

<span data-ttu-id="ba505-127">你可能希望使用以下情况下的 IB：</span><span class="sxs-lookup"><span data-stu-id="ba505-127">You might want to use IBs in situations like these:</span></span>

- <span data-ttu-id="ba505-128">必须禁止团队与特定其他团队通信或共享数据。</span><span class="sxs-lookup"><span data-stu-id="ba505-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="ba505-129">团队不得与团队外部的任何人通信或共享数据。</span><span class="sxs-lookup"><span data-stu-id="ba505-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="ba505-130">信息屏障策略评估服务确定通信是否符合 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with IB policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="ba505-131">管理信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="ba505-131">Managing information barrier policies</span></span>

<span data-ttu-id="ba505-132">IB 策略在 Microsoft 365 合规中心 (SCC) PowerShell cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="ba505-132">IB policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="ba505-133">有关详细信息，请参阅 [定义信息屏障的策略](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="ba505-133">For more information, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba505-134">在设置或定义策略之前，必须在 Microsoft Teams 中启用范围目录搜索。</span><span class="sxs-lookup"><span data-stu-id="ba505-134">Before you set up or define policies, you must enable scoped directory search in Microsoft Teams.</span></span> <span data-ttu-id="ba505-135">启用范围目录搜索后，请至少等待几个小时，然后设置或定义信息屏障的策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="ba505-136">有关详细信息，请参阅定义 [信息屏障策略](/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="ba505-136">For more information, see [Define information barrier policies](/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="ba505-137">信息屏障管理员角色</span><span class="sxs-lookup"><span data-stu-id="ba505-137">Information barriers administrator role</span></span>

<span data-ttu-id="ba505-138">IB 合规性管理角色负责管理 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-138">The IB Compliance Management role is responsible for managing IB policies.</span></span> <span data-ttu-id="ba505-139">有关此角色的信息，请参阅 [Microsoft 365 合规中心中的权限](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="ba505-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="ba505-140">信息屏障触发器</span><span class="sxs-lookup"><span data-stu-id="ba505-140">Information barrier triggers</span></span>

<span data-ttu-id="ba505-141">当发生以下 Teams 事件时，将激活 IB 策略：</span><span class="sxs-lookup"><span data-stu-id="ba505-141">IB policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="ba505-142">**将成员添加到团队** - 每当将用户添加到团队时，都必须根据其他团队成员的 IB 策略评估用户策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the IB policies of other team members.</span></span> <span data-ttu-id="ba505-143">成功添加用户后，用户无需进一步检查即可在团队中执行所有功能。</span><span class="sxs-lookup"><span data-stu-id="ba505-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="ba505-144">如果用户的策略阻止他们添加到团队，该用户不会显示在搜索中。</span><span class="sxs-lookup"><span data-stu-id="ba505-144">If the user's policy blocks them from being added to the team, the user won't show up in search.</span></span>

    ![屏幕截图：搜索要添加到团队的新功能并查找任何匹配项](media/information-barriers-add-members.png)

- <span data-ttu-id="ba505-146">**请求新的** 聊天 - 每次用户请求与一个或多个其他用户进行新聊天时，会评估聊天以确保它未违反任何 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-146">**A new chat is requested** - Each time that a user requests a new chat with one or more other users, the chat is evaluated to make sure that it isn't violating any IB policies.</span></span> <span data-ttu-id="ba505-147">如果聊天违反 IB 策略，则聊天不会启动。</span><span class="sxs-lookup"><span data-stu-id="ba505-147">If the conversation violates an IB policy, then the conversation isn't started.</span></span>

    <span data-ttu-id="ba505-148">下面是一对一聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-148">Here's an example of a 1:1 chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-149">![显示 1：1 聊天中阻止通信的屏幕截图](media/information-barriers-one-one-chat.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-149">![Screenshot showing blocked communication in 1:1 chat](media/information-barriers-one-one-chat.png)</span></span>

    <span data-ttu-id="ba505-150">下面是群组聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-150">Here's an example of a group chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-151">![显示群组聊天的屏幕截图](media/information-barriers-group-chat.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-151">![Screenshot showing group chat](media/information-barriers-group-chat.png)</span></span>

- <span data-ttu-id="ba505-152">**邀请用户** 加入会议 - 当邀请用户加入会议时，将针对适用于其他团队成员的 IB 策略评估适用于该用户的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the IB policy that applies to the user is evaluated against the IB policies that apply to the other team members.</span></span> <span data-ttu-id="ba505-153">如果存在冲突，则不允许用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="ba505-153">If there's a violation, the user won't be allowed to join the meeting.</span></span>

    ![显示用户被阻止参加会议的屏幕截图](media/information-barriers-meeting.png)

- <span data-ttu-id="ba505-155">**屏幕在两个或多个** 用户之间共享 - 当用户与其他用户共享屏幕时，必须评估共享以确保它不会违反其他用户的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-155">**A screen is shared between two or more users** - When a user shares a screen with other users, the sharing must be evaluated to make sure that it doesn't violate the IB policies of other users.</span></span> <span data-ttu-id="ba505-156">如果违反 IB 策略，则不允许屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="ba505-156">If an IB policy is violated, the screen share won't be allowed.</span></span>

    <span data-ttu-id="ba505-157">下面是应用策略之前屏幕共享的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-157">Here's an example of screen share before the policy is applied.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-158">![显示用户聊天的屏幕截图](media/ib-before-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-158">![Screenshot showing a user chat](media/ib-before-screen-share-policy.png)</span></span>

    <span data-ttu-id="ba505-159">下面是应用策略后屏幕共享的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-159">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="ba505-160">屏幕共享和呼叫图标不可见。</span><span class="sxs-lookup"><span data-stu-id="ba505-160">The screen share and call icons aren't visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-161">![显示具有阻止设置的用户字符的屏幕截图](media/ib-after-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-161">![Screenshot showing user char with blocked settings](media/ib-after-screen-share-policy.png)</span></span>

- <span data-ttu-id="ba505-162">用户在 **Teams** 中发起电话呼叫 - 每当用户通过 VOIP) 向其他用户或用户组发起语音呼叫 (时，将评估该呼叫以确保它不会违反其他团队成员的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-162">**A user places a phone call in Teams** - Whenever a user initiates a voice call (via VOIP) to another user or group of users, the call is evaluated to make sure that it doesn't violate the IB policies of other team members.</span></span> <span data-ttu-id="ba505-163">如果存在任何冲突，语音呼叫将被阻止。</span><span class="sxs-lookup"><span data-stu-id="ba505-163">If there's any violation, the voice call is blocked.</span></span>

- <span data-ttu-id="ba505-164">**Teams 中的来宾** - IB 策略也适用于 Teams 中的来宾。</span><span class="sxs-lookup"><span data-stu-id="ba505-164">**Guests in Teams** - IB policies apply to guests in Teams, too.</span></span> <span data-ttu-id="ba505-165">如果需要在组织的全局地址列表中发现来宾，请参阅 [在 Microsoft 365](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)组中管理来宾访问。</span><span class="sxs-lookup"><span data-stu-id="ba505-165">If guests need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="ba505-166">来宾可发现后，可以定义 [IB 策略](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="ba505-166">Once guests are discoverable, you can [define IB policies](/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="ba505-167">策略更改如何影响现有聊天</span><span class="sxs-lookup"><span data-stu-id="ba505-167">How policy changes impact existing chats</span></span>

<span data-ttu-id="ba505-168">当 IB 策略管理员对策略进行更改，或者由于用户的个人资料 (（例如作业更改) ）而激活策略更改时，信息屏障策略评估服务会自动搜索成员，以确保他们在团队中的成员身份不会违反任何策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-168">When the IB policy administrator makes changes to a policy, or when a policy change is activated because of a change to a user's profile (such as for a job change), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that their membership in the team doesn't violate any policies.</span></span>

<span data-ttu-id="ba505-169">如果用户之间存在现有聊天或其他通信，并且设置了新策略或更改了现有策略，该服务将评估现有通信，以确保仍允许通信发生。</span><span class="sxs-lookup"><span data-stu-id="ba505-169">If there's an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="ba505-170">**1：1** 聊天 - 如果由于向阻止通信的策略的一个或两个用户应用了 (，不再允许两个用户之间的通信，) 进一步通信。</span><span class="sxs-lookup"><span data-stu-id="ba505-170">**1:1 chat** - If communication between two users is no longer allowed (because of application to one or both users of a policy that blocks communication), further communication is blocked.</span></span> <span data-ttu-id="ba505-171">他们现有的聊天对话将变为只读。</span><span class="sxs-lookup"><span data-stu-id="ba505-171">Their existing chat conversations become read-only.</span></span>

    <span data-ttu-id="ba505-172">下面是显示聊天可见的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-172">Here's an example that shows the chat is visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-173">![显示可用用户聊天的屏幕截图](media/ib-before-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-173">![Screenshot showing user chat is available](media/ib-before-1-1chat-policy.png)</span></span>

    <span data-ttu-id="ba505-174">以下示例显示聊天已禁用。</span><span class="sxs-lookup"><span data-stu-id="ba505-174">Here's an example that shows the chat is disabled.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-175">![显示用户聊天已禁用的屏幕截图](media/ib-after-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-175">![Screenshot showing user chat is disabled](media/ib-after-1-1chat-policy.png)</span></span>

- <span data-ttu-id="ba505-176">群组聊天 **-** 如果不再允许从一个用户到组的通信 (例如，由于用户更改了作业) ，则该用户及其参与违反策略的其他用户可能会从群组聊天中删除，并且不允许与组进一步通信。</span><span class="sxs-lookup"><span data-stu-id="ba505-176">**Group chat** - If communication from one user to a group is no longer allowed (for example, because a user changed jobs), the user—along with the other users whose participation violates the policy—may be removed from group chat, and further communication with the group won't be allowed.</span></span> <span data-ttu-id="ba505-177">用户仍可以看到旧对话，但无法查看或参与与组的任何新对话。</span><span class="sxs-lookup"><span data-stu-id="ba505-177">The user can still see old conversations, but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="ba505-178">如果阻止通信的新策略或已更改策略应用于多个用户，则受该策略影响的用户可能会从群组聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="ba505-178">If the new or changed policy that prevents communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="ba505-179">他们仍可以看到旧对话。</span><span class="sxs-lookup"><span data-stu-id="ba505-179">They can still see old conversations.</span></span>

  <span data-ttu-id="ba505-180">此示例中，Enrico 已移至组织内部的不同部门，已从群组聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="ba505-180">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![已从中删除用户的群组聊天的屏幕截图](media/information-barriers-user-changes-job.png)

  <span data-ttu-id="ba505-182">Enrico 无法再向群组聊天发送消息。</span><span class="sxs-lookup"><span data-stu-id="ba505-182">Enrico can no longer send messages to the group chat.</span></span>

  ![由于用户已从组中删除，无法向群组聊天发送消息的屏幕截图](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="ba505-184">**团队** - 已从组中删除的任何用户将从团队中删除，并且无法查看或参与现有或新对话。</span><span class="sxs-lookup"><span data-stu-id="ba505-184">**Team** - Any users who have been removed from the group are removed from the team and won't be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="ba505-185">场景：现有聊天中的用户被阻止</span><span class="sxs-lookup"><span data-stu-id="ba505-185">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="ba505-186">目前，如果 IB 策略阻止其他用户，则用户遇到以下情况：</span><span class="sxs-lookup"><span data-stu-id="ba505-186">Currently, users experience the following scenarios if an IB policy blocks another user:</span></span>

- <span data-ttu-id="ba505-187">**"人员** "选项卡 - 用户在"人员"选项卡上看不到 **被阻止** 的用户。</span><span class="sxs-lookup"><span data-stu-id="ba505-187">**People tab** - A user can't see blocked users on the **People** tab.</span></span>

- <span data-ttu-id="ba505-188">**人员选取** 器 - 被阻止的用户在人员选取器中不可见。</span><span class="sxs-lookup"><span data-stu-id="ba505-188">**People Picker** - Blocked users won't be visible in the people picker.</span></span>

    ![Teams 提醒用户策略阻止显示其他用户信息的屏幕截图](media/information-barriers-people-picker.png)

- <span data-ttu-id="ba505-190">**"活动**"选项卡 - 如果用户访问被阻止用户的"活动"选项卡，则不显示任何帖子。</span><span class="sxs-lookup"><span data-stu-id="ba505-190">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="ba505-191">**("活动**"选项卡仅显示频道帖子，并且两个用户之间将不存在常见的) </span><span class="sxs-lookup"><span data-stu-id="ba505-191">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="ba505-192">下面是被阻止的活动选项卡视图的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-192">Here's an example of the activity tab view that is blocked.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-193">![显示被阻止的活动选项卡的屏幕截图](media/ib-after-activity-tab-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-193">![Screenshot showing the activity tab that is blocked](media/ib-after-activity-tab-policy.png)</span></span>

- <span data-ttu-id="ba505-194">**组织结构图** - 如果用户访问显示被阻止用户的组织结构图，则被阻止的用户不会显示在组织结构图上。</span><span class="sxs-lookup"><span data-stu-id="ba505-194">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart.</span></span> <span data-ttu-id="ba505-195">而是会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="ba505-195">Instead, an error message will appear.</span></span>

- <span data-ttu-id="ba505-196">**人员** 卡片 - 如果用户参与对话后被阻止，其他用户将鼠标悬停在被阻止用户的姓名上时，会看到一条错误消息，而不是人员卡片。</span><span class="sxs-lookup"><span data-stu-id="ba505-196">**People card** - If a user participates in a conversation and the user is later blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="ba505-197">卡上列出的操作 (例如通话和聊天) 将不可用。</span><span class="sxs-lookup"><span data-stu-id="ba505-197">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>

- <span data-ttu-id="ba505-198">**建议的联系人** - 被阻止的用户不会显示在建议联系人列表中， (新用户显示的初始联系人列表) 。</span><span class="sxs-lookup"><span data-stu-id="ba505-198">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>

- <span data-ttu-id="ba505-199">**聊天联系人** - 用户可以在聊天联系人列表上看到被阻止的用户，但被阻止的用户将被识别。</span><span class="sxs-lookup"><span data-stu-id="ba505-199">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="ba505-200">用户可以对被阻止的用户执行的唯一操作是删除他们。</span><span class="sxs-lookup"><span data-stu-id="ba505-200">The only action that the user can perform on the blocked users is to delete them.</span></span> <span data-ttu-id="ba505-201">用户还可以单击他们以查看其过去的对话。</span><span class="sxs-lookup"><span data-stu-id="ba505-201">The user can also click on them to view their past conversation.</span></span>

- <span data-ttu-id="ba505-202">**呼叫联系人** - 用户可以在通话联系人列表上看到被阻止的用户，但被阻止的用户将被识别。</span><span class="sxs-lookup"><span data-stu-id="ba505-202">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="ba505-203">用户可以对阻止用户执行的唯一操作是删除他们。</span><span class="sxs-lookup"><span data-stu-id="ba505-203">The only action that the user can perform on the block users is to delete them.</span></span>

    <span data-ttu-id="ba505-204">下面是通话联系人列表中被阻止的用户的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-204">Here's an example of a blocked user in the calls contact list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-205">![显示用户用户聊天的屏幕截图](media/ib-before-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-205">![Screenshot showing user user chat](media/ib-before-chat-contacts-policy.png)</span></span>

    <span data-ttu-id="ba505-206">下面是在通话内容列表中为用户禁用聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="ba505-206">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba505-207">![显示阻止用户聊天的屏幕截图](media/ib-after-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ba505-207">![Screenshot showing user blocked from chat](media/ib-after-chat-contacts-policy.png)</span></span>

- <span data-ttu-id="ba505-208">**Skype 到 Teams 的** 迁移 - 从 Skype for Business 迁移到 Teams 期间，所有用户（即使是被 IB 策略阻止的用户）都将迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="ba505-208">**Skype to Teams migration** - During a migration from Skype for Business to Teams, all users—even those users who are blocked by IB policies—will be migrated to Teams.</span></span> <span data-ttu-id="ba505-209">然后，如上所述处理这些用户。</span><span class="sxs-lookup"><span data-stu-id="ba505-209">Those users are then handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="ba505-210">Teams 策略和 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="ba505-210">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="ba505-211">创建团队后，将预配 SharePoint 网站并与 Microsoft Teams 关联，以体验文件。</span><span class="sxs-lookup"><span data-stu-id="ba505-211">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="ba505-212">默认情况下，此 SharePoint 网站和文件上不遵守 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="ba505-212">IB policies aren't honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="ba505-213">若要启用 IB 策略，管理员已填写一个表单，请求在 SharePoint 和 OneDrive 上启用 IB 策略 (请参阅"信息屏障") 。 [](/sharepoint/information-barriers#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="ba505-213">To enable IB policies, the administrator has already filled out a form, requesting that IB policies be enabled on SharePoint and OneDrive (see the *Prerequisites* section in [Information barriers](/sharepoint/information-barriers#prerequisites)).</span></span> <span data-ttu-id="ba505-214">如果在 SharePoint 和 OneDrive 中启用 IB 策略，则 IB 策略将在使用 Microsoft Teams 创建团队时预配的 SharePoint 网站上工作。</span><span class="sxs-lookup"><span data-stu-id="ba505-214">If the IB policy is turned on in SharePoint and OneDrive, then the IB policies will work on SharePoint sites that are provisioned when a team is created with Microsoft Teams.</span></span>

<span data-ttu-id="ba505-215">团队的 **SharePoint** 站点上的 IB 策略示例：在 Contoso Bank 公司中，用户"Sesha@contosobank.onmicrosoft.com"属于投资银行业务段，用户"Nikita@contosobank.onmicrosoft.com"属于顾问段。</span><span class="sxs-lookup"><span data-stu-id="ba505-215">**Example of IB policies on SharePoint site of a team**: In Contoso Bank corporation, user 'Sesha@contosobank.onmicrosoft.com' belongs to the Investment Banking segment and user 'Nikita@contosobank.onmicrosoft.com' belongs to the Advisory segment.</span></span> <span data-ttu-id="ba505-216">组织的 IB 策略阻止这两个部分之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="ba505-216">The organization's IB policy blocks communication and collaboration between these two segments.</span></span>
<span data-ttu-id="ba505-217">当用户 Sesha 为 Investment Banking 段创建团队时，支持它的团队和 SharePoint 网站将仅可供 Investment Banking 用户访问。</span><span class="sxs-lookup"><span data-stu-id="ba505-217">When user Sesha creates a team for the Investment Banking segment, the team and the SharePoint site that backs it will be accessible only to Investment Banking users.</span></span> <span data-ttu-id="ba505-218">即使 Nikita 用户具有网站链接，她也无法访问该网站。</span><span class="sxs-lookup"><span data-stu-id="ba505-218">User Nikita can't access that site even if she has the site link.</span></span>

<span data-ttu-id="ba505-219">有关详细信息，请参阅对 [SharePoint 使用信息屏障](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。</span><span class="sxs-lookup"><span data-stu-id="ba505-219">For more information, see [Use information barriers with SharePoint](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ba505-220">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="ba505-220">Required licenses and permissions</span></span>

<span data-ttu-id="ba505-221">有关许可证和权限（包括计划和定价）的详细信息，请参阅 Microsoft [365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全与合规&指南。</span><span class="sxs-lookup"><span data-stu-id="ba505-221">For more information on licenses and permissions, including plans and pricing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="ba505-222">已知问题</span><span class="sxs-lookup"><span data-stu-id="ba505-222">Known Issues</span></span>

- <span data-ttu-id="ba505-223">**用户无法** 加入临时会议：如果启用了 IB 策略，则如果会议花名册的大小大于会议出席限制，则不允许用户 [加入会议](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ba505-223">**Users can't join ad-hoc meetings**: If IB policies are enabled, users aren't allowed to join meetings if the size of the meeting roster is greater than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="ba505-224">根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="ba505-224">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="ba505-225">加入会议一次的用户会将该用户添加到名单;因此对于定期会议，花名册可以快速填满。</span><span class="sxs-lookup"><span data-stu-id="ba505-225">A user joining a meeting once adds that user to the roster; hence for recurring meetings, the roster can fill up fast.</span></span> <span data-ttu-id="ba505-226">聊天名单达到 [会议出席限制后](limits-specifications-teams.md)，不允许向会议添加其他用户。</span><span class="sxs-lookup"><span data-stu-id="ba505-226">Once the chat roster reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting.</span></span> <span data-ttu-id="ba505-227">如果为租户启用了 IB 且会议聊天花名册已满，则新用户 (那些未加入花名册的用户) 不允许加入会议。</span><span class="sxs-lookup"><span data-stu-id="ba505-227">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those users who aren't already on the roster) aren't allowed to join the meeting.</span></span> <span data-ttu-id="ba505-228">但是，如果未为租户启用 IB 且会议聊天名单已满，则新用户 (那些尚未加入花名册) 的用户可以加入会议，但他们在会议中看不到聊天选项。</span><span class="sxs-lookup"><span data-stu-id="ba505-228">But if IB isn't enabled for the tenant and the meeting chat roster is full, new users (those users who aren't already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="ba505-229">短期解决方案是从会议聊天名单中删除非活动成员，为新用户提供空间。</span><span class="sxs-lookup"><span data-stu-id="ba505-229">A short-term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="ba505-230">但是，我们将在以后增加会议聊天花名册的大小。</span><span class="sxs-lookup"><span data-stu-id="ba505-230">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>
- <span data-ttu-id="ba505-231">**用户无法加入频道会议**：如果启用了 IB 策略，则如果用户不是团队的成员，则不允许他们加入频道会议。</span><span class="sxs-lookup"><span data-stu-id="ba505-231">**Users can't join channel meetings**: If IB policies are enabled, users aren't allowed to join channel meetings if they're not a member of the team.</span></span> <span data-ttu-id="ba505-232">根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="ba505-232">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="ba505-233">频道会议中的聊天线程仅适用于团队/频道成员，非成员无法查看或访问聊天线程。</span><span class="sxs-lookup"><span data-stu-id="ba505-233">The chat thread in a channel meeting is available to Team/Channel members only, and non-members can't see or access the chat thread.</span></span> <span data-ttu-id="ba505-234">如果为租户启用了 IB，并且非团队成员尝试加入频道会议，则不允许该用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="ba505-234">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, that user isn't allowed to join the meeting.</span></span> <span data-ttu-id="ba505-235">但是，如果未为租户启用 IB 且非团队成员尝试加入频道会议，则用户可以加入会议，但他们在会议中看不到聊天选项。</span><span class="sxs-lookup"><span data-stu-id="ba505-235">However, if IB is *not* enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting—but they won't see the chat option in the meeting.</span></span>
- <span data-ttu-id="ba505-236">**不会删除** 团队所有者：如果应用了新的 IB 策略，导致 Teams 频道中出现两个或多个冲突段，则具有团队所有者的段会获得更高的首选项，并且会删除其他段用户。</span><span class="sxs-lookup"><span data-stu-id="ba505-236">**Team owners are not removed**: If a new IB policy is applied that results in two or more conflicting segments present in a Teams channel, the segments with team owners are given higher preference and other segment users are removed.</span></span> <span data-ttu-id="ba505-237">此外，目前不会删除团队所有者，即使他们与其他所有者/用户冲突。</span><span class="sxs-lookup"><span data-stu-id="ba505-237">Also, at this time, team owners are not getting removed, even if they are in conflict with other owners/users.</span></span> <span data-ttu-id="ba505-238">租户管理员和其他通道所有者必须手动删除有冲突的所有者。</span><span class="sxs-lookup"><span data-stu-id="ba505-238">Tenant admins and other channel owners will have to remove conflicting owners manually.</span></span>
- <span data-ttu-id="ba505-239">**租户中允许的最大段数**：配置 IB 策略时，每个租户最多可以设置 100 个段。</span><span class="sxs-lookup"><span data-stu-id="ba505-239">**Maximum number of segments allowed in a tenant**: Each tenant can set up to 100 segments when configuring IB policies.</span></span> <span data-ttu-id="ba505-240">可以配置的策略数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="ba505-240">There is no limit on the number of policies that can be configured.</span></span>

## <a name="more-information"></a><span data-ttu-id="ba505-241">更多信息</span><span class="sxs-lookup"><span data-stu-id="ba505-241">More information</span></span>

- <span data-ttu-id="ba505-242">若要详细了解数据库，请参阅 [信息屏障](/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="ba505-242">To learn more about IBs, see [Information barriers](/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="ba505-243">若要设置 IB 策略，请参阅 [定义信息屏障的策略](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="ba505-243">To set up IB policies, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="ba505-244">若要编辑或删除 IB 策略，请参阅编辑 ([或删除) 策略](/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="ba505-244">To edit or remove IB policies, see [Edit (or remove) information barrier policies](/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>

## <a name="availability"></a><span data-ttu-id="ba505-245">可用性</span><span class="sxs-lookup"><span data-stu-id="ba505-245">Availability</span></span>

- <span data-ttu-id="ba505-246">此功能在我们的公有云中可用;我们于 2021 年 1 月推出了 GCC 云中的信息屏障。</span><span class="sxs-lookup"><span data-stu-id="ba505-246">The feature is available in our public cloud; in January 2021, we rolled out Information Barriers in the GCC cloud.</span></span>
- <span data-ttu-id="ba505-247">此功能在 GCCH 和 DOD 云中尚不可用。</span><span class="sxs-lookup"><span data-stu-id="ba505-247">The feature is not yet available in the GCCH and DOD clouds.</span></span>