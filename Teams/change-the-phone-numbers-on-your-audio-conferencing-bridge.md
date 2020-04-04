---
title: 更改音频会议桥的电话号码
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
description: 了解将新服务电话号码分配给你的会议桥所需的步骤，以便为你的用户扩展覆盖范围。
ms.openlocfilehash: 571b7a9c14db1601e0a4b94740395ad087808a49
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139071"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="74095-103">更改音频会议网桥中的电话号码</span><span class="sxs-lookup"><span data-stu-id="74095-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="74095-104">当您购买**音频会议**许可证时，Microsoft 将为您的组织托管您的音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="74095-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="74095-105">音频会议网桥提供来自不同位置的拨入电话号码，以便会议组织者和参与者可以使用电话加入 Skype for business 或 Microsoft 团队会议。</span><span class="sxs-lookup"><span data-stu-id="74095-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="74095-106">除了已分配给您的会议网桥的电话号码，您还可以从其他位置[获取其他服务号码](/microsoftteams/getting-service-phone-numbers)（用于音频会议的收费和免费电话号码），然后将它们分配给会议桥，以便您可以为您的用户展开覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="74095-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74095-107">为能够分配/取消分配会议网桥的电话号码，电话号码必须是 "*服务*" 号码。</span><span class="sxs-lookup"><span data-stu-id="74095-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="74095-108">你可以通过导航到旧版门户中的**语音** > **电话号码**并在 "**数字类型**" 列中查看，来查看号码的类型。</span><span class="sxs-lookup"><span data-stu-id="74095-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the legacy portal and looking in the **Number Type** column.</span></span> <span data-ttu-id="74095-109">为了让用户拨入免费电话号码上的网桥，应首先设置 Office 365 通信点数。</span><span class="sxs-lookup"><span data-stu-id="74095-109">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="74095-110">将新的服务电话号码分配给会议网桥的操作步骤</span><span class="sxs-lookup"><span data-stu-id="74095-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="74095-111">步骤 1-将新电话号码分配给您的音频会议桥</span><span class="sxs-lookup"><span data-stu-id="74095-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="74095-112">使用你的工作帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="74095-112">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="74095-113">转到**Microsoft 365 管理中心** > **管理中心** > **团队 & Skype** > **旧门户** > **语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="74095-113">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="74095-114">从列表中选择电话号码，然后在 "操作" 窗格中单击 "**分配**"。</span><span class="sxs-lookup"><span data-stu-id="74095-114">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="74095-115">在" **分配**"页面上，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="74095-115">On the **Assign** page, click **Save**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="74095-116">步骤 2-更改您的会议桥的默认电话号码（可选）</span><span class="sxs-lookup"><span data-stu-id="74095-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="74095-117">您的会议网桥的默认电话号码定义了当参与者或组织者在会议中发出出站呼叫时，将使用的呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="74095-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="74095-118">只有服务收费电话号码才能设置为您的会议桥的默认号码;**服务免费电话号码不能设置为您的会议网桥的默认号码**。</span><span class="sxs-lookup"><span data-stu-id="74095-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="74095-119">如果您要分配服务的收费电话号码，并且想要将其设置为您的音频会议网桥的新默认号码，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="74095-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

1. <span data-ttu-id="74095-120">使用你的工作帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="74095-120">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="74095-121">转到**Microsoft 365 管理中心** > **管理中心** > **团队 & Skype** > **会议** > **桥**。</span><span class="sxs-lookup"><span data-stu-id="74095-121">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="74095-122">突出显示要配置为默认电话的服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="74095-122">Highlight the service toll number that you want to configure as the default.</span></span>

4. <span data-ttu-id="74095-123">选择“**设置为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="74095-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="74095-124">步骤 3-更改用户的会议邀请中包含的默认电话号码（可选）</span><span class="sxs-lookup"><span data-stu-id="74095-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="74095-125">在安排会议时，用户的默认电话号码是会议邀请中包含的电话号码。</span><span class="sxs-lookup"><span data-stu-id="74095-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="74095-126">有关详细信息（包括如何为新用户分配 defaul 电话号码），请参阅[设置 Microsoft 团队邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)，或[在 Skype for Business Online 中设置邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="74095-126">For more information, including how the defaul phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="74095-127">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="74095-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="74095-128">转到**Microsoft 365 管理中心** > **管理中心** > **团队 & Skype** > **旧版门户** > **音频会议** > **用户**，然后在列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="74095-128">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users**, and select the users on the list.</span></span>

3. <span data-ttu-id="74095-129">在"操作"窗格中单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="74095-129">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="74095-130">在 "**默认收费电话号码**" 或 "**默认免费电话号码**" 下，选择列表中的号码，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="74095-130">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="74095-131">保存更改后，新的默认电话号码将包含在组织者下次安排新会议时的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="74095-131">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="74095-132">步骤 4-使用会议迁移服务更新用户的现有会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="74095-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="74095-133">对于接下来的两个步骤，你将需要启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="74095-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="74095-134">如果已更新某些或所有用户的会议邀请中 inlcuded 的默认电话号码，则可以选择更新已发送给组织中的用户的会议邀请，并使用会议迁移服务更改其默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="74095-134">If you updated the default phone numbers that are inlcuded in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="74095-135">有关更多信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="74095-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="74095-136">为在步骤2中更改了默认电话号码的用户运行会议迁移服务（MMS）。</span><span class="sxs-lookup"><span data-stu-id="74095-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="74095-137">要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="74095-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="74095-138">你还可以查看会议迁移状态。</span><span class="sxs-lookup"><span data-stu-id="74095-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="74095-139">一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。</span><span class="sxs-lookup"><span data-stu-id="74095-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="74095-140">取消为会议网桥分配的服务电话号码的操作步骤</span><span class="sxs-lookup"><span data-stu-id="74095-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="74095-141">取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码加入任何会议。</span><span class="sxs-lookup"><span data-stu-id="74095-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="74095-142">由于电话号码已更改，因此，将可能具有电话号码的所有用户更新为其默认号码（如果有），并在从音频会议桥中取消分配电话号码之前更新现有会议邀请非常重要。</span><span class="sxs-lookup"><span data-stu-id="74095-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="74095-143">如果删除电话号码时未更新用户及其会议，则他们的现有会议邀请可能包含不能用于加入会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="74095-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="74095-144">对于前三步，需要启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="74095-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="74095-145">若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="74095-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="74095-146">步骤 1-将要取消分配的电话号码的用户更新为其默认号码之一</span><span class="sxs-lookup"><span data-stu-id="74095-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="74095-147">将具有要取消分配的号码的所有用户的默认收费或免费号码替换为默认号码，并开始重新安排其会议的过程。</span><span class="sxs-lookup"><span data-stu-id="74095-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="74095-148">要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="74095-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="74095-149">您也可以在 Skype for Business 管理中心更改默认的收费或免费的用户数。</span><span class="sxs-lookup"><span data-stu-id="74095-149">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="74095-150">但是，这不会自动重新安排他们的会议。</span><span class="sxs-lookup"><span data-stu-id="74095-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="74095-151">有关其他信息，请参阅[设置 Microsoft 团队邀请中包含的电话号码，](set-the-phone-numbers-included-on-invites-in-teams.md)或[在 Skype for Business Online 中设置邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="74095-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="74095-152">[!注释] 根据组织的规模，这可能需要一段时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="74095-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="74095-153">第 2 步 - 使用 Windows PowerShell 查看会议迁移状态</span><span class="sxs-lookup"><span data-stu-id="74095-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="74095-154">一旦没有任何操作处于*挂起*或*正在进行*状态，将重新安排所有会议。</span><span class="sxs-lookup"><span data-stu-id="74095-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="74095-155">有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="74095-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="74095-156">步骤 3-取消分配音频会议桥的旧电话号码</span><span class="sxs-lookup"><span data-stu-id="74095-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="74095-157">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="74095-157">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="74095-158">转到**Microsoft 365 管理中心** > **管理中心** > **团队 & Skype** > **旧门户** > **语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="74095-158">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="74095-159">如果电话号码是免费号码，请从列表中选择电话号码，然后在 "操作" 窗格中单击 "**取消分配**"。</span><span class="sxs-lookup"><span data-stu-id="74095-159">If the phone number is a toll-free number, select the phone number from the list, and in the Action pane, click **Unassign**.</span></span> <span data-ttu-id="74095-160">如果电话号码是收费电话号码，请联系[Microsoft 支持](https://go.microsoft.com/fwlink/?linkid=2091806)部门，让电话号码未分配。</span><span class="sxs-lookup"><span data-stu-id="74095-160">If the phone number is a toll-number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

4. <span data-ttu-id="74095-161">如果电话号码是收费 fre 号码，请在确认窗口中单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="74095-161">If the phone number is a toll-fre number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="74095-162">从音频会议桥中取消分配电话号码后，用户将不再可以使用该电话号码加入新的或现有会议。</span><span class="sxs-lookup"><span data-stu-id="74095-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="74095-163">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="74095-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="74095-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="74095-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="74095-165">确认 Windows PowerShell 是否准备就绪</span><span class="sxs-lookup"><span data-stu-id="74095-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="74095-166">这些步骤将检查你是否正在运行 Windows PowerShell 版本3.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="74095-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="74095-167">键入 **开始菜单** > **Windows PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="74095-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="74095-168">在 _ Windows PowerShell_ 窗口中键入 **Get-Host** ，以检查版本。</span><span class="sxs-lookup"><span data-stu-id="74095-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="74095-169">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="74095-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="74095-170">请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。</span><span class="sxs-lookup"><span data-stu-id="74095-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="74095-171">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="74095-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="74095-172">你还需要安装适用于 Skype for business Online 的 Windows PowerShell 模块，使你能够创建连接到 Skype for business Online 的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="74095-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="74095-173">此模块仅在64位计算机上受支持，并且可从[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下载中心下载。</span><span class="sxs-lookup"><span data-stu-id="74095-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="74095-174">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="74095-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="74095-175">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="74095-175">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="74095-176">启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74095-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="74095-177">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="74095-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="74095-178">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="74095-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="74095-179">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="74095-179">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="74095-180">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="74095-180">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="74095-181">如果需要有关启动 Windows PowerShell 的详细信息，请参阅使用 Windows PowerShell[连接到单个 Windows powershell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[连接到 Skype for business Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="74095-181">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="74095-182">节省时间并实现自动化</span><span class="sxs-lookup"><span data-stu-id="74095-182">Save time and automate</span></span>

<span data-ttu-id="74095-183">为了通过自动化此过程节省时间，你可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688)或**set-csonlinedialinconferencinguserdefaultnumber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="74095-183">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="74095-184">使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="74095-184">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="74095-185">若要更改用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="74095-185">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="74095-186">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="74095-186">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74095-187">若要查找 BridgeID，请使用**get-csonlinedialinconferencingbridge**。</span><span class="sxs-lookup"><span data-stu-id="74095-187">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="74095-188">若要为没有默认免费电话号码的所有用户将默认免费电话号码设置为 8005551234，请运行：</span><span class="sxs-lookup"><span data-stu-id="74095-188">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="74095-189">若要为默认免费电话号码已设置为 8005551234 的所有用户将默认免费电话号码更改为 8005551239，并自动重新安排其会议，请运行：</span><span class="sxs-lookup"><span data-stu-id="74095-189">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="74095-190">若要为位于美国的所有用户将默认免费电话号码设置为 8005551234，并自动重新安排其会议，请运行：</span><span class="sxs-lookup"><span data-stu-id="74095-190">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="74095-191">上面使用的位置需要与在 Microsoft 365 管理中心中设置的用户联系信息匹配。</span><span class="sxs-lookup"><span data-stu-id="74095-191">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="74095-192">故障排除</span><span class="sxs-lookup"><span data-stu-id="74095-192">Troubleshooting</span></span>

<span data-ttu-id="74095-193">**"取消分配" 按钮呈灰显**</span><span class="sxs-lookup"><span data-stu-id="74095-193">**Unassign button is greyed-out**</span></span>

<span data-ttu-id="74095-194">您想要取消分配某个号码，但该按钮在 hoovering 上时呈灰显状态，如果在上，您将被重定向到联系支持人员，并显示以下消息： _"默认或共享号码可以储存从桥中取消分配。要取消分配专用的收费电话，请联系支持部门。_"。</span><span class="sxs-lookup"><span data-stu-id="74095-194">You want to Unassign a number but the button is greyed-out and if while hoovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="74095-195">若要获取有关桥的详细信息，请运行以下 Powershell：</span><span class="sxs-lookup"><span data-stu-id="74095-195">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="74095-196">结果，除了标识、名称和区域之类的其他信息之外，还应包含 DefaultServiceNumber。</span><span class="sxs-lookup"><span data-stu-id="74095-196">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="74095-197">**例如**，若要取消分配，DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="74095-197">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="74095-198">有关 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74095-198">About Windows PowerShell</span></span>

<span data-ttu-id="74095-199">可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。</span><span class="sxs-lookup"><span data-stu-id="74095-199">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="74095-200">Windows PowerShell 可帮助你使用单一的管理点管理 Office 365 和 Skype for business Online，尤其是当你有多个任务需要执行此操作时。</span><span class="sxs-lookup"><span data-stu-id="74095-200">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="74095-201">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="74095-201">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="74095-202">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="74095-202">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="74095-203">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="74095-203">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="74095-204">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="74095-204">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="74095-205">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="74095-205">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="74095-206">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="74095-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="74095-207">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="74095-207">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="74095-208">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="74095-208">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="74095-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="74095-209">Related topics</span></span>
[<span data-ttu-id="74095-210">更改音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="74095-210">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
