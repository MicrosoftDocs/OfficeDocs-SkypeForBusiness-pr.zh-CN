---
title: Skype for Business Online 和 Exchange 服务器之间的集成
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在本地 Exchange 和 Skype for Business Online 之间配置 OAuth 身份验证可启用功能支持中所述的 Skype for Business 和 Exchange 集成功能。
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833972"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="5e644-103">配置 Skype for Business Online 和 Skype for Business Online 之间的集成和 OAuth Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5e644-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="5e644-104">配置 Exchange 服务器与 Skype for Business Online 之间的集成支持功能支持中所述的 Skype for Business 和 Exchange [集成功能](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="5e644-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="5e644-105">本主题适用于与 2013 Exchange Server 2019 年集成。</span><span class="sxs-lookup"><span data-stu-id="5e644-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5e644-106">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="5e644-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5e644-107">估计完成该任务的时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="5e644-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="5e644-108">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="5e644-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="5e644-109">若要了解所需的权限，请参阅 [Exchange 和命令行管理程序基础结构权限](https://go.microsoft.com/fwlink/p/?LinkId=746511) 主题。</span><span class="sxs-lookup"><span data-stu-id="5e644-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="5e644-110">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 [Exchange 管理中心内的键盘快捷键]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。</span><span class="sxs-lookup"><span data-stu-id="5e644-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="5e644-111">有关兼容性的信息，请参阅 [Skype for Business 与 Office 应用的兼容性](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)。</span><span class="sxs-lookup"><span data-stu-id="5e644-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="5e644-112">配置 Exchange Server 和 O365 之间的集成</span><span class="sxs-lookup"><span data-stu-id="5e644-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="5e644-113">步骤 1：在 Exchange Server 和 O365 之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="5e644-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="5e644-114">执行以下文章中的步骤：</span><span class="sxs-lookup"><span data-stu-id="5e644-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="5e644-115">在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="5e644-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="5e644-116">步骤 2：为 Skype for Business Online 合作伙伴应用程序创建新的邮件用户帐户</span><span class="sxs-lookup"><span data-stu-id="5e644-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="5e644-117">此步骤在 Exchange 服务器上完成。</span><span class="sxs-lookup"><span data-stu-id="5e644-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="5e644-118">它将创建一个邮件用户，并为其分配适当的管理角色权限。</span><span class="sxs-lookup"><span data-stu-id="5e644-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="5e644-119">此帐户将在下一步中使用。</span><span class="sxs-lookup"><span data-stu-id="5e644-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="5e644-120">为 Exchange 组织指定验证域。</span><span class="sxs-lookup"><span data-stu-id="5e644-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="5e644-121">此域应是用作本地 Exchange 帐户的主 SMTP 域的同一个域。</span><span class="sxs-lookup"><span data-stu-id="5e644-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="5e644-122">以下过程中将 \<your Verified Domain\> 引用此域。</span><span class="sxs-lookup"><span data-stu-id="5e644-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="5e644-123">此外， \<DomainControllerFQDN\> 这应该是域控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5e644-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="5e644-124">此命令将在地址列表中隐藏新邮件用户。</span><span class="sxs-lookup"><span data-stu-id="5e644-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="5e644-125">接下来的两个命令将 UserApplication 和 ArchiveApplication 管理角色分配给此新帐户。</span><span class="sxs-lookup"><span data-stu-id="5e644-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="5e644-126">步骤 3：为 Skype for Business Online 创建和启用合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="5e644-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="5e644-127">创建新的合作伙伴应用程序，并使用刚创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="5e644-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="5e644-128">在本地 Exchange 组织的 Exchange PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="5e644-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="5e644-129">步骤 4：导出本地授权证书</span><span class="sxs-lookup"><span data-stu-id="5e644-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="5e644-130">运行 PowerShell 脚本以导出本地授权证书，你将在下一步中将其导入 Skype for Business Online 组织。</span><span class="sxs-lookup"><span data-stu-id="5e644-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="5e644-131">将以下文本保存到名为 ExportAuthCert.ps1（示例名称）的 PowerShell 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="5e644-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="5e644-132">在本地 Exchange 组织的 Exchange PowerShell 中，运行刚创建的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="5e644-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="5e644-133">例如：.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="5e644-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="5e644-134">步骤 5：将本地授权证书上载到 Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="5e644-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="5e644-135">接下来，Windows PowerShell将上一步中导出的本地授权证书上载到 ACS (Azure Active Directory 访问控制服务) 。</span><span class="sxs-lookup"><span data-stu-id="5e644-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="5e644-136">为此，必须已安装用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="5e644-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="5e644-137">如果尚未安装，请转到 [https://aka.ms/aadposh](https://aka.ms/aadposh) 安装 用于 Windows PowerShell 的 Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="5e644-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="5e644-138">安装 用于 Windows PowerShell 的 Azure Active Directory 模块 后，完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="5e644-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="5e644-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span><span class="sxs-lookup"><span data-stu-id="5e644-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="5e644-141">将以下文本保存到 PowerShell 脚本文件中，例如，  `UploadAuthCert.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="5e644-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="5e644-142">运行您在上一步骤中创建的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="5e644-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="5e644-143">例如：  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="5e644-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="5e644-144">启动脚本后，您会看到凭据对话框。</span><span class="sxs-lookup"><span data-stu-id="5e644-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="5e644-145">输入 Microsoft Online Azure AD 组织的租户管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="5e644-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="5e644-146">运行脚本后，让 Azure AD 会话的 Windows PowerShell 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="5e644-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="5e644-147">您将在下一步骤中使用此程序运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="5e644-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="5e644-148">步骤 6：验证证书已上载到 Skype for Business 服务主体</span><span class="sxs-lookup"><span data-stu-id="5e644-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="5e644-149">在打开并经过 Azure Active Directory 身份验证的 PowerShell 中，运行以下代码</span><span class="sxs-lookup"><span data-stu-id="5e644-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="5e644-150">当系统提示输入 ReturnKeyValues 时按 Enter</span><span class="sxs-lookup"><span data-stu-id="5e644-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="5e644-151">确认您看到列出了与 Exchange Oauth 证书开始日期和结束日期相匹配的开始日期和结束数据的密钥</span><span class="sxs-lookup"><span data-stu-id="5e644-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="5e644-152">验证是否成功</span><span class="sxs-lookup"><span data-stu-id="5e644-152">Verify your success</span></span>

<span data-ttu-id="5e644-153">通过验证某些功能是否正常工作来验证配置是否正确。</span><span class="sxs-lookup"><span data-stu-id="5e644-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="5e644-154">确认具有云语音邮件服务的 Skype for Business 用户（在具有混合语音Exchange Server配置的组织）可以成功更改其语音邮件问候语。</span><span class="sxs-lookup"><span data-stu-id="5e644-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="5e644-155">确认移动客户端的对话历史记录在 Outlook 对话历史记录文件夹中可见。</span><span class="sxs-lookup"><span data-stu-id="5e644-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="5e644-156">使用 [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)确认存档的聊天消息将存储在用户本地邮箱的"清除"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5e644-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="5e644-157">或者，查看流量。</span><span class="sxs-lookup"><span data-stu-id="5e644-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="5e644-158">OAuth 握手中的流量非常独特， (基本身份验证模式) 。 尤其是在领域方面，你将开始看到如下所示的颁发者流量：000000004-0000-0ff1-ce00-000000000000@ (有时在 @ 符号) 之前，在正在传递的令牌中显示 a/。</span><span class="sxs-lookup"><span data-stu-id="5e644-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="5e644-159">你将看不到用户名或密码，这是 OAuth 的要点。</span><span class="sxs-lookup"><span data-stu-id="5e644-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="5e644-160">但是，你将看到"Office"颁发者（本例中为"4"为 Skype for Business）以及你的订阅领域。</span><span class="sxs-lookup"><span data-stu-id="5e644-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="5e644-161">如果希望确保成功使用 OAuth，请确保了解预期结果，并知道流量应该是什么样。</span><span class="sxs-lookup"><span data-stu-id="5e644-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="5e644-162">因此[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)，下面是 Microsoft 应用程序 (中 OAuth 流量的一个相当标准的标准示例，虽然它不使用刷新令牌) ，但此处是一个非常标准的[OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)流量示例，有一些 Fiddler 扩展，可让你查看 OAuth JWT (JSON Web 令牌) 。</span><span class="sxs-lookup"><span data-stu-id="5e644-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="5e644-163">下面是 [设置一个](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)网络跟踪工具的示例，但您可以使用任何要执行此过程的网络跟踪工具。</span><span class="sxs-lookup"><span data-stu-id="5e644-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5e644-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="5e644-164">Related topics</span></span>

[<span data-ttu-id="5e644-165">在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="5e644-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
