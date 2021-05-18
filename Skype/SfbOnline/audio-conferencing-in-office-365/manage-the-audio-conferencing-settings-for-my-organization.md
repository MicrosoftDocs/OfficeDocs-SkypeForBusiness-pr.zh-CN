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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '请参阅Skype for Business向用户和许多其他电话拨入式会议设置分配电话拨入式会议许可证和会议 ID 的联机步骤。 '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237238"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="d05cd-103">在 Skype for Business Online 中管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="d05cd-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="d05cd-104">如果您要在团队中管理这些设置，请参阅 [在 Microsoft Teams 中管理我的组织的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="d05cd-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="d05cd-105">在一个地方查看会议的所有音频会议设置Skype for Business更方便。</span><span class="sxs-lookup"><span data-stu-id="d05cd-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="d05cd-106">分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="d05cd-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="d05cd-107">你不能使用管理中心 分配Skype for Business **许可证**。</span><span class="sxs-lookup"><span data-stu-id="d05cd-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="d05cd-108">必须使用 Microsoft 365管理中心。</span><span class="sxs-lookup"><span data-stu-id="d05cd-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="d05cd-109">请参阅[分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="d05cd-110">**为用户分配许可证**</span><span class="sxs-lookup"><span data-stu-id="d05cd-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="d05cd-111">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-112">在管理中心的左侧导航中，转到"用户  >  **""活动** 用户"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d05cd-113">[!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="d05cd-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="d05cd-114">然后单击" **编辑**"，单击 **下一步** 两次，然后选择许可证并单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="d05cd-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="d05cd-115">你也可以使用 Windows Powershell 向多个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d05cd-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="d05cd-116">有关说明和示例 PowerShell 脚本，请参阅[分配Skype for Business许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="d05cd-117">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d05cd-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="d05cd-118">在 **产品许可证** 页上，打开 **音频会议**，然后单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="d05cd-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="d05cd-119">有关许可的更多信息，请参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d05cd-120">分配许可证后，Microsoft 最初可能不会在列表中显示为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="d05cd-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="d05cd-121">如果发生这种情况，请注销管理中心或按 Ctrl+F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="d05cd-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="d05cd-122">启用或禁用发送给音频会议用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d05cd-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="d05cd-123">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="d05cd-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d05cd-124">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-125">转到管理中心 **> Skype for Business** 导航中，单击"音频 **会议"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d05cd-126">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="d05cd-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="d05cd-127">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d05cd-127">Click **Save**.</span></span>

    <span data-ttu-id="d05cd-128">您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"**通过电子邮件发送会议信息"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="d05cd-129">会议 ID 和默认音频会议电话号码包含在会议邀请中，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="d05cd-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="d05cd-130">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="d05cd-131">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d05cd-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="d05cd-132">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d05cd-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="d05cd-133">可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 管理组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d05cd-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="d05cd-134">在发送给用户的电子邮件中更改发件人的联系信息</span><span class="sxs-lookup"><span data-stu-id="d05cd-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="d05cd-135">您可以更改自动发送给用户的电子邮件，包括实际电子邮件地址和显示名称发件人的联系信息。</span><span class="sxs-lookup"><span data-stu-id="d05cd-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="d05cd-136">默认情况下，电子邮件的发件人是 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 更改电子邮件地址和 显示名称。</span><span class="sxs-lookup"><span data-stu-id="d05cd-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d05cd-137">若要更改向用户发送电子邮件的电子邮件地址，必须：</span><span class="sxs-lookup"><span data-stu-id="d05cd-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="d05cd-138">在 _SendEmailFromAddress 参数中输入_ 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d05cd-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="d05cd-139">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d05cd-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="d05cd-140">将 _SendEmailOverride_ 参数设置为 _True_。</span><span class="sxs-lookup"><span data-stu-id="d05cd-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="d05cd-141">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="d05cd-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="d05cd-142">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d05cd-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="d05cd-143">可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 管理组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d05cd-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="d05cd-144">请参阅 [当用户的音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="d05cd-145">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="d05cd-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="d05cd-146">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-147">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d05cd-148">在 **Skype for Business 管理中心**，在左侧导航窗格中，转到 **音频会议**，并在 **会议 ID** 下的操作窗格中，单击 **重置**。</span><span class="sxs-lookup"><span data-stu-id="d05cd-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="d05cd-149">在"**重置会议 ID？"** 窗口中，单击"**是"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="d05cd-150">如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="d05cd-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="d05cd-151">默认情况下启用它。</span><span class="sxs-lookup"><span data-stu-id="d05cd-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="d05cd-152">[!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d05cd-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d05cd-153">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="d05cd-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="d05cd-154">用户可以使用会议Skype for Business工具来更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="d05cd-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="d05cd-155">若要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅：适用于 Skype for Business 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的会议更新工具、Skype for Business Online、会议迁移工具[ (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 Skype for Business Online 会议迁移工具[ (32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。</span><span class="sxs-lookup"><span data-stu-id="d05cd-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="d05cd-156">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="d05cd-157">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="d05cd-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="d05cd-158">用户安排的每次会议将分配到一个唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d05cd-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="d05cd-159">尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而您想要将其设置为特定号码，或者您的用户无法记住或已丢失其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d05cd-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="d05cd-160">可以使用 Skype for Business 管理中心和 Windows PowerShell 来查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d05cd-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="d05cd-161">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-162">转到管理中心 **> Skype for Business** 导航中，单击"音频 **会议"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d05cd-163">单击 **"** 用户"，然后选择要重置其 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="d05cd-164">在"操作"窗格中的 **"PIN"下**，单击"**重置"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="d05cd-165">启用音频会议或重置 PIN 时，用户将收到一封包含 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d05cd-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="d05cd-166">但是，如果已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，您必须手动将 PIN 发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="d05cd-167">PIN 将仅在重置后显示一次。</span><span class="sxs-lookup"><span data-stu-id="d05cd-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="d05cd-168">重置后显示 PIN 后，PIN 不再显示在用户属性上;而是会显示 \*\*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="d05cd-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="d05cd-169">请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="d05cd-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="d05cd-170">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d05cd-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="d05cd-171">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-172">转到管理中心 **> Skype for Business** 导航中，单击"音频 **会议"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d05cd-173">单击 **"** 用户"，然后选择要重置其 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="d05cd-174">在操作窗格中，单击" **通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="d05cd-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d05cd-175">当你这样做时，音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="d05cd-176">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="d05cd-177">设置邀请中包含的电话号码</span><span class="sxs-lookup"><span data-stu-id="d05cd-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="d05cd-178">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-179">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d05cd-180">在左侧导航窗格中，转到 **音频会议** > **用户** 　。</span><span class="sxs-lookup"><span data-stu-id="d05cd-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="d05cd-181">选择要为音频会议启用的用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="d05cd-182">在操作窗格中，您可以设置 　**收费电话号码**　，如果允许， **免费电话号码**　。</span><span class="sxs-lookup"><span data-stu-id="d05cd-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="d05cd-183">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d05cd-183">Click **Save**.</span></span>

<span data-ttu-id="d05cd-184">请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="d05cd-185">选择音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="d05cd-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="d05cd-186">**当呼叫者加入会议时设置会议体验**</span><span class="sxs-lookup"><span data-stu-id="d05cd-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="d05cd-187">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-188">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d05cd-189">在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="d05cd-190">在 **"会议加入体验"** 下，选择以下操作：</span><span class="sxs-lookup"><span data-stu-id="d05cd-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="d05cd-191">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="d05cd-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="d05cd-192">如果清除此复选框，则默认情况下已加入会议的用户在有人进入或离开会议时不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="d05cd-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="d05cd-193">当用户使用 Skype for Business 应用加入会议，并修改会议"Skype 会议 **选项"菜单中** 的"何时进入或离开时通知"设置时，可以基于会议进行此设置。</span><span class="sxs-lookup"><span data-stu-id="d05cd-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="d05cd-194">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="d05cd-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="d05cd-195">如果清除此复选框，呼叫者在加入会议之前不会要求他们录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="d05cd-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="d05cd-196">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="d05cd-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="d05cd-197">请参阅 [更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="d05cd-198">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="d05cd-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="d05cd-199">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-200">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d05cd-201">在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="d05cd-202">在 **"安全性**"下，在"PIN 长度"列表中输入 PIN的位数，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="d05cd-203">PIN 必须介于4到12位之间。</span><span class="sxs-lookup"><span data-stu-id="d05cd-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="d05cd-204">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="d05cd-204">The default is 5.</span></span>
    
<span data-ttu-id="d05cd-205">请参阅 [更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="d05cd-206">**启用或禁用向音频用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="d05cd-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="d05cd-207">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-208">转到管理中心 **> Skype for Business** 导航中，单击"音频 **会议"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d05cd-209">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="d05cd-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="d05cd-210">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d05cd-210">Click **Save**.</span></span>

    <span data-ttu-id="d05cd-211">您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"**通过电子邮件发送会议信息"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="d05cd-212">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="d05cd-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="d05cd-213">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="d05cd-214">在音频会议网桥上 () 辅助 (和) 语言的主要语言</span><span class="sxs-lookup"><span data-stu-id="d05cd-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="d05cd-215">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-216">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d05cd-217">在 **Skype for Business管理** 中心的 左侧导航中，转到"音频 **会议**"，然后单击 **"Microsoft 网桥"。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="d05cd-218">从列表中选择一个电话号码，单击"操作"窗格中的"设置语言"，然后在"设置语言"页上，单击"使用主要语言"列表查看受支持语言的完整列表。 </span><span class="sxs-lookup"><span data-stu-id="d05cd-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="d05cd-219">还可以设置选择 Microsoft 作为音频会议提供商时支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="d05cd-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="d05cd-220">您在列表中选择的顺序与将语言呈现给调用方的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="d05cd-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="d05cd-221">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="d05cd-222">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="d05cd-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="d05cd-223">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-224">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="d05cd-225">在 **Skype for Business管理** 中心的 左侧导航中，转到音频会议 Microsoft  >  **网桥**。</span><span class="sxs-lookup"><span data-stu-id="d05cd-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="d05cd-226">可在此处：</span><span class="sxs-lookup"><span data-stu-id="d05cd-226">Here you can:</span></span>

   - <span data-ttu-id="d05cd-227">查看由音频会议Microsoft 365 Office 365设置的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d05cd-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="d05cd-228">查看音频会议自动助理使用的位置以及主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="d05cd-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="d05cd-229">选择为用户启用音频会议时将给予他们的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="d05cd-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="d05cd-230">但是，如果音频会议网桥的默认电话号码发生更改，则现有用户的默认电话号码不会更改。</span><span class="sxs-lookup"><span data-stu-id="d05cd-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="d05cd-231">你可以转到"**音频** 会议用户"并选择用户的属性，通过从组织中可用的号码列表中选择新号码来更改  >  用户的默认号码。</span><span class="sxs-lookup"><span data-stu-id="d05cd-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="d05cd-232">请参阅 [查看音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="d05cd-233">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="d05cd-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="d05cd-234">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d05cd-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="d05cd-235">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="d05cd-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d05cd-236">在 **Skype for Business管理** 中心的 左侧导航中，转到"音频会议">"用户 **"。** </span><span class="sxs-lookup"><span data-stu-id="d05cd-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="d05cd-237">请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d05cd-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d05cd-238">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="d05cd-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="d05cd-239">可以使用以下方法在组织级别管理多个Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d05cd-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="d05cd-240">这样，就可以轻松将设置应用到所有用户。</span><span class="sxs-lookup"><span data-stu-id="d05cd-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="d05cd-241">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="d05cd-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="d05cd-242">下面是组织级别的设置：</span><span class="sxs-lookup"><span data-stu-id="d05cd-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="d05cd-243">**设置输入/退出通知** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="d05cd-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="d05cd-244">**设置名称录制** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="d05cd-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="d05cd-245">**设置 PIN 长度** 默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="d05cd-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="d05cd-246">**仅从电话中设置拨入会议** 默认 _$false_。</span><span class="sxs-lookup"><span data-stu-id="d05cd-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="d05cd-247">**设置是否向用户发送电子邮件** 默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="d05cd-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="d05cd-248">**设置是否从不同的帐户发送电子邮件** 默认值为 _$false_ 。</span><span class="sxs-lookup"><span data-stu-id="d05cd-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="d05cd-249">**在发送给用户的电子邮件中设置发件地址** 默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="d05cd-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="d05cd-250">**为发送给用户的电子邮件设置显示名称** 默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="d05cd-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d05cd-251">想要了解有关Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d05cd-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="d05cd-252">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="d05cd-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d05cd-253">使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="d05cd-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d05cd-254">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d05cd-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d05cd-255">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d05cd-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="d05cd-256">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d05cd-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="d05cd-257">Windows PowerShell管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。</span><span class="sxs-lookup"><span data-stu-id="d05cd-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="d05cd-258">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="d05cd-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d05cd-259">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d05cd-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="d05cd-260">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d05cd-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="d05cd-261">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d05cd-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="d05cd-p121">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="d05cd-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="d05cd-264">相关主题</span><span class="sxs-lookup"><span data-stu-id="d05cd-264">Related topics</span></span>

[<span data-ttu-id="d05cd-265">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="d05cd-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)
