---
title: 更改音频会议网桥的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 在购买音频会议许可证时，是 Microsoft 在托管组织的音频会议网桥。 该会议网桥会提供不同地点的拨入电话号码，会议组织者和参与者可以借助电话用这些号码参加 Skype for Business 或者 Microsoft Teams 会议。
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255708"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="a8a46-104">更改音频会议网桥的电话号码</span><span class="sxs-lookup"><span data-stu-id="a8a46-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="a8a46-105">在购买 **音频会议** 许可证时，是 Microsoft 在托管组织的 *音频会议网桥* 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-105">When you buy **Skype for Business PSTN Conferencing** licenses, Microsoft is hosting a *conferencing bridge*  for your organization.</span></span> <span data-ttu-id="a8a46-106">该会议网桥会提供不同地点的拨入电话号码，会议组织者和参与者可以借助电话用这些号码参加 Skype for Business 或者 Microsoft Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="a8a46-106">The conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join meetings using a phone.</span></span>

<span data-ttu-id="a8a46-107">除了已分配的会议网桥电话号码，还可以从其他位置 [获取额外的服务号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) （用于音频会议的收费和免费电话号码），然后分配给会议网桥以便展开用户的范围。</span><span class="sxs-lookup"><span data-stu-id="a8a46-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [Getting Skype for Business service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (toll and toll-free numbers used for dial-in conferencing) from other locations and then assign them to the conferencing bridge so you can expand the area/country/region coverage for your users.</span></span>

> [!NOTE]
> <span data-ttu-id="a8a46-108">为了能够为某个会议网桥分配 / 取消分配电话号码，电话号码必须是一个“ *服务* ”号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a 'service' number.</span></span> <span data-ttu-id="a8a46-109">通过导航至 **语音** > **电话号码** 并查看 **号码类型** 列，可以看到号码类型是什么。</span><span class="sxs-lookup"><span data-stu-id="a8a46-109">You can see the type of number it is by using the **Voice** > **Phone numbers** tab and look under the **Number Type** column.</span></span> <span data-ttu-id="a8a46-110">为了让用户拨入免费电话号码上的网桥，应首先设置 Office 365 通信点数。</span><span class="sxs-lookup"><span data-stu-id="a8a46-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="a8a46-111">将新的服务电话号码分配给会议网桥的操作步骤</span><span class="sxs-lookup"><span data-stu-id="a8a46-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="a8a46-112">第 1 步 - 将新的电话号码分配给音频会议网桥</span><span class="sxs-lookup"><span data-stu-id="a8a46-112">Step 1 - Assign the new phone number to your conferencing bridge</span></span>

1. <span data-ttu-id="a8a46-113">使用工作帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8a46-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="a8a46-114">转至 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **语音** > **电话号码** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-114">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="a8a46-115">从列表中选择电话号码，然后在“操作”窗格中，单击 **分配** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-115">Select the phone number from the list and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="a8a46-116">在 **分配** 页面上，单击 **保存** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-116">On the **Assign** page, click **Save**.</span></span>

    <span data-ttu-id="a8a46-117">只有收费服务电话号码可以设置为会议网桥的默认号码； **免费服务电话号码不能设置为会议网桥的默认号码** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-117">Only a service toll number can be set as the default number for your conferencing bridge, **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="a8a46-118">如果在分配收费服务号码时希望将其设置为会议网桥的新默认号码，请选择 **使用此号码作为默认号码** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-118">If you are assigning a service toll number and you would like to set it as the new default number for your conferencing bridge, check **Use this number as the default**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8a46-119">[!注释] 分配了新电话号码后，即使该号码已经是新默认号码，现有用户的默认号码也不会更改。</span><span class="sxs-lookup"><span data-stu-id="a8a46-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="a8a46-120">若要设置添加到组织者的会议邀请的默认收费电话号码或免费电话号码，请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md) 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="a8a46-121">第 2 步 - 更改用户会议邀请中包含的默认电话号码（可选）</span><span class="sxs-lookup"><span data-stu-id="a8a46-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="a8a46-122">用户的默认电话是他们安排会议时在会议邀请中包含的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="a8a46-123">有关详细信息，请参阅 [设置邀请中的电话号码](set-the-phone-numbers-included-on-invites.md) 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-123">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

1. <span data-ttu-id="a8a46-124">使用工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8a46-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a8a46-125">转至 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议** > **用户** 在列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="a8a46-125">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Dial-in conferencing** > **Dial-in users** and find the users in the list.</span></span>

3. <span data-ttu-id="a8a46-126">在"操作"窗格中单击 **编辑** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-126">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="a8a46-127">在 **默认收费电话号码** 或者 **默认免费电话号码** 下，选择列表中的电话号码并单击 **保存** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-127">Under ** Default toll number** or Default toll-free number, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="a8a46-128">保存更改后，他们再安排会议时，组织者的会议邀请中包含的将是新的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-128">Once the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="a8a46-129">第 3 步 - 使用会议迁移服务更新用户的现有会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="a8a46-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="a8a46-130">接下来的两个步骤，将需要启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a8a46-130">For the first three steps, you will need to start Windows PowerShell.</span></span>

<span data-ttu-id="a8a46-131">通过使用会议迁移服务，可以选择更新会议邀请，这些邀请在默认电话号码被更改之前就发送给了组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="a8a46-131">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers had been changed.</span></span> <span data-ttu-id="a8a46-132">有关更多信息，请参阅 [设置会议迁移服务 (MMS)](setting-up-the-meeting-migration-service-mms.md) 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-132">For additional information, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

- <span data-ttu-id="a8a46-133">对其默认电话号码已在第 2 步中更改了的用户运行会议迁移服务 (MMS)。</span><span class="sxs-lookup"><span data-stu-id="a8a46-133">Run the Meeting Migration Service for the users that had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="a8a46-134">要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a8a46-134">To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="a8a46-p109">亦可查看会议迁移状态。一旦在 *挂起* 或者 *正在进行* 状态中没有操作，所有会议将被重新安排。</span><span class="sxs-lookup"><span data-stu-id="a8a46-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="a8a46-137">取消为会议网桥分配的服务电话号码的操作步骤</span><span class="sxs-lookup"><span data-stu-id="a8a46-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="a8a46-138">取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码参加任何会议。</span><span class="sxs-lookup"><span data-stu-id="a8a46-138">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="a8a46-139">由于电话号码在不断变化，在取消为音频会议网桥分配的电话号码之前，重要的是更新所有可能具有某个电话号码作为其默认号码的用户（如果存在），并更新现有会议邀请。</span><span class="sxs-lookup"><span data-stu-id="a8a46-139">Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the bridge.</span></span>

<span data-ttu-id="a8a46-140">如果删除电话号码时没有通知用户及更新其会议，那么他们的现有会议邀请可能包含无法再用于加入其会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>

<span data-ttu-id="a8a46-141">对于前三步，需要启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a8a46-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="a8a46-142">若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="a8a46-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="a8a46-143">第 1 步 - 更新其默认电话号码之一要被取消分配的电话号码的用户</span><span class="sxs-lookup"><span data-stu-id="a8a46-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="a8a46-p112">为其默认号码是要取消分配的号码的用户替换默认的收费或免费号码，并开始重新安排其会议的过程。要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a8a46-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 ><span data-ttu-id="a8a46-146">还可以在 Sktpy 管理中心更改默认的用户收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-146">You can also change the default toll or toll-free number of users in the Skype for Business admin center, however, this won't automatically reschedule their meetings.</span></span> <span data-ttu-id="a8a46-147">但是，这不会自动重新安排他们的会议。</span><span class="sxs-lookup"><span data-stu-id="a8a46-147">However, this won't automatically reschedule their meetings.</span></span>

 <span data-ttu-id="a8a46-148">有关详细信息，请参阅 [设置邀请中的电话号码](set-the-phone-numbers-included-on-invites.md) 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-148">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a8a46-149">根据组织的规模，这可能需要一段时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="a8a46-149">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="a8a46-150">第 2 步 - 使用 Windows PowerShell 查看会议迁移状态</span><span class="sxs-lookup"><span data-stu-id="a8a46-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="a8a46-151">一旦在 *挂起* 或 *正在进行* 状态下没有操作，所有会议将被重新安排。</span><span class="sxs-lookup"><span data-stu-id="a8a46-151">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="a8a46-152">有关会议迁移服务的详细信息，请参阅 [设置会议迁移服务 (MMS)](setting-up-the-meeting-migration-service-mms.md) 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="a8a46-153">第 3 步 - 取消为音频会议网桥分配的旧电话号码</span><span class="sxs-lookup"><span data-stu-id="a8a46-153">Step 3 - Unassign the old phone number from the dial-in conferencing bridge</span></span>

1. <span data-ttu-id="a8a46-154">使用工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8a46-154">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a8a46-155">转至 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **语音** > **电话号码** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-155">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="a8a46-156">从列表中选择电话号码，然后在“操作”窗格中单击 **取消分配** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-156">Select the phone number from the list and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="a8a46-157">在确认窗口中，单击 **是** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-157">In the ** Reset conference ID?** window, click **Yes**.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="a8a46-158">从音频会议网桥中取消分配某个电话号码后，用户就无法使用该电话号码参加新的或现有会议。</span><span class="sxs-lookup"><span data-stu-id="a8a46-158">Once a phone number is unassigned from a conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a8a46-159">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="a8a46-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="a8a46-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="a8a46-160"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="a8a46-161">确认 Windows PowerShell 是否准备就绪</span><span class="sxs-lookup"><span data-stu-id="a8a46-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="a8a46-162">这些步骤检查运行的是不是 3.0 或以上版本的 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a8a46-162">Check that you are running Windows PowerShell version 3.0 or higher</span></span>

1. <span data-ttu-id="a8a46-163">键入 **开始菜单** > **Windows PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-163">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="a8a46-164">在 _ Windows PowerShell_ 窗口中键入 **Get-Host** ，以检查版本。</span><span class="sxs-lookup"><span data-stu-id="a8a46-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="a8a46-p114">如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="a8a46-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="a8a46-168">还需要为 Skype for Business Online 安装 Windows PowerShell 模块，以便创建一个连接 Skype for Business Online 的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="a8a46-168">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="a8a46-169">仅 64 位计算机支持此模块，可在 Microsoft 下载中心的 [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) 下载此模块。</span><span class="sxs-lookup"><span data-stu-id="a8a46-169">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="a8a46-170">出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="a8a46-170">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="a8a46-171">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a8a46-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="a8a46-172">启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8a46-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="a8a46-173">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="a8a46-173">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="a8a46-174">从 **开始菜单** > **Windows PowerShell** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-174">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="a8a46-175">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="a8a46-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8a46-176">首次使用 Skype for Business Online Windows PowerShell 模块时只需运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="a8a46-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="a8a46-177">如果想要深入了解如何启动 Windows PowerShell，请参阅 [在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 或 [使用 Windows PowerShell 连接到 Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="a8a46-178">节省时间并自动给出</span><span class="sxs-lookup"><span data-stu-id="a8a46-178">Save time or automate</span></span>

<span data-ttu-id="a8a46-179">要通过自动执行此过程来节省时间，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a8a46-179">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="a8a46-180">使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 更改特定用户的默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-180">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="a8a46-181">若要更改用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="a8a46-181">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="a8a46-182">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 基于用户的原始默认电话号码或原始位置来更改其默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8a46-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8a46-183">若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge** 。</span><span class="sxs-lookup"><span data-stu-id="a8a46-183">Note:To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="a8a46-184">为所有没有默认免费电话号码的用户将默认免费电话号码设置为 8005551234，请运行：</span><span class="sxs-lookup"><span data-stu-id="a8a46-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="a8a46-185">若要为默认免费电话号码已设置为 8005551234 的所有用户将默认免费电话号码更改为 8005551239，并自动重新安排其会议，请运行：</span><span class="sxs-lookup"><span data-stu-id="a8a46-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="a8a46-186">若要为位于美国的所有用户将默认免费电话号码设置为 8005551234，并自动重新安排其会议，请运行：</span><span class="sxs-lookup"><span data-stu-id="a8a46-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="a8a46-187">上面使用的位置信息需要与在 Office 365 管理中心中设置的用户联系人信息相匹配。</span><span class="sxs-lookup"><span data-stu-id="a8a46-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="a8a46-188">有关 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8a46-188">About Windows PowerShell</span></span>

<span data-ttu-id="a8a46-189">可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。</span><span class="sxs-lookup"><span data-stu-id="a8a46-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="a8a46-190">Windows PowerShell 可以通过能够简化日常工作的单点管理来帮助管理 Office 365 和 Skype for Business Online，尤其当有多个要执行的任务时。</span><span class="sxs-lookup"><span data-stu-id="a8a46-190">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="a8a46-191">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a8a46-191">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a8a46-192">Windows PowerShell 和 Skype for Business Online 的介绍</span><span class="sxs-lookup"><span data-stu-id="a8a46-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="a8a46-193">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8a46-193">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="a8a46-p117">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="a8a46-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="a8a46-196">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a8a46-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="a8a46-197">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a8a46-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="a8a46-198">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a8a46-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="a8a46-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="a8a46-199">Related topics</span></span>
[<span data-ttu-id="a8a46-200">更改音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="a8a46-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
