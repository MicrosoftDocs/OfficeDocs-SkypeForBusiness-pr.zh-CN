---
title: 将 Skype 会议室系统 v2 与本地 Exchange 一起部署（混合）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: 请阅读有关如何部署 Skype 的空间系统 v2 使用内部部署 Exchange 的混合环境中此主题。
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a><span data-ttu-id="9fc38-103">将 Skype 会议室系统 v2 与本地 Exchange 一起部署（混合）</span><span class="sxs-lookup"><span data-stu-id="9fc38-103">Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)</span></span>
 
<span data-ttu-id="9fc38-104">请阅读有关如何部署 Skype 的空间系统 v2 使用内部部署 Exchange 的混合环境中此主题。</span><span class="sxs-lookup"><span data-stu-id="9fc38-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises.</span></span>
  
<span data-ttu-id="9fc38-105">如果组织中有一些位于内部部署和联机寄宿某些服务，同时，然后您的配置将取决于每个服务所在。</span><span class="sxs-lookup"><span data-stu-id="9fc38-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="9fc38-106">本主题介绍与投放在内部部署的 Exchange Skype 的空间系统 v2 的混合部署。</span><span class="sxs-lookup"><span data-stu-id="9fc38-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="9fc38-107">由于有这么多的不同变体，这种类型的部署中，不可能提供有关它们的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="9fc38-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="9fc38-108">以下过程适用于多种不同的配置。</span><span class="sxs-lookup"><span data-stu-id="9fc38-108">The following process will work for many configurations.</span></span> <span data-ttu-id="9fc38-109">如果过程不适合于您的安装程序，我们建议使用 Windows PowerShell 来实现相同的最终结果，因为有文档记录，和其他部署选项。</span><span class="sxs-lookup"><span data-stu-id="9fc38-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="9fc38-110">然后应使用提供的 Windows PowerShell 脚本以验证您的 Skype 的空间系统 v2 安装。</span><span class="sxs-lookup"><span data-stu-id="9fc38-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="9fc38-111">（请参阅帐户验证脚本）。</span><span class="sxs-lookup"><span data-stu-id="9fc38-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="9fc38-112">将 Skype 会议室系统 v2 与本地 Exchange 一起部署</span><span class="sxs-lookup"><span data-stu-id="9fc38-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="9fc38-113">Skype 的空间系统 v2 与内部部署的 Exchange 部署之前，请确保已满足要求。</span><span class="sxs-lookup"><span data-stu-id="9fc38-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="9fc38-114">有关详细信息，请参阅[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fc38-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="9fc38-115">如果您正在部署 Skype 的空间系统 v2 与内部部署的 Exchange，您将使用 Active Directory 管理工具为您内部的域帐户添加电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9fc38-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="9fc38-116">此帐户将被同步到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9fc38-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="9fc38-117">你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9fc38-117">You will need to:</span></span>
  
- <span data-ttu-id="9fc38-118">创建一个帐户并将该帐户与 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="9fc38-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="9fc38-119">启用远程邮箱并设置属性。</span><span class="sxs-lookup"><span data-stu-id="9fc38-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="9fc38-120">分配一个 Office 365 提供许可证。</span><span class="sxs-lookup"><span data-stu-id="9fc38-120">Assign an Office 365 license.</span></span>
    
- <span data-ttu-id="9fc38-121">为业务服务器启用设备与 Skype 的帐户。</span><span class="sxs-lookup"><span data-stu-id="9fc38-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="9fc38-122">要启用设备帐户，你的环境需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="9fc38-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="9fc38-123">您需要在您的 Office 365 计划有 Skype 的在线业务 (计划 2) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9fc38-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="9fc38-124">该计划需要支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="9fc38-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="9fc38-125">如果您需要企业语音 （PSTN 电话服务） 对 Skype 的空间系统 v2 使用电话服务提供程序需要 Skype 业务联机 (计划 3)。</span><span class="sxs-lookup"><span data-stu-id="9fc38-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="9fc38-126">租户用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="9fc38-126">Your tenant users must have Exchange mailboxes.</span></span>
    
  - <span data-ttu-id="9fc38-127">Skype 的空间系统 v2 帐户需要 Skype 的在线业务 (计划 2) 或 Skype 的在线业务 (计划 3) 许可证，但它不需要 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="9fc38-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="9fc38-128">分配到 Skype 的空间系统 v2 帐户业务服务器许可证 Skype。</span><span class="sxs-lookup"><span data-stu-id="9fc38-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="9fc38-129">创建一个帐户并与 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="9fc38-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="9fc38-130">在**Active Directory 用户和计算机 AD**工具中，右键单击文件夹或 Skype 的空间系统 v2 将为其创建帐户，单击**新建**，然后单击**用户**的组织单位。</span><span class="sxs-lookup"><span data-stu-id="9fc38-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>
    
2. <span data-ttu-id="9fc38-p106">将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9fc38-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="9fc38-p107">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="9fc38-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9fc38-136">选择**密码永不过期**是 Skype 的空间系统 v2 为 Skype 业务服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="9fc38-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="9fc38-137">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="9fc38-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="9fc38-138">如果是这样，您需要针对每个 Skype 的空间系统 v2 设备帐户创建例外。</span><span class="sxs-lookup"><span data-stu-id="9fc38-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="9fc38-139">创建该帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="9fc38-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="9fc38-140">完成时，请转到 Office 365 管理中心用户页，并验证具有在线合并到前面的步骤中创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="9fc38-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="9fc38-141">启用远程邮箱并设置属性</span><span class="sxs-lookup"><span data-stu-id="9fc38-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="9fc38-142">通过使用管理员权限打开您内部 Exchange 管理外壳程序启用远程邮箱并运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="9fc38-142">Enable the remote mailbox by opening your on-premises Exchange management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="9fc38-143">启动远程 Windows PowerShell 会话，并连接到 Microsoft Exchange。</span><span class="sxs-lookup"><span data-stu-id="9fc38-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="9fc38-144">从您的 Office 365 租户，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9fc38-144">From your Office 365 tenant, run the following commands:</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. <span data-ttu-id="9fc38-145">为了提高会议的经验，需要对设备帐户设置 Exchange 属性如下：</span><span class="sxs-lookup"><span data-stu-id="9fc38-145">To improve the meeting experience, you'll need to set the Exchange properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="9fc38-146">您需要的属性有关的设置的详细信息，请参阅 Exchange 属性。</span><span class="sxs-lookup"><span data-stu-id="9fc38-146">For more information about which properties you need to set, see Exchange properties.</span></span>
    
4. <span data-ttu-id="9fc38-147">你需要连接至 Azure AD 来应用一些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="9fc38-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="9fc38-148">你可以通过运行此命令来连接：</span><span class="sxs-lookup"><span data-stu-id="9fc38-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="9fc38-149">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="9fc38-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="9fc38-150">设备的帐户需要有有效的 Office 365 许可证以确保 Exchange 和 Skype 业务服务器将起作用。</span><span class="sxs-lookup"><span data-stu-id="9fc38-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="9fc38-151">如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="9fc38-151">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="9fc38-152">接下来，使用 Get MsolAccountSku Office 365 租户为检索可用 Sku 列表。</span><span class="sxs-lookup"><span data-stu-id="9fc38-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="9fc38-p113">列出 SKU 后，便可使用 Set-MsolUserLicense cmdlet 来添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="9fc38-p113">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="9fc38-155">使用 Skype for Business 启用设备帐户</span><span class="sxs-lookup"><span data-stu-id="9fc38-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="9fc38-156">从一台电脑，如下所示创建远程 Windows PowerShell 会话：</span><span class="sxs-lookup"><span data-stu-id="9fc38-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="9fc38-157">若要启用业务服务器的 Skype Skype 的空间系统 v2 帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9fc38-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="9fc38-158">如果您不确定要用于您的环境中的 RegistrarPool 参数的值，您可以从现有业务服务器使用此命令的用户的 Skype 获得价值</span><span class="sxs-lookup"><span data-stu-id="9fc38-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="9fc38-159">向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business 许可证</span><span class="sxs-lookup"><span data-stu-id="9fc38-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="9fc38-160">租户管理员的身份登录，打开 Office 365 管理门户网站，然后单击管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="9fc38-160">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="9fc38-161">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="9fc38-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="9fc38-162">Skype 的空间系统 v2 帐户，单击，然后单击笔图标可编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="9fc38-162">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="9fc38-163">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9fc38-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="9fc38-164">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="9fc38-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="9fc38-165">您必须使用计划 3 许可证，如果您想要使用 Skype 的空间系统 v2 企业语音。</span><span class="sxs-lookup"><span data-stu-id="9fc38-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="9fc38-166">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="9fc38-166">Click **Save**.</span></span>
    
<span data-ttu-id="9fc38-167">进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="9fc38-167">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fc38-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fc38-168">See also</span></span>

#### 

[<span data-ttu-id="9fc38-169">Skype 的空间规划系统 v2</span><span class="sxs-lookup"><span data-stu-id="9fc38-169">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="9fc38-170">部署 Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="9fc38-170">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="9fc38-171">配置控制台，Skype 的空间系统 v2</span><span class="sxs-lookup"><span data-stu-id="9fc38-171">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="9fc38-172">Skype 的机房管理系统 v2</span><span class="sxs-lookup"><span data-stu-id="9fc38-172">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

