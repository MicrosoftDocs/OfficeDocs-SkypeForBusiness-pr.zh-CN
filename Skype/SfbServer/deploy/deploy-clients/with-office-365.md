---
title: 将 Skype 会议室系统 v2 与 Office 365 一起部署
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读此主题以获取如何部署与 Office 365 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: a931ec6cb55e654612c451f15d4a4895f61ba990
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645385"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="6043a-103">将 Skype 会议室系统 v2 与 Office 365 一起部署 </span><span class="sxs-lookup"><span data-stu-id="6043a-103">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="6043a-104">阅读此主题以获取如何部署与 Office 365，其中的业务和 Exchange Skype 都联机 Skype 会议室系统 v2 的信息。</span><span class="sxs-lookup"><span data-stu-id="6043a-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="6043a-105">设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="6043a-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="6043a-106">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="6043a-107">如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="6043a-108">要求</span><span class="sxs-lookup"><span data-stu-id="6043a-108">Requirements</span></span>

<span data-ttu-id="6043a-109">部署与 Office 365 的 Skype 会议室系统 v2 之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="6043a-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="6043a-110">有关详细信息，请参阅 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6043a-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="6043a-111">若要启用 for Business 的 Skype，您必须：</span><span class="sxs-lookup"><span data-stu-id="6043a-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="6043a-112">Skype 业务 online （计划 2 中或基于企业的规划） 或更高版本 Office 365 计划中。</span><span class="sxs-lookup"><span data-stu-id="6043a-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="6043a-113">计划需要允许电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="6043a-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="6043a-114">如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="6043a-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="6043a-115">如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。</span><span class="sxs-lookup"><span data-stu-id="6043a-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="6043a-116">您的租户用户必须拥有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="6043a-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="6043a-117">Skype 会议室系统 v2 帐户确实需要至少 Skype 业务 Online (计划 2) 许可证，但它不需要的 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="6043a-117">Your Skype Room Systems v2 account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="6043a-118">有关详细信息，请参阅[Skype 会议室系统 v2 许可](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="6043a-118">See [Skype Room Systems v2 Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="6043a-119">Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6043a-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="6043a-120">添加设备帐户</span><span class="sxs-lookup"><span data-stu-id="6043a-120">Add a device account</span></span>

https://docs.microsoft.com/en-us/powershell/module/msonline/?view=azureadps-1.0

https://docs.microsoft.com/en-us/powershell/module/Azuread/?view=azureadps-2.0 


1. <span data-ttu-id="6043a-121">连接到 Exchange Online PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="6043a-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="6043a-122">有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="6043a-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="6043a-123">在 Exchange Online PowerShell 中，创建新会议室邮箱或修改现有的会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="6043a-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="6043a-124">默认情况下，会议室邮箱不具有关联的帐户，因此您需要创建或修改会议室邮箱，使其可以通过 Skype 会议室系统 v2 进行身份验证时添加帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="6043a-125">若要创建新的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6043a-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="6043a-126">本示例创建新的会议室邮箱，使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="6043a-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="6043a-127">名称： 项目-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="6043a-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="6043a-128">别名： ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="6043a-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="6043a-129">帐户： ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6043a-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="6043a-130">帐户密码： P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="6043a-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="6043a-131">若要修改现有的会议室邮箱，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6043a-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="6043a-132">本示例启用现有的会议室邮箱的别名值 ProjectRigel02，并将密码设置为 9898P@$$W0rd 的帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="6043a-133">请注意，帐户将由于现有别名值是 ProjectRigel02@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="6043a-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="6043a-134">有关详细的语法和参数信息，请参阅[New-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="6043a-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="6043a-135">在 Exchange Online PowerShell 中，在要改进的会议体验的会议室邮箱上配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6043a-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="6043a-136">如果不将 AutomateProcessing: AutoAccept (会议组织者接收直接不需要人工干预的会议室预订决策： 免费 = 接受; 闲 = 拒绝。)</span><span class="sxs-lookup"><span data-stu-id="6043a-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="6043a-137">AddOrganizerToSubject: $false （会议组织者未添加到会议请求中的主题。）</span><span class="sxs-lookup"><span data-stu-id="6043a-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="6043a-138">DeleteComments: $false （传入会议请求邮件正文中保留任何文本）。</span><span class="sxs-lookup"><span data-stu-id="6043a-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6043a-139">DeleteSubject: $false （保留传入会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="6043a-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6043a-140">RemovePrivateProperty: $false （确保的私有标志： 由会议组织者在原始的会议中发送的请求保持指定）。</span><span class="sxs-lookup"><span data-stu-id="6043a-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="6043a-141">AddAdditionalResponse: $true （AdditionalResponse 参数指定的文本添加到会议请求中）。</span><span class="sxs-lookup"><span data-stu-id="6043a-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="6043a-142">AdditionalResponse:"This is Skype 会议室 ！"</span><span class="sxs-lookup"><span data-stu-id="6043a-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="6043a-143">（其他文本添加到会议请求。）</span><span class="sxs-lookup"><span data-stu-id="6043a-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="6043a-144">本示例在名为项目-Rigel-01 的会议室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="6043a-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="6043a-145">有关详细的语法和参数信息，请参阅[Set-calendarprocessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="6043a-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="6043a-146">连接到 PowerShell 的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6043a-146">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="6043a-147">有关说明，请参阅[使用图模块 Azure Active Directory PowerShell 连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6043a-147">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

5. <span data-ttu-id="6043a-148">如果不希望使用的密码到期，则在 Azure Active Directory PowerShell 中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6043a-148">If you do not want the password to expire, use the following syntax in Azure Active Directory PowerShell:</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="6043a-149">本示例设置 ProjectRigel01@contoso.onmicrosoft.com 为永不过期的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="6043a-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="6043a-150">您还可以设置帐户的电话的号码，通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6043a-150">You can also set a phone number for the account by running the following command:</span></span>

   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```

6. <span data-ttu-id="6043a-151">设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="6043a-151">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="6043a-152">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="6043a-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="6043a-153">您可以使用 Get AzureADSubscribedSku，如下所示的 Office 365 租户中检索可用的 Sku 的列表：</span><span class="sxs-lookup"><span data-stu-id="6043a-153">You can use Get-AzureADSubscribedSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   <span data-ttu-id="6043a-154">接下来，您可以添加使用集 AzureADUserLicense cmdlet 的许可证。</span><span class="sxs-lookup"><span data-stu-id="6043a-154">Next, you can add a license using the Set-AzureADUserLicense cmdlet.</span></span> <span data-ttu-id="6043a-155">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="6043a-155">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   <span data-ttu-id="6043a-156">有关详细说明，请参阅[分配到与 Office 365 PowerShell 中的用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6043a-156">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="6043a-157">接下来，您需要启用 for Business 的 Skype 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-157">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="6043a-158">确保你的环境满足 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="6043a-158">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="6043a-159">启动远程[Windows PowerShell 会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示 （确保[安装 Skype 业务 Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)）：</span><span class="sxs-lookup"><span data-stu-id="6043a-159">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="6043a-160">接下来，您 Skype 会议室系统 v2 帐户启用 Skype 业务服务器通过运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6043a-160">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="6043a-161">本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：</span><span class="sxs-lookup"><span data-stu-id="6043a-161">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="6043a-162">不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-162">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="6043a-163">上面的命令将防止由于这种情况下的帐户设置中的错误。</span><span class="sxs-lookup"><span data-stu-id="6043a-163">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="6043a-164">您已完成上述步骤中 Skype 您 Skype 会议室系统 v2 帐户启用业务联机后，您需要将许可证分配给 Skype 会议室系统 v2 设备。</span><span class="sxs-lookup"><span data-stu-id="6043a-164">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="6043a-165">使用 Office 365 管理门户，为业务 Online (计划 2) 或业务 Online (计划 3) 许可证设备 Skype 分配任一 Skype。</span><span class="sxs-lookup"><span data-stu-id="6043a-165">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="6043a-166">向你的帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="6043a-166">Assign a license to your account</span></span>

1. <span data-ttu-id="6043a-167">登录以租户管理员，打开 Office 365 管理门户，并单击管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="6043a-167">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="6043a-168">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="6043a-168">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="6043a-169">选择 Skype 会议室系统 v2 帐户，然后单击或点击笔图标，表示编辑。</span><span class="sxs-lookup"><span data-stu-id="6043a-169">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="6043a-170">单击“**许可证**”选项。</span><span class="sxs-lookup"><span data-stu-id="6043a-170">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="6043a-171">在**分配许可证**部分中，您需要选择 Skype 业务 Online (计划 2) 或 Skype 的业务 Online (计划 3)，具体取决于您的授权和决定方面需要企业语音。</span><span class="sxs-lookup"><span data-stu-id="6043a-171">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="6043a-172">您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 云 PBX。</span><span class="sxs-lookup"><span data-stu-id="6043a-172">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="6043a-173">至少需要 CloudPBX 才能进行语音连接。</span><span class="sxs-lookup"><span data-stu-id="6043a-173">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="6043a-174">然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="6043a-174">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="6043a-175">有关详细信息，请参阅[Skype 会议室系统 v2 许可证](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)。</span><span class="sxs-lookup"><span data-stu-id="6043a-175">See [Skype Room Systems v2 licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="6043a-176">单击“**保存**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="6043a-176">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="6043a-177">示例： 会议室帐户安装在 Exchange Online 和 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="6043a-177">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="6043a-178">Exchange Online PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6043a-178">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="6043a-179">Azure Active Directory PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6043a-179">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<span data-ttu-id="6043a-180">Skype 业务 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6043a-180">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="6043a-181">这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。</span><span class="sxs-lookup"><span data-stu-id="6043a-181">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="6043a-182">此外，需要使用管理中心界面分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="6043a-182">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="6043a-183">验证</span><span class="sxs-lookup"><span data-stu-id="6043a-183">Validate</span></span>

<span data-ttu-id="6043a-184">进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="6043a-184">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="6043a-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6043a-185">See also</span></span>

[<span data-ttu-id="6043a-186">配置帐户 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6043a-186">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="6043a-187">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="6043a-187">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="6043a-188">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6043a-188">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)

[<span data-ttu-id="6043a-189">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="6043a-189">Configure a Skype Room Systems v2 console</span></span>](console.md)

[<span data-ttu-id="6043a-190">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6043a-190">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="6043a-191">Skype 会议室系统 v2 许可</span><span class="sxs-lookup"><span data-stu-id="6043a-191">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
