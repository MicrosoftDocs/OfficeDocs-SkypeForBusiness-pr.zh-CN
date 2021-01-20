---
title: 在 Teams 中管理一线员工基于排班的访问
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Teams 中为组织的一线员工管理基于排班的访问。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 437902136bf72685dabf5bd6359dd6221c7467de
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909466"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a><span data-ttu-id="47780-103">在 Teams 中管理一线员工基于排班的访问</span><span class="sxs-lookup"><span data-stu-id="47780-103">Manage shift-based access for Frontline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47780-104">自 2020 年 6 月 30 起，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="47780-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="47780-105">我们正在将 StaffHub 功能构建到 Microsoft Teams 中。</span><span class="sxs-lookup"><span data-stu-id="47780-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="47780-106">目前，Teams 包含用于计划管理的 Shifts 应用，其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="47780-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="47780-107">StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="47780-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="47780-108">尝试打开 StaffHub 的任何人都会显示一条消息，指示他们下载 Teams。</span><span class="sxs-lookup"><span data-stu-id="47780-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="47780-109">有关详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="47780-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="47780-110">概述</span><span class="sxs-lookup"><span data-stu-id="47780-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="47780-111">Microsoft Teams 中的状态向其他用户指示用户的当前可用性和状态。</span><span class="sxs-lookup"><span data-stu-id="47780-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="47780-112">一线员工的存在通常不如其他员工预测，因为每天的工作时间通常不同。</span><span class="sxs-lookup"><span data-stu-id="47780-112">The presence of Frontline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="47780-113">作为管理员，你可以将 Teams 配置为为贵组织的一线员工显示一组基于排班的显示状态，以指示其何时上班和上班。</span><span class="sxs-lookup"><span data-stu-id="47780-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Frontline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="47780-114">这些基于班次的显示状态为纯绿色对号，表示"上班"，灰色圆圈表示 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ x，表示 ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md)"关班"，红色实心圆圈表示"忙碌"与 Teams 中的默认状态集分开。</span><span class="sxs-lookup"><span data-stu-id="47780-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="47780-115">通过这两组状态，你可以根据用户的角色为组织成员配置不同的体验。</span><span class="sxs-lookup"><span data-stu-id="47780-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="47780-116">使用基于班次的访问，可以在一线员工轮班时管理对 Teams 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="47780-116">With shift-based access, you can manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="47780-117">例如，可以将 Teams 设置为显示一条消息，要求一线员工在未按计划排班使用 Teams 之前必须先确认该消息。</span><span class="sxs-lookup"><span data-stu-id="47780-117">For example, you can set Teams to display a message that Frontline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="47780-118">使用场景</span><span class="sxs-lookup"><span data-stu-id="47780-118">Scenario</span></span>

<span data-ttu-id="47780-119">下面是组织如何管理基于班次的访问的示例。</span><span class="sxs-lookup"><span data-stu-id="47780-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="47780-120">您的组织中的一线员工应仅为其经理安排和批准的排班工时付费。</span><span class="sxs-lookup"><span data-stu-id="47780-120">You have Frontline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="47780-121">不应为在计划排班（包括使用 Teams 应用）外工作的时间付费。</span><span class="sxs-lookup"><span data-stu-id="47780-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="47780-122">你设置了一条自定义消息，显示"你在 Teams 上排班的时间不计入应付时间"，当一线员工尝试在轮班时访问 Teams 时，会显示该消息。</span><span class="sxs-lookup"><span data-stu-id="47780-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Frontline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="47780-123">如果他们选择使用 Teams，他们单击" **我** 接受"，了解这一次不会付费。</span><span class="sxs-lookup"><span data-stu-id="47780-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="47780-124">您的组织中还有一些信息工作者，这些员工是工资工，不工作轮班。</span><span class="sxs-lookup"><span data-stu-id="47780-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="47780-125">将信息工作者配置为使用 Teams 中的默认状态，同时为一线员工提供基于班次的显示。</span><span class="sxs-lookup"><span data-stu-id="47780-125">You configure your information workers to use the default presence states in Teams while giving your Frontline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="47780-126">基于班次的状态</span><span class="sxs-lookup"><span data-stu-id="47780-126">Shift-based presence states</span></span>

<span data-ttu-id="47780-127">下面是基于班次的状态。</span><span class="sxs-lookup"><span data-stu-id="47780-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="47780-128">应用配置</span><span class="sxs-lookup"><span data-stu-id="47780-128">App configured</span></span> |<span data-ttu-id="47780-129">用户配置</span><span class="sxs-lookup"><span data-stu-id="47780-129">User configured</span></span>  |<span data-ttu-id="47780-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="47780-130">More information</span></span>  |
|---------|---------|---------|
|![实心绿色对号，表示正在轮班](../../media/flw-presence-on-shift.png) <span data-ttu-id="47780-132">轮班</span><span class="sxs-lookup"><span data-stu-id="47780-132">On shift</span></span>     |         |<span data-ttu-id="47780-133">在班次开始时自动设置</span><span class="sxs-lookup"><span data-stu-id="47780-133">Automatically set at the start of a shift</span></span>         |
|![带 x 的灰色圆圈，指示"关"shift](../../media/flw-presence-off-shift.png) <span data-ttu-id="47780-135">关班</span><span class="sxs-lookup"><span data-stu-id="47780-135">Off shift</span></span>     |         |<span data-ttu-id="47780-136">在轮班结束时自动设置</span><span class="sxs-lookup"><span data-stu-id="47780-136">Automatically set at the end of a shift</span></span>         |
|![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="47780-138">忙碌</span><span class="sxs-lookup"><span data-stu-id="47780-138">Busy</span></span>      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="47780-140">忙碌</span><span class="sxs-lookup"><span data-stu-id="47780-140">Busy</span></span>         |<span data-ttu-id="47780-141">自动设置。</span><span class="sxs-lookup"><span data-stu-id="47780-141">Automatically set.</span></span> <span data-ttu-id="47780-142">还可以在前线辅助角色轮班时手动设置。</span><span class="sxs-lookup"><span data-stu-id="47780-142">Can also be manually set when the Frontline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="47780-143">不轮班访问 Teams</span><span class="sxs-lookup"><span data-stu-id="47780-143">Off shift access to Teams</span></span>

<span data-ttu-id="47780-144">此功能允许你在一线员工轮班时管理对 Teams 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="47780-144">This feature lets you manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="47780-145">如果一线员工在轮班时访问 Teams，可以将 Teams 设置为显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="47780-145">You can set Teams to display a message to Frontline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="47780-146">一线员工必须 **单击"我接受** "才能确认消息，然后才能使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="47780-146">Frontline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="47780-147">可以使用默认消息、从一组预定义邮件中选择，或自定义邮件以显示任何需要的文本。</span><span class="sxs-lookup"><span data-stu-id="47780-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="47780-148">下面是默认消息：</span><span class="sxs-lookup"><span data-stu-id="47780-148">Here's the default message:</span></span>

![默认消息的屏幕截图](../../media/shifts-presence-message.png)

<span data-ttu-id="47780-150">还可以设置消息的显示频率，并设置第一个班次开始或最后一个轮班结束与限制 Teams 访问之间的宽限期。</span><span class="sxs-lookup"><span data-stu-id="47780-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="47780-151">管理基于班次的访问</span><span class="sxs-lookup"><span data-stu-id="47780-151">Manage shift-based access</span></span>

<span data-ttu-id="47780-152">作为管理员，您可以使用策略来控制组织中一线员工基于排班的存在。</span><span class="sxs-lookup"><span data-stu-id="47780-152">As an admin, you use policies to control shift-based presence for Frontline Workers in your organization.</span></span> <span data-ttu-id="47780-153">可以使用以下 PowerShell cmdlet 管理这些策略：</span><span class="sxs-lookup"><span data-stu-id="47780-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="47780-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="47780-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="47780-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="47780-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="47780-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="47780-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="47780-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="47780-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="47780-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="47780-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="47780-159">使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置想要的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="47780-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="47780-160">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="47780-160">Here's some examples.</span></span> <span data-ttu-id="47780-161">有关每个策略设置和参数的详细信息，包括可以选择的预定义的轮班消息列表，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="47780-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="47780-162">示例 1</span><span class="sxs-lookup"><span data-stu-id="47780-162">Example 1</span></span>

<span data-ttu-id="47780-163">本示例创建一个名为 Off Shift Teams Access 默认消息的新策略。</span><span class="sxs-lookup"><span data-stu-id="47780-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="47780-164">在此策略中，基于班次的显示状态将打开，每次分配此策略的用户在轮班时访问 Teams 时，都会显示默认消息。</span><span class="sxs-lookup"><span data-stu-id="47780-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="47780-165">如果接受消息，用户可以在轮班时使用 Teams，第一个班次开始或最后一个轮班结束与限制访问之间的宽限期为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="47780-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="47780-166">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="47780-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="47780-167">若要查看可用于此参数的预定义消息的列表，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="47780-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="47780-168">示例 2</span><span class="sxs-lookup"><span data-stu-id="47780-168">Example 2</span></span> 

<span data-ttu-id="47780-169">本示例创建一个名为 Off Shift Teams Access 自定义消息的新策略。</span><span class="sxs-lookup"><span data-stu-id="47780-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="47780-170">在此策略中，每次分配此策略的用户在轮班时访问 Teams 时，都会打开基于班次的显示状态并显示自定义消息。</span><span class="sxs-lookup"><span data-stu-id="47780-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="47780-171">如果接受消息，用户可以在轮班时使用 Teams，第一个班次开始或最后一个轮班结束与限制访问之间的宽限期为 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="47780-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="47780-172">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="47780-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="47780-173">若要了解有关详细信息，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="47780-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="47780-174">示例 3</span><span class="sxs-lookup"><span data-stu-id="47780-174">Example 3</span></span>

<span data-ttu-id="47780-175">本示例创建名为 Off Shift Teams Access Message1 的新策略。</span><span class="sxs-lookup"><span data-stu-id="47780-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="47780-176">在此策略中，每次分配此策略的用户在轮班时访问 Teams 时，都会打开基于班次的显示状态，并显示以下预定义消息。</span><span class="sxs-lookup"><span data-stu-id="47780-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="47780-177">"您的雇主不会授权或批准非豁免或每小时员工在其非工作时间使用其网络、应用程序、系统或工具。</span><span class="sxs-lookup"><span data-stu-id="47780-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="47780-178">接受后，即表示你确认在非班次期间使用 Teams 未授权，并且你将不会获得补偿。"</span><span class="sxs-lookup"><span data-stu-id="47780-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="47780-179">如果接受消息，用户可以在轮班时使用 Teams，第一个班次开始或最后一个轮班结束与限制访问之间的宽限期为 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="47780-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="47780-180">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="47780-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="47780-181">若要查看可用于此参数的预定义消息的列表，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="47780-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="47780-182">示例 4</span><span class="sxs-lookup"><span data-stu-id="47780-182">Example 4</span></span>

<span data-ttu-id="47780-183">本示例将名为 Off Shift Teams Access 自定义消息的策略分配给名为 remy@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="47780-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="47780-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="47780-184">Related topics</span></span>

- [<span data-ttu-id="47780-185">在 Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="47780-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="47780-186">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="47780-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
