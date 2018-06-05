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
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>在 Skype for Business Online 和 Exchange 本地之间配置 OAuth
 
配置 OAuth 业务 online 本地 Exchange 和 Skype 之间的身份验证使 Skype[功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的业务和 Exchange 集成功能。
  
本主题适用于 Exchange Server 2016 和 Exchange Server 2013。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始之前你需要了解哪些信息？

- 完成此任务的估计时间：15 分钟
    
-  在可以执行此过程或其他过程之前，你需要被分配适当的权限。 若要查看所需的权限，请参阅[and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511)主题。
    
- 有关可能适用于此主题中的过程的键盘快捷方式的信息，请参阅[Exchange 管理中心中的键盘快捷方式]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>在本地 Exchange 和 Skype for Business 组织之间配置 OAuth 身份验证

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>步骤 1：为你的 Skype for Business Online 组织创建授权服务器对象

指定您的业务 Online 组织的 Skype 已验证的域。 此域应是用作基于云的帐户的主要 SIP 域的相同域。 此域称作\<验证域\>在下面的过程。
  
运行以下命令在 Exchange Management Shell (Exchange PowerShell) 中您的内部部署 Exchange 组织。
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>步骤 2：为你的 Skype for Business Online 组织启用合作伙伴应用程序

运行以下命令在 Exchange PowerShell 中，在您的内部部署 Exchange 组织。
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>步骤 3：为 Skype for Business Online 合作伙伴应用程序创建新的邮件用户帐户

此步骤在本地执行。它将创建一个邮件用户并为其分配合适的管理角色权限。随后此用户将用于下一步骤。
  
指定为 Exchange 组织已验证的域。 此域应为同一个域用作用于内部部署 Exchange 帐户的主 SMTP 域。 此域称作\<验证域\>在下面的过程。 此外， \<DomainControllerFQDN\>应域控制器的 FQDN。 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

此命令将在地址列表中隐藏新的邮件用户。
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

接下来的两个命令将为这个新帐户分配 UserApplication 和 ArchiveApplication 管理角色。
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>步骤 4：为 Skype for Business Online 创建和启用合作伙伴应用程序

创建新的合作伙伴应用程序，并且将使用你刚刚创建的帐户。 运行以下命令在 Exchange PowerShell 中，在您的内部部署 Exchange 组织。 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>步骤 5：导出本地授权证书

运行可导出本地授权证书，您将导入到下一步中的业务 Online 组织您 Skype 的 PowerShell 脚本。
  
请将以下文本保存到一个 PowerShell 脚本文件，例如名为 ExportAuthCert.ps1 的文件。
  
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

在 Exchange 内部部署 Exchange 组织中的 PowerShell 运行您刚创建的 PowerShell 脚本。 例如：.\ExportAuthCert.ps1
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>步骤 6：将本地授权证书上载到 Azure Active Directory ACS

接下来，使用 Windows PowerShell 将你在上一步中导出的本地授权证书上载到 Azure Active Directory 访问控制服务 (ACS)。 要执行此操作，必须已经安装用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块。 如果未安装，请转到[https://aka.ms/aadposh](https://aka.ms/aadposh)来安装 Azure Active Directory 的 Windows PowerShell 的模块。 在安装用于 Windows PowerShell 的 Azure Active Directory 模块之后，请完成以下步骤。
  
1. 单击**用于 Windows PowerShell 的 Azure Active Directory 模块**快捷方式以打开安装了 Azure AD cmdlet 的 Windows PowerShell 工作区。此步骤中的所有命令都将使用 Windows PowerShell for Azure Active Directory 控制台运行。
    
2. 例如，将以下文本保存到名为的 PowerShell 脚本文件`UploadAuthCert.ps1`。
    
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

3. 运行你在上一步中创建的 PowerShell 脚本。 例如：`.\UploadAuthCert.ps1`
    
4. 在启动脚本之后，将显示凭据对话框。请输入你的 Microsoft Online Azure AD 组织的租户管理员帐户的凭据。在运行脚本之后，请将 Windows PowerShell for Azure AD 会话保持打开。你将使用此会话来在下一步中运行 PowerShell 脚本。
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>步骤 7：为 SMTP 域注册主机名颁发机构

指定为 Exchange 组织已验证的域。 此域应为同一个域用作用于内部部署 Exchange 帐户的主 SMTP 域。 此域称作\<验证域\>在下面的过程。
  
> [!NOTE]
> 要成功运行以下脚本，需要按照上一节的步骤 4 中的说明将“用于 Azure Active Directory 的 Windows PowerShell”连接到 Microsoft Online Azure AD 租户。 
  
1. 将以下文本保存到一个 PowerShell 脚本文件中，例如将脚本文件命名为 RegisterEndpoints.ps1。 此示例使用通配符注册 contoso.com 的所有终结点。 Contoso.com 替换为内部部署 Exchange 组织的主机名颁发机构
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  在用于 Azure Active Directory 的 Windows PowerShell 中，运行在上一步骤中创建的 Windows PowerShell 脚本。 例如：`.\RegisterEndpoints.ps1`
    
### <a name="verify-your-success"></a>验证是否成功

通过验证某些功能是否正常工作来验证 OAuth 配置的正确性，例如，让移动客户端的对话历史记录出现在 Outlook “对话历史记录”文件夹中。
  
1. 在 Windows Phone 或 iOS 设备上启动业务移动应用程序 Skype 并以具有 Exchange 2016 或 Exchange 2013 内部部署邮箱的业务联机用户 Skype 的身份登录。
    
2. 具有与另一个 Skype Online 业务用户的即时消息对话。
    
3. 关闭即时消息对话窗口。
    
4. 为此用户启动 Outlook，并验证对话是否出现在 Outlook“对话历史记录”文件夹中。
    

