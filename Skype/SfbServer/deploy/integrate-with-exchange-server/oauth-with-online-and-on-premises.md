---
title: Skype for Business Online 和 Exchange server 之间的集成
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在 Exchange Online 和 Skype for business Online 之间配置 OAuth 身份验证可启用功能支持中所述的 Skype for Business 和 Exchange 集成功能。
ms.openlocfilehash: 35dc8777ddf5c7102e99d726f916f9b8f8bb4aae
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002892"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="13960-103">在 Skype for Business Online 和 Exchange Server 之间配置集成和 OAuth</span><span class="sxs-lookup"><span data-stu-id="13960-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="13960-104">配置 Exchange server 和 Skype for business Online 之间的集成可启用[功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的 Skype for Business 和 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="13960-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="13960-105">本主题适用于与 Exchange Server 2013 到2019的集成。</span><span class="sxs-lookup"><span data-stu-id="13960-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="13960-106">开始之前你需要了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="13960-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="13960-107">完成此任务的估计时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="13960-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="13960-108">在可以执行此过程或其他过程之前，你需要被分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="13960-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="13960-109">若要查看所需的权限，请参阅[Exchange 和 Shell 基础结构权限](https://go.microsoft.com/fwlink/p/?LinkId=746511)主题。</span><span class="sxs-lookup"><span data-stu-id="13960-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="13960-110">有关可适用于本主题中的过程的键盘快捷方式的信息，请参阅[Exchange 管理中心中的键盘快捷方式]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。</span><span class="sxs-lookup"><span data-stu-id="13960-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="13960-111">有关兼容性的信息，请参阅[Skype for business 与 Office 应用的兼容性](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)。</span><span class="sxs-lookup"><span data-stu-id="13960-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="13960-112">配置 Exchange Server 和 O365 之间的集成</span><span class="sxs-lookup"><span data-stu-id="13960-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="13960-113">步骤1：在 Exchange Server 和 O365 之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="13960-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="13960-114">执行以下文章中的步骤：</span><span class="sxs-lookup"><span data-stu-id="13960-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="13960-115">在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="13960-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="13960-116">步骤2：为 Skype for Business Online 合作伙伴应用程序创建新的邮件用户帐户</span><span class="sxs-lookup"><span data-stu-id="13960-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="13960-117">此步骤在 Exchange 服务器上执行。</span><span class="sxs-lookup"><span data-stu-id="13960-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="13960-118">它将创建一个邮件用户并为其分配合适的管理角色权限。</span><span class="sxs-lookup"><span data-stu-id="13960-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="13960-119">随后此用户将用于下一步骤。</span><span class="sxs-lookup"><span data-stu-id="13960-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="13960-120">为您的 Exchange 组织指定经验证的域。</span><span class="sxs-lookup"><span data-stu-id="13960-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="13960-121">此域应该是用作本地 Exchange 帐户使用的主 SMTP 域的相同域。</span><span class="sxs-lookup"><span data-stu-id="13960-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="13960-122">此域在以下过程\<中称为 "\>已验证域"。</span><span class="sxs-lookup"><span data-stu-id="13960-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="13960-123">此外， \<DomainControllerFQDN\>应该是域控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="13960-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="13960-124">此命令将在地址列表中隐藏新的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="13960-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="13960-125">接下来的两个命令将为这个新帐户分配 UserApplication 和 ArchiveApplication 管理角色。</span><span class="sxs-lookup"><span data-stu-id="13960-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="13960-126">步骤3：为 Skype for business Online 创建和启用合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="13960-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="13960-127">创建新的合作伙伴应用程序，并且将使用你刚刚创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="13960-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="13960-128">在您的本地 Exchange 组织中的 Exchange PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="13960-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="13960-129">步骤4：导出本地授权证书</span><span class="sxs-lookup"><span data-stu-id="13960-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="13960-130">运行 PowerShell 脚本以导出本地授权证书，您将在下一步将这些证书导入到您的 Skype for Business Online 组织。</span><span class="sxs-lookup"><span data-stu-id="13960-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="13960-131">请将以下文本保存到一个 PowerShell 脚本文件，例如名为 ExportAuthCert.ps1 的文件。</span><span class="sxs-lookup"><span data-stu-id="13960-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

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

<span data-ttu-id="13960-132">在 Exchange PowerShell 中的本地 Exchange 组织中，运行刚刚创建的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="13960-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="13960-133">例如： .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="13960-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="13960-134">步骤5：将本地授权证书上载到 Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="13960-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="13960-135">接下来，使用 Windows PowerShell 将你在上一步中导出的本地授权证书上载到 Azure Active Directory 访问控制服务 (ACS)。</span><span class="sxs-lookup"><span data-stu-id="13960-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="13960-136">要执行此操作，必须已经安装用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="13960-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="13960-137">如果未安装，请转到[https://aka.ms/aadposh](https://aka.ms/aadposh)安装适用于 Windows PowerShell 的 Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="13960-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="13960-138">在安装用于 Windows PowerShell 的 Azure Active Directory 模块之后，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="13960-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="13960-p107">单击**用于 Windows PowerShell 的 Azure Active Directory 模块**快捷方式以打开安装了 Azure AD cmdlet 的 Windows PowerShell 工作区。此步骤中的所有命令都将使用 Windows PowerShell for Azure Active Directory 控制台运行。</span><span class="sxs-lookup"><span data-stu-id="13960-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="13960-141">将以下文本保存到一个名为的 PowerShell 脚本文件中， `UploadAuthCert.ps1`例如。</span><span class="sxs-lookup"><span data-stu-id="13960-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

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

3. <span data-ttu-id="13960-142">运行你在上一步中创建的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="13960-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="13960-143">例如：`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="13960-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="13960-p109">在启动脚本之后，将显示凭据对话框。请输入你的 Microsoft Online Azure AD 组织的租户管理员帐户的凭据。在运行脚本之后，请将 Windows PowerShell for Azure AD 会话保持打开。你将使用此会话来在下一步中运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="13960-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="13960-148">步骤6：验证证书是否已上载到 Skype for Business 服务主体</span><span class="sxs-lookup"><span data-stu-id="13960-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="13960-149">在已打开并验证到 Azure Active Directory 的 PowerShell 中，运行以下</span><span class="sxs-lookup"><span data-stu-id="13960-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="13960-150">出现提示时按 Enter ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="13960-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="13960-151">确认看到列出了与 Exchange Oauth 证书开始和结束日期相匹配的 "开始日期" 和 "结束数据" 的键</span><span class="sxs-lookup"><span data-stu-id="13960-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="13960-152">验证是否成功</span><span class="sxs-lookup"><span data-stu-id="13960-152">Verify your success</span></span>

<span data-ttu-id="13960-153">通过验证某些功能是否已成功运行，验证配置是否正确。</span><span class="sxs-lookup"><span data-stu-id="13960-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="13960-154">在具有混合 Exchange 服务器配置的组织中确认使用云语音邮件服务的 Skype for Business 用户可以成功更改其语音邮件问候语。</span><span class="sxs-lookup"><span data-stu-id="13960-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="13960-155">确认移动客户的对话历史记录在 "Outlook 对话历史记录" 文件夹中可见。</span><span class="sxs-lookup"><span data-stu-id="13960-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="13960-156">使用[EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)确认在 "清除" 文件夹中将已存档的聊天消息保存到用户的本地邮箱中。</span><span class="sxs-lookup"><span data-stu-id="13960-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="13960-157">或者，查看您的流量。</span><span class="sxs-lookup"><span data-stu-id="13960-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="13960-158">OAuth 握手中的流量非常特殊（并且看起来不像基本身份验证），特别是在领域内，你将在其中开始查看颁发者流量，如下所示： 00000004-0000-0ff1-ce00-000000000000 @ （有时带有 @ 符号的一个/之前），位于要传递的令牌中。</span><span class="sxs-lookup"><span data-stu-id="13960-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="13960-159">您将看不到用户名或密码，这是 OAuth 的点。</span><span class="sxs-lookup"><span data-stu-id="13960-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="13960-160">但是，你将看到 "Office" 颁发者-在本例中，"4" 是 Skype for Business-以及你的订阅领域。</span><span class="sxs-lookup"><span data-stu-id="13960-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="13960-161">如果你想要确保你成功使用了 OAuth，请确定你知道所需的内容，并了解流量应类似的内容。</span><span class="sxs-lookup"><span data-stu-id="13960-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="13960-162">因此[，下面是](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34) [Microsoft 应用程序中的 OAuth 流量](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)的非常标准示例（虽然它不使用刷新令牌，但仍很有帮助，虽然它不使用刷新令牌），并且将允许你查看 OAuth JWT （JSON Web 令牌）的 Fiddler 扩展。</span><span class="sxs-lookup"><span data-stu-id="13960-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="13960-163">下面是[一个设置的示例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)，但你可以使用任何你喜欢的网络跟踪工具来执行此过程。</span><span class="sxs-lookup"><span data-stu-id="13960-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="13960-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="13960-164">Related topics</span></span>

[<span data-ttu-id="13960-165">在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="13960-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
