---
title: 使用 Exchange on premises 部署 Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 阅读本主题，了解如何使用 Exchange on on-premises 在混合环境中部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: 62840e0a28ee1eba2a9b5a94f976f169eab628da
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952715"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="a56db-103">使用 Exchange on premises 部署 Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a56db-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="a56db-104">阅读本主题，了解如何使用 Exchange on on-premises 和 Microsoft 团队或 Skype for business Online 在混合环境中部署 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="a56db-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="a56db-105">如果你的组织具有混合服务，并且某些托管在本地托管和某些托管网络，则你的配置将取决于托管每个服务的位置。</span><span class="sxs-lookup"><span data-stu-id="a56db-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="a56db-106">本主题介绍 Microsoft 团队聊天室的混合部署，Exchange 托管于本地托管。</span><span class="sxs-lookup"><span data-stu-id="a56db-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="a56db-107">由于这种类型的部署中存在如此多的不同变体，因此不可能提供所有这些类型的详细说明。</span><span class="sxs-lookup"><span data-stu-id="a56db-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="a56db-108">以下过程将适用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="a56db-108">The following process will work for many configurations.</span></span> <span data-ttu-id="a56db-109">如果该进程不适合你的设置，我们建议你使用 Windows PowerShell 获得相同的最终结果，如此处所述以及其他部署选项。</span><span class="sxs-lookup"><span data-stu-id="a56db-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="a56db-110">Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)，该脚本可帮助创建新的用户帐户，或验证你拥有的现有资源帐户，以帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a56db-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="a56db-111">如果你愿意，可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="a56db-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a56db-112">要求</span><span class="sxs-lookup"><span data-stu-id="a56db-112">Requirements</span></span>

<span data-ttu-id="a56db-113">在使用 Exchange 内部部署部署 Microsoft 团队聊天室之前，请确保满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="a56db-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="a56db-114">有关详细信息，请参阅[Microsoft 团队会议室要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a56db-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="a56db-115">如果要使用 Exchange on on-premises 部署 Microsoft 团队聊天室，您将使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a56db-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="a56db-116">此帐户将同步到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a56db-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="a56db-117">你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a56db-117">You will need to:</span></span>
  
- <span data-ttu-id="a56db-118">创建一个帐户并将该帐户与 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="a56db-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="a56db-119">启用远程邮箱并设置属性。</span><span class="sxs-lookup"><span data-stu-id="a56db-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="a56db-120">分配 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="a56db-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="a56db-121">启用使用 Skype for Business 服务器的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="a56db-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="a56db-122">要启用设备帐户，你的环境需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="a56db-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="a56db-123">您需要在 Office 365 计划中安装 Skype for Business Online （计划2）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a56db-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="a56db-124">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="a56db-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="a56db-125">如果您需要使用适用于 Microsoft 团队聊天室的电话服务提供商的企业语音（PSTN 电话），您需要 Skype for Business Online （计划3）。</span><span class="sxs-lookup"><span data-stu-id="a56db-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="a56db-126">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="a56db-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="a56db-127">您的 Microsoft 团队会议室帐户需要 Skype for business Online （计划2）或 Skype for business Online （计划3）许可证，但不需要 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="a56db-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="a56db-128">将 Skype for Business Server 许可证分配给你的 Microsoft 团队聊天室帐户。</span><span class="sxs-lookup"><span data-stu-id="a56db-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="a56db-129">创建一个帐户并与 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="a56db-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="a56db-130">在 " **Active Directory 用户和计算机**" 工具中，右键单击将在其中创建 Microsoft 团队聊天室帐户的文件夹或组织单位，单击 "**新建**"，然后单击 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="a56db-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="a56db-p107">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a56db-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="a56db-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="a56db-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a56db-136">选择 "**密码永不过期**" 是 Microsoft 团队聊天室上的 Skype For business 服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="a56db-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="a56db-137">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="a56db-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="a56db-138">如果是这样，你将需要为每个 Microsoft 团队聊天室设备帐户创建一个例外。</span><span class="sxs-lookup"><span data-stu-id="a56db-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="a56db-139">创建该帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="a56db-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="a56db-140">完成后，转到 Microsoft 365 管理中心中的 "用户" 页面，并验证在先前步骤中创建的帐户是否已合并到 "联机"。</span><span class="sxs-lookup"><span data-stu-id="a56db-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="a56db-141">启用远程邮箱并设置属性</span><span class="sxs-lookup"><span data-stu-id="a56db-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="a56db-142">[打开 Exchange 命令行管理](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)程序或[使用远程 PowerShell 连接到 exchange 服务器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a56db-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="a56db-143">在 Exchange PowerShell 中，通过运行以下命令为帐户（邮箱启用帐户）包装箱提供邮箱：</span><span class="sxs-lookup"><span data-stu-id="a56db-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="a56db-144">有关详细语法和参数信息，请参阅[启用-邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="a56db-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="a56db-145">在 Exchange PowerShell 中，在聊天室邮箱上配置以下设置以改进会议体验：</span><span class="sxs-lookup"><span data-stu-id="a56db-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="a56db-146">AutomateProcessing： AutoAccept （会议组织者直接收到会议室保留决定，无需人工干预：闲 = 接受; 忙 = 拒绝。）</span><span class="sxs-lookup"><span data-stu-id="a56db-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="a56db-147">AddOrganizerToSubject： $false （会议组织者未添加到会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="a56db-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="a56db-148">DeleteComments： $false （保留收到的会议请求的邮件正文中的任何文本。）</span><span class="sxs-lookup"><span data-stu-id="a56db-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="a56db-149">DeleteSubject： $false （请保留收到的会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="a56db-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="a56db-150">RemovePrivateProperty： $false （确保由会议组织者在原始会议请求中发送的私人标志保持指定。）</span><span class="sxs-lookup"><span data-stu-id="a56db-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="a56db-151">AddAdditionalResponse： $true （由 AdditionalResponse 参数指定的文本将添加到会议请求。）</span><span class="sxs-lookup"><span data-stu-id="a56db-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="a56db-152">AdditionalResponse： "这是 Skype 会议室！"</span><span class="sxs-lookup"><span data-stu-id="a56db-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="a56db-153">（要添加到会议请求的其他文本。）</span><span class="sxs-lookup"><span data-stu-id="a56db-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="a56db-154">此示例在名为 Project-01 的聊天室邮箱上配置这些设置 Rigel。</span><span class="sxs-lookup"><span data-stu-id="a56db-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="a56db-155">有关详细的语法和参数信息，请参阅[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="a56db-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="a56db-156">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="a56db-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="a56db-157">连接到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a56db-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="a56db-158">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="a56db-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="a56db-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。</span><span class="sxs-lookup"><span data-stu-id="a56db-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="a56db-160">设备帐户需要拥有有效的 Office 365 许可证，否则 Exchange 和 Microsoft 团队将不起作用。</span><span class="sxs-lookup"><span data-stu-id="a56db-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="a56db-161">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="a56db-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="a56db-162">你可以使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="a56db-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="a56db-163">检索可用 Sku 的列表。</span><span class="sxs-lookup"><span data-stu-id="a56db-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="a56db-164">接下来，你可以使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="a56db-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="a56db-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a56db-165">cmdlet.</span></span> <span data-ttu-id="a56db-166">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="a56db-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="a56db-167">有关详细说明，请参阅[使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a56db-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="a56db-168">启用设备帐户</span><span class="sxs-lookup"><span data-stu-id="a56db-168">Enable the device account</span></span>

<span data-ttu-id="a56db-169">Skype for Business Online PowerShell 用于管理 Microsoft 团队和 Skype for business Online 的服务。</span><span class="sxs-lookup"><span data-stu-id="a56db-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="a56db-170">从电脑创建远程 Windows PowerShell 会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a56db-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="a56db-171">获取帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="a56db-171">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="a56db-172">若要启用 Microsoft 团队聊天室帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a56db-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="a56db-173">如果你不确定要在你的环境中使用 RegistrarPool 参数的值，可以使用此命令从现有用户获取值：</span><span class="sxs-lookup"><span data-stu-id="a56db-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="a56db-174">将许可证分配给你的 Microsoft 团队聊天室帐户</span><span class="sxs-lookup"><span data-stu-id="a56db-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="a56db-175">以租户管理员身份登录，打开 Office 365 管理门户，然后单击 "管理" 应用。</span><span class="sxs-lookup"><span data-stu-id="a56db-175">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="a56db-176">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="a56db-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="a56db-177">单击 "Microsoft 团队聊天室帐户"，然后单击 "笔" 图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="a56db-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="a56db-178">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="a56db-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="a56db-179">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="a56db-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="a56db-180">如果要在 Microsoft 团队聊天室上使用企业语音，则必须使用计划3许可证。</span><span class="sxs-lookup"><span data-stu-id="a56db-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="a56db-181">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a56db-181">Click **Save**.</span></span>

<span data-ttu-id="a56db-182">对于验证，你应该能够使用任何客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="a56db-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a56db-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a56db-183">See also</span></span>

[<span data-ttu-id="a56db-184">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="a56db-184">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="a56db-185">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a56db-185">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="a56db-186">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a56db-186">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="a56db-187">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="a56db-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="a56db-188">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="a56db-188">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
