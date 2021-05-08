---
title: 管理工作电话中一线员工基于排班Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何管理组织中一线Teams中的基于排班的访问。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092540"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a><span data-ttu-id="fce86-103">管理工作电话中一线员工基于排班Teams</span><span class="sxs-lookup"><span data-stu-id="fce86-103">Manage shift-based access for Frontline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fce86-104">从 2020 年 6 月 30 开始，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="fce86-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="fce86-105">我们正在将 StaffHub 功能构建到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="fce86-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="fce86-106">如今，Teams 包含用于日程安排管理的“班次”应用，并且随着时间推移将推出其他功能。</span><span class="sxs-lookup"><span data-stu-id="fce86-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="fce86-107">StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="fce86-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="fce86-108">尝试打开 StaffHub 的任何用户都会看到一则提示其下载 Teams 的消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="fce86-109">若要了解详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="fce86-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="fce86-110">概述</span><span class="sxs-lookup"><span data-stu-id="fce86-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="fce86-111">"Microsoft Teams状态"表示用户当前的可用性和其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="fce86-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="fce86-112">一线员工的存在通常不如其他员工预测，因为每天的工作时间通常不同。</span><span class="sxs-lookup"><span data-stu-id="fce86-112">The presence of Frontline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="fce86-113">作为管理员，您可以配置Teams为您的组织中的一线员工显示一组基于排班的显示状态，以指示其何时上班和下班。</span><span class="sxs-lookup"><span data-stu-id="fce86-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Frontline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="fce86-114">这些基于班次的显示状态实心绿色对号，表示"上移时"，灰色圆圈带 x，表示"关班""关班 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; "，"实心红圈"，[](../../presence-admins.md)表示"忙碌"与 Teams 中的默认状态集分开。</span><span class="sxs-lookup"><span data-stu-id="fce86-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="fce86-115">通过这两组状态，你可以根据用户的角色为组织成员配置不同的体验。</span><span class="sxs-lookup"><span data-stu-id="fce86-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="fce86-116">使用基于班次的访问，可以在一线员工Teams，管理对非班次的访问。</span><span class="sxs-lookup"><span data-stu-id="fce86-116">With shift-based access, you can manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="fce86-117">例如，可以将"Teams设置为显示一条消息，即"第一线工作人员必须确认"，Teams排班时才能使用电话。</span><span class="sxs-lookup"><span data-stu-id="fce86-117">For example, you can set Teams to display a message that Frontline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="fce86-118">使用场景</span><span class="sxs-lookup"><span data-stu-id="fce86-118">Scenario</span></span>

<span data-ttu-id="fce86-119">下面是组织如何管理基于班次的访问的示例。</span><span class="sxs-lookup"><span data-stu-id="fce86-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="fce86-120">您的组织中的一线员工只应支付其经理安排和批准的排班工时。</span><span class="sxs-lookup"><span data-stu-id="fce86-120">You have Frontline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="fce86-121">不应为在计划排班外工作的时间支付这些费用，包括使用 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="fce86-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="fce86-122">您设置了一条自定义消息，显示"当您在 Teams 上排班的时间不计入应付时间"，当一线员工尝试在轮班时访问 Teams 时，会显示该消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Frontline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="fce86-123">如果他们选择使用Teams，他们单击"我接受"，了解这一次不会付费。</span><span class="sxs-lookup"><span data-stu-id="fce86-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="fce86-124">您组织中还有一些具有薪金和不工作班次的信息工作者。</span><span class="sxs-lookup"><span data-stu-id="fce86-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="fce86-125">将信息工作者配置为使用默认状态Teams为一线员工提供基于班次的显示。</span><span class="sxs-lookup"><span data-stu-id="fce86-125">You configure your information workers to use the default presence states in Teams while giving your Frontline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="fce86-126">基于班次的状态</span><span class="sxs-lookup"><span data-stu-id="fce86-126">Shift-based presence states</span></span>

<span data-ttu-id="fce86-127">下面是基于班次的"状态"。</span><span class="sxs-lookup"><span data-stu-id="fce86-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="fce86-128">应用配置</span><span class="sxs-lookup"><span data-stu-id="fce86-128">App configured</span></span> |<span data-ttu-id="fce86-129">用户配置</span><span class="sxs-lookup"><span data-stu-id="fce86-129">User configured</span></span>  |<span data-ttu-id="fce86-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="fce86-130">More information</span></span>  |
|---------|---------|---------|
|![实心绿色对号，指示"正在上移"](../../media/flw-presence-on-shift.png) <span data-ttu-id="fce86-132">轮班</span><span class="sxs-lookup"><span data-stu-id="fce86-132">On shift</span></span>     |         |<span data-ttu-id="fce86-133">在班次开始时自动设置</span><span class="sxs-lookup"><span data-stu-id="fce86-133">Automatically set at the start of a shift</span></span>         |
|![带 x 的灰色圆圈，指示"关班"](../../media/flw-presence-off-shift.png) <span data-ttu-id="fce86-135">非班次</span><span class="sxs-lookup"><span data-stu-id="fce86-135">Off shift</span></span>     |         |<span data-ttu-id="fce86-136">在班次结束时自动设置</span><span class="sxs-lookup"><span data-stu-id="fce86-136">Automatically set at the end of a shift</span></span>         |
|![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="fce86-138">忙碌</span><span class="sxs-lookup"><span data-stu-id="fce86-138">Busy</span></span>      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="fce86-140">忙碌</span><span class="sxs-lookup"><span data-stu-id="fce86-140">Busy</span></span>         |<span data-ttu-id="fce86-141">自动设置。</span><span class="sxs-lookup"><span data-stu-id="fce86-141">Automatically set.</span></span> <span data-ttu-id="fce86-142">还可以在前线工作人员上班时手动设置。</span><span class="sxs-lookup"><span data-stu-id="fce86-142">Can also be manually set when the Frontline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="fce86-143">不轮班访问Teams</span><span class="sxs-lookup"><span data-stu-id="fce86-143">Off shift access to Teams</span></span>

<span data-ttu-id="fce86-144">此功能允许管理在一线Teams非班次时对员工的访问权限。</span><span class="sxs-lookup"><span data-stu-id="fce86-144">This feature lets you manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="fce86-145">可以设置Teams，以在"第一线员工"在轮Teams时向"一线员工"显示消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-145">You can set Teams to display a message to Frontline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="fce86-146">一线员工必须 **单击"我接受**"才能确认消息，然后才能Teams。</span><span class="sxs-lookup"><span data-stu-id="fce86-146">Frontline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="fce86-147">您可以使用默认消息，从一组预定义邮件中选择，或自定义邮件以显示任何需要的文本。</span><span class="sxs-lookup"><span data-stu-id="fce86-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="fce86-148">下面是默认消息：</span><span class="sxs-lookup"><span data-stu-id="fce86-148">Here's the default message:</span></span>

![默认消息的屏幕截图](../../media/shifts-presence-message.png)

<span data-ttu-id="fce86-150">还可以设置显示消息的频率，并设置介于第一个班次开始或最后一个轮班结束和限制对Teams之间的宽限期。</span><span class="sxs-lookup"><span data-stu-id="fce86-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="fce86-151">管理基于班次的访问</span><span class="sxs-lookup"><span data-stu-id="fce86-151">Manage shift-based access</span></span>

<span data-ttu-id="fce86-152">作为管理员，可以使用策略来控制组织中一线员工基于排班的存在。</span><span class="sxs-lookup"><span data-stu-id="fce86-152">As an admin, you use policies to control shift-based presence for Frontline Workers in your organization.</span></span> <span data-ttu-id="fce86-153">可以使用以下 PowerShell cmdlet 管理这些策略：</span><span class="sxs-lookup"><span data-stu-id="fce86-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="fce86-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="fce86-154">New-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="fce86-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="fce86-155">Get-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="fce86-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="fce86-156">Set-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="fce86-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="fce86-157">Grant-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="fce86-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="fce86-158">Remove-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="fce86-159">使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置想要的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="fce86-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="fce86-160">此处为一些示例。</span><span class="sxs-lookup"><span data-stu-id="fce86-160">Here's some examples.</span></span> <span data-ttu-id="fce86-161">有关每个策略设置和参数的详细信息，包括可以选择的预定义班次消息列表，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="fce86-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="fce86-162">示例 1</span><span class="sxs-lookup"><span data-stu-id="fce86-162">Example 1</span></span>

<span data-ttu-id="fce86-163">本示例创建名为 Off Shift 的新策略Teams访问默认消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="fce86-164">在此策略中，基于班次的显示状态将打开，并且每当分配了此策略的用户在轮班时访问Teams会显示默认消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="fce86-165">如果用户接受Teams，则用户可以在轮班时使用此模式，以及第一个轮班开始或最后一个班次结束之间的宽限期，以及限制访问的 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="fce86-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="fce86-166">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="fce86-167">若要查看为此参数可以选择的预定义消息列表，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="fce86-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="fce86-168">示例 2</span><span class="sxs-lookup"><span data-stu-id="fce86-168">Example 2</span></span> 

<span data-ttu-id="fce86-169">本示例创建名为 Off Shift 的新策略Teams Access 自定义消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="fce86-170">在此策略中，启用基于班次的显示状态，每次分配此策略的用户在轮班时访问Teams显示自定义消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="fce86-171">如果用户接受Teams，则用户可以在轮班时使用通知，以及第一个轮班开始或最后一个轮班结束之间的宽限期，以及限制访问的 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="fce86-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="fce86-172">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="fce86-173">有关详细信息，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="fce86-173">To learn more, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="fce86-174">示例 3</span><span class="sxs-lookup"><span data-stu-id="fce86-174">Example 3</span></span>

<span data-ttu-id="fce86-175">本示例创建名为 Off Shift 的新策略Teams Access Message1。</span><span class="sxs-lookup"><span data-stu-id="fce86-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="fce86-176">在此策略中，启用基于班次的显示状态，并且每次分配此策略的用户在轮班时访问Teams显示以下预定义消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="fce86-177">"您的雇主不会授权或批准非豁免或每小时员工在其非工作时间使用其网络、应用程序、系统或工具。</span><span class="sxs-lookup"><span data-stu-id="fce86-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="fce86-178">通过接受，即表示你确认在Teams轮班期间使用公司，并且您将不获得补偿。"</span><span class="sxs-lookup"><span data-stu-id="fce86-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="fce86-179">如果用户接受Teams，则用户可以在轮班时，以及第一个轮班开始或最后一个轮班结束到限制访问之间的宽限期为 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="fce86-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="fce86-180">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="fce86-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="fce86-181">若要查看为此参数可以选择的预定义消息列表，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="fce86-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="fce86-182">示例 4</span><span class="sxs-lookup"><span data-stu-id="fce86-182">Example 4</span></span>

<span data-ttu-id="fce86-183">本示例将名为 Off Shift Teams Access 自定义消息的策略分配给名为 remy@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fce86-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="fce86-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="fce86-184">Related topics</span></span>

- [<span data-ttu-id="fce86-185">在 Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="fce86-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="fce86-186">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="fce86-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)