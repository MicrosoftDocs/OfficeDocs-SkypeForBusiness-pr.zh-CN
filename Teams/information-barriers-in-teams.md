---
title: Microsoft Teams
description: 本文介绍数据中的信息屏障Microsoft Teams如何影响Teams。
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
ms.openlocfilehash: 7946d6c098979d478f91d8ef67a3214c11823d7d
ms.sourcegitcommit: dba7984f899f8921b462a56d158fa0a1cc2c2a8b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929318"
---
# <a name="information-barriers-in-microsoft-teams"></a><span data-ttu-id="2f873-103">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f873-103">Information barriers in Microsoft Teams</span></span>

<span data-ttu-id="2f873-104">IB (信息) 是管理员可以配置的策略，以防止个人或组相互通信。</span><span class="sxs-lookup"><span data-stu-id="2f873-104">Information barriers (IBs) are policies that an admin can configure to prevent individuals or groups from communicating with each other.</span></span> <span data-ttu-id="2f873-105">例如，如果一个部门正在处理不应与其他部门共享的信息，则 IB 非常有用。</span><span class="sxs-lookup"><span data-stu-id="2f873-105">IBs are useful if, for example, one department is handling information that shouldn't be shared with other departments.</span></span> <span data-ttu-id="2f873-106">当需要隔离或阻止组与该组外部的任何人通信时，数据库也很有用。</span><span class="sxs-lookup"><span data-stu-id="2f873-106">IBs are also useful when a group needs to be isolated or prevented from communicating with anyone outside of that group.</span></span>

>[!NOTE]
>- <span data-ttu-id="2f873-107">无法 (IB) 组的信息屏障。</span><span class="sxs-lookup"><span data-stu-id="2f873-107">Information barrier (IB) groups cannot be created across tenants.</span></span>
>- <span data-ttu-id="2f873-108">版本 1 Azure Active Directory (不支持使用机器人Azure Active Directory (Azure AD) 应用、用于发送活动源通知的 API 以及用于添加用户的一些 API。</span><span class="sxs-lookup"><span data-stu-id="2f873-108">Using bots, Azure Active Directory (Azure AD) apps, APIs to send activity feed notifications, and some APIs to add users is not supported in version 1.</span></span>
>- <span data-ttu-id="2f873-109">专用通道符合配置的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-109">Private channels are compliant to IB policies that you configure.</span></span>
>- <span data-ttu-id="2f873-110">新增：有关对连接到 SharePoint 网站的支持屏障Teams，请参阅与网站关联的[Microsoft Teams段](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)。</span><span class="sxs-lookup"><span data-stu-id="2f873-110">New: For information about support for barriers for SharePoint sites that are connected to Teams, see [Segments associated with Microsoft Teams sites](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).</span></span>

<span data-ttu-id="2f873-111">IB 策略还会阻止查找和发现。</span><span class="sxs-lookup"><span data-stu-id="2f873-111">IB policies also prevent lookups and discovery.</span></span> <span data-ttu-id="2f873-112">如果您尝试与不应通信的某人进行通信，您将在人员选取器中找不到该用户。</span><span class="sxs-lookup"><span data-stu-id="2f873-112">If you attempt to communicate with someone you shouldn't be communicating with, you won't find that user in the people picker.</span></span>

## <a name="background"></a><span data-ttu-id="2f873-113">背景</span><span class="sxs-lookup"><span data-stu-id="2f873-113">Background</span></span>

<span data-ttu-id="2f873-114">IB 的主要驱动因素来自金融服务行业。</span><span class="sxs-lookup"><span data-stu-id="2f873-114">The primary driver for IBs comes from the financial services industry.</span></span> <span data-ttu-id="2f873-115">金融行业监管局 ([FINRA]( https://www.finra.org)) 评审成员公司内部的数据库和利益冲突，并提供有关管理此类冲突的指导 (FINRA 2241，债务研究法规通知[15-31。](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)</span><span class="sxs-lookup"><span data-stu-id="2f873-115">The Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) reviews IBs and conflicts of interest within member firms and provides guidance about managing such conflicts (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).</span></span>

<span data-ttu-id="2f873-116">但是，自引入 IB 以来，许多其他领域发现它们很有用。</span><span class="sxs-lookup"><span data-stu-id="2f873-116">However, since introducing IBs, many other areas have found them to be useful.</span></span> <span data-ttu-id="2f873-117">其他常见方案包括：</span><span class="sxs-lookup"><span data-stu-id="2f873-117">Other common scenarios include:</span></span>

- <span data-ttu-id="2f873-118">教育：一个学校的学生无法查找其他学校学生的联系人详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f873-118">Education: Students in one school aren't able to look up contact details for students of other schools.</span></span>

- <span data-ttu-id="2f873-119">法律：维护由一个客户的律师获取的数据的保密性，防止代表不同客户的同一家公司的律师访问这些数据。</span><span class="sxs-lookup"><span data-stu-id="2f873-119">Legal: Maintaining the confidentiality of data that is obtained by the lawyer of one client and preventing it from being accessed by a lawyer for the same firm who represents a different client.</span></span>

- <span data-ttu-id="2f873-120">政府：信息访问和控制在部门和组中受到限制。</span><span class="sxs-lookup"><span data-stu-id="2f873-120">Government: Information access and control are limited across departments and groups.</span></span>

- <span data-ttu-id="2f873-121">Professional服务：公司中的一组人员只能在客户参与期间通过来宾访问与客户或特定客户聊天。</span><span class="sxs-lookup"><span data-stu-id="2f873-121">Professional services: A group of people in a company is only able to chat with a client or a specific customer via guest access during a customer engagement.</span></span>

<span data-ttu-id="2f873-122">例如，Enrico 属于银行段，Pradeep 属于财务顾问段。</span><span class="sxs-lookup"><span data-stu-id="2f873-122">For example, Enrico belongs to the Banking segment and Pradeep belongs to the Financial advisor segment.</span></span> <span data-ttu-id="2f873-123">Enrico 和 Pradeep 无法相互通信，因为组织的 IB 策略阻止这两个段之间的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="2f873-123">Enrico and Pradeep can't communicate with each other because the organization's IB policy blocks communication and collaboration between these two segments.</span></span> <span data-ttu-id="2f873-124">但是，Enrico 和 Pradeep 可以在 HR 中与 Lee 通信。</span><span class="sxs-lookup"><span data-stu-id="2f873-124">However, Enrico and Pradeep can communicate with Lee in HR.</span></span>

![显示阻止段之间通信的信息屏障的示例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a><span data-ttu-id="2f873-126">何时使用信息屏障</span><span class="sxs-lookup"><span data-stu-id="2f873-126">When to use information barriers</span></span>

<span data-ttu-id="2f873-127">你可能希望使用以下情况下的 IB：</span><span class="sxs-lookup"><span data-stu-id="2f873-127">You might want to use IBs in situations like these:</span></span>

- <span data-ttu-id="2f873-128">必须禁止团队与特定其他团队通信或共享数据。</span><span class="sxs-lookup"><span data-stu-id="2f873-128">A team must be prevented from communicating or sharing data with a specific other team.</span></span>
- <span data-ttu-id="2f873-129">团队不得与团队外部的任何人通信或共享数据。</span><span class="sxs-lookup"><span data-stu-id="2f873-129">A team must not communicate or share data with anyone outside of the team.</span></span>

<span data-ttu-id="2f873-130">信息屏障策略评估服务确定通信是否符合 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-130">The Information Barrier Policy Evaluation Service determines whether a communication complies with IB policies.</span></span>

## <a name="managing-information-barrier-policies"></a><span data-ttu-id="2f873-131">管理信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="2f873-131">Managing information barrier policies</span></span>

<span data-ttu-id="2f873-132">IB 策略使用 PowerShell cmdlet Microsoft 365合规性 (SCC) 管理。</span><span class="sxs-lookup"><span data-stu-id="2f873-132">IB policies are managed in the Microsoft 365 Compliance Center (SCC) using PowerShell cmdlets.</span></span> <span data-ttu-id="2f873-133">有关详细信息，请参阅 [定义信息屏障的策略](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="2f873-133">For more information, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f873-134">在设置或定义策略之前，必须在目录中启用范围目录Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="2f873-134">Before you set up or define policies, you must enable scoped directory search in Microsoft Teams.</span></span> <span data-ttu-id="2f873-135">启用范围目录搜索后，请至少等待几个小时，然后设置或定义信息屏障的策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-135">Wait at least a few hours after enabling scoped directory search before you set up or define policies for information barriers.</span></span> <span data-ttu-id="2f873-136">有关详细信息，请参阅定义 [信息屏障策略](/office365/securitycompliance/information-barriers-policies#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2f873-136">For more information, see [Define information barrier policies](/office365/securitycompliance/information-barriers-policies#prerequisites).</span></span>

## <a name="information-barriers-administrator-role"></a><span data-ttu-id="2f873-137">信息屏障管理员角色</span><span class="sxs-lookup"><span data-stu-id="2f873-137">Information barriers administrator role</span></span>

<span data-ttu-id="2f873-138">IB 合规性管理角色负责管理 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-138">The IB Compliance Management role is responsible for managing IB policies.</span></span> <span data-ttu-id="2f873-139">有关此角色详细信息，请参阅合规性中心[中Microsoft 365权限](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="2f873-139">For more information about this role, see [Permissions in the Microsoft 365 Compliance Center](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).</span></span>

## <a name="information-barrier-triggers"></a><span data-ttu-id="2f873-140">信息屏障触发器</span><span class="sxs-lookup"><span data-stu-id="2f873-140">Information barrier triggers</span></span>

<span data-ttu-id="2f873-141">发生以下事件时，将Teams IB 策略：</span><span class="sxs-lookup"><span data-stu-id="2f873-141">IB policies are activated when the following Teams events take place:</span></span>

- <span data-ttu-id="2f873-142">**将成员添加到团队** - 每当将用户添加到团队时，都必须根据其他团队成员的 IB 策略评估用户策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-142">**Members are added to a team** - Whenever you add a user to a team, the user's policy must be evaluated against the IB policies of other team members.</span></span> <span data-ttu-id="2f873-143">成功添加用户后，用户无需进一步检查即可在团队中执行所有功能。</span><span class="sxs-lookup"><span data-stu-id="2f873-143">After the user is successfully added, the user can perform all functions in the team without further checks.</span></span> <span data-ttu-id="2f873-144">如果用户的策略阻止他们添加到团队，该用户不会显示在搜索中。</span><span class="sxs-lookup"><span data-stu-id="2f873-144">If the user's policy blocks them from being added to the team, the user won't show up in search.</span></span>

    ![屏幕截图：搜索要添加到团队的新功能并查找任何匹配项](media/information-barriers-add-members.png)

- <span data-ttu-id="2f873-146">**请求新的** 聊天 - 每次用户请求与一个或多个其他用户进行新聊天时，会评估聊天以确保它未违反任何 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-146">**A new chat is requested** - Each time that a user requests a new chat with one or more other users, the chat is evaluated to make sure that it isn't violating any IB policies.</span></span> <span data-ttu-id="2f873-147">如果聊天违反 IB 策略，则聊天不会启动。</span><span class="sxs-lookup"><span data-stu-id="2f873-147">If the conversation violates an IB policy, then the conversation isn't started.</span></span>

    <span data-ttu-id="2f873-148">下面是一对一聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-148">Here's an example of a 1:1 chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-149">![显示 1：1 聊天中阻止通信的屏幕截图](media/information-barriers-one-one-chat.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-149">![Screenshot showing blocked communication in 1:1 chat](media/information-barriers-one-one-chat.png)</span></span>

    <span data-ttu-id="2f873-150">下面是群组聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-150">Here's an example of a group chat.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-151">![显示群组聊天的屏幕截图](media/information-barriers-group-chat.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-151">![Screenshot showing group chat](media/information-barriers-group-chat.png)</span></span>

- <span data-ttu-id="2f873-152">**邀请用户** 加入会议 - 当邀请用户加入会议时，将针对适用于其他团队成员的 IB 策略评估适用于该用户的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-152">**A user is invited to join a meeting** - When a user is invited to join a meeting, the IB policy that applies to the user is evaluated against the IB policies that apply to the other team members.</span></span> <span data-ttu-id="2f873-153">如果存在冲突，则不允许用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="2f873-153">If there's a violation, the user won't be allowed to join the meeting.</span></span>

    ![显示用户被阻止参加会议的屏幕截图](media/information-barriers-meeting.png)

- <span data-ttu-id="2f873-155">**屏幕在两个或多个** 用户之间共享 - 当用户与其他用户共享屏幕时，必须评估共享以确保它不会违反其他用户的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-155">**A screen is shared between two or more users** - When a user shares a screen with other users, the sharing must be evaluated to make sure that it doesn't violate the IB policies of other users.</span></span> <span data-ttu-id="2f873-156">如果违反 IB 策略，则不允许屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="2f873-156">If an IB policy is violated, the screen share won't be allowed.</span></span>

    <span data-ttu-id="2f873-157">下面是应用策略之前屏幕共享的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-157">Here's an example of screen share before the policy is applied.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-158">![显示用户聊天的屏幕截图](media/ib-before-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-158">![Screenshot showing a user chat](media/ib-before-screen-share-policy.png)</span></span>

    <span data-ttu-id="2f873-159">下面是应用策略后屏幕共享的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-159">Here's an example of screen share after the policy is applied.</span></span> <span data-ttu-id="2f873-160">屏幕共享和呼叫图标不可见。</span><span class="sxs-lookup"><span data-stu-id="2f873-160">The screen share and call icons aren't visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-161">![显示具有阻止设置的用户字符的屏幕截图](media/ib-after-screen-share-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-161">![Screenshot showing user char with blocked settings](media/ib-after-screen-share-policy.png)</span></span>

- <span data-ttu-id="2f873-162">用户在 **Teams** 中发起电话呼叫 - 每当用户通过 VOIP) 向其他用户或用户组发起语音呼叫 (时，都会评估该呼叫，以确保它不会违反其他团队成员的 IB 策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-162">**A user places a phone call in Teams** - Whenever a user initiates a voice call (via VOIP) to another user or group of users, the call is evaluated to make sure that it doesn't violate the IB policies of other team members.</span></span> <span data-ttu-id="2f873-163">如果存在任何冲突，语音呼叫将被阻止。</span><span class="sxs-lookup"><span data-stu-id="2f873-163">If there's any violation, the voice call is blocked.</span></span>

- <span data-ttu-id="2f873-164">**Teams** - IB 策略也适用于 Teams 中的来宾。</span><span class="sxs-lookup"><span data-stu-id="2f873-164">**Guests in Teams** - IB policies apply to guests in Teams, too.</span></span> <span data-ttu-id="2f873-165">如果需要在组织的全局地址列表中发现来宾，请参阅管理组Microsoft 365[访问](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)。</span><span class="sxs-lookup"><span data-stu-id="2f873-165">If guests need to be discoverable in your organization's global address list, see [Manage guest access in Microsoft 365 Groups](/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span> <span data-ttu-id="2f873-166">来宾可发现后，可以定义 [IB 策略](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="2f873-166">Once guests are discoverable, you can [define IB policies](/office365/securitycompliance/information-barriers-policies).</span></span>

## <a name="how-policy-changes-impact-existing-chats"></a><span data-ttu-id="2f873-167">策略更改如何影响现有聊天</span><span class="sxs-lookup"><span data-stu-id="2f873-167">How policy changes impact existing chats</span></span>

<span data-ttu-id="2f873-168">当 IB 策略管理员对策略进行更改，或者由于用户的个人资料 (（例如作业更改) ）而激活策略更改时，信息屏障策略评估服务会自动搜索成员，以确保他们在团队中的成员身份不会违反任何策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-168">When the IB policy administrator makes changes to a policy, or when a policy change is activated because of a change to a user's profile (such as for a job change), the Information Barrier Policy Evaluation Service automatically searches the members to ensure that their membership in the team doesn't violate any policies.</span></span>

<span data-ttu-id="2f873-169">如果用户之间存在现有聊天或其他通信，并且设置了新策略或更改了现有策略，该服务将评估现有通信，以确保仍允许通信发生。</span><span class="sxs-lookup"><span data-stu-id="2f873-169">If there's an existing chat or other communication between users, and a new policy is set or an existing policy is changed, the service evaluates existing communications to make sure that the communications are still allowed to occur.</span></span> 

- <span data-ttu-id="2f873-170">**1：1** 聊天 - 如果由于向阻止通信的策略的一个或两个用户应用了 (，不再允许两个用户之间的通信，) 进一步通信。</span><span class="sxs-lookup"><span data-stu-id="2f873-170">**1:1 chat** - If communication between two users is no longer allowed (because of application to one or both users of a policy that blocks communication), further communication is blocked.</span></span> <span data-ttu-id="2f873-171">他们现有的聊天对话将变为只读。</span><span class="sxs-lookup"><span data-stu-id="2f873-171">Their existing chat conversations become read-only.</span></span>

    <span data-ttu-id="2f873-172">下面是显示聊天可见的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-172">Here's an example that shows the chat is visible.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-173">![显示可用用户聊天的屏幕截图](media/ib-before-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-173">![Screenshot showing user chat is available](media/ib-before-1-1chat-policy.png)</span></span>

    <span data-ttu-id="2f873-174">以下示例显示聊天已禁用。</span><span class="sxs-lookup"><span data-stu-id="2f873-174">Here's an example that shows the chat is disabled.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-175">![显示用户聊天已禁用的屏幕截图](media/ib-after-1-1chat-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-175">![Screenshot showing user chat is disabled](media/ib-after-1-1chat-policy.png)</span></span>

- <span data-ttu-id="2f873-176">群组聊天 **-** 如果不再允许从一个用户到组的通信 (例如，由于用户更改了作业) ，则该用户及其参与违反策略的其他用户可能会从群组聊天中删除，并且不允许与组进一步通信。</span><span class="sxs-lookup"><span data-stu-id="2f873-176">**Group chat** - If communication from one user to a group is no longer allowed (for example, because a user changed jobs), the user—along with the other users whose participation violates the policy—may be removed from group chat, and further communication with the group won't be allowed.</span></span> <span data-ttu-id="2f873-177">用户仍可以看到旧对话，但无法查看或参与与组的任何新对话。</span><span class="sxs-lookup"><span data-stu-id="2f873-177">The user can still see old conversations, but won't be able to see or participate in any new conversations with the group.</span></span> <span data-ttu-id="2f873-178">如果阻止通信的新策略或已更改策略应用于多个用户，则受该策略影响的用户可能会从群组聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="2f873-178">If the new or changed policy that prevents communication is applied to more than one user, the users who are affected by the policy may be removed from group chat.</span></span> <span data-ttu-id="2f873-179">他们仍可以看到旧对话。</span><span class="sxs-lookup"><span data-stu-id="2f873-179">They can still see old conversations.</span></span>

  <span data-ttu-id="2f873-180">此示例中，Enrico 已移至组织内部的不同部门，已从群组聊天中删除。</span><span class="sxs-lookup"><span data-stu-id="2f873-180">In this example, Enrico moved to a different department within the organization and is removed from the group chat.</span></span>

  ![已从中删除用户的群组聊天的屏幕截图](media/information-barriers-user-changes-job.png)

  <span data-ttu-id="2f873-182">Enrico 无法再向群组聊天发送消息。</span><span class="sxs-lookup"><span data-stu-id="2f873-182">Enrico can no longer send messages to the group chat.</span></span>

  ![由于用户已从组中删除，无法向群组聊天发送消息的屏幕截图](media/information-barriers-user-changes-job-2.png)

- <span data-ttu-id="2f873-184">**团队** - 已从组中删除的任何用户将从团队中删除，并且无法查看或参与现有或新对话。</span><span class="sxs-lookup"><span data-stu-id="2f873-184">**Team** - Any users who have been removed from the group are removed from the team and won't be able to see or participate in existing or new conversations.</span></span>

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a><span data-ttu-id="2f873-185">场景：现有聊天中的用户被阻止</span><span class="sxs-lookup"><span data-stu-id="2f873-185">Scenario: A user in an existing chat becomes blocked</span></span>

<span data-ttu-id="2f873-186">目前，如果 IB 策略阻止其他用户，则用户遇到以下情况：</span><span class="sxs-lookup"><span data-stu-id="2f873-186">Currently, users experience the following scenarios if an IB policy blocks another user:</span></span>

- <span data-ttu-id="2f873-187">**"人员** "选项卡 - 用户在"人员"选项卡上看不到 **被阻止** 的用户。</span><span class="sxs-lookup"><span data-stu-id="2f873-187">**People tab** - A user can't see blocked users on the **People** tab.</span></span>

- <span data-ttu-id="2f873-188">**人员选取** 器 - 被阻止的用户在人员选取器中不可见。</span><span class="sxs-lookup"><span data-stu-id="2f873-188">**People Picker** - Blocked users won't be visible in the people picker.</span></span>

    ![屏幕截图Teams警告用户策略阻止显示其他用户的信息](media/information-barriers-people-picker.png)

- <span data-ttu-id="2f873-190">**"活动**"选项卡 - 如果用户访问被阻止用户的"活动"选项卡，则不显示任何帖子。</span><span class="sxs-lookup"><span data-stu-id="2f873-190">**Activity tab** - If a user visits the **Activity** tab of a blocked user, no posts will appear.</span></span> <span data-ttu-id="2f873-191">**("活动**"选项卡仅显示频道帖子，并且两个用户之间将不存在常见的) </span><span class="sxs-lookup"><span data-stu-id="2f873-191">(The **Activity** tab displays channel posts only, and there would be no common channels between the two users.)</span></span>

    <span data-ttu-id="2f873-192">下面是被阻止的活动选项卡视图的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-192">Here's an example of the activity tab view that is blocked.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-193">![显示被阻止的活动选项卡的屏幕截图](media/ib-after-activity-tab-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-193">![Screenshot showing the activity tab that is blocked](media/ib-after-activity-tab-policy.png)</span></span>

- <span data-ttu-id="2f873-194">**组织结构图** - 如果用户访问显示被阻止用户的组织结构图，则被阻止的用户不会显示在组织结构图上。</span><span class="sxs-lookup"><span data-stu-id="2f873-194">**Org charts** - If a user accesses an org chart on which a blocked user appears, the blocked user won't appear on the org chart.</span></span> <span data-ttu-id="2f873-195">而是会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="2f873-195">Instead, an error message will appear.</span></span>

- <span data-ttu-id="2f873-196">**人员** 卡片 - 如果用户参与对话后被阻止，其他用户将鼠标悬停在被阻止用户的姓名上时，会看到一条错误消息，而不是人员卡片。</span><span class="sxs-lookup"><span data-stu-id="2f873-196">**People card** - If a user participates in a conversation and the user is later blocked, other users will see an error message instead of the people card when they hover over the blocked user's name.</span></span> <span data-ttu-id="2f873-197">卡上列出的操作 (例如通话和聊天) 将不可用。</span><span class="sxs-lookup"><span data-stu-id="2f873-197">Actions listed on the card (such as calling and chat) will be unavailable.</span></span>

- <span data-ttu-id="2f873-198">**建议的联系人** - 被阻止的用户不会显示在建议联系人列表中， (新用户显示的初始联系人列表) 。</span><span class="sxs-lookup"><span data-stu-id="2f873-198">**Suggested contacts** - Blocked users don't appear on the suggested contacts list (the initial contact list that appears for new users).</span></span>

- <span data-ttu-id="2f873-199">**聊天联系人** - 用户可以在聊天联系人列表上看到被阻止的用户，但被阻止的用户将被识别。</span><span class="sxs-lookup"><span data-stu-id="2f873-199">**Chat contacts** - A user can see blocked users on the chats contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="2f873-200">用户可以对被阻止的用户执行的唯一操作是删除他们。</span><span class="sxs-lookup"><span data-stu-id="2f873-200">The only action that the user can perform on the blocked users is to delete them.</span></span> <span data-ttu-id="2f873-201">用户还可以单击他们以查看其过去的对话。</span><span class="sxs-lookup"><span data-stu-id="2f873-201">The user can also click on them to view their past conversation.</span></span>

- <span data-ttu-id="2f873-202">**呼叫联系人** - 用户可以在通话联系人列表上看到被阻止的用户，但被阻止的用户将被识别。</span><span class="sxs-lookup"><span data-stu-id="2f873-202">**Calls contacts** - A user can see blocked users on the calls contact list, but the blocked users will be identified.</span></span> <span data-ttu-id="2f873-203">用户可以对阻止用户执行的唯一操作是删除他们。</span><span class="sxs-lookup"><span data-stu-id="2f873-203">The only action that the user can perform on the block users is to delete them.</span></span>

    <span data-ttu-id="2f873-204">下面是通话联系人列表中被阻止的用户的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-204">Here's an example of a blocked user in the calls contact list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-205">![显示用户用户聊天的屏幕截图](media/ib-before-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-205">![Screenshot showing user user chat](media/ib-before-chat-contacts-policy.png)</span></span>

    <span data-ttu-id="2f873-206">下面是在通话内容列表中为用户禁用聊天的示例。</span><span class="sxs-lookup"><span data-stu-id="2f873-206">Here's an example of the chat being disabled for a user on the calls content list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2f873-207">![显示阻止用户聊天的屏幕截图](media/ib-after-chat-contacts-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f873-207">![Screenshot showing user blocked from chat](media/ib-after-chat-contacts-policy.png)</span></span>

- <span data-ttu-id="2f873-208">**Skype** 迁移Teams - 从 Skype for Business 迁移到 Teams 期间，所有用户（即使是被 IB 策略阻止的用户）都将迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="2f873-208">**Skype to Teams migration** - During a migration from Skype for Business to Teams, all users—even those users who are blocked by IB policies—will be migrated to Teams.</span></span> <span data-ttu-id="2f873-209">然后，如上所述处理这些用户。</span><span class="sxs-lookup"><span data-stu-id="2f873-209">Those users are then handled as described above.</span></span>

## <a name="teams-policies-and-sharepoint-sites"></a><span data-ttu-id="2f873-210">Teams策略和SharePoint网站</span><span class="sxs-lookup"><span data-stu-id="2f873-210">Teams policies and SharePoint sites</span></span>

<span data-ttu-id="2f873-211">创建团队时，将预配SharePoint网站，并关联Microsoft Teams体验。</span><span class="sxs-lookup"><span data-stu-id="2f873-211">When a team is created, a SharePoint site is provisioned and associated with Microsoft Teams for the files experience.</span></span> <span data-ttu-id="2f873-212">默认情况下，此网站和SharePoint不执行信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2f873-212">Information barrier policies aren't honored on this SharePoint site and files by default.</span></span> <span data-ttu-id="2f873-213">若要在 SharePoint 和 OneDrive 中启用信息屏障，请遵循将信息屏障与 SharePoint 主题中的指导[和](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization)步骤。</span><span class="sxs-lookup"><span data-stu-id="2f873-213">To enable information barriers in SharePoint and OneDrive, follow the guidance and steps in the [Use information barriers with SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) topic.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="2f873-214">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="2f873-214">Required licenses and permissions</span></span>

<span data-ttu-id="2f873-215">有关许可证和权限（包括计划和定价）的详细信息，请参阅Microsoft 365安全与合规[&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="2f873-215">For more information on licenses and permissions, including plans and pricing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="known-issues"></a><span data-ttu-id="2f873-216">已知问题</span><span class="sxs-lookup"><span data-stu-id="2f873-216">Known Issues</span></span>

- <span data-ttu-id="2f873-217">**用户无法** 加入临时会议：如果启用了 IB 策略，则如果会议花名册的大小大于会议出席限制，则不允许用户 [加入会议](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2f873-217">**Users can't join ad-hoc meetings**: If IB policies are enabled, users aren't allowed to join meetings if the size of the meeting roster is greater than the [meeting attendance limits](limits-specifications-teams.md).</span></span> <span data-ttu-id="2f873-218">根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="2f873-218">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="2f873-219">加入会议一次的用户会将该用户添加到名单;因此对于定期会议，花名册可以快速填满。</span><span class="sxs-lookup"><span data-stu-id="2f873-219">A user joining a meeting once adds that user to the roster; hence for recurring meetings, the roster can fill up fast.</span></span> <span data-ttu-id="2f873-220">聊天名单达到 [会议出席限制后](limits-specifications-teams.md)，不允许向会议添加其他用户。</span><span class="sxs-lookup"><span data-stu-id="2f873-220">Once the chat roster reaches the [meeting attendance limits](limits-specifications-teams.md), no additional users are allowed to be added to the meeting.</span></span> <span data-ttu-id="2f873-221">如果为租户启用了 IB 且会议聊天花名册已满，则新用户 (那些未加入花名册的用户) 不允许加入会议。</span><span class="sxs-lookup"><span data-stu-id="2f873-221">If IB is enabled for the tenant and the chat roster is full for a meeting, new users (those users who aren't already on the roster) aren't allowed to join the meeting.</span></span> <span data-ttu-id="2f873-222">但是，如果未为租户启用 IB 且会议聊天名单已满，则新用户 (那些尚未加入花名册) 的用户可以加入会议，但他们在会议中看不到聊天选项。</span><span class="sxs-lookup"><span data-stu-id="2f873-222">But if IB isn't enabled for the tenant and the meeting chat roster is full, new users (those users who aren't already on the roster) are allowed to join the meeting, though they won't see the chat option in the meeting.</span></span> <span data-ttu-id="2f873-223">短期解决方案是从会议聊天名单中删除非活动成员，为新用户提供空间。</span><span class="sxs-lookup"><span data-stu-id="2f873-223">A short-term solution is to remove inactive members from the meeting chat roster to make space for new users.</span></span> <span data-ttu-id="2f873-224">但是，我们将在以后增加会议聊天花名册的大小。</span><span class="sxs-lookup"><span data-stu-id="2f873-224">We will, however, be increasing the size of meeting chat rosters at a later date.</span></span>
- <span data-ttu-id="2f873-225">**用户无法加入频道会议**：如果启用了 IB 策略，则如果用户不是团队的成员，则不允许他们加入频道会议。</span><span class="sxs-lookup"><span data-stu-id="2f873-225">**Users can't join channel meetings**: If IB policies are enabled, users aren't allowed to join channel meetings if they're not a member of the team.</span></span> <span data-ttu-id="2f873-226">根本原因是 IB 检查依赖于是否可以将用户添加到会议聊天名单，并且只有当用户可以添加到花名册时，才允许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="2f873-226">The root cause is that IB checks rely on whether users can be added to a meeting chat roster, and only when they can be added to the roster are they allowed to join the meeting.</span></span> <span data-ttu-id="2f873-227">频道会议中的聊天线程仅适用于团队/频道成员，非成员无法查看或访问聊天线程。</span><span class="sxs-lookup"><span data-stu-id="2f873-227">The chat thread in a channel meeting is available to Team/Channel members only, and non-members can't see or access the chat thread.</span></span> <span data-ttu-id="2f873-228">如果为租户启用了 IB，并且非团队成员尝试加入频道会议，则不允许该用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="2f873-228">If IB is enabled for the tenant and a non-team member attempts to join a channel meeting, that user isn't allowed to join the meeting.</span></span> <span data-ttu-id="2f873-229">但是，如果未为租户启用 IB 且非团队成员尝试加入频道会议，则用户可以加入会议，但他们在会议中看不到聊天选项。</span><span class="sxs-lookup"><span data-stu-id="2f873-229">However, if IB is *not* enabled for the tenant and a non-team member attempts to join a channel meeting, the user is allowed to join the meeting—but they won't see the chat option in the meeting.</span></span>
- <span data-ttu-id="2f873-230">不会删除团队所有者：如果应用了新的 IB 策略，导致 Teams 频道中出现两个或多个冲突段，则团队所有者的段会获得更高的首选项，并删除其他段用户。</span><span class="sxs-lookup"><span data-stu-id="2f873-230">**Team owners are not removed**: If a new IB policy is applied that results in two or more conflicting segments present in a Teams channel, the segments with team owners are given higher preference and other segment users are removed.</span></span> <span data-ttu-id="2f873-231">此外，目前不会删除团队所有者，即使他们与其他所有者/用户冲突。</span><span class="sxs-lookup"><span data-stu-id="2f873-231">Also, at this time, team owners are not getting removed, even if they are in conflict with other owners/users.</span></span> <span data-ttu-id="2f873-232">租户管理员和其他通道所有者必须手动删除有冲突的所有者。</span><span class="sxs-lookup"><span data-stu-id="2f873-232">Tenant admins and other channel owners will have to remove conflicting owners manually.</span></span>
- <span data-ttu-id="2f873-233">**租户中允许的最大段数**：配置 IB 策略时，每个租户最多可以设置 100 个段。</span><span class="sxs-lookup"><span data-stu-id="2f873-233">**Maximum number of segments allowed in a tenant**: Each tenant can set up to 100 segments when configuring IB policies.</span></span> <span data-ttu-id="2f873-234">可以配置的策略数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="2f873-234">There is no limit on the number of policies that can be configured.</span></span>

- <span data-ttu-id="2f873-235">**IB 策略对** 联合用户不起作用：如果允许与外部租户联合，则这些租户的用户不受 IB 策略的限制。</span><span class="sxs-lookup"><span data-stu-id="2f873-235">**IB policies don't work for federated users**: If you allow federation with external tenants, the users of those tenants won't be restricted by IB policies.</span></span> <span data-ttu-id="2f873-236">如果组织的用户加入由外部联合用户组织的聊天或会议，则 IB 策略也不会限制组织用户之间的通信。</span><span class="sxs-lookup"><span data-stu-id="2f873-236">If users of your organization join a chat or meeting organized by external federated users, then IB policies also won't restrict communication between users of your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="2f873-237">更多信息</span><span class="sxs-lookup"><span data-stu-id="2f873-237">More information</span></span>

- <span data-ttu-id="2f873-238">若要详细了解数据库，请参阅 [信息屏障](/office365/securitycompliance/information-barriers)。</span><span class="sxs-lookup"><span data-stu-id="2f873-238">To learn more about IBs, see [Information barriers](/office365/securitycompliance/information-barriers).</span></span>

- <span data-ttu-id="2f873-239">若要设置 IB 策略，请参阅 [定义信息屏障的策略](/office365/securitycompliance/information-barriers-policies)。</span><span class="sxs-lookup"><span data-stu-id="2f873-239">To set up IB policies, see [Define policies for information barriers](/office365/securitycompliance/information-barriers-policies).</span></span>

- <span data-ttu-id="2f873-240">若要编辑或删除 IB 策略，请参阅编辑 ([或删除) 策略](/microsoft-365/compliance/information-barriers-edit-segments-policies)。</span><span class="sxs-lookup"><span data-stu-id="2f873-240">To edit or remove IB policies, see [Edit (or remove) information barrier policies](/microsoft-365/compliance/information-barriers-edit-segments-policies).</span></span>

## <a name="availability"></a><span data-ttu-id="2f873-241">可用性</span><span class="sxs-lookup"><span data-stu-id="2f873-241">Availability</span></span>

- <span data-ttu-id="2f873-242">此功能在我们的公有云中可用;我们于 2021 年 1 月推出了云中GCC屏障。</span><span class="sxs-lookup"><span data-stu-id="2f873-242">The feature is available in our public cloud; in January 2021, we rolled out Information Barriers in the GCC cloud.</span></span>
- <span data-ttu-id="2f873-243">此功能在 GCCH 和 DOD 云中尚不可用。</span><span class="sxs-lookup"><span data-stu-id="2f873-243">The feature is not yet available in the GCCH and DOD clouds.</span></span>
