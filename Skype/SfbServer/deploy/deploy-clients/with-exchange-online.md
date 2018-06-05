---
title: 将 Skype 会议室系统 v2 与 Exchange Online 一起部署（混合）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读此主题以获取如何部署与 Exchange Online 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 210f01f4d016ee0d3855edc79f20e2adceaa4f18
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568875"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a><span data-ttu-id="2457f-103">将 Skype 会议室系统 v2 与 Exchange Online 一起部署（混合）</span><span class="sxs-lookup"><span data-stu-id="2457f-103">Deploy Skype Room Systems v2 with Exchange Online (Hybrid)</span></span>
 
<span data-ttu-id="2457f-104">阅读此主题以获取如何部署与 Exchange Online 的 Skype 会议室系统 v2 的信息。</span><span class="sxs-lookup"><span data-stu-id="2457f-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online.</span></span>
  
<span data-ttu-id="2457f-105">如果您的组织具有其中的部分位于内部部署和一些在线承载的服务，组合，然后您的配置将取决于承载每个服务。</span><span class="sxs-lookup"><span data-stu-id="2457f-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="2457f-106">本主题介绍了与 Exchange online 承载的混合部署的 Skype 会议室系统 v2。</span><span class="sxs-lookup"><span data-stu-id="2457f-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="2457f-107">由于存在太多不同的变体在这种部署，不能提供的所有这些详细的说明。</span><span class="sxs-lookup"><span data-stu-id="2457f-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="2457f-108">以下过程将用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="2457f-108">The following process will work for many configurations.</span></span> <span data-ttu-id="2457f-109">如果过程不适合您的安装程序，我们建议您使用 Windows PowerShell (请参阅附录： PowerShell) 可以记录在这里，以及其他部署选项的获得相同的最终结果。</span><span class="sxs-lookup"><span data-stu-id="2457f-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell (see Appendix: PowerShell) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="2457f-110">然后您应使用提供的 Windows PowerShell 脚本验证 Skype 会议室系统 v2 安装程序。</span><span class="sxs-lookup"><span data-stu-id="2457f-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="2457f-111">（请参阅帐户验证脚本）。</span><span class="sxs-lookup"><span data-stu-id="2457f-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="2457f-112">将 Skype 会议室系统 v2 与 Exchange Online 一起部署</span><span class="sxs-lookup"><span data-stu-id="2457f-112">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="2457f-113">部署与 Exchange Online 的 Skype 会议室系统 v2 之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="2457f-113">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="2457f-114">有关详细信息，请参阅[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2457f-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="2457f-115">若要部署与 Exchange Online 的 Skype 会议室系统 v2，按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2457f-115">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="2457f-116">确保你有合适的权限来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2457f-116">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="2457f-117">创建帐户并设置 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="2457f-117">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="2457f-118">在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2457f-118">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="2457f-119">后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="2457f-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="2457f-120">这将使到 Skype 会议室系统 v2 进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="2457f-120">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="2457f-121">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="2457f-121">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="2457f-122">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="2457f-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="2457f-123">为了改进的会议体验，您需要设置 Exchange 属性，如下所示的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="2457f-123">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="2457f-p105">你需要连接至 Azure AD 来应用一些帐户设置。你可以通过运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="2457f-p105">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="2457f-126">为你的本地域帐户添加电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="2457f-126">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="2457f-127">在**Active Directory 用户和计算机 AD**工具中，右键单击 Skype 会议室系统 v2 帐户将创建中，单击**新建**，然后单击**用户**的组织单位的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2457f-127">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="2457f-p106">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2457f-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="2457f-p107">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="2457f-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2457f-133">选择**密码永不过期**是 Skype 会议室系统 v2 上的业务服务器 2015 Skype 的要求。</span><span class="sxs-lookup"><span data-stu-id="2457f-133">Selecting **Password never expires** is a requirement for Skype for Business Server 2015 on Skype Room Systems v2.</span></span> <span data-ttu-id="2457f-134">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="2457f-134">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="2457f-135">如果是这样，您将需要针对每个 Skype 会议室系统 v2 用户帐户创建例外。</span><span class="sxs-lookup"><span data-stu-id="2457f-135">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="2457f-136">单击“**完成**”创建帐户。</span><span class="sxs-lookup"><span data-stu-id="2457f-136">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="2457f-p109">创建该帐户后，运行目录同步。完成后，转至用户页面并验证在上述步骤中创建的两个帐户是否已合并。</span><span class="sxs-lookup"><span data-stu-id="2457f-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="2457f-139">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="2457f-139">Assign an Office 365 license</span></span>

1. <span data-ttu-id="2457f-140">需要有有效的 Office 365 许可，以确保 Exchange 和 Skype 的业务服务器 2015年将工作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2457f-140">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server 2015 will work.</span></span> <span data-ttu-id="2457f-141">如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="2457f-141">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="2457f-142">接下来，使用 Get-msolaccountsku 的 Office 365 租户中检索可用的 Sku 的列表。</span><span class="sxs-lookup"><span data-stu-id="2457f-142">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="2457f-p111">列出 SKU 后，便可使用 Set-MsolUserLicense cmdlet 来添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="2457f-p111">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a><span data-ttu-id="2457f-145">使用 Skype for Business Server 2015 启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="2457f-145">Enable the user account with Skype for Business Server 2015</span></span>

1. <span data-ttu-id="2457f-146">从 PC 创建远程 Windows PowerShell 会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2457f-146">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="2457f-147">若要启用业务服务器 2015 Skype 的 Skype 会议室系统 v2 帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2457f-147">To enable your Skype Room Systems v2 account for Skype for Business Server 2015, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="2457f-148">如果不确定哪些值用于您的环境中的 RegistrarPool 参数，您可以从现有 Skype 业务服务器 2015年用户使用此命令获取值</span><span class="sxs-lookup"><span data-stu-id="2457f-148">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server 2015 user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="2457f-149">向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business Server 2015 许可证</span><span class="sxs-lookup"><span data-stu-id="2457f-149">Assign a Skype for Business Server 2015 license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="2457f-150">以租户管理员身份登录，打开 Office 365 管理门户，并单击管理中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="2457f-150">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="2457f-151">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="2457f-151">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="2457f-152">单击 Skype 会议室系统 v2 帐户，，然后单击笔图标可编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="2457f-152">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="2457f-153">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="2457f-153">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="2457f-154">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="2457f-154">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="2457f-155">您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 企业语音。</span><span class="sxs-lookup"><span data-stu-id="2457f-155">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="2457f-156">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2457f-156">Click **Save**.</span></span>
    
<span data-ttu-id="2457f-157">进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="2457f-157">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2457f-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2457f-158">See also</span></span>

#### 

[<span data-ttu-id="2457f-159">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="2457f-159">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="2457f-160">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="2457f-160">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="2457f-161">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="2457f-161">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="2457f-162">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="2457f-162">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

