---
title: Skype for Business Online 与 Exchange 服务器之间的集成
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在本地 Exchange 和 Skype for Business Online 之间配置 OAuth 身份验证可实现功能支持中所述的 Skype for Business 和 Exchange Integration 功能。
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886639"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>在 Skype for Business Online 和 Exchange Server 之间配置集成和 OAuth 

配置 Exchange 服务器与 Skype for Business Online 之间的集成可实现 [功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的 Skype for Business 和 Exchange Integration 功能。

本主题适用于与 Exchange Server 2013 到 2019 的集成。

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成该任务的时间：15 分钟

-  您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限，请参阅 [Exchange 和 Shell 基础结构权限](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) 主题。

- 若要了解本主题中的过程可能适用的键盘快捷键，请参阅 [Exchange 管理中心内的键盘快捷键]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

- 有关兼容性的信息，请 [参阅 Skype for Business 与 Office 应用的兼容性](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>配置 Exchange Server 与 O365 之间的集成

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步骤 1：在 Exchange Server 和 O365 之间配置 OAuth 身份验证

执行以下文章中的步骤：

[在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>步骤 2：为 Skype for Business Online 合作伙伴应用程序创建新的邮件用户帐户

此步骤在 Exchange 服务器上完成。 它将创建一个邮件用户，并为其分配适当的管理角色权限。 然后，将在下一步骤中使用此帐户。

为 Exchange 组织指定已验证的域。 此域应与用于本地 Exchange 帐户的主 SMTP 域使用的域相同。 此域在以下过程中称为 \<your Verified Domain\> ” 此外， \<DomainControllerFQDN\> 应为域控制器的 FQDN。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

此命令将隐藏地址列表中的新邮件用户。

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

接下来的两个命令将为此新帐户分配 UserApplication 和 ArchiveApplication 管理角色。

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>步骤 3：创建并启用适用于 Skype for Business Online 的合作伙伴应用程序 

创建新的合作伙伴应用程序，并使用刚创建的帐户。 在本地 Exchange 组织的 Exchange PowerShell 中运行以下命令。

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>步骤 4：导出本地授权证书

运行 PowerShell 脚本以导出本地授权证书，下一步将导入到 Skype for Business Online 组织。

将以下文本保存到名为 ExportAuthCert.ps1（示例名称）的 PowerShell 脚本文件中。

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

在本地 Exchange 组织的 Exchange PowerShell 中，运行刚创建的 PowerShell 脚本。 例如：.\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>步骤 5：将本地授权证书上传到 Azure Active Directory ACS

接下来，使用 Windows PowerShell 将上一步中导出的本地授权证书上传到 Azure Active Directory 访问控制服务 (ACS) 。 为此，必须已安装适用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块。 如果尚未安装，请转到 [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) 安装 用于 Windows PowerShell 的 Azure Active Directory 模块。 安装 用于 Windows PowerShell 的 Azure Active Directory 模块 后，完成以下步骤。

1. Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.

2. 例如  `UploadAuthCert.ps1`，将以下文本保存到名为 PowerShell 的脚本文件。

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. 运行您在上一步骤中创建的 PowerShell 脚本。 例如：  `.\UploadAuthCert.ps1`

4. 启动脚本后，您会看到凭据对话框。 输入 Microsoft Online Azure AD 组织的租户管理员帐户的凭据。 运行脚本后，让 Azure AD 会话的 Windows PowerShell 处于打开状态。 您将在下一步骤中使用此程序运行 PowerShell 脚本。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>步骤 6：验证证书是否已上传到 Skype for Business 服务主体
1. 在 PowerShell 中，打开并向 Azure Active Directory 进行身份验证，运行以下命令

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. 出现 ReturnKeyValues 提示时按 Enter
3. 确认看到列出了与 Exchange Oauth 证书开始日期和结束日期匹配的开始日期和结束数据的密钥

### <a name="verify-your-success"></a>验证成功

验证某些功能是否正常工作，验证配置是否正确。 

1. 确认具有云语音邮件服务的 Skype for Business 用户（在具有混合 Exchange Server 配置的组织中）可以成功更改其语音邮件问候语。

2. 确认移动客户端的对话历史记录在 Outlook 对话历史记录文件夹中可见。

3. 确认已存档的聊天消息已使用 [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor) 保存在 Purges 文件夹中的用户本地邮箱中。

或者，查看流量。 OAuth 握手中的流量 (非常独特，看起来不像基本身份验证) ， 特别是在领域周围，你将开始看到如下所示的颁发者流量：000000004-0000-0ff1-ce00-000000000000@ (有时在正在传递的令牌中具有 @符号) 之前的 /。 不会看到用户名或密码，这是 OAuth 的要点。 但你会看到“Office”颁发者-在本例中“4”是 Skype for Business - 和你的订阅领域。

若要确保已成功使用 OAuth，请确保知道预期内容并知道流量的外观。 [因此，](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)下面是一个相当标准的 [Microsoft 应用程序中 OAuth 流量示例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)， (非常有助于阅读，尽管它不使用刷新令牌) ，并且有 Fiddler 扩展可让你查看 OAuth JWT (JSON Web 令牌) 。

下面是 [设置一个设置的示例](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)，但可以使用任何你喜欢执行此过程的网络跟踪工具。

## <a name="related-topics"></a>相关主题

[在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
