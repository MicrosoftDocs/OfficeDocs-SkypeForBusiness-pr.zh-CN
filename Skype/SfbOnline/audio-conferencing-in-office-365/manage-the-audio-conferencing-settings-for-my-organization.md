---
title: 在 Skype for Business Online 中管理我的组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '请参阅 Skype for Business Online 的步骤，为用户和许多其他拨入会议设置分配拨入会议许可和会议 ID。 '
ms.openlocfilehash: d8fc38929e059d0c8fdaf0babec5f8b6fb72856a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255725"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="0c79c-103">在 Skype for Business Online 中管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="0c79c-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="0c79c-104">如果您要在团队中管理这些设置，请参阅 [在 Microsoft Teams 中管理我的组织的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="0c79c-105">在一个位置查看 Skype for Business 的所有音频会议设置可能比较容易。</span><span class="sxs-lookup"><span data-stu-id="0c79c-105">It might be easier for you to see all of the dial-in conferencing settings in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="0c79c-106">分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="0c79c-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="0c79c-107">您不能使用 **Skype for Business 管理中心** 分配的许可证。</span><span class="sxs-lookup"><span data-stu-id="0c79c-107">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span></span> <span data-ttu-id="0c79c-108">您必须使用 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0c79c-108">You can use the Office 365 admin center though too.</span></span> <span data-ttu-id="0c79c-109">请参阅 [分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="0c79c-110">**为用户分配许可证**</span><span class="sxs-lookup"><span data-stu-id="0c79c-110">**** To assign a license for a user</span></span>

1. <span data-ttu-id="0c79c-111">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-112">在**Office 365 管理中心**的左侧导航窗格中，转到 **用户** > **活动用户**，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-112">In the left navigation of the Office 365 admin center, go to Users  Active users > and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c79c-113">[!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="0c79c-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="0c79c-114">然后单击" **编辑**"，单击 **下一步**两次，然后选择许可证并单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="0c79c-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="0c79c-115">你也可以使用 Windows Powershell 向多个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="0c79c-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="0c79c-116"> 有关 PowerShell 脚本的说明和示例，请参阅 [分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  。</span><span class="sxs-lookup"><span data-stu-id="0c79c-116">For for instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="0c79c-117">在"操作"窗格中的**产品许可证**下，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="0c79c-118">在**产品许可证**页上，打开 **音频会议**，然后单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="0c79c-119">有关许可的更多信息，请参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0c79c-120">分配许可证后，Microsoft 可能不作为最初在列表中的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="0c79c-120">After you assign the license, Microsoft might not appear initially in the drop-down as a dial-in conferencing provider.</span></span> <span data-ttu-id="0c79c-121">如果发生这种情况，请退出 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="0c79c-121">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="0c79c-122">启用或禁用发送到音频会议用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="0c79c-122">Enable or disable emails from being sent to dial-in users</span></span>

<span data-ttu-id="0c79c-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="0c79c-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="0c79c-124">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-125">转到 **Office 365 管理中心** > **Skype for Business** ，在左侧导航窗格中，单击 **音频会议** 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="0c79c-126">在  **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**   。</span><span class="sxs-lookup"><span data-stu-id="0c79c-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="0c79c-127">单击　**保存**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-127">Click **Save**.</span></span>

    <span data-ttu-id="0c79c-128">您也可以向用户发送电子邮件，您还可以通过进入用户的音频会议属性并单击　**通过电子邮件发送会议信息**　向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c79c-128">You can also send emails to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span> <span data-ttu-id="0c79c-129">会议 ID 和默认音频会议电话号码包括在会议邀请上而不是 PIN 上。</span><span class="sxs-lookup"><span data-stu-id="0c79c-129">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="0c79c-130">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="0c79c-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="0c79c-131">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0c79c-131">**** Using Windows PowerShell</span></span>

- <span data-ttu-id="0c79c-132">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c79c-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="0c79c-133">你可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) 管理你的组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c79c-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="0c79c-134">在发送给用户的电子邮件中更改发件人的联系信息</span><span class="sxs-lookup"><span data-stu-id="0c79c-134">Change the senders contact information of email messages sent to users</span></span>

<span data-ttu-id="0c79c-135">您可以对自动发送给用户的电子邮件进行更改，包括实际的电子邮件地址和发件人联系信息的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c79c-135">You can make changes to the email that is automatically sent to your users including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="0c79c-136">默认情况下，此电子邮件将显示为发自 Office 365，但你可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c79c-136">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="0c79c-137">若要更改向用户发送电子邮件的电子邮件地址，你必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c79c-137">To make changes to the email address that is sending the email to the users you must:</span></span>

- <span data-ttu-id="0c79c-138">在  _SendEmailFromAddress_ 参数中输入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0c79c-138">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="0c79c-139">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c79c-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="0c79c-140">将_SendEmailOverride_参数设置为 _True_。</span><span class="sxs-lookup"><span data-stu-id="0c79c-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="0c79c-141">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="0c79c-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="0c79c-142">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c79c-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="0c79c-143">你可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 管理你的组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c79c-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization including email.</span></span>

<span data-ttu-id="0c79c-144">请参阅　[在音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-144">See [Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="0c79c-145">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="0c79c-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="0c79c-146">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-147">转到**Office 365 管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-148">在**Skype for Business 管理中心**，在左侧导航窗格中，转到 **音频会议**，并在 **会议 ID**下的操作窗格中，单击 **重置**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="0c79c-149">在**重置会议 ID？** 窗口，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-149">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="0c79c-150">如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="0c79c-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="0c79c-151">默认情况下启用它。</span><span class="sxs-lookup"><span data-stu-id="0c79c-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="0c79c-152">[!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0c79c-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="0c79c-153">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="0c79c-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="0c79c-154">用户可以使用 Skype for Business 会议迁移工具来更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="0c79c-154">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="0c79c-155">要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅：[Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[Skype for Business Online、会议迁移工具（64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)和  [Skype for Business Online、会议迁移工具（32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="0c79c-155">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

<span data-ttu-id="0c79c-156">请参阅 [重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="0c79c-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="0c79c-157">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="0c79c-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="0c79c-158">用户安排的每次会议将分配到一个唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0c79c-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="0c79c-159">虽然会议 ID 是自动创建并分配给用户的，但有时用户不希望使用此标识，您又希望将它设置为特定数字，或者您的用户无法记住或者已丢失了其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0c79c-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="0c79c-160">可以使用 Skype for Business 管理中心和 Windows PowerShell 来查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0c79c-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="0c79c-161">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-162">转到 **Office 365　管理中心**  >  **Skype for Business**，在左侧导航窗格中，单击  **音频会议** 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="0c79c-163">单击 **用户** ，然后选择您要重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-163">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="0c79c-164">在操作窗格中，在**PIN**下单击 **重置**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-164">In the Action pane, click **Reset PIN**.</span></span>

<span data-ttu-id="0c79c-165">当用户启用电话拨入式会议时或者重置 PIN 时，用户将收到包含 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c79c-165">Users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="0c79c-166">但如果你已禁用自动发送电子邮件，则不会向用户发送 PIN 重置电子邮件，并且你必须手动将 PIN 发送给用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-166">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="0c79c-167">PIN 将仅在重置后显示一次。</span><span class="sxs-lookup"><span data-stu-id="0c79c-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="0c79c-168">PIN 在重置后即会显示，当 PIN 不会再显示在用户属性上，而是会显示 \*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c79c-168">Once it's displayed just after being reset, the PIN won't be shown anymore on the user properties and instead \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="0c79c-169">请参阅　[重置音频会议 PIN](reset-the-audio-conferencing-pin.md)　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md)</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="0c79c-170">向用户发送带有音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="0c79c-170">Send an email to a user with their Audio Conferencing information</span></span>

1. <span data-ttu-id="0c79c-171">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-172">转到 **Office 365 管理中心** > **Skype for Business** ，在左侧导航窗格中，单击 **音频会议** 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="0c79c-173">单击　**用户** 　，然后选择您要重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-173">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="0c79c-174">在操作窗格中，　**单击　通过电子邮件发送会议信息**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c79c-175">执行此操作时。音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-175">When you do this, the dial-in conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="0c79c-176">请参阅　[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="0c79c-177">设置包含在邀请中的电话号码</span><span class="sxs-lookup"><span data-stu-id="0c79c-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="0c79c-178">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-179">转到**Office 365 管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-180">在左侧导航窗格中，转到 **音频会议** > **用户** 　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="0c79c-181">选择要为音频会议启用的用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-181">Select the user that you want to enable for dial-in conferencing.</span></span>

4. <span data-ttu-id="0c79c-182">在操作窗格中，您可以设置 　**收费电话号码**　，如果允许， **免费电话号码**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="0c79c-183">单击 **保存**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-183">Click **Save**.</span></span>

<span data-ttu-id="0c79c-184">请参阅  [设置包含在邀请中的电话号码](set-the-phone-numbers-included-on-invites.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-184">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md)</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="0c79c-185">选择音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="0c79c-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="0c79c-186">**设置当呼叫者加入会议时的会议体验**</span><span class="sxs-lookup"><span data-stu-id="0c79c-186">**** Set the meeting experience when callers join a meeting</span></span>


1. <span data-ttu-id="0c79c-187">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-188">转到　**Office 365 管理中心** > **Skype for Business**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-189">在  **Skype for Business 管理中心** 中在左侧导航中，转到 **音频会议** > **Microsoft 桥接设置**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-189">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="0c79c-190">在　**加入会议体验**　下，选择下列操作：</span><span class="sxs-lookup"><span data-stu-id="0c79c-190">Under **Meeting join experience** select the following actions:</span></span>

  - <span data-ttu-id="0c79c-191">**启用会议进入和退出通知**　此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="0c79c-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="0c79c-192">如果清除此复选框，默认情况下已加入会议的用户将不会在某人进入或离开会议时收到通知。</span><span class="sxs-lookup"><span data-stu-id="0c79c-192">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="0c79c-193">当用户使用 Skype for Business 客户端加入会议时，可以在会议的基础上设置这一功能，并且他们可以修改　 **当人员进入或离开时发出通知** 　在　Skype Meeting　会议的　**选项** 　菜单中.。</span><span class="sxs-lookup"><span data-stu-id="0c79c-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="0c79c-194">**要求呼叫者在加入会议之前录制其名称**　此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="0c79c-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="0c79c-195">如果清除此复选框，呼叫者不需要记录其姓名，他们加入会议之前。</span><span class="sxs-lookup"><span data-stu-id="0c79c-195">However, if you uncheck it, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="0c79c-196">完成更改后，单击 **保存**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-196">After you make your changes, click **Save**.</span></span>

<span data-ttu-id="0c79c-197">请参阅　[更改音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)  。</span><span class="sxs-lookup"><span data-stu-id="0c79c-197">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

 <span data-ttu-id="0c79c-198">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="0c79c-198">**** Set the PIN length for meetings</span></span>

1. <span data-ttu-id="0c79c-199">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-200">转到　**Office 365 管理中心** > **Skype for Business**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-201">在 **Skype for Business 管理中心** 中，在左侧导航中，转到**音频会议** > **Microsoft 桥接设置**  。</span><span class="sxs-lookup"><span data-stu-id="0c79c-201">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="0c79c-202">在**安全**下输入您希望在 **PIN 长度** 列表中，PIN 的位数，然后单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-202">Under **Security**PIN length > enter the number of digits you want for the PIN and then click **Save**.</span></span>

    <span data-ttu-id="0c79c-203">PIN 必须介于4到12位之间。</span><span class="sxs-lookup"><span data-stu-id="0c79c-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="0c79c-204">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="0c79c-204">The default is 5.</span></span>

<span data-ttu-id="0c79c-205">请参阅　[更改音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)  。</span><span class="sxs-lookup"><span data-stu-id="0c79c-205">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

 <span data-ttu-id="0c79c-206">**启用或禁用向拨入用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="0c79c-206">**** Enable or disable email from being sent to dial-in users</span></span>

1. <span data-ttu-id="0c79c-207">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-208">转到**Office 365 管理中心** > **Skype for Business**，在左侧导航窗格中，单击 **音频会议**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="0c79c-209">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="0c79c-210">单击 **保存**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-210">Click **Save**.</span></span>

    <span data-ttu-id="0c79c-211">您也可以向用户发送电子邮件，您还可以通过进入用户的音频会议属性并单击，通过电子邮件发送会议信息　**向用户发送电子邮件** 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-211">You can also send email to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span>

    <span data-ttu-id="0c79c-212">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="0c79c-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="0c79c-213">请参阅　[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="0c79c-214">在音频会议桥上查看和设置主（默认）和辅助 （备用）语言</span><span class="sxs-lookup"><span data-stu-id="0c79c-214">See and set the primary and secondary languages on a dial-in conferencing bridge</span></span>


1. <span data-ttu-id="0c79c-215">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-216">转到　**Office 365 管理中心** > **Skype for Business**　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-217">在 **Skype for Business 管理中心**中的左侧导航中转到**音频会议**，然后单击**Microsoft 网桥**  。</span><span class="sxs-lookup"><span data-stu-id="0c79c-217">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="0c79c-218">从列表中选择一个电话号码，单击操作窗格中中的 **设置语言** ，然后在 **设置语言** 页上，单击使用 **主要语言** 列表，以查看受支持的语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="0c79c-218">In the Action pane, select the phone number from the list, click **Set languages** and then on the **Set languages** page, click the drop-down under **Primary language** to view the complete list of supported languages.</span></span>

    <span data-ttu-id="0c79c-219">您还可以设置选择 Microsoft 作为音频会议提供程序时所支持的主语言和辅语。</span><span class="sxs-lookup"><span data-stu-id="0c79c-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="0c79c-220">您在列表中选择的顺序与将语言呈现给调用方的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="0c79c-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="0c79c-221">请参阅　[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)　。</span><span class="sxs-lookup"><span data-stu-id="0c79c-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="0c79c-222">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="0c79c-222">See dial-in conferencing dial-in numbers</span></span>

1. <span data-ttu-id="0c79c-223">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-224">转到 **Office 365 管理中心** > **Skype for Business** 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-225">在**Skype for Business 管理中心中**，在左侧导航中，转到 **音频会议** > **Microsoft 桥接设置**。</span><span class="sxs-lookup"><span data-stu-id="0c79c-225">In the **Skype for Business admin center**, in the left navigation go to **dial-in conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="0c79c-226">您可以在这里：</span><span class="sxs-lookup"><span data-stu-id="0c79c-226">Here you can Discover additional bots.</span></span>

  - <span data-ttu-id="0c79c-227">查看由 Office 365 设置以用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0c79c-227">You can view the phone numbers that are set by Office 365 to be used for dial-in conferencing.</span></span>

  - <span data-ttu-id="0c79c-228">查看将由音频会议自动助理使用的位置和主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="0c79c-228">You can also view the location, and the primary and secondary languages that will be used by the dial-in conferencing auto attendant.</span></span>

  - <span data-ttu-id="0c79c-229">选择在启用音频会议时将给用户的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="0c79c-229">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.</span></span> <span data-ttu-id="0c79c-230">但是，如果电话拨入式会议网桥的默认电话号码发生更改，现有用户的默认电话号码不会改变。</span><span class="sxs-lookup"><span data-stu-id="0c79c-230">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="0c79c-231">您可以转到 **音频会议** > **用户** 选择用户的属性，通过从组织中可用的数字列表中选择一个新号码来更改用户的默认编号。</span><span class="sxs-lookup"><span data-stu-id="0c79c-231">You can go to **Dial-in conferencing** > **Dial-in users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="0c79c-232">请参阅 [查音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-232">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md)</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="0c79c-233">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="0c79c-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="0c79c-234">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0c79c-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0c79c-235">转到 **Office 365 管理中心** > **Skype for Business** 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0c79c-236">在**Skype for Business管理中心**，在左侧导航窗格中，转到 **音频会议**> ，然后**用户**   。</span><span class="sxs-lookup"><span data-stu-id="0c79c-236">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing**> and then **Dial-in users**.</span></span>

<span data-ttu-id="0c79c-237">请参阅 [请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0c79c-238">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="0c79c-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="0c79c-239">可以使用 Windows PowerShell 在组织级别管理多个设置。</span><span class="sxs-lookup"><span data-stu-id="0c79c-239">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="0c79c-240">这便于将设置应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="0c79c-240">This makes it easy to make these settings and have them apply to all of your users.</span></span>

<span data-ttu-id="0c79c-241">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324) 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="0c79c-242">以下是组织级设置：</span><span class="sxs-lookup"><span data-stu-id="0c79c-242">Here are the performance settings:</span></span>

- <span data-ttu-id="0c79c-243">**设置输入/退出通知** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="0c79c-244">**设置名称录制** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="0c79c-245">**设置 PIN 长度** 默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="0c79c-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="0c79c-246">**仅从电话中设置拨入会议**默认 _$false_。</span><span class="sxs-lookup"><span data-stu-id="0c79c-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="0c79c-247">**设置是否向用户发送电子邮件**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="0c79c-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="0c79c-248">**设置是否从不同的帐户发送电子邮件** 默认值为 _$false_ 。</span><span class="sxs-lookup"><span data-stu-id="0c79c-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="0c79c-249">**在发送给用户的电子邮件中设置发件地址** 默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="0c79c-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="0c79c-250">**为发送给用户的电子邮件设置显示名称**默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="0c79c-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0c79c-251">想了解更多关于 Windows PowerShell 的信息</span><span class="sxs-lookup"><span data-stu-id="0c79c-251">Want to know more about Windows Powershell?</span></span>
- <span data-ttu-id="0c79c-p119">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="0c79c-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="0c79c-255">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c79c-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="0c79c-256">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="0c79c-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="0c79c-257">Windows PowerShell 在速度、简单性和生产率方面有许多优点，仅限于使用 Office 365 管理中心，例如当您同时为许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="0c79c-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0c79c-258">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="0c79c-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="0c79c-259">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="0c79c-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="0c79c-260">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0c79c-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="0c79c-261">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="0c79c-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="0c79c-p121">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="0c79c-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c79c-264">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c79c-264">Related topics</span></span>

[<span data-ttu-id="0c79c-265">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="0c79c-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


