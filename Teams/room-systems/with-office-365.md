---
title: 部署与 Office 365 的 Microsoft 团队聊天室
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读此主题以获取如何部署与 Office 365 的 Microsoft 团队聊天室的信息。
ms.openlocfilehash: 16d0fad14bd52a13fa6735ec0b786cb15f3ce8c1
ms.sourcegitcommit: 728507d34031d01f663d9b551cd4794867244854
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467531"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="0a5f3-103">部署与 Office 365 的 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0a5f3-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="0a5f3-104">阅读本主题有关如何部署与 Office 365，其中的 Microsoft 团队或商业和 Exchange Skype 都是联机 Microsoft 团队聊天室的信息。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="0a5f3-105">设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="0a5f3-106">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Microsoft 团队聊天室用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="0a5f3-107">如果您愿意，您可以按照以下步骤来配置您的 Microsoft 团队聊天室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a5f3-108">要求</span><span class="sxs-lookup"><span data-stu-id="0a5f3-108">Requirements</span></span>

<span data-ttu-id="0a5f3-109">部署与 Office 365 的 Microsoft 团队聊天室之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="0a5f3-110">有关详细信息，请参阅[Microsoft 团队聊天室要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="0a5f3-111">若要启用 for Business 的 Skype，您必须：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="0a5f3-112">Skype 业务 online （计划 2 中或基于企业的规划） 或更高版本 Office 365 计划中。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="0a5f3-113">计划需要允许电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="0a5f3-114">如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="0a5f3-115">如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="0a5f3-116">您的租户用户必须拥有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="0a5f3-117">您的 Microsoft 团队会议室帐户确实需要至少 Skype 业务 Online (计划 2) 许可证，但它不需要的 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="0a5f3-118">有关详细信息，请参阅[Microsoft 团队聊天室许可证](skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="0a5f3-119">Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="0a5f3-120">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="0a5f3-120">Add a device account</span></span>

1. <span data-ttu-id="0a5f3-121">连接到 Exchange Online PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="0a5f3-122">有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="0a5f3-123">在 Exchange Online PowerShell 中，创建新会议室邮箱或修改现有的会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="0a5f3-124">默认情况下，会议室邮箱不具有关联的帐户，因此您需要创建或修改会议室邮箱，使其可以通过 Skype 会议室系统 v2 进行身份验证时添加帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="0a5f3-125">若要创建新的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="0a5f3-126">本示例创建新的会议室邮箱，使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="0a5f3-127">名称： 项目-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="0a5f3-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="0a5f3-128">别名： ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="0a5f3-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="0a5f3-129">帐户： ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0a5f3-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="0a5f3-130">帐户密码： P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="0a5f3-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="0a5f3-131">若要修改现有的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="0a5f3-132">本示例启用现有的会议室邮箱的别名值 ProjectRigel02，并将密码设置为 9898P@$$W0rd 的帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="0a5f3-133">请注意，帐户将由于现有别名值是 ProjectRigel02@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="0a5f3-134">有关详细的语法和参数信息，请参阅[New-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="0a5f3-135">在 Exchange Online PowerShell 中，在要改进的会议体验的会议室邮箱上配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="0a5f3-136">如果不将 AutomateProcessing: AutoAccept (会议组织者接收直接不需要人工干预的会议室预订决策： 免费 = 接受; 闲 = 拒绝。)</span><span class="sxs-lookup"><span data-stu-id="0a5f3-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="0a5f3-137">AddOrganizerToSubject: $false （会议组织者未添加到会议请求中的主题。）</span><span class="sxs-lookup"><span data-stu-id="0a5f3-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="0a5f3-138">DeleteComments: $false （传入会议请求邮件正文中保留任何文本）。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="0a5f3-139">DeleteSubject: $false （保留传入会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="0a5f3-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="0a5f3-140">RemovePrivateProperty: $false （确保的私有标志： 由会议组织者在原始的会议中发送的请求保持指定）。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="0a5f3-141">AddAdditionalResponse: $true （AdditionalResponse 参数指定的文本添加到会议请求中）。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="0a5f3-142">AdditionalResponse:"This is Skype 会议室 ！"</span><span class="sxs-lookup"><span data-stu-id="0a5f3-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="0a5f3-143">（其他文本添加到会议请求。）</span><span class="sxs-lookup"><span data-stu-id="0a5f3-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="0a5f3-144">本示例在名为项目-Rigel-01 的会议室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="0a5f3-145">有关详细的语法和参数信息，请参阅[Set-calendarprocessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="0a5f3-146">连接到 MS 联机 PowerShell，可以通过运行使 Active Directory 设置`Connect-MsolService -Credential $cred`powershell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="0a5f3-147">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. <span data-ttu-id="0a5f3-148">如果您不希望密码过期，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-148">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="0a5f3-149">本示例设置 ProjectRigel01@contoso.onmicrosoft.com 为永不过期的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="0a5f3-150">您还可以设置帐户的电话的号码，通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-150">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="0a5f3-151">设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Microsoft 团队或 Skype for Business 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-151">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="0a5f3-152">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="0a5f3-153">您可以使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="0a5f3-153">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="0a5f3-154">若要为 Office 365 租户检索可用的 Sku 的列表，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-154">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="0a5f3-155">接下来，添加许可证使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="0a5f3-155">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="0a5f3-156">cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-156">cmdlet.</span></span> <span data-ttu-id="0a5f3-157">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-157">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="0a5f3-158">有关详细说明，请参阅[分配到与 Office 365 PowerShell 中的用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-158">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="0a5f3-159">接下来，您需要启用 for Business 的 Skype 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-159">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="0a5f3-160">确保您的环境符合[Microsoft 团队聊天室要求](requirements.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-160">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="0a5f3-161">启动远程[Windows PowerShell 会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示 （确保[安装 Skype 业务 Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)）：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-161">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="0a5f3-162">接下来，您的 Microsoft 团队会议室帐户为启用 Skype 业务服务器通过运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0a5f3-162">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="0a5f3-163">本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-163">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="0a5f3-164">不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-164">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="0a5f3-165">上面的命令将防止由于这种情况下的帐户设置中的错误。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-165">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="0a5f3-166">您已完成上述步骤将您的 Microsoft 团队或 Skype 中的 Microsoft 团队会议室帐户启用业务联机后，您需要将许可证分配给 Microsoft 团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-166">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="0a5f3-167">使用 Office 365 管理门户，为业务 Online (计划 2) 或业务 Online (计划 3) 许可证设备 Skype 分配任一 Skype。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-167">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="0a5f3-168">向你的帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="0a5f3-168">Assign a license to your account</span></span>

1. <span data-ttu-id="0a5f3-169">登录以租户管理员，打开 Office 365 管理门户，并单击管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-169">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="0a5f3-170">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-170">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="0a5f3-171">选择 Microsoft 团队会议室帐户，然后单击或点击笔图标，表示编辑。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-171">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="0a5f3-172">单击“**许可证**”选项。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-172">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="0a5f3-173">在**分配许可证**部分中，您需要选择 Skype 业务 Online (计划 2) 或 Skype 的业务 Online (计划 3)，具体取决于您的授权和决定方面需要企业语音。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-173">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="0a5f3-174">您将需要使用规划 3 许可证，如果您想要使用 Microsoft 团队聊天室云 PBX。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-174">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="0a5f3-175">至少需要 CloudPBX 才能进行语音连接。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-175">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="0a5f3-176">然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-176">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="0a5f3-177">有关详细信息，请参阅[Microsoft 团队聊天室许可证](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-177">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="0a5f3-178">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-178">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="0a5f3-179">示例： 会议室帐户安装在 Exchange Online 和 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="0a5f3-179">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="0a5f3-180">Exchange Online PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-180">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="0a5f3-181">Azure Active Directory PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-181">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="0a5f3-182">Skype 业务 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0a5f3-182">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="0a5f3-183">这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-183">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="0a5f3-184">此外，需要使用管理中心界面分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-184">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="0a5f3-185">验证</span><span class="sxs-lookup"><span data-stu-id="0a5f3-185">Validate</span></span>

<span data-ttu-id="0a5f3-186">进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="0a5f3-186">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a5f3-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a5f3-187">See also</span></span>

[<span data-ttu-id="0a5f3-188">为 Microsoft 团队房间配置帐户</span><span class="sxs-lookup"><span data-stu-id="0a5f3-188">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="0a5f3-189">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0a5f3-189">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="0a5f3-190">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0a5f3-190">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="0a5f3-191">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="0a5f3-191">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="0a5f3-192">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="0a5f3-192">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="0a5f3-193">授权的 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0a5f3-193">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
