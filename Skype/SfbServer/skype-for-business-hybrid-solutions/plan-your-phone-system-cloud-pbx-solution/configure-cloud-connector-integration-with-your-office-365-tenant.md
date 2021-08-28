---
title: 配置云连接器与组织Microsoft 365 Office 365集成
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 了解如何配置云连接器与组织或Microsoft 365 Office 365集成。
ms.openlocfilehash: 5e6cf8033a4207b79ff2f7d0915849b19eec2b65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628524"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>配置云连接器与组织Microsoft 365 Office 365集成

> [!Important] 
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

了解如何配置云连接器与组织或Microsoft 365 Office 365集成。
  
完成Skype for Business 云连接器版本后，执行本节中的步骤以配置部署，并连接到 Microsoft 365 或 Office 365 组织。
  
## <a name="configure-firewall-settings"></a>配置防火墙设置

为外围网络配置内部和外部防火墙设置的防火墙设置，以打开所需的端口，如 Plan for Skype for Business 云连接器版本 中的[端口](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)[和协议中所述](plan-skype-for-business-cloud-connector-edition.md)。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>设置公用电话交换网 (PSTN) 网关

在每个 PSTN 网关上设置中继，以针对所有设备重新指向中介服务器。 由于池中所有服务器的池 FQDN 都相同，因此每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN。 应设置相同优先级的中继。
  
如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：
  
1. 从云连接器 Active Directory 计算机导出根 CA。
    
2. 按照 PSTN 网关供应商说明导入根 CA。
    
3. 导入在中介服务器上颁发给网关的证书的根 CA 证书。 如果需要获取网关的 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务进行此操作，如下所示：
    
   - 修改现有 Web 服务器模板以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并启用经过身份验证的用户进行注册。 有关详细说明，请参阅证书 [模板](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。
    
   - 使用"证书"管理单元（选择已启用的 Web 服务器模板）请求证书。 请确保在"主题"中添加"公用名"，在"备用名称"中添加 DNS 名称以及网关的 FQDN，并确认在"私钥"上"使私钥可导出"在"密钥选项"下选中。 
    
4. 使用私钥导出 SSL 证书，并按照 PSTN 网关供应商提供的说明导入证书。
    
## <a name="update-the-domain-for-your-tenant"></a>更新租户的域

请确保已完成在域中更新域Microsoft 365 Office 365并能够添加 DNS 记录。 若要详细了解如何在 Microsoft 365 或 Office 365 中设置域，请参阅将域Microsoft 365[或Office 365。](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
  
## <a name="add-dns-records-for-your-edge"></a>为边缘添加 DNS 记录

将以下 DNS 记录添加到组织Microsoft 365 Office 365组织。 若要了解如何添加 DNS 记录，请参阅 Add [or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
  
1. 为访问边缘添加 DNS A 记录。
    
2. SRV 记录将自动由部署脚本Microsoft 365或Office 365创建。 确认您可以在边缘上查找以下两个 SIP 服务 \_ ：sip 和 \_ sipfederationtls。
    
     ![SRV 记录确认](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>设置云连接器版本与云连接器版本Microsoft 365或Office 365

若要配置 Skype for Business 云连接器版本 部署与 Microsoft 365 或 Office 365 组织之间的混合连接，请运行远程 PowerShell 会话中的以下 cmdlet。 若要了解如何建立远程 PowerShell 会话，请参阅：为计算机设置[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
此 cmdlet 设置访问边缘外部 FQDN。 在命令的第一个中， \<External Access Edge FQDN\> 应为 SIP 访问边缘角色的 。 默认情况下，这应该是 ap. \<Domain Name\> 。
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 用于对等目标的外部访问边缘 FQDN 应设置为 PSTN 站点，该站点在用户未分配到 PSTN 站点时将仅用作回退。 有关详细信息，请参阅在云 [连接器](deploy-a-single-site-in-cloud-connector.md) 中部署单个站点和在云连接器中 [部署多个站点](deploy-multiple-sites-in-cloud-connector.md)。 
  
## <a name="set-up-pstn-gateways"></a>设置 PSTN 网关

在每个 PSTN 网关上设置中继，以针对所有设备重新指向中介服务器。 每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN，因为池中所有服务器的池 FQDN 都相同。 应设置相同优先级的中继。
  
如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：
  
1. 从云连接器 Active Directory 计算机导出根 CA。
    
2. 按照 PSTN 网关供应商说明导入根 CA。
    
3. 导入在中介服务器上颁发给网关的证书的根 CA 证书。 如果需要获取网关的 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务进行此操作，如下所示：
    
   - 修改现有 Web 服务器模板以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并启用经过身份验证的用户进行注册。 有关详细说明，请参阅证书 [模板](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。
    
   - 使用"证书"管理单元（选择已启用的 Web 服务器模板）请求证书。 请确保在"主题"中添加"公用名"，在"备用名称"中添加 DNS 名称以及网关的 FQDN，并确认在"私钥"上"使私钥可导出"在"密钥选项"下选中。 
    
4. 使用私钥导出 SSL 证书，并按照 PSTN 网关供应商提供的说明导入证书。
    
5. 一个 PSTN 站点 (PSTN) PSTN 网关应仅连接到同一站点 (中介) 服务器。
    
## <a name="set-up-your-users"></a>设置用户

登录到 Microsoft 365 管理中心，添加将启用联机语音服务的用户，并将 E5 许可证或 电话系统 加载项分配给这些用户。 有关添加用户的信息，请参阅向企业[Microsoft 365用户](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>为用户启用电话系统语音和语音邮件服务
 
将用户添加到 Microsoft 365 或 Office 365 后，电话系统语音服务（包括语音邮件）启用其帐户。 若要启用这些功能，必须使用全局管理员角色Microsoft 365或 Office 365 帐户登录到组织或组织，并能够运行远程 PowerShell。 若要了解如何建立远程 PowerShell 会话，请参阅：为计算机设置[Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- 将策略分配给用户并配置用户的业务语音电话号码（使用 **Identity** 参数的值指定）：
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 可以使用用户的 SIP 地址、用户主体名称 (UPN) 或用户的 Active Directory 显示名称 (例如，"Bob Kelly") 。 星号字符 \* () 显示名称作为用户标识。 例如，标识"Smith"将返回具有以字符串值 \* "Smith"显示名称的所有用户。
  
然后，可以使用以下脚本验证用户是否添加和启用：
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

你需要确定你的用户是否应该能够进行国际呼叫。 默认情况下，将启用国际呼叫。 可以使用联机拨号管理中心禁用或启用Skype for Business拨号。
  
若要基于每个用户禁用国际呼叫，请运行 Skype for Business Online PowerShell 中的 cmdlet：
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

若要在禁用国际呼叫后基于每个用户重新启用该呼叫，请运行相同的 cmdlet，但将 **PolicyName** 的值更改为 *InternationalCallsAllowed*  。
  
## <a name="assign-users-to-pstn-sites"></a>向 PSTN 站点分配用户

使用租户远程 PowerShell 将网站分配给用户，即使仅部署了一个站点。 若要了解如何建立远程 PowerShell 会话，请参阅：为计算机设置[Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 如果未向用户分配 PSTN 站点，Skype for Business 云连接器版本 部署与 Microsoft 365 或 Office 365 组织之间的混合连接将回退到使用租户级别默认一个 (对等目标) 以便可以完成呼叫。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>配置联机混合中介服务器设置
<a name="BKMK_ConfigureMediationServer"> </a>

当 P2P 呼叫升级为 PSTN 会议时，Skype for Business Online 会议服务器将向云连接器中介服务器发送邀请。 若要确保Microsoft 365或Office 365成功路由此邀请，你需要在联机租户中为每个云连接器中介服务器配置一个设置，如下所示： 
  
1. 在"管理"中Microsoft 365 管理中心。 使用您想要的任何用户名，例如"MediationServer1"。
    
    使用云连接器的默认 SIP 域 (文件的第一个 SIP .ini sip) 用户域。
    
    请注意，用户传播到联机目录仅需要许可证Skype for Business分配。 将 Microsoft 365 或 Office 365 许可证 (（如 E5) ）分配给你创建的帐户，最多允许传播更改一小时，通过运行以下 cmdlet 验证用户帐户是否正确预配到 Skype for Business 联机目录，然后从此帐户中删除许可证。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 使用全局或用户管理员凭据启动租户 Azure AD 远程 PowerShell 会话，然后运行以下 cmdlet，将步骤 1 中配置的 Azure AD 用户帐户的部门设置为"HybridMediationServer"：

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 使用 Skype for Business 租户管理员凭据启动租户 Skype for Business 远程 PowerShell 会话，然后运行以下 cmdlet 将中介服务器和边缘服务器 FQDN 设置为该用户帐户，将 替换为步骤 1 中创建的帐户的用户的显示名称 \<DisplayName\> ：
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    对于 Identity，请使用为此中介服务器创建的用户帐户的显示名称。
    
    对于  *MediationServerFQDN，*  请使用为中介服务器定义的内部 FQDN。
    
    对于  *EdgeServerExternalFQDN，*  使用为边缘服务器访问代理定义的外部 FQDN。 如果有多个云连接器 PSTN 站点，请选择分配给中介服务器所在的站点的边缘服务器访问代理 FQDN。
    
4. 如果多个云连接器中介服务器 (站点 HA) ，请对每个服务器重复上述步骤。
