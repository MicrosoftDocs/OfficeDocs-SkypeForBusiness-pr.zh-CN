---
title: 部署 Microsoft 团队聊天室与 Exchange Online
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读此主题以获取如何部署与 Exchange Online 的 Microsoft 团队聊天室的信息。
ms.openlocfilehash: 4bff1fb6adce254608aa9286ec080cf6677c1a48
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214826"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="8b3bc-103">部署 Microsoft 团队聊天室与 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b3bc-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="8b3bc-104">阅读本主题有关如何部署与 Exchange Online 和 Skype 业务服务器本地的 Microsoft 团队聊天室的信息。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="8b3bc-105">如果您的组织具有其中的部分位于内部部署和一些在线承载的服务，组合，然后您的配置将取决于承载每个服务。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="8b3bc-106">本主题介绍了与 Exchange online 承载的 Microsoft 团队聊天室的混合部署。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="8b3bc-107">由于存在太多不同的变体在这种部署，不能提供的所有这些详细的说明。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="8b3bc-108">以下过程将用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-108">The following process will work for many configurations.</span></span> <span data-ttu-id="8b3bc-109">如果过程不适合您的安装程序，我们建议您使用 Windows PowerShell 可以获得相同的最终结果记录在这里，以及其他部署选项的。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="8b3bc-110">设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="8b3bc-111">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Microsoft 团队聊天室用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="8b3bc-112">如果您愿意，您可以按照以下步骤来配置您的 Microsoft 团队聊天室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b3bc-113">要求</span><span class="sxs-lookup"><span data-stu-id="8b3bc-113">Requirements</span></span>

<span data-ttu-id="8b3bc-114">部署与 Exchange Online 的 Microsoft 团队聊天室之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="8b3bc-115">有关详细信息，请参阅[Microsoft 团队聊天室要求](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-115">For more information, see [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="8b3bc-116">若要部署与 Exchange Online 的 Microsoft 团队聊天室，请按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="8b3bc-117">确保你有合适的权限来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="8b3bc-118">创建帐户并设置 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="8b3bc-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="8b3bc-119">在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b3bc-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="8b3bc-120">后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="8b3bc-121">这将使到 Microsoft 团队聊天室进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="8b3bc-122">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="8b3bc-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="8b3bc-123">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="8b3bc-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="8b3bc-124">为了改进的会议体验，您需要设置 Exchange 属性，如下所示的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="8b3bc-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="8b3bc-125">为你的本地域帐户添加电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="8b3bc-125">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="8b3bc-126">在**Active Directory 用户和计算机 AD**工具中，右键单击容器或组织单位中，将在创建帐户您 Microsoft 团队聊天室单击**新建**，然后单击**用户**。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-126">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="8b3bc-127">键入显示名称 (-Identity) 从**全名**框中，和到**用户登录名**框中的别名 （Set-mailbox 或 New-mailbox） 早期 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-127">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="8b3bc-128">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-128">Click **Next**.</span></span>
3. <span data-ttu-id="8b3bc-p107">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b3bc-132">选择**密码永不过期**是 Skype 的 Microsoft 团队聊天室业务服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-132">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="8b3bc-133">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-133">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="8b3bc-134">如果是这样，您需要创建一个例外的 Microsoft 团队聊天室的每个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-134">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="8b3bc-135">单击“**完成**”创建帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-135">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="8b3bc-p109">创建该帐户后，运行目录同步。完成后，转至用户页面并验证在上述步骤中创建的两个帐户是否已合并。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="8b3bc-138">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="8b3bc-138">Assign an Office 365 license</span></span>

1. <span data-ttu-id="8b3bc-139">首先，连接到 Azure AD 应用某些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-139">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="8b3bc-140">你可以通过运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-140">You can run this cmdlet to connect.</span></span>

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="8b3bc-141">需要有有效的 Office 365 许可，以确保 Exchange 和 Skype 业务服务器将工作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="8b3bc-142">如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="8b3bc-143">您将在下面的步骤中进行工作分配。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-143">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="8b3bc-144">接下来，使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="8b3bc-144">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="8b3bc-145">Office 365 租户中检索可用的 Sku 的列表。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-145">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="8b3bc-146">一旦您列出出 Sku，还可以添加许可证使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="8b3bc-146">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="8b3bc-147">cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-147">cmdlet.</span></span> <span data-ttu-id="8b3bc-148">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-148">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="8b3bc-149">Skype 的用户帐户启用企业服务器</span><span class="sxs-lookup"><span data-stu-id="8b3bc-149">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="8b3bc-150">从 PC 创建远程 Windows PowerShell 会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b3bc-150">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="8b3bc-151">为业务 Server 启用的 Skype 的 Microsoft 团队会议室帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8b3bc-151">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="8b3bc-152">如果不确定哪些值用于您的环境中的 RegistrarPool 参数，您可以从现有 Skype 企业服务器用户使用此命令获取值</span><span class="sxs-lookup"><span data-stu-id="8b3bc-152">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="8b3bc-153">将业务服务器许可证 Skype 分配给您的 Microsoft 团队会议室帐户</span><span class="sxs-lookup"><span data-stu-id="8b3bc-153">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="8b3bc-154">以租户管理员身份登录，打开 Office 365 管理门户，并单击管理中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-154">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="8b3bc-155">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-155">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="8b3bc-156">单击 Microsoft 团队会议室帐户中，然后单击笔图标可编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-156">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="8b3bc-157">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-157">Click **Licenses**.</span></span>
5. <span data-ttu-id="8b3bc-158">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-158">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="8b3bc-159">您将需要使用规划 3 许可证，如果您想要使用 Microsoft 团队聊天室企业语音。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-159">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="8b3bc-160">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-160">Click **Save**.</span></span>

<span data-ttu-id="8b3bc-161">进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="8b3bc-161">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b3bc-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b3bc-162">See also</span></span>

[<span data-ttu-id="8b3bc-163">为 Microsoft 团队房间配置帐户</span><span class="sxs-lookup"><span data-stu-id="8b3bc-163">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="8b3bc-164">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="8b3bc-164">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="8b3bc-165">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="8b3bc-165">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="8b3bc-166">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="8b3bc-166">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="8b3bc-167">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="8b3bc-167">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
