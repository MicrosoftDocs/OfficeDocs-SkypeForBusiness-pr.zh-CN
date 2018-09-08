---
title: 配置云连接器与 Office 365 租户的集成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 了解如何配置云连接器与 Office 365 租户的集成。
ms.openlocfilehash: 6971858b4e31fb7f98a98f5c80b9bb983a11802a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886170"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>配置云连接器与 Office 365 租户的集成
 
了解如何配置云连接器与 Office 365 租户的集成。
  
Skype for Business Cloud Connector Edition 安装完成后，执行本节中的步骤，以配置你的部署并将其连接到你的 Office 365 租户。
  
## <a name="configure-firewall-settings"></a>配置防火墙设置

配置外围网络的内部和外部防火墙设置，以打开所需的端口[的端口和协议](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中[规划商业云连接器 edition Skype](plan-skype-for-business-cloud-connector-edition.md)中所述的防火墙设置。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>设置公用电话交换网 (PSTN) 网关

将每个 PSTN 网关上的中继设置为重新指向所有设备的中介服务器。由于池中所有服务器具有相同的池 FQDN，因此每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN。应为中继设置相同的优先级。
  
如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所述：
  
1. 从云连接器 Active Directory 计算机导出根 CA。
    
2. 按照 PSTN 网关供应商的说明导入根 CA。
    
3. 在中介服务器上导入颁发给网关的证书的根 CA 证书。如果需要为网关获取 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所述：
    
  - 修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板，以配置其他属性并允许经过身份验证的用户注册。 有关详细说明，请参阅[证书模板](https://technet.microsoft.com/en-us/library/cc730705.aspx)。
    
  - 使用证书管理单元申请证书，选择你已启用的 Web 服务器模板。 请确保使用网关的 FQDN 在“使用者名称”中添加公用名，在“备用名称”中添加 DNS 名称，并确认在“私钥”上选中“密钥选项”下的“使私钥可以导出”。 
    
4. 使用私有密钥导出 SSL 证书，并按照 PSTN 网关供应商的说明导入证书。
    
## <a name="update-the-domain-for-your-tenant"></a>为你的租户更新域

确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。 有关如何设置您在 Office 365 中的域的详细信息，请参阅[添加到 Office 365 域](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>在 Office 365 中为边缘添加 DNS 记录

将以下 DNS 记录添加到 Office 365 租户。 有关如何将 DNS 记录添加到 Office 365 租户的信息，请参阅[添加或编辑自定义中的 DNS 记录 Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
  
1. 为访问边缘添加 DNS A 记录。
    
2. SRV 记录将由 Office 365 和部署脚本自动创建。确认你可以在边缘上查找以下两个 SIP 服务：_sip 和 _sipfederationtls。
    
     ![SRV 记录确认](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>在云连接器版本与 Office 365 之间设置混合连接

若要配置混合部署业务云连接器 Edition 您 Skype 和 Office 365 租户之间的连接，请在远程 PowerShell 会话中运行以下 cmdlet。 若要了解如何建立一个远程 PowerShell 会话，请参阅： [Windows PowerShell 将计算机设置](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。
  
此 cmdlet 会设置访问边缘外部 FQDN。 在第一个命令，\<访问的外部边缘 FQDN\>应为 SIP 访问边缘角色。 默认情况下，应为 ap.\<域名\>。
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 用于对等方目标外部访问边缘 FQDN 应设置为一个 PSTN 网站，仅将在用户未分配到 PSTN 站点的情况下使用用作后备。 有关详细信息，请参阅[部署云 Connector 中单个网站](deploy-a-single-site-in-cloud-connector.md)和[部署云 Connector 中的多个网站](deploy-multiple-sites-in-cloud-connector.md)。 
  
## <a name="set-up-pstn-gateways"></a>设置 PSTN 网关

将每个 PSTN 网关上的中继设置为重新指向所有设备的中介服务器。由于池中所有服务器具有相同的池 FQDN，因此每个中继应指向一个中介服务器 FQDN 或 IP 地址，而不是中介服务器池 FQDN。应为中继设置相同的优先级。
  
如果在中介服务器和网关之间使用 TLS，则需要将网关和中介服务器配置为支持 MTLS，如下所述：
  
1. 从云连接器 Active Directory 计算机导出根 CA。
    
2. 按照 PSTN 网关供应商的说明导入根 CA。
    
3. 在中介服务器上导入颁发给网关的证书的根 CA 证书。如果需要为网关获取 SSL 证书，可以使用云连接器 Active Directory 计算机上运行的证书颁发机构服务执行此操作，如下所述：
    
  - 修改现有 Web 服务器模板，以允许经过身份验证的用户注册，或创建新的 Web 服务器模板，以配置其他属性并允许经过身份验证的用户注册。 有关详细说明，请参阅[证书模板](https://technet.microsoft.com/library/cc730705.aspx)。
    
  - 使用证书管理单元申请证书，选择你已启用的 Web 服务器模板。 请确保使用网关的 FQDN 在“使用者名称”中添加公用名，在“备用名称”中添加 DNS 名称，并确认在“私钥”上选中“密钥选项”下的“使私钥可以导出”。 
    
4. 使用私有密钥导出 SSL 证书，并按照 PSTN 网关供应商的说明导入证书。
    
5. 一个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器。
    
## <a name="set-up-your-users-in-office-365"></a>在 Office 365 中设置用户

登录 Office 365 管理门户，添加将启用在线语音服务的用户，并向这些用户分配 E5 许可证或基于 E3 许可证的 Office 365 电话系统附加许可证。 有关添加用户的信息，请参阅[添加用户移动到 Office 365 的业务](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>为用户启用 Office 365 电话系统语音和语音邮件服务

将用户添加到 Office 365 之后，为其帐户启用 Office 365 电话系统语音服务，包括语音邮件。 要启用这些功能，必须使用具有 Office 365 全局管理员角色的帐户登录你的 Office 365 租户，并且能够运行远程 PowerShell。 若要了解如何建立一个远程 PowerShell 会话，请参阅： [Windows PowerShell 将计算机设置](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- 向用户分配策略和配置用户的企业语音电话号码，指定**Identity**参数的值：
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 也可以通过用户的 SIP 地址、用户主体名称 (UPN)、域名和用户名（域\用户名）以及 Active Directory 中的显示名称（“Bob Kelly”）来指定用户身份。 
  
然后，可以使用以下脚本验证是否已添加并启用用户：
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

你将需要确定用户是否可以进行国际呼叫。默认情况下，启用国际呼叫。你可以使用在线 Skype for Business 管理中心禁止或允许用户进行国际呼叫。
  
要按用户禁用国际呼叫，请在 Skype for Business Online PowerShell 中运行以下 cmdlet：
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

若要重新启用国际后已禁用调用基于每个用户，请运行相同 cmdlet，但将值更改为*InternationalCallsAllowed* **PolicyName** 。
  
## <a name="assign-users-to-pstn-sites"></a>将用户分配到 PSTN 站点

使用租户远程 PowerShell 向用户分配站点，即使只部署了一个站点也需要执行此操作。 若要了解如何建立一个远程 PowerShell 会话，请参阅： [Windows PowerShell 将计算机设置](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 如果没有向用户分配 PSTN 站点，Skype for Business 云连接器版本部署与 Office 365 租户之间的混合连接将回退到使用租户级默认站点（对等目的），才能完成呼叫。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>配置联机混合中介服务器设置
<a name="BKMK_ConfigureMediationServer"> </a>

当 P2P 呼叫提升到 PSTN 会议，否则时，业务联机会议服务器的 Skype 将发送到云连接器中介服务器的邀请。 若要确保 Office 365 可以成功路由该邀请，您需要 online 租户的每台云连接器中介服务器中，如下所示配置设置： 
  
1. 在 Office 365 管理门户中创建一个用户。 使用任何用户名称您希望，如"MediationServer1。"
    
    用作用户域云连接器 （.ini 文件中的第一个 SIP 域） 的默认 SIP 域。
    
    请注意，只是许可证分配所需的用户传播到业务联机目录 Skype。 将 Office 365 许可证 （如 E5) 分配给创建，允许达 1 小时，更改将传播，然后从该帐户删除许可证的帐户。
    
2. 开始使用您全局租户 Azure AD 远程 PowerShell 会话或用户管理员凭据，并向"HybridMediationServer"，然后运行以下 cmdlet，以设置 Azure AD 用户帐户的部门中的配置步骤 1:

 ```
  Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
  ```

3. 使用您 Skype 业务租户管理凭据，然后运行以下 cmdlet 以将中介服务器和边缘服务器 FQDN 设置为该用户帐户，替换业务远程 PowerShell 会话启动租户 Skype \<DisplayName\>用户帐户的显示名称与您创建在步骤 1 中：
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    对于“标识”，请使用你为此中介服务器创建的 Office 365 用户帐户的显示名称。
    
    对于*MediationServerFQDN* ，使用定义中介服务器的内部 FQDN。
    
    对于*EdgeServerExternalFQDN* ，使用定义为边缘服务器访问代理服务器的外部 FQDN。 如果存在多个云连接器 PSTN 站点，请选择分配给中介服务器所在站点的边缘服务器访问代理 FQDN。
    
3. 如果存在多台云连接器中介服务器（多站点，高可用性），请对每台服务器重复执行上述步骤。
    

