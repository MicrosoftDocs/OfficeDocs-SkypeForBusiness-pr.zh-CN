---
title: Skype for Business Online Exchange服务器之间的集成
ms.reviewer: cbland
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在本地和 Exchange Online 之间配置 OAuth Skype for Business启用功能Skype for Business Exchange集成功能。
ms.openlocfilehash: 0e811a7feb713e2c356acdeba5461a212bfff17e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764770"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>配置 Skype for Business Online 和 Exchange Server 之间的集成和 OAuth 

通过配置 Exchange 和 Skype for Business Online 之间的集成，Skype for Business Exchange支持 中所述的集成[功能和集成功能](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。

本主题适用于与 2013 Exchange Server 2019 年集成。

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成该任务的时间：15 分钟

-  您必须先获得权限，然后才能执行此过程或多个过程。 若要了解所需的权限，请参阅 Exchange[和命令行管理程序基础结构权限](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)主题。

- 若要了解本主题中的过程可能适用的键盘快捷键，请参阅 [Exchange 管理中心内的键盘快捷键]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

- 有关兼容性的信息，请参阅Skype for Business[应用的Office兼容性](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>配置 Exchange Server 和 O365 之间的集成

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步骤 1：在 Exchange Server 和 O365 之间配置 OAuth 身份验证

执行以下文章中的步骤：

[在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>步骤 2：为 Skype for Business Online 合作伙伴应用程序创建新的邮件用户帐户

此步骤在 Exchange 服务器上完成。 它将创建一个邮件用户，并为其分配适当的管理角色权限。 然后，将在下一步中对此帐户使用。

为组织指定验证Exchange域。 此域应是用作本地部署帐户的主 SMTP Exchange域。 以下过程中引用 \<your Verified Domain\> 了此域。 此外 \<DomainControllerFQDN\> ，应为域控制器的 FQDN。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

此命令将在地址列表中隐藏新邮件用户。

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

接下来的两个命令将 UserApplication 和 ArchiveApplication 管理角色分配给此新帐户。

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>步骤 3：为 Skype for Business Online 创建和启用合作伙伴应用程序 

创建新的合作伙伴应用程序，并使用你刚刚创建的帐户。 在本地 Exchange 组织的 Exchange PowerShell 中运行以下命令。

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>步骤 4：导出本地授权证书

运行 PowerShell 脚本以导出本地授权证书，该证书将在下一步Skype for Business导入到 Skype for Business Online 组织。

将以下文本保存到名为 ExportAuthCert.ps1（示例名称）的 PowerShell 脚本文件中。

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

在Exchange内部部署部署Exchange PowerShell 中，运行刚创建的 PowerShell 脚本。 例如：.\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>步骤 5：Upload本地授权证书Azure Active Directory ACS

接下来，Windows PowerShell将上一步中导出的本地授权证书上载到 Azure Active Directory Access Control Services (ACS) 。 为此，必须已安装Azure Active Directory cmdlet Windows PowerShell模块。 如果尚未安装，请转到 [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) 安装 用于 Windows PowerShell 的 Azure Active Directory 模块。 安装 用于 Windows PowerShell 的 Azure Active Directory 模块 后，完成以下步骤。

1. Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.

2. 将以下文本保存到名为 的 PowerShell 脚本文件，例如  `UploadAuthCert.ps1` ， 。

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

3. 运行您在上一步骤中创建的 PowerShell 脚本。 例如：  `.\UploadAuthCert.ps1`

4. 启动脚本后，您会看到凭据对话框。 输入 Microsoft Online 组织租户管理员帐户Azure AD凭据。 运行脚本后，让 Azure AD 会话的 Windows PowerShell 处于打开状态。 您将在下一步骤中使用此程序运行 PowerShell 脚本。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>步骤 6：验证证书已上载到 Skype for Business 服务主体
1. 在 PowerShell 中打开并经过身份验证Azure Active Directory，运行以下代码
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. 当系统提示输入 ReturnKeyValues 时按 Enter
3. 确认你看到列出了与 Oauth 证书开始日期和结束日期Exchange和结束日期相匹配的开始日期和结束日期的密钥

### <a name="verify-your-success"></a>验证是否成功

通过验证某些功能是否正常工作来验证配置是否正确。 

1. 确认Skype for Business混合云语音邮件配置的组织使用 Exchange Server 服务的用户可以成功更改其语音邮件问候语。

2. 确认移动客户端的对话历史记录在"对话历史记录"Outlook可见。

3. 使用 [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)确认存档的聊天消息存储在用户本地邮箱的"清除"文件夹中。

或者，查看流量。 OAuth 握手中的流量非常独特 (，看起来并不如基本身份验证) ， 尤其是对于领域，你将开始看到如下所示的颁发者通信：000000004-0000-0ff1-ce00-0000000000000@ (有时在要传递的令牌中 @ 符号) 之前有 / 。 你将看不到用户名或密码，这是 OAuth 的要点。 但是，你将看到"Office"颁发者（本例中为"4"Skype for Business）和订阅的领域。

如果你希望确保成功使用 OAuth，请确保你了解预期结果，并知道流量应该是什么样。 因此[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)，下面是 Microsoft 应用程序 (中[OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)流量的一个相当标准的标准示例，尽管它不使用刷新令牌) ，并且有 Fiddler 扩展，可让你查看 OAuth JWT (JSON Web 令牌) 。

下面是设置 [一个](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)的示例，但您可以使用任何要执行此过程的网络跟踪工具。

## <a name="related-topics"></a>相关主题

[在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)