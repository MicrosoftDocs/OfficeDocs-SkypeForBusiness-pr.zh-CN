---
title: 从 Skype 业务联机到内部部署的移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 摘要： 了解如何将用户帐户移到联机部署在 Skype 上业务服务器。
ms.openlocfilehash: e429aebc6847146ad5bef2b34d6ccfa7d2997ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>从 Skype 业务联机到内部部署的移动用户
 
**摘要：**了解如何将用户帐户移到联机部署在 Skype 上业务服务器。
  
您可能需要将用户帐户移到联机，内部部署，以确保用户在线穴，并在场所发现到另一个。 为可发现到另一个，所有用户必须都有内部部署 Active Directory 中存在。 有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。 您可能想要在线将用户移动到在场所，例如，如果： 
  
- 有需要在内部部署中创建，然后移动到云的新用户。
    
- 您的组织部署 Skype 业务联机之前该业务服务器部署 Skype。 因此，第一，创建在云中的用户，现在需要转向内部部署，才能移动到 Skype 的在线业务。 
    
本主题介绍两种方案：
  
- [将在线用户移动 — — 谁是最初在线 — — 为在部署](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [在场所移动到在线用户 （人最初是在场所）](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>将在线用户移动 — — 谁是最初在线 — — 为在部署
<a name="BKMK_originallyonline"> </a>

此部分仅适用于谁已创建和启用联机状态，但又不在内部部署 Active Directory 中具有帐户的用户。 
  
开始将联机用户迁移到本地环境之前，请检查确保符合以下全部条件：
  
- 本地环境必须完全完成部署并通过验证。 有关详细信息，请参阅[部署 Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx)或[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md)，这取决于哪一个版本使用的场所。 
    
- 您在线租户必须配置为远程 PowerShell 访问。
    
    若要执行此操作，首先安装 Skype 业务在线连接器模块 Windows PowerShell，您可以在此处： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。
    
    安装本模块后，您可以通过键入以下 cmdlet Skype 业务服务器管理外壳程序的建立远程会话：
    
  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    有关如何建立远程 PowerShell 会话与 Skype 的在线业务的详细信息，请参阅[连接到 Lync 在线通过使用 Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx)。
    
    有关使用 Skype 业务在线连接器 PowerShell 模块的详细信息，请参阅[管理 Lync Online 对使用 Windows PowerShell](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx)。
    
- 您在线租户必须配置为共享的 SIP 地址空间。 若要执行此操作，首先启动远程 Powershell 会话与 Skype 的在线业务。 然后运行以下 cmdlet：
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > 保持联机移动到最后，直到"真"，没有用户的 SharedSipAddressSpace 特性需求保持在场所。 
  
您完成这些步骤后，您可以迁移的用户帐户，如下面的过程所述：
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>最初到内部部署中启用联机移动用户帐户

1. 首先，确保组织配置为混合，包括 Azure Active Directory Connect 和同步工具。 有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。
    
  - 在内部部署，为业务服务器管理外壳，Skype 键入以下 cmdlet 创建联机业务 Skype 的承载提供程序。 可以对 Identity 和 Name 参数使用您想要的任何值。
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. 确认内部部署边缘服务器上有证书链，使连接到 Skype 的在线业务下, 表中所示。 您可以下载此链此处： [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip)。
    
|**证书**|**证书存储区**|
|:-----|:-----|
|Baltimore CyberTrust Root  <br/> |受信任根 CA  <br/> |
|Microsoft Internet Authority（新 CA 证书）  <br/> |中间 CA  <br/> |
|MSIT Machine Auth CA2（新颁发的 CA2）  <br/> |中间 CA  <br/> |
   
3. 在内部部署 Active Directory 为内部部署的业务服务器 2015年启用 Skype 为受影响的用户帐户。 为此，可以单独为每个相关用户键入以下 cmdlet： 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    也可以创建一个脚本，从文件中读取用户名，并将其作为输入提供给 Enable-CsUser cmdlet：
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. 更新现有内部用户与同步在线的用户。 有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。
    
5. 更新下面的 DNS 记录，将定向到内部部署的所有 SIP 通信：
    
  - 将 **lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。
    
  - 更新 * * *_sip* 。 _tls.contoso.com** SRV 记录解析为 Lync 部署的访问边缘服务的公共 IP 或 VIP 地址。
    
  - 更新 * * *_sipfederationtls* 。 _tcp.contoso.com** SRV 记录的内部业务服务器 2015年到 Skype 的访问边缘服务的公共 IP 或 VIP 地址解析。
    
  - 如果您的组织使用拆分 DNS （有时称为"分裂 DNS"），请确保通过内部 DNS 区域的名称解析的用户被定向到前结束池。
    
6. 类型`Get-CsUser`用于检查您将移动用户有关的某些属性。 您需要确保 HostingProviderProxyFQDN 设置为`"sipfed.online.lync.com"`，且 SIP 地址设置正确。
    
7. 在场所移动到在线用户。
    
    要移动单个用户，请键入：
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    您可以通过使用**Get CsUSer** cmdlet 移动多个用户使用的筛选器参数选择具有特定属性的用户。 例如，您可以通过筛选 {承载提供程序-eq"sipfed.online.lync.om"} 选择所有在线的用户。 您可以通过管道**移动 CsUSer** cmdlet，返回的用户，如下所示。
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    指定**HostedMigrationOverrideUrl**参数必须到池承载迁移服务正在运行，按以下格式的 URL 的 URL 的格式： _Https://\<池的 FQDN\>/HostedMigration/hostedmigrationService.svc_。
    
    您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>确定 Office 365 租户的托管迁移服务 URL

1. 以管理员身份登录到 Office 365 租户。
    
2. 打开“Skype for Business 管理中心”****。
    
3. 显示“Skype for Business 管理中心”****后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. 将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL： 
    
     `https://admin0a.online.lync.com`
    
5. 向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。
    
    所生成的 URL，这是**HostedMigrationOverrideUrl**的值，应如下所示：
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > rtcxds 数据库事务日志文件的默认大小上限为 16 GB。 这可能不是足够大，如果要移动大量的用户，尤其是如果您有启用镜像。 为解决此问题，您可以扩大文件大小，或者定期备份日志文件。 有关详细信息，请参阅[https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725)。 
  
8. 这是一个可选步骤。 如果需要集成 Exchange 2013 Online，那么需要使用额外的托管服务提供商。 有关详细信息，请参阅[配置业务服务器 2015年和 Outlook Web App 内部 Skype 之间的集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)。
    
9. 现在用户已经移动。为核查下表所示的用户属性具有正确的值，键入此 cmdlet： 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**活动目录属性**|**属性名称**|**在线用户的正确值**|**对于内部用户正确的值**|
|:-----|:-----|:-----|:-----|
|msRTCSIP DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.online.lync.com  <br/> |SRV：  <br/> |
|msRTCSIP PrimaryUserAddress  <br/> |SIPAddress  <br/> |sip:userName@contoso.com  <br/> |sip:userName@contoso.com  <br/> |
|sRTCSIP UserEnabled  <br/> |已启用  <br/> |True  <br/> |True  <br/> |
   
10. 每个已迁移的用户需要先注销，然后重新登录。登录时，用户应验证联系人列表，在必要情况下添加联系人。
    
    请注意，排定的会议不会从联机迁移到本地。用户在迁移后需要重新安排这些会议。
    
    HostingProvider 属性更新 DNS 记录和所有用户将被都定向到内部部署后，指导用户使用 SRV 记录，或者将它们应用到的联机提供"sipfed.online.lync.com"。
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>在场所移动到在线用户 （人最初是在场所）
<a name="BKMK_originallyonprem"> </a>

此部分仅适用于创建和启用内部部署，然后从内部部署移动到在线用户。 
  
- 运行以下 cmdlet 以后退用户从 Skype 的在线业务到内部部署，替换更正您的环境的值**标识**和**目标**参数的值：
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

为**HostedMigrationOverrideUrl**参数指定的 URL 的格式必须是到池承载迁移服务正在运行，按以下格式的 URL:
  
 _Https://\<池的 FQDN\>/HostedMigration/hostedmigrationService.svc_。 您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>确定 Office 365 租户的托管迁移服务 URL

1. 以管理员身份登录到 Office 365 租户。
    
2. 打开“Skype for Business 管理中心”****。
    
3. 显示“Skype for Business 管理中心”****后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. 将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL： 
    
     `https://admin0a.online.lync.com`
    
5. 向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。
    
    所生成的 URL，这是**HostedMigrationOverrideUrl**的值，应如下所示：
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

