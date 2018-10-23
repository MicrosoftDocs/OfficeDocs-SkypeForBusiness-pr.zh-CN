---
title: 将 Skype 会议室系统 v2 与 Exchange Online 一起部署
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读此主题以获取如何部署与 Exchange Online 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 7e9e7dbf0c1ec29444b9ba783acd2e5cd0987440
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699698"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="e7427-103">将 Skype 会议室系统 v2 与 Exchange Online 一起部署</span><span class="sxs-lookup"><span data-stu-id="e7427-103">Deploy Skype Room Systems v2 with Exchange Online</span></span> 
 
<span data-ttu-id="e7427-104">阅读此主题以获取如何部署与 Exchange Online 和 Skype 业务服务器本地的 Skype 会议室系统 v2 的信息。</span><span class="sxs-lookup"><span data-stu-id="e7427-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="e7427-105">如果您的组织具有其中的部分位于内部部署和一些在线承载的服务，组合，然后您的配置将取决于承载每个服务。</span><span class="sxs-lookup"><span data-stu-id="e7427-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="e7427-106">本主题介绍了与 Exchange online 承载的混合部署的 Skype 会议室系统 v2。</span><span class="sxs-lookup"><span data-stu-id="e7427-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="e7427-107">由于存在太多不同的变体在这种部署，不能提供的所有这些详细的说明。</span><span class="sxs-lookup"><span data-stu-id="e7427-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="e7427-108">以下过程将用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="e7427-108">The following process will work for many configurations.</span></span> <span data-ttu-id="e7427-109">如果过程不适合您的安装程序，我们建议您使用 Windows PowerShell 可以获得相同的最终结果记录在这里，以及其他部署选项的。</span><span class="sxs-lookup"><span data-stu-id="e7427-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="e7427-110">设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="e7427-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="e7427-111">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="e7427-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="e7427-112">如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="e7427-112">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="e7427-113">将 Skype 会议室系统 v2 与 Exchange Online 一起部署</span><span class="sxs-lookup"><span data-stu-id="e7427-113">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="e7427-114">部署与 Exchange Online 的 Skype 会议室系统 v2 之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="e7427-114">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="e7427-115">有关详细信息，请参阅 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7427-115">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="e7427-116">若要部署与 Exchange Online 的 Skype 会议室系统 v2，按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e7427-116">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="e7427-117">确保你有合适的权限来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7427-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="e7427-118">创建帐户并设置 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="e7427-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="e7427-119">在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7427-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="e7427-120">后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="e7427-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e7427-121">这将使到 Skype 会议室系统 v2 进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="e7427-121">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="e7427-122">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="e7427-122">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="e7427-123">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="e7427-123">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="e7427-124">为了改进的会议体验，您需要设置 Exchange 属性，如下所示的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e7427-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="e7427-125">你需要连接至 Azure AD 来应用一些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="e7427-125">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="e7427-126">你可以通过运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="e7427-126">You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="e7427-127">为你的本地域帐户添加电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="e7427-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="e7427-128">在**Active Directory 用户和计算机 AD**工具中，右键单击 Skype 会议室系统 v2 帐户将创建中，单击**新建**，然后单击**用户**的组织单位的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e7427-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="e7427-p107">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e7427-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="e7427-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="e7427-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7427-134">选择**密码永不过期**是在 Skype 会议室系统 v2 Skype 业务服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="e7427-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="e7427-135">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="e7427-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="e7427-136">如果是这样，您将需要针对每个 Skype 会议室系统 v2 用户帐户创建例外。</span><span class="sxs-lookup"><span data-stu-id="e7427-136">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="e7427-137">单击“**完成**”创建帐户。</span><span class="sxs-lookup"><span data-stu-id="e7427-137">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="e7427-p110">创建该帐户后，运行目录同步。完成后，转至用户页面并验证在上述步骤中创建的两个帐户是否已合并。</span><span class="sxs-lookup"><span data-stu-id="e7427-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="e7427-140">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="e7427-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="e7427-141">需要有有效的 Office 365 许可，以确保 Exchange 和 Skype 业务服务器将工作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e7427-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="e7427-142">如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="e7427-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="e7427-143">接下来，使用 Get-msolaccountsku 的 Office 365 租户中检索可用的 Sku 的列表。</span><span class="sxs-lookup"><span data-stu-id="e7427-143">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="e7427-p112">列出 SKU 后，便可使用 Set-MsolUserLicense cmdlet 来添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="e7427-p112">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="e7427-146">Skype 的用户帐户启用企业服务器</span><span class="sxs-lookup"><span data-stu-id="e7427-146">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="e7427-147">从 PC 创建远程 Windows PowerShell 会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7427-147">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="e7427-148">为业务服务器启用 Skype Skype 会议室系统 v2 帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e7427-148">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="e7427-149">如果不确定哪些值用于您的环境中的 RegistrarPool 参数，您可以从现有 Skype 企业服务器用户使用此命令获取值</span><span class="sxs-lookup"><span data-stu-id="e7427-149">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="e7427-150">将业务服务器许可证 Skype 分配给您的 Skype 会议室系统 v2 帐户</span><span class="sxs-lookup"><span data-stu-id="e7427-150">Assign a Skype for Business Server license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="e7427-151">以租户管理员身份登录，打开 Office 365 管理门户，并单击管理中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7427-151">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="e7427-152">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="e7427-152">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="e7427-153">单击 Skype 会议室系统 v2 帐户，，然后单击笔图标可编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="e7427-153">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="e7427-154">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="e7427-154">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="e7427-155">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="e7427-155">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="e7427-156">您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 企业语音。</span><span class="sxs-lookup"><span data-stu-id="e7427-156">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="e7427-157">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e7427-157">Click **Save**.</span></span>
    
<span data-ttu-id="e7427-158">进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="e7427-158">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7427-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7427-159">See also</span></span>

[<span data-ttu-id="e7427-160">配置帐户 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="e7427-160">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="e7427-161">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="e7427-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="e7427-162">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="e7427-162">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="e7427-163">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="e7427-163">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="e7427-164">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="e7427-164">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

