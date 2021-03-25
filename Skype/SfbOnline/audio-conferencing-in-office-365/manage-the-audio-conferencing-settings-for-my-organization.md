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
description: '请参阅 Skype for Business Online 步骤，为用户和许多其他电话拨入式会议设置分配电话拨入式会议许可证和会议 ID。 '
ms.openlocfilehash: eb0212bcd7c03fac619efa2749a8308097f75505
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114228"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="4849e-103">在 Skype for Business Online 中管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="4849e-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="4849e-104">如果您要在团队中管理这些设置，请参阅 [在 Microsoft Teams 中管理我的组织的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="4849e-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="4849e-105">在一个地方查看 Skype for Business 的所有音频会议设置可能会更方便。</span><span class="sxs-lookup"><span data-stu-id="4849e-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="4849e-106">分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="4849e-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="4849e-107">你不能使用 Skype for Business 管理中心 **分配许可证**。</span><span class="sxs-lookup"><span data-stu-id="4849e-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="4849e-108">必须使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="4849e-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="4849e-109">请参阅[分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="4849e-110">**为用户分配许可证**</span><span class="sxs-lookup"><span data-stu-id="4849e-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="4849e-111">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-112">在管理中心的左侧导航中，转到"用户  >  **""活动** 用户"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4849e-113">[!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="4849e-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="4849e-114">然后单击" **编辑**"，单击 **下一步** 两次，然后选择许可证并单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="4849e-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="4849e-115">你也可以使用 Windows Powershell 向多个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4849e-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="4849e-116">有关说明和示例 PowerShell 脚本，请参阅 [分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="4849e-117">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="4849e-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="4849e-118">在 **产品许可证** 页上，打开 **音频会议**，然后单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="4849e-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="4849e-119">有关许可的更多信息，请参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4849e-120">分配许可证后，Microsoft 最初可能不会在列表中显示为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="4849e-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="4849e-121">如果发生这种情况，请注销管理中心或按 Ctrl+F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="4849e-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="4849e-122">启用或禁用发送给音频会议用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="4849e-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="4849e-123">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="4849e-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4849e-124">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-125">转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4849e-126">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="4849e-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4849e-127">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4849e-127">Click **Save**.</span></span>

    <span data-ttu-id="4849e-128">您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"**通过电子邮件发送会议信息"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="4849e-129">会议 ID 和默认音频会议电话号码包含在会议邀请中，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="4849e-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="4849e-130">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="4849e-131">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4849e-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="4849e-132">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4849e-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="4849e-133">可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 管理组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4849e-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="4849e-134">在发送给用户的电子邮件中更改发件人的联系信息</span><span class="sxs-lookup"><span data-stu-id="4849e-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="4849e-135">您可以更改自动发送给用户的电子邮件，包括实际电子邮件地址和显示名称发件人的联系信息。</span><span class="sxs-lookup"><span data-stu-id="4849e-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="4849e-136">默认情况下，电子邮件的发件人是 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 更改电子邮件地址和 显示名称。</span><span class="sxs-lookup"><span data-stu-id="4849e-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4849e-137">若要更改向用户发送电子邮件的电子邮件地址，必须：</span><span class="sxs-lookup"><span data-stu-id="4849e-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="4849e-138">在 _SendEmailFromAddress 参数中输入_ 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4849e-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="4849e-139">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4849e-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="4849e-140">将 _SendEmailOverride_ 参数设置为 _True_。</span><span class="sxs-lookup"><span data-stu-id="4849e-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="4849e-141">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="4849e-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="4849e-142">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4849e-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="4849e-143">可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 管理组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4849e-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="4849e-144">请参阅 [当用户的音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="4849e-145">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="4849e-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="4849e-146">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-147">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4849e-148">在 **Skype for Business 管理中心**，在左侧导航窗格中，转到 **音频会议**，并在 **会议 ID** 下的操作窗格中，单击 **重置**。</span><span class="sxs-lookup"><span data-stu-id="4849e-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="4849e-149">在"**重置会议 ID？"** 窗口中，单击"**是"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="4849e-150">如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="4849e-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="4849e-151">默认情况下启用它。</span><span class="sxs-lookup"><span data-stu-id="4849e-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="4849e-152">[!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4849e-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4849e-153">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="4849e-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4849e-154">用户可以使用 Skype for Business 会议迁移工具来更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="4849e-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="4849e-155">若要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅 [：Skype for Business](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)和 Lync 的会议更新工具 [、Skype for Business Online、 ](https://go.microsoft.com/fwlink/?LinkID=626047)会议迁移工具 (64 位) 和 Skype for Business Online 会议迁移工具  [ (32 ](https://www.microsoft.com/download/details.aspx?id=54079)位) 。</span><span class="sxs-lookup"><span data-stu-id="4849e-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="4849e-156">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="4849e-157">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="4849e-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="4849e-158">用户安排的每次会议将分配到一个唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4849e-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="4849e-159">尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而您想要将其设置为特定号码，或者您的用户无法记住或已丢失其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4849e-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="4849e-160">可以使用 Skype for Business 管理中心和 Windows PowerShell 来查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4849e-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="4849e-161">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-162">转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4849e-163">单击 **"** 用户"，然后选择要重置其 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="4849e-164">在"操作"窗格中的 **"PIN"下**，单击"**重置"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="4849e-165">启用音频会议或重置 PIN 时，用户将收到一封包含 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4849e-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="4849e-166">但是，如果已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，您必须手动将 PIN 发送给用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="4849e-167">PIN 将仅在重置后显示一次。</span><span class="sxs-lookup"><span data-stu-id="4849e-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="4849e-168">重置后显示 PIN 后，PIN 不再显示在用户属性上;而是会显示 \*\*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="4849e-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="4849e-169">请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="4849e-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="4849e-170">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="4849e-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="4849e-171">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-172">转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4849e-173">单击 **"** 用户"，然后选择要重置其 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="4849e-174">在操作窗格中，单击" **通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="4849e-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4849e-175">当你这样做时，音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="4849e-176">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="4849e-177">设置邀请中包含的电话号码</span><span class="sxs-lookup"><span data-stu-id="4849e-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="4849e-178">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-179">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4849e-180">在左侧导航窗格中，转到 **音频会议** > **用户** 　。</span><span class="sxs-lookup"><span data-stu-id="4849e-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="4849e-181">选择要为音频会议启用的用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="4849e-182">在操作窗格中，您可以设置 　**收费电话号码**　，如果允许， **免费电话号码**　。</span><span class="sxs-lookup"><span data-stu-id="4849e-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="4849e-183">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4849e-183">Click **Save**.</span></span>

<span data-ttu-id="4849e-184">请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="4849e-185">选择音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="4849e-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="4849e-186">**当呼叫者加入会议时设置会议体验**</span><span class="sxs-lookup"><span data-stu-id="4849e-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="4849e-187">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-188">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4849e-189">在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="4849e-190">在 **"会议加入体验"** 下，选择以下操作：</span><span class="sxs-lookup"><span data-stu-id="4849e-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="4849e-191">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="4849e-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="4849e-192">如果清除此复选框，则默认情况下已加入会议的用户在有人进入或离开会议时不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="4849e-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="4849e-193">当用户使用 Skype for Business 应用加入会议，并修改会议"Skype 会议选项"菜单中的"何时进入或离开时通知"设置时，可以按 **会议进行此设置**。</span><span class="sxs-lookup"><span data-stu-id="4849e-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="4849e-194">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="4849e-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="4849e-195">如果清除此复选框，呼叫者在加入会议之前不会要求他们录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="4849e-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="4849e-196">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="4849e-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="4849e-197">请参阅 [更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="4849e-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="4849e-198">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="4849e-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="4849e-199">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-200">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4849e-201">在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="4849e-202">在 **"安全性**"下，在"PIN 长度"列表中输入 PIN的位数，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="4849e-203">PIN 必须介于4到12位之间。</span><span class="sxs-lookup"><span data-stu-id="4849e-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="4849e-204">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="4849e-204">The default is 5.</span></span>
    
<span data-ttu-id="4849e-205">请参阅 [更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="4849e-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="4849e-206">**启用或禁用向音频用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4849e-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="4849e-207">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-208">转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="4849e-209">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="4849e-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4849e-210">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4849e-210">Click **Save**.</span></span>

    <span data-ttu-id="4849e-211">您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"**通过电子邮件发送会议信息"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="4849e-212">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="4849e-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="4849e-213">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="4849e-214">在音频会议网桥上 () 辅助 (和) 语言的主要语言</span><span class="sxs-lookup"><span data-stu-id="4849e-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="4849e-215">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-216">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4849e-217">在 **Skype for Business 管理中心的** 左侧导航中，转到"音频会议 **"，** 然后单击 **"Microsoft 网桥"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="4849e-218">从列表中选择一个电话号码，单击"操作"窗格中的"设置语言"，然后在"设置语言"页上，单击"使用主要语言"列表查看受支持语言的完整列表。 </span><span class="sxs-lookup"><span data-stu-id="4849e-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="4849e-219">还可以设置选择 Microsoft 作为音频会议提供商时支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="4849e-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="4849e-220">您在列表中选择的顺序与将语言呈现给调用方的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="4849e-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="4849e-221">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="4849e-222">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="4849e-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="4849e-223">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-224">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="4849e-225">在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="4849e-226">可在此处：</span><span class="sxs-lookup"><span data-stu-id="4849e-226">Here you can:</span></span>

   - <span data-ttu-id="4849e-227">查看由 Microsoft 365 或 Office 365 设置用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4849e-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="4849e-228">查看音频会议自动助理使用的位置以及主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="4849e-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="4849e-229">选择为用户启用音频会议时将给予他们的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="4849e-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4849e-230">但是，如果音频会议网桥的默认电话号码发生更改，则现有用户的默认电话号码不会更改。</span><span class="sxs-lookup"><span data-stu-id="4849e-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="4849e-231">你可以转到"**音频** 会议用户"并选择用户的属性，通过从组织中可用的号码列表中选择新号码来更改  >  用户的默认号码。</span><span class="sxs-lookup"><span data-stu-id="4849e-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="4849e-232">请参阅 [查看音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="4849e-233">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="4849e-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="4849e-234">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4849e-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4849e-235">转到 Skype for Business > **管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4849e-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4849e-236">在 **Skype for Business 管理中心的** 左侧导航中，转到"音频会议">"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="4849e-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="4849e-237">请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="4849e-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4849e-238">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="4849e-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4849e-239">可以使用以下方法在组织级别管理多个Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4849e-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="4849e-240">这样，就可以轻松将设置应用到所有用户。</span><span class="sxs-lookup"><span data-stu-id="4849e-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="4849e-241">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="4849e-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="4849e-242">下面是组织级别的设置：</span><span class="sxs-lookup"><span data-stu-id="4849e-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="4849e-243">**设置输入/退出通知** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="4849e-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="4849e-244">**设置名称录制** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="4849e-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="4849e-245">**设置 PIN 长度** 默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="4849e-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="4849e-246">**仅从电话中设置拨入会议** 默认 _$false_。</span><span class="sxs-lookup"><span data-stu-id="4849e-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="4849e-247">**设置是否向用户发送电子邮件** 默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="4849e-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="4849e-248">**设置是否从不同的帐户发送电子邮件** 默认值为 _$false_ 。</span><span class="sxs-lookup"><span data-stu-id="4849e-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="4849e-249">**在发送给用户的电子邮件中设置发件地址** 默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="4849e-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="4849e-250">**为发送给用户的电子邮件设置显示名称** 默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="4849e-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4849e-251">想要了解有关Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4849e-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="4849e-252">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="4849e-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4849e-253">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="4849e-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4849e-254">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4849e-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4849e-255">为何需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4849e-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="4849e-256">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4849e-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="4849e-257">Windows PowerShell管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。</span><span class="sxs-lookup"><span data-stu-id="4849e-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="4849e-258">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="4849e-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="4849e-259">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="4849e-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="4849e-260">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4849e-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="4849e-261">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="4849e-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="4849e-p121">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="4849e-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="4849e-264">相关主题</span><span class="sxs-lookup"><span data-stu-id="4849e-264">Related topics</span></span>

[<span data-ttu-id="4849e-265">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="4849e-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)