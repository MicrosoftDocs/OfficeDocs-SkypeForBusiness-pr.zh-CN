---
title: 通过 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读本主题，了解如何在 Microsoft 365 或 Office 365 （团队或 Skype for Business 和 Exchange 均在线）上部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: 4b5bd3967d3a1fcc8859cf4da8b039418819cb4e
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616886"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="77e3e-103">通过 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="77e3e-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="77e3e-104">阅读本主题，了解如何在 microsoft 团队或 Skype for business 和 Exchange 均在线的情况下，通过 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室的相关信息。</span><span class="sxs-lookup"><span data-stu-id="77e3e-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="77e3e-105">设置用户帐户最简单的方法是使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="77e3e-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="77e3e-106">Microsoft [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)提供了可帮助创建新用户帐户的脚本，或验证你拥有的现有资源帐户，以便帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="77e3e-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="77e3e-107">如果你愿意，可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="77e3e-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="77e3e-108">要求</span><span class="sxs-lookup"><span data-stu-id="77e3e-108">Requirements</span></span>

<span data-ttu-id="77e3e-109">在使用 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室之前，请确保满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="77e3e-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="77e3e-110">有关详细信息，请参阅 [Microsoft 团队会议室要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="77e3e-111">若要启用 Skype for Business，您必须具有以下各项：</span><span class="sxs-lookup"><span data-stu-id="77e3e-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="77e3e-112">Skype for Business Online (计划2或您的 Microsoft 365 或 Office 365 计划中的基于企业的计划) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="77e3e-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="77e3e-113">该计划需要允许电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="77e3e-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="77e3e-114">如果需要来自会议的电话拨入式功能，您需要音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="77e3e-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="77e3e-115">如果需要来自会议的拨出功能，您将需要音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="77e3e-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="77e3e-116">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="77e3e-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="77e3e-117">您的 Microsoft 团队会议室帐户至少需要 Skype for Business Online (计划 2) 许可证，但不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="77e3e-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="77e3e-118">有关详细信息，请参阅 [Microsoft 团队聊天室许可证](rooms-licensing.md) 。</span><span class="sxs-lookup"><span data-stu-id="77e3e-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="77e3e-119">有关 Skype for Business Online 计划的详细信息，请参阅 [skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="77e3e-120">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="77e3e-120">Add a device account</span></span>

1. <span data-ttu-id="77e3e-121">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="77e3e-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="77e3e-122">有关说明，请参阅 [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="77e3e-123">在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="77e3e-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="77e3e-124">默认情况下，会议室邮箱没有关联帐户，因此当您创建或修改允许它通过 Skype 会议室系统 v2 进行身份验证的会议室邮箱时，您将需要添加帐户。</span><span class="sxs-lookup"><span data-stu-id="77e3e-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="77e3e-125">若要创建新的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="77e3e-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="77e3e-126">此示例使用以下设置创建新的会议室邮箱：</span><span class="sxs-lookup"><span data-stu-id="77e3e-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="77e3e-127">名称： Rigel-01</span><span class="sxs-lookup"><span data-stu-id="77e3e-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="77e3e-128">别名： Rigel1</span><span class="sxs-lookup"><span data-stu-id="77e3e-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="77e3e-129">帐户： Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="77e3e-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="77e3e-130">帐户密码： P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="77e3e-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="77e3e-131">若要修改现有的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="77e3e-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="77e3e-132">此示例启用具有 alias 值 Rigel2 的现有聊天室邮箱的帐户，并将密码设置为 9898P@ $ $W 0rd。</span><span class="sxs-lookup"><span data-stu-id="77e3e-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="77e3e-133">请注意，由于现有的别名值，该帐户将 Rigel2@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="77e3e-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="77e3e-134">有关详细的语法和参数信息，请参阅 [新邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 和 [设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="77e3e-135">在 Exchange Online PowerShell 中，在聊天室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="77e3e-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="77e3e-136">AutomateProcessing： AutoAccept (会议组织者直接收到会议室保留决策，无需人工干预：闲 = 接受;占线 = 拒绝。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="77e3e-137">AddOrganizerToSubject： $false (会议组织者未添加到会议请求的主题。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="77e3e-138">DeleteComments： $false (保留收到的会议请求的邮件正文中的任何文本。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="77e3e-139">DeleteSubject： $false (保留收到的会议请求的主题。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="77e3e-140">RemovePrivateProperty： $false (确保由会议组织者在原始会议请求中发送的私人标志保持指定。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="77e3e-141">AddAdditionalResponse： $true (将 AdditionalResponse 参数指定的文本添加到会议请求。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="77e3e-142">AdditionalResponse： "这是 Skype 会议室！"</span><span class="sxs-lookup"><span data-stu-id="77e3e-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="77e3e-143"> (要添加到会议请求的其他文本。 ) </span><span class="sxs-lookup"><span data-stu-id="77e3e-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="77e3e-144">此示例在名为 Rigel-01 的聊天室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="77e3e-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="77e3e-145">有关详细的语法和参数信息，请参阅 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="77e3e-146">通过运行 PowerShell cmdlet 连接到 MS Online PowerShell 以进行 Active Directory 设置 `Connect-MsolService -Credential $cred` 。</span><span class="sxs-lookup"><span data-stu-id="77e3e-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="77e3e-147">有关 Active Directory 的详细信息，请参阅 [Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="77e3e-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支持。</span><span class="sxs-lookup"><span data-stu-id="77e3e-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="77e3e-149">如果不希望密码过期，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="77e3e-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="77e3e-150">此示例将帐户 Rigel1@contoso.onmicrosoft.com 的密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="77e3e-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="77e3e-151">您也可以通过运行以下命令为帐户设置电话号码：</span><span class="sxs-lookup"><span data-stu-id="77e3e-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="77e3e-152">设备帐户需要有有效的 Microsoft 365 或 Office 365 许可证，或者 Exchange 和 Microsoft 团队或 Skype for Business 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="77e3e-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="77e3e-153">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="77e3e-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="77e3e-154">你可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="77e3e-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="77e3e-155">若要检索 Microsoft 365 或 Office 365 组织的可用 Sku 列表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77e3e-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="77e3e-156">接下来，你可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="77e3e-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="77e3e-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77e3e-157">cmdlet.</span></span> <span data-ttu-id="77e3e-158">此示例向帐户添加会议室许可证：</span><span class="sxs-lookup"><span data-stu-id="77e3e-158">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="77e3e-159">有关详细说明，请参阅 [使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="77e3e-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="77e3e-160">您还可以将电话系统功能添加到此帐户，但必须首先进行配置。</span><span class="sxs-lookup"><span data-stu-id="77e3e-160">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="77e3e-161">请参阅 [什么是电话系统？](../what-is-phone-system-in-office-365.md) 了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="77e3e-161">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="77e3e-162">此示例添加 PSTN 国内和国际呼叫计划：</span><span class="sxs-lookup"><span data-stu-id="77e3e-162">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="77e3e-163">接下来，你需要启用 Skype for Business 设备帐户。</span><span class="sxs-lookup"><span data-stu-id="77e3e-163">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="77e3e-164">请确保你的环境满足 [Microsoft 团队会议室要求](requirements.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="77e3e-164">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="77e3e-165">按如下方式启动远程 [Windows PowerShell 会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) (确保 [安装 Skype For business Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) ：</span><span class="sxs-lookup"><span data-stu-id="77e3e-165">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="77e3e-166">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="77e3e-166">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="77e3e-167">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="77e3e-167">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="77e3e-168">从正在设置的新用户帐户获取 RegistrarPool 信息，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="77e3e-168">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="77e3e-169">接下来，通过运行以下 cmdlet 为 Skype for business 服务器启用 Microsoft 团队聊天室帐户：</span><span class="sxs-lookup"><span data-stu-id="77e3e-169">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="77e3e-170">新用户帐户可能不会在与租户中的现有用户帐户相同的注册机构池中创建。</span><span class="sxs-lookup"><span data-stu-id="77e3e-170">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="77e3e-171">上面的命令将防止由于此情况而导致帐户设置出错。</span><span class="sxs-lookup"><span data-stu-id="77e3e-171">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="77e3e-172">复核</span><span class="sxs-lookup"><span data-stu-id="77e3e-172">Validate</span></span>

<span data-ttu-id="77e3e-173">对于验证，你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="77e3e-173">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="77e3e-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77e3e-174">See also</span></span>

[<span data-ttu-id="77e3e-175">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="77e3e-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="77e3e-176">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="77e3e-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="77e3e-177">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="77e3e-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="77e3e-178">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="77e3e-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="77e3e-179">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="77e3e-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="77e3e-180">Microsoft 团队聊天室许可</span><span class="sxs-lookup"><span data-stu-id="77e3e-180">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
