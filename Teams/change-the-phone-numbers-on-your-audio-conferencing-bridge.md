---
title: 更改音频会议网桥上的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 了解向会议网桥分配新服务电话号码以扩大用户的覆盖范围所需的步骤。
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102657"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="5ee75-103">更改音频会议网桥中的电话号码</span><span class="sxs-lookup"><span data-stu-id="5ee75-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="5ee75-104">当你购买 **音频会议许可证** 时，Microsoft 将托管你的组织的音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="5ee75-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="5ee75-105">音频会议网桥提供不同位置的拨入电话号码，以便会议组织者和参与者可以使用它们通过电话加入 Skype for Business 或 Microsoft Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="5ee75-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="5ee75-106">除了已分配给会议网桥的电话号码外，您还可以从其他位置获取用于音频会议) 的其他服务号码 [ (](./getting-service-phone-numbers.md) 收费和免费号码，然后将这些号码分配给会议网桥，以便你可以扩大用户的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="5ee75-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](./getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ee75-107">为了能够为会议网桥分配/取消分配电话号码，电话号码必须是"*服务"* 号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="5ee75-108">导航到管理中心中的"语音"或"电话"并查看"号码类型"Microsoft Teams，  >  可看到号码的类型。 </span><span class="sxs-lookup"><span data-stu-id="5ee75-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="5ee75-109">Microsoft 365或Office 365，必须先设置通信信用额度，用户才能拨打免费号码拨入网桥。</span><span class="sxs-lookup"><span data-stu-id="5ee75-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="5ee75-110">将新的服务电话号码分配给会议网桥的操作步骤</span><span class="sxs-lookup"><span data-stu-id="5ee75-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="5ee75-111">步骤 1 - 将新电话号码分配给音频会议网桥</span><span class="sxs-lookup"><span data-stu-id="5ee75-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="5ee75-112">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="5ee75-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5ee75-113">在左侧导航窗格中，转到"**语音** 电话  >  **数字"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="5ee75-114">从列表中选择电话号码，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="5ee75-115">在"**编辑"** 页面上的 **"分配到"下**，展开下拉列表，然后选择"会议 **网桥** 应用  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="5ee75-116">步骤 2 - 更改会议网桥的默认电话号码 (可选) </span><span class="sxs-lookup"><span data-stu-id="5ee75-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="5ee75-117">会议网桥的默认电话号码定义当参与者或组织者从会议内拨打出站呼叫时将使用的呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="5ee75-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="5ee75-118">只能将服务收费电话号码设置为会议网桥的默认号码; **无法将服务** 免费号码设置为会议网桥的默认号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="5ee75-119">如果要分配服务收费电话号码，并且希望将其设置为音频会议网桥的新默认号码，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5ee75-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="5ee75-120">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="5ee75-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5ee75-121">在左侧导航窗格中，转到"**会议**  >  **会议网桥"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="5ee75-122">突出显示要配置为默认值的服务收费电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="5ee75-123">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="5ee75-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="5ee75-124">步骤 3 - 更改用户的会议邀请中包含的默认电话号码 (可选) </span><span class="sxs-lookup"><span data-stu-id="5ee75-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="5ee75-125">用户的默认电话号码是安排会议时包含在其会议邀请中的号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="5ee75-126">有关详细信息，包括如何为新用户分配默认电话号码，请参阅在 Microsoft Teams 中设置邀请中包含的电话号码[或](set-the-phone-numbers-included-on-invites-in-teams.md)设置 Skype for Business Online 中的邀请[中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="5ee75-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="5ee75-127">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="5ee75-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5ee75-128">在左侧导航窗格中，转到 **"用户"，** 然后单击列表中的所需用户的"显示名称"。</span><span class="sxs-lookup"><span data-stu-id="5ee75-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="5ee75-129">在"**音频会议"旁边**，单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="5ee75-130">在 **"收费** 电话号码 **"或"免费** 电话号码"下，从下拉列表中选择号码，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="5ee75-131">应用更改后，组织者下次安排新会议时，新的默认电话号码将包含在会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="5ee75-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="5ee75-132">步骤 4 - 使用会议迁移服务更新用户的现有会议邀请 (可选) </span><span class="sxs-lookup"><span data-stu-id="5ee75-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="5ee75-133">对于接下来的两个步骤，需要开始Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5ee75-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="5ee75-134">如果您更新了部分或所有用户的会议邀请中包含的默认电话号码，您可以选择更新在使用会议迁移服务更改用户的默认电话号码之前已发送给您的组织中的用户的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="5ee75-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="5ee75-135">有关更多信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="5ee75-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="5ee75-136">为在步骤 2 中更改 (用户) MMS 帐户运行会议迁移服务。</span><span class="sxs-lookup"><span data-stu-id="5ee75-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="5ee75-137">要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ee75-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="5ee75-p107">你还可以查看会议迁移状态。一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。</span><span class="sxs-lookup"><span data-stu-id="5ee75-p107">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="5ee75-140">取消为会议网桥分配的服务电话号码的操作步骤</span><span class="sxs-lookup"><span data-stu-id="5ee75-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="5ee75-141">取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码加入任何会议。</span><span class="sxs-lookup"><span data-stu-id="5ee75-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="5ee75-142">由于电话号码正在更改，因此，必须更新具有电话号码作为默认号码的所有用户 (如果有) ，并且从音频会议网桥取消分配电话号码之前更新其现有会议邀请。</span><span class="sxs-lookup"><span data-stu-id="5ee75-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="5ee75-143">如果在不更新用户及其会议的情况下删除了电话号码，则其现有会议邀请可能包含一个无法加入其会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="5ee75-144">对于前三步，需要启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5ee75-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="5ee75-145">若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="5ee75-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="5ee75-146">步骤 1 - 更新将电话号码取消分配为默认号码之一的用户</span><span class="sxs-lookup"><span data-stu-id="5ee75-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="5ee75-147">将具有取消分配号码的所有用户的默认收费或免费号码替换为默认号码，并开始重新安排其会议的过程。</span><span class="sxs-lookup"><span data-stu-id="5ee75-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="5ee75-148">要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ee75-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="5ee75-149">还可在管理中心内更改默认收费或免费Microsoft Teams号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5ee75-150">但是，这不会自动重新安排他们的会议。</span><span class="sxs-lookup"><span data-stu-id="5ee75-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="5ee75-151">有关其他信息，请参阅[设置](set-the-phone-numbers-included-on-invites-in-teams.md)邀请中包含的电话号码Microsoft Teams或在 Skype for Business Online 中设置[邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="5ee75-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="5ee75-152">[!注释] 根据组织的规模，这可能需要一段时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="5ee75-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="5ee75-153">第 2 步 - 使用 Windows PowerShell 查看会议迁移状态</span><span class="sxs-lookup"><span data-stu-id="5ee75-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="5ee75-154">在没有任何操作进入"挂起"或"正在进行"状态后，将 *重新安排所有* 会议。</span><span class="sxs-lookup"><span data-stu-id="5ee75-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="5ee75-155">有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="5ee75-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="5ee75-156">步骤 3 - 从音频会议网桥取消分配旧电话号码</span><span class="sxs-lookup"><span data-stu-id="5ee75-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="5ee75-157">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="5ee75-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5ee75-158">在左侧导航栏中，转到"**语音**  >  **"电话号码"**。</span><span class="sxs-lookup"><span data-stu-id="5ee75-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="5ee75-159">如果电话号码是免费电话号码，请从列表中选择电话号码，然后单击"释放 **"。**</span><span class="sxs-lookup"><span data-stu-id="5ee75-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="5ee75-160">如果电话号码是收费电话号码，请联系 [Microsoft](/microsoft-365/admin/contact-support-for-business-products) 支持部门以取消分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-160">If the phone number is a toll number, please contact [Microsoft support](/microsoft-365/admin/contact-support-for-business-products) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="5ee75-161">如果电话号码是免费电话号码，请在确认窗口中 **单击"是** "。</span><span class="sxs-lookup"><span data-stu-id="5ee75-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5ee75-162">从音频会议网桥取消分配电话号码后，用户将无法再使用电话号码加入新会议或现有会议。</span><span class="sxs-lookup"><span data-stu-id="5ee75-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="5ee75-163">节省时间并自动执行</span><span class="sxs-lookup"><span data-stu-id="5ee75-163">Save time and automate</span></span>

<span data-ttu-id="5ee75-164">若要通过自动执行此过程来节省时间，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ee75-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="5ee75-165">使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-165">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="5ee75-166">若要更改用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="5ee75-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="5ee75-167">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ee75-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ee75-168">若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge**。</span><span class="sxs-lookup"><span data-stu-id="5ee75-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="5ee75-169">若要为没有默认免费电话号码的所有用户将默认免费电话号码设置为 8005551234，请运行：</span><span class="sxs-lookup"><span data-stu-id="5ee75-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="5ee75-170">若要为默认免费电话号码已设置为 8005551234 的所有用户将默认免费电话号码更改为 8005551239，并自动重新安排其会议，请运行：</span><span class="sxs-lookup"><span data-stu-id="5ee75-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="5ee75-171">若要为位于美国的所有用户将默认免费电话号码设置为 8005551234，并自动重新安排其会议，请运行：</span><span class="sxs-lookup"><span data-stu-id="5ee75-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="5ee75-172">上面使用的位置需要匹配用户在管理 (中) 设置的Microsoft 365信息。</span><span class="sxs-lookup"><span data-stu-id="5ee75-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5ee75-173">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5ee75-173">Troubleshooting</span></span>

<span data-ttu-id="5ee75-174">**"取消分配"按钮不可用**</span><span class="sxs-lookup"><span data-stu-id="5ee75-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="5ee75-175">您希望取消分配号码，但按钮不可用，并且如果将鼠标悬停在该号码上，将重定向至联系支持人员，显示以下消息："无法从网桥取消分配默认号码或共享号码。 _若要取消分配专用收费号码，请联系支持人员_。"。</span><span class="sxs-lookup"><span data-stu-id="5ee75-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="5ee75-176">若要获取有关网桥 () ，请运行以下 Powershell：</span><span class="sxs-lookup"><span data-stu-id="5ee75-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="5ee75-177">结果（除了标识、名称和区域等其他信息）还应包含 DefaultServiceNumber。</span><span class="sxs-lookup"><span data-stu-id="5ee75-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="5ee75-178">**示例**， 要取消分配，DefaultServiceNumber 为 "8005551234"</span><span class="sxs-lookup"><span data-stu-id="5ee75-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="5ee75-179">有关 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee75-179">About Windows PowerShell</span></span>

<span data-ttu-id="5ee75-180">可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。</span><span class="sxs-lookup"><span data-stu-id="5ee75-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="5ee75-181">Windows PowerShell单点管理Microsoft 365管理 Office 365 Skype for Business Online，可以简化日常工作，尤其是有多个任务需要执行时。</span><span class="sxs-lookup"><span data-stu-id="5ee75-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="5ee75-182">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5ee75-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="5ee75-183">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5ee75-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="5ee75-184">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee75-184">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

<span data-ttu-id="5ee75-185">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="5ee75-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5ee75-186">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="5ee75-186">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="5ee75-187">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5ee75-187">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="5ee75-188">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5ee75-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="5ee75-189">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5ee75-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="5ee75-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ee75-190">Related topics</span></span>
[<span data-ttu-id="5ee75-191">更改音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="5ee75-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)