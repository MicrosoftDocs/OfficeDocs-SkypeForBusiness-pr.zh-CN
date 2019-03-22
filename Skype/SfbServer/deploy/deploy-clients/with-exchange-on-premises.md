---
title: 将 Skype 会议室系统 v2 与本地 Exchange 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: 阅读此主题以获取如何部署与 Exchange 内部部署混合环境中的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 9ebd7463465d8b2fbf11e95d71c8fcb557666b3a
ms.sourcegitcommit: cad74f2546a6384747b1280c3d9244aa13fd0989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737792"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="6af8e-103">将 Skype 会议室系统 v2 与本地 Exchange 一起部署</span><span class="sxs-lookup"><span data-stu-id="6af8e-103">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="6af8e-104">阅读本主题有关如何为业务 Online 部署在混合环境与本地 Exchange 和 Skype 的 Skype 会议室系统 v2 的信息。</span><span class="sxs-lookup"><span data-stu-id="6af8e-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises and Skype for Business Online.</span></span>
  
<span data-ttu-id="6af8e-105">如果您的组织具有其中的部分位于内部部署和一些在线承载的服务，组合，然后您的配置将取决于承载每个服务。</span><span class="sxs-lookup"><span data-stu-id="6af8e-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="6af8e-106">本主题介绍与部署上承载的 Exchange 混合部署的 Skype 会议室系统 v2。</span><span class="sxs-lookup"><span data-stu-id="6af8e-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="6af8e-107">由于存在太多不同的变体在这种部署，不能提供的所有这些详细的说明。</span><span class="sxs-lookup"><span data-stu-id="6af8e-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="6af8e-108">以下过程将用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="6af8e-108">The following process will work for many configurations.</span></span> <span data-ttu-id="6af8e-109">如果过程不适合您的安装程序，我们建议您使用 Windows PowerShell 可以获得相同的最终结果记录在这里，以及其他部署选项的。</span><span class="sxs-lookup"><span data-stu-id="6af8e-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="6af8e-110">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6af8e-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="6af8e-111">如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="6af8e-111">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6af8e-112">要求</span><span class="sxs-lookup"><span data-stu-id="6af8e-112">Requirements</span></span>

<span data-ttu-id="6af8e-113">部署与 Exchange 本地 Skype 会议室系统 v2 之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="6af8e-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="6af8e-114">有关详细信息，请参阅 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6af8e-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="6af8e-115">如果您正在部署与本地 Exchange 的 Skype 会议室系统 v2，您将使用 Active Directory 管理工具添加您的内部部署域帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6af8e-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="6af8e-116">此帐户将同步到 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="6af8e-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="6af8e-117">你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6af8e-117">You will need to:</span></span>
  
- <span data-ttu-id="6af8e-118">创建一个帐户并将该帐户与 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="6af8e-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="6af8e-119">启用远程邮箱并设置属性。</span><span class="sxs-lookup"><span data-stu-id="6af8e-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="6af8e-120">分配 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="6af8e-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="6af8e-121">启用 Business Server Skype 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="6af8e-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="6af8e-122">要启用设备帐户，你的环境需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="6af8e-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="6af8e-123">您需要在您的 Office 365 计划中具有 Skype 业务 online (计划 2) 或更高。</span><span class="sxs-lookup"><span data-stu-id="6af8e-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="6af8e-124">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="6af8e-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="6af8e-125">如果您需要企业语音 （PSTN 电话） 使用 Skype 会议室系统 v2 电话服务提供程序需要 Skype 业务 online (计划 3)。</span><span class="sxs-lookup"><span data-stu-id="6af8e-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="6af8e-126">您的租户用户必须拥有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="6af8e-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="6af8e-127">Skype 会议室系统 v2 帐户确实需要 Skype 业务 online (计划 2) 或 Skype 业务 Online (计划 3) 许可证，但它不需要的 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="6af8e-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="6af8e-128">将业务服务器许可证 Skype 分配给您的 Skype 会议室系统 v2 帐户。</span><span class="sxs-lookup"><span data-stu-id="6af8e-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="6af8e-129">创建一个帐户并与 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="6af8e-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="6af8e-130">在**Active Directory 用户和计算机 AD**工具中，右键单击该组织单位 Skype 会议室系统 v2 帐户将创建中，单击**新建**，然后单击**用户**或文件夹。</span><span class="sxs-lookup"><span data-stu-id="6af8e-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="6af8e-p107">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6af8e-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="6af8e-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="6af8e-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6af8e-136">选择**密码永不过期**是在 Skype 会议室系统 v2 Skype 业务服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="6af8e-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="6af8e-137">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="6af8e-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="6af8e-138">如果是这样，您需要创建的每个 Skype 会议室系统 v2 设备帐户异常。</span><span class="sxs-lookup"><span data-stu-id="6af8e-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="6af8e-139">创建该帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="6af8e-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="6af8e-140">完成后，转到您的 Office 365 管理中心中用户页，并验证已联机合并到上一步骤中创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="6af8e-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="6af8e-141">启用远程邮箱并设置属性</span><span class="sxs-lookup"><span data-stu-id="6af8e-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="6af8e-142">[打开 Exchange 命令行管理程序](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)或[连接到 Exchange 服务器使用远程 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6af8e-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="6af8e-143">在 Exchange PowerShell 中，通过运行以下命令创建的帐户 （邮箱启用的帐户） 的邮箱：</span><span class="sxs-lookup"><span data-stu-id="6af8e-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="6af8e-144">有关详细的语法和参数信息，请参阅[Enable-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="6af8e-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="6af8e-145">在 Exchange PowerShell 中，在要改进的会议体验的会议室邮箱上配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6af8e-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="6af8e-146">如果不将 AutomateProcessing: AutoAccept (会议组织者接收直接不需要人工干预的会议室预订决策： 免费 = 接受; 闲 = 拒绝。)</span><span class="sxs-lookup"><span data-stu-id="6af8e-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="6af8e-147">AddOrganizerToSubject: $false （会议组织者未添加到会议请求中的主题。）</span><span class="sxs-lookup"><span data-stu-id="6af8e-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="6af8e-148">DeleteComments: $false （传入会议请求邮件正文中保留任何文本）。</span><span class="sxs-lookup"><span data-stu-id="6af8e-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6af8e-149">DeleteSubject: $false （保留传入会议请求的主题。）</span><span class="sxs-lookup"><span data-stu-id="6af8e-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6af8e-150">RemovePrivateProperty: $false （确保的私有标志： 由会议组织者在原始的会议中发送的请求保持指定）。</span><span class="sxs-lookup"><span data-stu-id="6af8e-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="6af8e-151">AddAdditionalResponse: $true （AdditionalResponse 参数指定的文本添加到会议请求中）。</span><span class="sxs-lookup"><span data-stu-id="6af8e-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="6af8e-152">AdditionalResponse:"This is Skype 会议室 ！"</span><span class="sxs-lookup"><span data-stu-id="6af8e-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="6af8e-153">（其他文本添加到会议请求。）</span><span class="sxs-lookup"><span data-stu-id="6af8e-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="6af8e-154">本示例在名为项目-Rigel-01 的会议室邮箱上配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="6af8e-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="6af8e-155">有关详细的语法和参数信息，请参阅[Set-calendarprocessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="6af8e-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="6af8e-156">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="6af8e-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="6af8e-157">连接到 PowerShell 的 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6af8e-157">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="6af8e-158">有关说明，请参阅[使用图模块 Azure Active Directory PowerShell 连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6af8e-158">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

2. <span data-ttu-id="6af8e-159">设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="6af8e-159">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="6af8e-160">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="6af8e-160">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="6af8e-161">您可以使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="6af8e-161">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="6af8e-162">若要检索可用的 Sku 的列表。</span><span class="sxs-lookup"><span data-stu-id="6af8e-162">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="6af8e-163">接下来，添加许可证使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="6af8e-163">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="6af8e-164">cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6af8e-164">cmdlet.</span></span> <span data-ttu-id="6af8e-165">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="6af8e-165">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="6af8e-166">有关详细说明，请参阅[分配到与 Office 365 PowerShell 中的用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6af8e-166">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="6af8e-167">使用 Skype for Business 启用设备帐户</span><span class="sxs-lookup"><span data-stu-id="6af8e-167">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="6af8e-168">从 PC 创建远程 Windows PowerShell 会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6af8e-168">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="6af8e-169">为业务服务器启用 Skype Skype 会议室系统 v2 帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6af8e-169">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="6af8e-170">如果不确定哪些值用于您的环境中的 RegistrarPool 参数，您可以从现有 Skype 企业服务器用户使用此命令获取值</span><span class="sxs-lookup"><span data-stu-id="6af8e-170">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="6af8e-171">向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business 许可证</span><span class="sxs-lookup"><span data-stu-id="6af8e-171">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="6af8e-172">以租户管理员身份登录，打开 Office 365 管理门户，并单击管理中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="6af8e-172">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="6af8e-173">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="6af8e-173">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="6af8e-174">单击 Skype 会议室系统 v2 帐户，，然后单击笔图标可编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="6af8e-174">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="6af8e-175">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="6af8e-175">Click **Licenses**.</span></span>
5. <span data-ttu-id="6af8e-176">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="6af8e-176">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="6af8e-177">您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 企业语音。</span><span class="sxs-lookup"><span data-stu-id="6af8e-177">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
6. <span data-ttu-id="6af8e-178">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6af8e-178">Click **Save**.</span></span>

<span data-ttu-id="6af8e-179">进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="6af8e-179">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6af8e-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6af8e-180">See also</span></span>

[<span data-ttu-id="6af8e-181">配置帐户 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6af8e-181">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="6af8e-182">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="6af8e-182">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="6af8e-183">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6af8e-183">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="6af8e-184">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="6af8e-184">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="6af8e-185">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6af8e-185">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)