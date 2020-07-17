---
title: 通过 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 440bf2f624bfd150f7e00f145770b0fda336deb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756793"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="0bcb7-103">通过 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0bcb7-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="0bcb7-104">阅读本主题，了解如何在 microsoft 团队或 Skype for business 和 Exchange 均在线的情况下，通过 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="0bcb7-105">设置用户帐户最简单的方法是使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="0bcb7-106">Microsoft [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)提供了可帮助创建新用户帐户的脚本，或验证你拥有的现有资源帐户，以便帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="0bcb7-107">如果你愿意，可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="0bcb7-108">要求</span><span class="sxs-lookup"><span data-stu-id="0bcb7-108">Requirements</span></span>

<span data-ttu-id="0bcb7-109">在使用 Microsoft 365 或 Office 365 部署 Microsoft 团队聊天室之前，请确保满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="0bcb7-110">有关详细信息，请参阅[Microsoft 团队会议室要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="0bcb7-111">若要启用 Skype for Business，您必须具有以下各项：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="0bcb7-112">您的 Microsoft 365 或 Office 365 计划中的 Skype for business Online （计划2或基于企业的计划）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="0bcb7-113">该计划需要允许电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="0bcb7-114">如果需要来自会议的电话拨入式功能，您需要音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="0bcb7-115">如果需要来自会议的拨出功能，您将需要音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="0bcb7-116">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="0bcb7-117">您的 Microsoft 团队会议室帐户至少需要 Skype for business Online （计划2）许可证，但不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="0bcb7-118">有关详细信息，请参阅[Microsoft 团队聊天室许可证](rooms-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="0bcb7-119">有关 Skype for Business Online 计划的详细信息，请参阅[skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="0bcb7-120">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="0bcb7-120">Add a device account</span></span>

1. <span data-ttu-id="0bcb7-121">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="0bcb7-122">有关说明，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="0bcb7-123">在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="0bcb7-124">默认情况下，会议室邮箱没有关联帐户，因此当您创建或修改允许它通过 Skype 会议室系统 v2 进行身份验证的会议室邮箱时，您将需要添加帐户。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="0bcb7-125">若要创建新的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="0bcb7-126">此示例使用以下设置创建新的会议室邮箱：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="0bcb7-127">名称： Rigel-01</span><span class="sxs-lookup"><span data-stu-id="0bcb7-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="0bcb7-128">别名： Rigel1</span><span class="sxs-lookup"><span data-stu-id="0bcb7-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="0bcb7-129">帐户： Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0bcb7-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="0bcb7-130">帐户密码： P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="0bcb7-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="0bcb7-131">若要修改现有的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="0bcb7-132">此示例启用具有 alias 值 Rigel2 的现有聊天室邮箱的帐户，并将密码设置为 9898P@ $ $W 0rd。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="0bcb7-133">请注意，由于现有的别名值，该帐户将 Rigel2@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="0bcb7-134">有关详细的语法和参数信息，请参阅[新邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="0bcb7-135">在 Exchange Online PowerShell 中，在聊天室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="0bcb7-136">AutomateProcessing： AutoAccept （会议组织者直接收到会议室保留决定，无需人工干预：闲 = 接受; 忙 = 拒绝。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="0bcb7-137">AddOrganizerToSubject： $false （会议组织者未添加到会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="0bcb7-138">DeleteComments： $false （保留收到的会议请求的邮件正文中的任何文本。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="0bcb7-139">DeleteSubject： $false （请保留收到的会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="0bcb7-140">RemovePrivateProperty： $false （确保由会议组织者在原始会议请求中发送的私人标志保持指定。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="0bcb7-141">AddAdditionalResponse： $true （由 AdditionalResponse 参数指定的文本将添加到会议请求。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="0bcb7-142">AdditionalResponse： "这是 Skype 会议室！"</span><span class="sxs-lookup"><span data-stu-id="0bcb7-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="0bcb7-143">（要添加到会议请求的其他文本。）</span><span class="sxs-lookup"><span data-stu-id="0bcb7-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="0bcb7-144">此示例在名为 Rigel-01 的聊天室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="0bcb7-145">有关详细的语法和参数信息，请参阅[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="0bcb7-146">通过运行 PowerShell cmdlet 连接到 MS Online PowerShell 以进行 Active Directory 设置 `Connect-MsolService -Credential $cred` 。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="0bcb7-147">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="0bcb7-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="0bcb7-149">如果不希望密码过期，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="0bcb7-150">此示例将帐户 Rigel1@contoso.onmicrosoft.com 的密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="0bcb7-151">您也可以通过运行以下命令为帐户设置电话号码：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="0bcb7-152">设备帐户需要有有效的 Microsoft 365 或 Office 365 许可证，或者 Exchange 和 Microsoft 团队或 Skype for Business 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="0bcb7-153">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="0bcb7-154">你可以使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="0bcb7-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="0bcb7-155">若要检索 Microsoft 365 或 Office 365 组织的可用 Sku 列表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="0bcb7-156">接下来，你可以使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="0bcb7-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="0bcb7-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0bcb7-157">cmdlet.</span></span> <span data-ttu-id="0bcb7-158">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="0bcb7-159">有关详细说明，请参阅[使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="0bcb7-160">接下来，你需要启用 Skype for Business 设备帐户。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="0bcb7-161">请确保你的环境满足[Microsoft 团队会议室要求](requirements.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="0bcb7-162">启动远程[Windows PowerShell 会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示（请务必[安装 Skype For business Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)）：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="0bcb7-163">接下来，通过运行以下 cmdlet 为 Skype for business 服务器启用 Microsoft 团队聊天室帐户：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="0bcb7-164">从正在设置的新用户帐户获取 RegistrarPool 信息，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="0bcb7-165">新用户帐户可能不会在与租户中的现有用户帐户相同的注册机构池中创建。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="0bcb7-166">上面的命令将防止由于此情况而导致帐户设置出错。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-166">The command above will prevent errors in account setup due to this situation.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="0bcb7-167">向你的帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="0bcb7-167">Assign a license to your account</span></span>

1. <span data-ttu-id="0bcb7-168">以租户管理员身份登录，打开 Microsoft 365 管理中心，然后单击 "管理" 应用。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-168">Login as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>

2. <span data-ttu-id="0bcb7-169">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-169">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="0bcb7-170">选择 "Microsoft 团队聊天室帐户"，然后单击或点击 "笔" 图标，这意味着 "编辑"。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-170">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="0bcb7-171">单击“**许可证**”选项。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-171">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="0bcb7-172">在 "**分配许可证**" 部分中，你需要选择 "Skype For business Online （计划2）" 或 "skype For business Online （计划3）"，具体取决于你的许可以及你根据需要企业语音确定的内容。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-172">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="0bcb7-173">如果要在 Microsoft 团队聊天室使用云 PBX，则必须使用计划3许可证。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-173">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="0bcb7-174">至少需要 CloudPBX 才能进行语音连接。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-174">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="0bcb7-175">然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-175">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="0bcb7-176">有关详细信息，请参阅[Microsoft 团队聊天室许可证](rooms-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-176">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for more details.</span></span>

6. <span data-ttu-id="0bcb7-177">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-177">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="0bcb7-178">示例： Exchange Online 和 Skype for business Online 中的房间帐户设置</span><span class="sxs-lookup"><span data-stu-id="0bcb7-178">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="0bcb7-179">Exchange Online PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-179">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="0bcb7-180">Azure Active Directory PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-180">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="0bcb7-181">Skype for business PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0bcb7-181">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="0bcb7-182">这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-182">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="0bcb7-183">此外，你需要使用管理员界面分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-183">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="0bcb7-184">复核</span><span class="sxs-lookup"><span data-stu-id="0bcb7-184">Validate</span></span>

<span data-ttu-id="0bcb7-185">对于验证，你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="0bcb7-185">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bcb7-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bcb7-186">See also</span></span>

[<span data-ttu-id="0bcb7-187">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="0bcb7-187">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="0bcb7-188">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="0bcb7-188">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="0bcb7-189">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="0bcb7-189">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="0bcb7-190">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="0bcb7-190">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="0bcb7-191">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="0bcb7-191">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="0bcb7-192">Microsoft 团队聊天室许可</span><span class="sxs-lookup"><span data-stu-id="0bcb7-192">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
