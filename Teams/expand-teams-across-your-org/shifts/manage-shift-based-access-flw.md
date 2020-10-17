---
title: 为团队中的一线工作者管理基于班次的访问
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中管理一线工作人员的团队中的基于班次的访问权限。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ec470422e402da07171bef627d1592c73d6c12f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514129"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a><span data-ttu-id="e1d5f-103">为团队中的一线工作者管理基于班次的访问</span><span class="sxs-lookup"><span data-stu-id="e1d5f-103">Manage shift-based access for Firstline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1d5f-104">2020年6月30日生效，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="e1d5f-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="e1d5f-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="e1d5f-107">StaffHub 已停止为2020年6月30日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="e1d5f-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="e1d5f-109">若要了解详细信息，请参阅 [Microsoft StaffHub 已停](microsoft-staffhub-to-be-retired.md)用。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="e1d5f-110">概述</span><span class="sxs-lookup"><span data-stu-id="e1d5f-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="e1d5f-111">Microsoft 团队中的状态表示用户的当前可用性和其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="e1d5f-112">与其他职员相比，一线工作人员的状态通常不会比其他职员更容易预测，因为它们的工作时间通常不是同一天。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-112">The presence of Firstline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="e1d5f-113">作为管理员，你可以将团队配置为显示组织中的一线工作人员的一组基于班次的状态，以指示它们何时处于 "开" 和 "关" 班次。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Firstline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="e1d5f-114">这些基于转换的状态显示 " &mdash; ![ 纯绿色复选标记"，指示 "shift on shift" （ ](../../media/flw-presence-on-shift.png) **On shift** ![ x 的灰色圆圈）指示 "移 ](../../media/flw-presence-off-shift.png) **出**Shift" （ ![ 纯红色圆圈）表示 "忙碌"，表示 "忙碌" ](../../media/flw-presence-busy.png) **Busy** &mdash; 。 [default set of presence states](../../presence-admins.md)</span><span class="sxs-lookup"><span data-stu-id="e1d5f-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="e1d5f-115">通过这两组状态状态，您可以根据自己的角色为组织中的人员配置不同的体验。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="e1d5f-116">使用基于班次的访问，您可以在一线工作人员停止班次时管理团队的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-116">With shift-based access, you can manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="e1d5f-117">例如，您可以将团队设置为显示一条消息，一线工作人员必须在他们使用团队而不是计划班次时才可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-117">For example, you can set Teams to display a message that Firstline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="e1d5f-118">使用场景</span><span class="sxs-lookup"><span data-stu-id="e1d5f-118">Scenario</span></span>

<span data-ttu-id="e1d5f-119">下面是组织如何管理基于班次的访问的示例。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="e1d5f-120">您的组织中有一线工作人员，仅应在其经理计划和批准的倒班上支付。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-120">You have Firstline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="e1d5f-121">不应在计划班次之外工作所花费的时间进行支付，包括使用团队应用。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="e1d5f-122">您设置了一个自定义消息，显示 "当下班后的时间超出" 班次不计为应付帐款时间 "，当一线工作人员尝试在停止班次时访问团队时，将显示该时间。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Firstline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="e1d5f-123">如果他们选择使用团队，他们单击 " **我接受** " 即表示不会支付这些团队。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="e1d5f-124">您的组织中还包含 salaried 的信息工作者和不起作用的人员。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="e1d5f-125">将您的信息工作者配置为使用团队中的默认状态，同时为一线工作人员提供基于班次的状态。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-125">You configure your information workers to use the default presence states in Teams while giving your Firstline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="e1d5f-126">基于班次的状态</span><span class="sxs-lookup"><span data-stu-id="e1d5f-126">Shift-based presence states</span></span>

<span data-ttu-id="e1d5f-127">下面是基于班次的状态。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="e1d5f-128">应用配置</span><span class="sxs-lookup"><span data-stu-id="e1d5f-128">App configured</span></span> |<span data-ttu-id="e1d5f-129">用户配置</span><span class="sxs-lookup"><span data-stu-id="e1d5f-129">User configured</span></span>  |<span data-ttu-id="e1d5f-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="e1d5f-130">More information</span></span>  |
|---------|---------|---------|
|![稳定绿色复选标记，指示在班次上](../../media/flw-presence-on-shift.png) <span data-ttu-id="e1d5f-132">在班次上</span><span class="sxs-lookup"><span data-stu-id="e1d5f-132">On shift</span></span>     |         |<span data-ttu-id="e1d5f-133">在班次开始时自动设置</span><span class="sxs-lookup"><span data-stu-id="e1d5f-133">Automatically set at the start of a shift</span></span>         |
|![X 的灰色圆圈表示离开班次](../../media/flw-presence-off-shift.png) <span data-ttu-id="e1d5f-135">离开班次</span><span class="sxs-lookup"><span data-stu-id="e1d5f-135">Off shift</span></span>     |         |<span data-ttu-id="e1d5f-136">在班次结束时自动设置</span><span class="sxs-lookup"><span data-stu-id="e1d5f-136">Automatically set at the end of a shift</span></span>         |
|![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="e1d5f-138">忙碌</span><span class="sxs-lookup"><span data-stu-id="e1d5f-138">Busy</span></span>      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) <span data-ttu-id="e1d5f-140">忙碌</span><span class="sxs-lookup"><span data-stu-id="e1d5f-140">Busy</span></span>         |<span data-ttu-id="e1d5f-141">自动设置。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-141">Automatically set.</span></span> <span data-ttu-id="e1d5f-142">当一线工作者在班次上时，也可以手动设置。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-142">Can also be manually set when the Firstline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="e1d5f-143">关闭对团队的班次访问</span><span class="sxs-lookup"><span data-stu-id="e1d5f-143">Off shift access to Teams</span></span>

<span data-ttu-id="e1d5f-144">此功能可让你在一线工作人员停止班次时管理团队的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-144">This feature lets you manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="e1d5f-145">你可以将团队设置为向一线工作人员显示一条消息，前提是他们在关闭班次时访问团队。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-145">You can set Teams to display a message to Firstline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="e1d5f-146">一线工作人员必须单击 " **我接受** " 才能使用团队确认消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-146">Firstline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="e1d5f-147">可以使用默认消息、从一组预定义的消息中进行选择，或自定义消息以显示所需的任何文本。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="e1d5f-148">下面是默认消息：</span><span class="sxs-lookup"><span data-stu-id="e1d5f-148">Here's the default message:</span></span>

![默认邮件的屏幕截图](../../media/shifts-presence-message.png)

<span data-ttu-id="e1d5f-150">你还可以在显示消息时设置频率，并设置在第一次班次开始或上一班次结束以及团队访问受限时的宽限期。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="e1d5f-151">管理基于班次的访问</span><span class="sxs-lookup"><span data-stu-id="e1d5f-151">Manage shift-based access</span></span>

<span data-ttu-id="e1d5f-152">作为管理员，你可以使用策略控制组织中的一线工作人员的基于班次的状态。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-152">As an admin, you use policies to control shift-based presence for Firstline Workers in your organization.</span></span> <span data-ttu-id="e1d5f-153">你可以使用以下 PowerShell cmdlet 管理这些策略：</span><span class="sxs-lookup"><span data-stu-id="e1d5f-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="e1d5f-154">新-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="e1d5f-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="e1d5f-155">CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="e1d5f-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="e1d5f-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="e1d5f-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="e1d5f-157">授权-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="e1d5f-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="e1d5f-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="e1d5f-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="e1d5f-159">使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置所需的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="e1d5f-160">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-160">Here's some examples.</span></span> <span data-ttu-id="e1d5f-161">有关每个策略设置和参数的详细信息，包括可从中进行选择的预定义关闭班次消息的列表，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="e1d5f-162">示例 1</span><span class="sxs-lookup"><span data-stu-id="e1d5f-162">Example 1</span></span>

<span data-ttu-id="e1d5f-163">在此示例中，我们创建一个名为 "关闭班次团队" 的新策略，并访问默认消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="e1d5f-164">在此策略中，打开基于移动的状态，并且每次分配了此策略的用户在关闭班次时都将显示默认消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="e1d5f-165">用户在接受消息时可以使用团队，并且在第一次班次开始或上一班次结束时和访问受限时间之间的宽限期是10分钟。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="e1d5f-166">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="e1d5f-167">若要查看可供此参数选择的预定义消息的列表，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="e1d5f-168">示例 2</span><span class="sxs-lookup"><span data-stu-id="e1d5f-168">Example 2</span></span> 

<span data-ttu-id="e1d5f-169">在此示例中，我们创建一个名为 "关闭倒班团队" 的新策略，访问自定义消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="e1d5f-170">在此策略中，打开基于移动的状态，并且每次分配了此策略的用户在关闭班次时都将显示自定义消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="e1d5f-171">用户在接受消息时可以使用团队，如果他们接受消息，则可以使用团队，在第一次班次开始或上一班次结束时和访问受限时间之间的宽限期是15分钟。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="e1d5f-172">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="e1d5f-173">若要了解详细信息，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="e1d5f-174">示例 3</span><span class="sxs-lookup"><span data-stu-id="e1d5f-174">Example 3</span></span>

<span data-ttu-id="e1d5f-175">在此示例中，我们创建名为 "关闭倒班团队访问 Message1" 的新策略。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="e1d5f-176">在此策略中，将打开基于移动的状态，并且每次分配了此策略的用户在关闭班次时都将显示以下预定义消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="e1d5f-177">"在非工作时间内，您的雇主不会授权或批准通过非豁免或每小时员工使用其网络、应用程序、系统或工具。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="e1d5f-178">通过接受，您确认您在非授权的情况下使用团队，并且不会获得报酬。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="e1d5f-179">用户在接受消息时可以使用团队，如果他们接受消息，则可以使用团队，在第一次班次开始或上一班次结束时和访问受限时间之间的宽限期为3分钟。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="e1d5f-180">使用 **ShiftNoticeMessageType** 参数设置要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="e1d5f-181">若要查看可供此参数选择的预定义消息的列表，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="e1d5f-182">示例 4</span><span class="sxs-lookup"><span data-stu-id="e1d5f-182">Example 4</span></span>

<span data-ttu-id="e1d5f-183">在此示例中，我们将名为 "注销班次团队" 的策略分配给名为 remy@contoso.com 的用户的自定义消息。</span><span class="sxs-lookup"><span data-stu-id="e1d5f-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="e1d5f-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="e1d5f-184">Related topics</span></span>

- [<span data-ttu-id="e1d5f-185">在 Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="e1d5f-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="e1d5f-186">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="e1d5f-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
