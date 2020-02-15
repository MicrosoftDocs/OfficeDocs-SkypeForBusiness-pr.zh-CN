---
title: 配置与 Office 365 租户的云连接器集成
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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 了解如何配置与 Office 365 租户的云连接器集成。
ms.openlocfilehash: cf683743064ec377c827fe0c52a59e464f65ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050204"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>配置与 Office 365 租户的云连接器集成
 
了解如何配置与 Office 365 租户的云连接器集成。
  
在 Skype for Business 云连接器版本安装完成后，执行本节中的步骤以配置部署并将其连接到 Office 365 租户。
  
## <a name="configure-firewall-settings"></a>配置防火墙设置

为您的外围网络配置内部和外部防火墙设置的防火墙设置，以按照[Plan For Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)中的[端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中所述打开所需端口。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>设置公共交换电话网络（PSTN）网关

将每个 PSTN 网关上的中继设置为指向所有设备的中介服务器。 由于池中的所有服务器的池 FQDN 都是相同的，因此每个中继都应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池的 FQDN。 应按相同的优先级设置中继。
  
如果要在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：
  
1. 从云连接器 Active Directory 计算机导出根 CA。
    
2. 按照 PSTN 网关供应商的说明导入根 CA。
    
3. 在中介服务器上导入颁发给您的网关的证书的根 CA 证书。 如果需要为网关获取 SSL 证书，可以使用在云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所示：
    
   - 修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并允许经过身份验证的用户进行注册。 有关详细说明，请参阅[证书模板](https://technet.microsoft.com/library/cc730705.aspx)。
    
   - 使用 "证书" 管理单元请求证书选择已启用的 Web 服务器模板。 请务必在 "主题" 和 "DNS 名称" 中添加与网关的 FQDN 相同的通用名称，并在 "密钥选项" 下选择 "使密钥可导出的私钥"。 
    
4. 使用私钥导出 SSL 证书，并按照来自 PSTN 网关供应商的说明导入证书。
    
## <a name="update-the-domain-for-your-tenant"></a>为你的租户更新域

确保已完成在 Office 365 中更新域的步骤，并且能够添加 DNS 记录。 有关如何在 Office 365 中设置域的详细信息，请参阅[Add a domain To Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>在 Office 365 中为你的边缘添加 DNS 记录

将以下 DNS 记录添加到 Office 365 租户。 有关如何向 Office 365 租户添加 DNS 记录的信息，请参阅[在 office 365 中添加或编辑自定义 DNS 记录](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
  
1. 为 Access Edge 添加 DNS A 记录。
    
2. SRV 记录将由 Office 365 和部署脚本自动创建。 确认您可以在边缘上查找以下两个 SIP 服务： "_sip" 和 "_sipfederationtls"。
    
     ![SRV 记录确认](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>在云连接器版本和 Office 365 之间设置混合连接

若要在 Skype for business 云连接器版本部署和 Office 365 租户之间配置混合连接，请在远程 PowerShell 会话中运行以下 cmdlet。 若要了解如何建立远程 PowerShell 会话，请参阅：[设置 Windows PowerShell 的计算机](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。
  
Cmdlet 设置访问边缘外部 FQDN。 在第一个命令中， \<外部访问边缘 FQDN\>应为 "SIP 访问边缘" 角色中的一个。 默认情况下，此名称\<\>应为 "接入点域名"。
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 将用于对等目标的外部访问边缘 FQDN 设置为仅当用户未分配到 PSTN 站点时才用作回退的 PSTN 站点。 有关详细信息，请参阅[在云连接器中部署单个站点](deploy-a-single-site-in-cloud-connector.md)和[在云连接器中部署多个站点](deploy-multiple-sites-in-cloud-connector.md)。 
  
## <a name="set-up-pstn-gateways"></a>设置 PSTN 网关

将每个 PSTN 网关上的中继设置为指向所有设备的中介服务器。 每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN，因为池的 FQDN 对于池中的所有服务器都是相同的。 应按相同的优先级设置中继。
  
如果要在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所示：
  
1. 从云连接器 Active Directory 计算机导出根 CA。
    
2. 按照 PSTN 网关供应商的说明导入根 CA。
    
3. 在中介服务器上导入颁发给您的网关的证书的根 CA 证书。 如果需要为网关获取 SSL 证书，可以使用在云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所示：
    
   - 修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板以配置其他属性并允许经过身份验证的用户进行注册。 有关详细说明，请参阅[证书模板](https://technet.microsoft.com/library/cc730705.aspx)。
    
   - 使用 "证书" 管理单元请求证书选择已启用的 Web 服务器模板。 请务必在 "主题" 和 "DNS 名称" 中添加与网关的 FQDN 相同的通用名称，并在 "密钥选项" 下选择 "使密钥可导出的私钥"。 
    
4. 使用私钥导出 SSL 证书，并按照来自 PSTN 网关供应商的说明导入证书。
    
5. 一个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器。
    
## <a name="set-up-your-users-in-office-365"></a>在 Office 365 中设置用户

登录到 Office 365 管理门户，添加将为联机语音服务启用的用户，并在 Office 365 外接程序中为这些用户分配对 E3 许可证的 E5 许可证或电话系统。 有关添加用户的信息，请参阅[向 Office 365 for Business 添加用户](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>为用户启用 Office 365 语音和语音邮件服务中的电话系统

将用户添加到 Office 365 后，为 Office 365 voice services 中的电话系统启用其帐户，包括语音邮件。 若要启用这些功能，您必须使用属于 Office 365 全局管理员角色的帐户登录到 Office 365 租户，并且能够运行远程 PowerShell。 若要了解如何建立远程 PowerShell 会话，请参阅：[设置 Windows PowerShell 的计算机](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- 将策略分配给用户并配置用户的业务语音电话号码（使用**Identity**参数的值指定）：
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 可以使用用户的 SIP 地址、用户主体名称（UPN）或用户的 Active Directory 显示名称（例如，"Bob 凯利"）来指定用户标识。 星号（\*）字符还可用于显示名称作为用户标识。 例如，标识 "\*smith" 将返回显示名称以字符串值 "smith" 结尾的所有用户。
  
然后，您可以使用以下脚本验证是否已添加并启用了用户：
  
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

您需要决定您的用户是否能够拨打国际电话。 默认情况下，启用国际呼叫。 您可以使用联机 Skype for Business 管理中心禁用或启用对用户进行国际拨号的用户。
  
若要基于每个用户禁用国际呼叫，请在 Skype for Business Online PowerShell 中运行以下 cmdlet：
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

若要在禁用国际呼叫后针对每个用户对其进行重新启用，请运行相同的 cmdlet，但将**PolicyName**的值更改为*InternationalCallsAllowed* 。
  
## <a name="assign-users-to-pstn-sites"></a>将用户分配到 PSTN 站点

使用租户远程 PowerShell 将网站分配给用户，即使仅部署了单个网站也是如此。 若要了解如何建立远程 PowerShell 会话，请参阅：[设置 Windows PowerShell 的计算机](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 如果没有任何 PSTN 站点分配给用户，则您的 Skype for Business 云连接器版本部署和 Office 365 租户之间的混合连接将回退为使用租户级别默认值（对等目标），以便可以完成呼叫。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>配置联机混合中介服务器设置
<a name="BKMK_ConfigureMediationServer"> </a>

在将 P2P 呼叫升级到 PSTN 会议时，Skype for Business Online 会议服务器将向云连接器中介服务器发送邀请。 若要确保 Office 365 能够成功路由此邀请，您需要为每个云连接器中介服务器配置您的联机租户中的设置，如下所示： 
  
1. 在 Office 365 管理门户中创建一个用户。 使用所需的任何用户名，如 "MediationServer1"。
    
    将云连接器（.ini 文件中的第一个 SIP 域）的默认 SIP 域用作用户域。
    
    请注意，仅当用户传播到 Skype for Business online 目录中时，才需要许可证分配。 将 Office 365 许可证（如 E5）分配给您创建的帐户，最多允许一个小时来传播所做的更改，并通过运行以下 cmdlet 验证是否已将用户帐户正确设置到 Skype for business online 目录中，然后删除此帐户的许可证。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 使用全局或用户管理员凭据启动租户 Azure AD 远程 PowerShell 会话，然后运行以下 cmdlet，以将步骤1中配置的 Azure AD 用户帐户的部门设置为 "HybridMediationServer"：

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 使用您的 Skype for Business 租户管理员凭据启动租户 Skype for Business 远程 PowerShell 会话，然后运行以下 cmdlet，以将中介服务器和边缘服务器 FQDN 设置为该用户帐户，将 DisplayName \<\>替换为您在步骤1中创建的帐户的显示名称：
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    对于 "标识"，请使用为此中介服务器创建的 Office 365 用户帐户的显示名称。
    
    对于*MediationServerFQDN* ，使用为中介服务器定义的内部 FQDN。
    
    对于*EdgeServerExternalFQDN* ，使用为边缘服务器访问代理定义的外部 FQDN。 如果有多个云连接器 PSTN 站点，请选择分配给中介服务器所在的站点的边缘服务器访问代理 FQDN。
    
4. 如果有多个云连接器中介服务器（多站点，HA），请对每个服务器重复前面的步骤。
    

