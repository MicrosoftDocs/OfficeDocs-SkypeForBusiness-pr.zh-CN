---
title: 在 Skype for Business Online 和 Exchange 本地之间配置 OAuth
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 配置 OAuth 业务 online 本地 Exchange 和 Skype 之间的身份验证使 Skype 功能支持中所述的业务和 Exchange 集成功能。
ms.openlocfilehash: ff7b45f3fcdbaaf752817d1705acb047a4c71f12
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568899"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="f98d9-103">在 Skype for Business Online 和 Exchange 本地之间配置 OAuth</span><span class="sxs-lookup"><span data-stu-id="f98d9-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>
 
<span data-ttu-id="f98d9-104">配置 OAuth 业务 online 本地 Exchange 和 Skype 之间的身份验证使 Skype[功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的业务和 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="f98d9-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>
  
<span data-ttu-id="f98d9-105">本主题适用于 Exchange Server 2016 和 Exchange Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f98d9-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f98d9-106">开始之前你需要了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="f98d9-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f98d9-107">完成此任务的估计时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="f98d9-107">Estimated time to complete this task: 15 minutes</span></span>
    
-  <span data-ttu-id="f98d9-108">在可以执行此过程或其他过程之前，你需要被分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="f98d9-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="f98d9-109">若要查看所需的权限，请参阅[and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511)主题。</span><span class="sxs-lookup"><span data-stu-id="f98d9-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>
    
- <span data-ttu-id="f98d9-110">有关可能适用于此主题中的过程的键盘快捷方式的信息，请参阅[Exchange 管理中心中的键盘快捷方式]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。</span><span class="sxs-lookup"><span data-stu-id="f98d9-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="f98d9-111">在本地 Exchange 和 Skype for Business 组织之间配置 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="f98d9-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="f98d9-112">步骤 1：为你的 Skype for Business Online 组织创建授权服务器对象</span><span class="sxs-lookup"><span data-stu-id="f98d9-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="f98d9-113">指定您的业务 Online 组织的 Skype 已验证的域。</span><span class="sxs-lookup"><span data-stu-id="f98d9-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="f98d9-114">此域应是用作基于云的帐户的主要 SIP 域的相同域。</span><span class="sxs-lookup"><span data-stu-id="f98d9-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="f98d9-115">此域称作\<验证域\>在下面的过程。</span><span class="sxs-lookup"><span data-stu-id="f98d9-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>
  
<span data-ttu-id="f98d9-116">运行以下命令在 Exchange Management Shell (Exchange PowerShell) 中您的内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="f98d9-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="f98d9-117">步骤 2：为你的 Skype for Business Online 组织启用合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="f98d9-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="f98d9-118">运行以下命令在 Exchange PowerShell 中，在您的内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="f98d9-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="f98d9-119">步骤 3：为 Skype for Business Online 合作伙伴应用程序创建新的邮件用户帐户</span><span class="sxs-lookup"><span data-stu-id="f98d9-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="f98d9-p103">此步骤在本地执行。它将创建一个邮件用户并为其分配合适的管理角色权限。随后此用户将用于下一步骤。</span><span class="sxs-lookup"><span data-stu-id="f98d9-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>
  
<span data-ttu-id="f98d9-123">指定为 Exchange 组织已验证的域。</span><span class="sxs-lookup"><span data-stu-id="f98d9-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="f98d9-124">此域应为同一个域用作用于内部部署 Exchange 帐户的主 SMTP 域。</span><span class="sxs-lookup"><span data-stu-id="f98d9-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="f98d9-125">此域称作\<验证域\>在下面的过程。</span><span class="sxs-lookup"><span data-stu-id="f98d9-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="f98d9-126">此外， \<DomainControllerFQDN\>应域控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f98d9-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span> 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

<span data-ttu-id="f98d9-127">此命令将在地址列表中隐藏新的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="f98d9-127">This command will hide the new mail user from address lists.</span></span>
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

<span data-ttu-id="f98d9-128">接下来的两个命令将为这个新帐户分配 UserApplication 和 ArchiveApplication 管理角色。</span><span class="sxs-lookup"><span data-stu-id="f98d9-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="f98d9-129">步骤 4：为 Skype for Business Online 创建和启用合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="f98d9-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="f98d9-130">创建新的合作伙伴应用程序，并且将使用你刚刚创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="f98d9-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="f98d9-131">运行以下命令在 Exchange PowerShell 中，在您的内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="f98d9-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span> 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="f98d9-132">步骤 5：导出本地授权证书</span><span class="sxs-lookup"><span data-stu-id="f98d9-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="f98d9-133">运行可导出本地授权证书，您将导入到下一步中的业务 Online 组织您 Skype 的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f98d9-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>
  
<span data-ttu-id="f98d9-134">请将以下文本保存到一个 PowerShell 脚本文件，例如名为 ExportAuthCert.ps1 的文件。</span><span class="sxs-lookup"><span data-stu-id="f98d9-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>
  
```
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

<span data-ttu-id="f98d9-135">在 Exchange 内部部署 Exchange 组织中的 PowerShell 运行您刚创建的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f98d9-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="f98d9-136">例如：.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="f98d9-136">For example: .\ExportAuthCert.ps1</span></span>
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="f98d9-137">步骤 6：将本地授权证书上载到 Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="f98d9-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="f98d9-138">接下来，使用 Windows PowerShell 将你在上一步中导出的本地授权证书上载到 Azure Active Directory 访问控制服务 (ACS)。</span><span class="sxs-lookup"><span data-stu-id="f98d9-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="f98d9-139">要执行此操作，必须已经安装用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="f98d9-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="f98d9-140">如果未安装，请转到[https://aka.ms/aadposh](https://aka.ms/aadposh)来安装 Azure Active Directory 的 Windows PowerShell 的模块。</span><span class="sxs-lookup"><span data-stu-id="f98d9-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="f98d9-141">在安装用于 Windows PowerShell 的 Azure Active Directory 模块之后，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f98d9-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>
  
1. <span data-ttu-id="f98d9-p108">单击**用于 Windows PowerShell 的 Azure Active Directory 模块**快捷方式以打开安装了 Azure AD cmdlet 的 Windows PowerShell 工作区。此步骤中的所有命令都将使用 Windows PowerShell for Azure Active Directory 控制台运行。</span><span class="sxs-lookup"><span data-stu-id="f98d9-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>
    
2. <span data-ttu-id="f98d9-144">例如，将以下文本保存到名为的 PowerShell 脚本文件`UploadAuthCert.ps1`。</span><span class="sxs-lookup"><span data-stu-id="f98d9-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>
    
  ```
  Connect-MsolService; 
Import-Module msonlineextended; 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
$objFSO = New-Object -ComObject Scripting.FileSystemObject; 
$CertFile = $objFSO.GetAbsolutePathName($CertFile); 
$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate 
$cer.Import($CertFile); 
$binCert = $cer.GetRawCertData(); 
$credValue = [System.Convert]::ToBase64String($binCert); 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName 
New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue 
  ```

3. <span data-ttu-id="f98d9-145">运行你在上一步中创建的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f98d9-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="f98d9-146">例如：`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="f98d9-146">For example:  `.\UploadAuthCert.ps1`</span></span>
    
4. <span data-ttu-id="f98d9-p110">在启动脚本之后，将显示凭据对话框。请输入你的 Microsoft Online Azure AD 组织的租户管理员帐户的凭据。在运行脚本之后，请将 Windows PowerShell for Azure AD 会话保持打开。你将使用此会话来在下一步中运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f98d9-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="f98d9-151">步骤 7：为 SMTP 域注册主机名颁发机构</span><span class="sxs-lookup"><span data-stu-id="f98d9-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="f98d9-152">指定为 Exchange 组织已验证的域。</span><span class="sxs-lookup"><span data-stu-id="f98d9-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="f98d9-153">此域应为同一个域用作用于内部部署 Exchange 帐户的主 SMTP 域。</span><span class="sxs-lookup"><span data-stu-id="f98d9-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="f98d9-154">此域称作\<验证域\>在下面的过程。</span><span class="sxs-lookup"><span data-stu-id="f98d9-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f98d9-155">要成功运行以下脚本，需要按照上一节的步骤 4 中的说明将“用于 Azure Active Directory 的 Windows PowerShell”连接到 Microsoft Online Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="f98d9-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span> 
  
1. <span data-ttu-id="f98d9-156">将以下文本保存到一个 PowerShell 脚本文件中，例如将脚本文件命名为 RegisterEndpoints.ps1。</span><span class="sxs-lookup"><span data-stu-id="f98d9-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="f98d9-157">此示例使用通配符注册 contoso.com 的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="f98d9-157">This example uses a wildcard to register all endpoints for contoso.com.</span></span> <span data-ttu-id="f98d9-158">Contoso.com 替换为内部部署 Exchange 组织的主机名颁发机构</span><span class="sxs-lookup"><span data-stu-id="f98d9-158">Replace contoso.com with a hostname authority for your on-premises Exchange organization</span></span>
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  <span data-ttu-id="f98d9-159">在用于 Azure Active Directory 的 Windows PowerShell 中，运行在上一步骤中创建的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f98d9-159">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="f98d9-160">例如：`.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="f98d9-160">For example: `.\RegisterEndpoints.ps1`</span></span>
    
### <a name="verify-your-success"></a><span data-ttu-id="f98d9-161">验证是否成功</span><span class="sxs-lookup"><span data-stu-id="f98d9-161">Verify your success</span></span>

<span data-ttu-id="f98d9-162">通过验证某些功能是否正常工作来验证 OAuth 配置的正确性，例如，让移动客户端的对话历史记录出现在 Outlook “对话历史记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f98d9-162">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>
  
1. <span data-ttu-id="f98d9-163">在 Windows Phone 或 iOS 设备上启动业务移动应用程序 Skype 并以具有 Exchange 2016 或 Exchange 2013 内部部署邮箱的业务联机用户 Skype 的身份登录。</span><span class="sxs-lookup"><span data-stu-id="f98d9-163">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>
    
2. <span data-ttu-id="f98d9-164">具有与另一个 Skype Online 业务用户的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="f98d9-164">Have an instant messaging conversation with another Skype for Business Online user.</span></span>
    
3. <span data-ttu-id="f98d9-165">关闭即时消息对话窗口。</span><span class="sxs-lookup"><span data-stu-id="f98d9-165">Close the IM conversation window.</span></span>
    
4. <span data-ttu-id="f98d9-166">为此用户启动 Outlook，并验证对话是否出现在 Outlook“对话历史记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f98d9-166">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>
    

