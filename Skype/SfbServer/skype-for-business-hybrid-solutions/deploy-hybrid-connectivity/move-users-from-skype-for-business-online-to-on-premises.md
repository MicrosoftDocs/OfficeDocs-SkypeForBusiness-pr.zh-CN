---
title: Skype 业务 online 到本地移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 摘要： 了解如何移动用户帐户从联机到本地 Skype 中的业务服务器。
ms.openlocfilehash: 655c037fc2299044aa3799d06e0d231784248d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260144"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Skype 业务 online 到本地移动用户

**摘要：** 了解如何移动用户帐户从联机到本地 Skype 中的业务服务器。

您可能需要将用户帐户从联机到移动本地以确保用户驻留在线和本地是到另一个可供搜索。 若要向其他可供搜索，所有用户必须都具有内部部署 Active Directory 中的状态。 有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。 您可能需要 online 将用户移动到在本地，例如，如果：

- 您必须是在本地创建，然后移到云中所需要的新用户。

- 您的组织部署业务 online Skype，其业务服务器部署 Skype 之前。 因此，您有首先，创建在云中的用户，并且现在需要移至本地移动到 Skype 业务 online 才能。

本主题介绍两种方案：

- [移动 online 用户 — 谁是最初联机 — 为本地](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [本地移动到联机用户 （人员最初在本地）](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>移动 online 用户 — 谁是最初联机 — 为本地
<a name="BKMK_originallyonline"> </a>

本节仅适用于用户创建和启用联机状态，但用户在本地 Active Directory 中没有帐户的用户。

开始将联机用户迁移到本地环境之前，请检查确保符合以下全部条件：

- 本地环境必须完全完成部署并通过验证。 有关详细信息，请参阅[Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx)或[部署的 Business Server 2015 的 Skype](../../deploy/deploy.md)，具体取决于哪个版本将在本地。

- 远程 PowerShell 访问，必须配置您的 online 租户。

    若要执行此操作，首先安装 for Business 联机连接器模块 Skype 用于 Windows PowerShell，您可以在此处获取： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。

    安装本模块后，您可以通过键入以下 cmdlet Skype 中的业务 Server 命令行管理程序建立远程会话：

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

    有关使用 PowerShell 和 Skype 业务 online 的详细信息，请参阅[Windows PowerShell 将计算机设置](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

- 必须为共享的 SIP 地址空间配置您的 online 租户。 若要执行此操作，首先开始远程 Powershell 会话 Skype 业务 online。 然后运行以下 cmdlet：

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > 在本地保留 SharedSipAddressSpace 属性需要保留搕 Rue 联机移动到是最终的直到和任何用户。

完成这些步骤后，您可以迁移用户帐户，如下面的过程中所述：

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>移动最初部署到的本地部署 online 启用的用户帐户

1. 首先，确保组织配置为混合，包括 Azure Active Directory Connect 和同步工具。 有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。

  - 有关您的本地部署、 业务 Server Management Shell，Skype 中键入以下 cmdlet 以创建业务联机 Skype 承载服务提供商。 可以对 Identity 和 Name 参数使用您想要的任何值。

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. 确认在内部部署边缘服务器，您有证书链，连接到 Skype 业务 online 下, 表中所示。 您可以下载此链此处： [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip)。

|**证书**|**证书存储**|
|:-----|:-----|
|Baltimore CyberTrust Root  <br/> |受信任根 CA  <br/> |
|Microsoft Internet Authority（新 CA 证书）  <br/> |中间 CA  <br/> |
|MSIT Machine Auth CA2（新颁发的 CA2）  <br/> |中间 CA  <br/> |

3. 您的本地 Active Directory 中，为本地业务服务器 2015年启用的 Skype 受影响的用户帐户。 为此，可以单独为每个相关用户键入以下 cmdlet：

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

4. 更新内部部署用户同步联机用户。 有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。

5. 更新定向到内部部署的所有 SIP 流量的以下 DNS 记录：

  - 将 **lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。

  - 更新***_sip* 。 _tls.contoso.com** SRV 记录来解析到 Lync 内部部署的访问边缘服务公用 IP 或 VIP 地址。

  - 更新***_sipfederationtls* 。 _tcp.contoso.com** SRV 记录以的业务服务器 2015年本地解析为 Skype 的访问边缘服务公用 IP 或 VIP 地址。

  - 如果组织使用拆分 DNS （有时称为"拆分式 DNS"），请确保用户解析名称通过内部 DNS 区域时转到 Front End Pool。

6. 键入`Get-CsUser`cmdlet 来检查您将移动的用户的某些属性。 您需要确保 HostingProviderProxyFQDN 设置为`"sipfed.online.lync.com"`，且 SIP 地址设置正确。

7. 联机将用户移动到本地。

    要移动单个用户，请键入：

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    您可以通过使用**Get-csuser** cmdlet 移动多个用户使用-Filter 参数，选择与特定属性的用户。 例如，您无法通过筛选 {宿主提供商-eq"sipfed.online.lync.om"} 选择所有联机用户。 您可以通过管道返回的用户到**Move-csuser** cmdlet，如下所示。

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    指定的**HostedMigrationOverrideUrl**参数必须为托管迁移服务正在运行，采用以下格式的池的 URL 的 url 格式： _Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc_。

    您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>确定 Office 365 租户的托管迁移服务 URL

1. 以管理员身份登录到 Office 365 租户。

2. 打开“Skype for Business 管理中心”****。

3. 显示“Skype for Business 管理中心”**** 后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. 将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：

     `https://admin0a.online.lync.com`

5. 向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。

    结果的 URL，即**HostedMigrationOverrideUrl**的值应如下所示：

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > rtcxds 数据库事务日志文件的默认大小上限为 16 GB。 这可能不是足够大，如果要同时移动大量用户尤其在您必须启用镜像。 为解决此问题，您可以扩大文件大小，或者定期备份日志文件。 有关详细信息，请参阅[https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725)。

8. 这是一个可选步骤。 如果需要集成 Exchange 2013 Online，那么需要使用额外的托管服务提供商。 有关详细信息，请参阅[Configure 集成业务服务器 2015年和 Outlook Web App 的内部部署 Skype](../../deploy/integrate-with-exchange-server/outlook-web-app.md)。

9. 现在用户已经移动。为核查下表所示的用户属性具有正确的值，键入此 cmdlet：

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Active Directory 属性**|**属性名称**|**Online 用户的正确值**|**内部部署用户的正确值**|
|:-----|:-----|:-----|:-----|
|msRTCSIP DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.online.lync.com  <br/> |SRV：  <br/> |
|msRTCSIP PrimaryUserAddress  <br/> |SIPAddress  <br/> |sip:userName@contoso.com  <br/> |sip:userName@contoso.com  <br/> |
|msRTCSIP UserEnabled  <br/> |已启用  <br/> |True  <br/> |True  <br/> |

10. 每个已迁移的用户需要先注销，然后重新登录。登录时，用户应验证联系人列表，在必要情况下添加联系人。

    请注意，排定的会议不会从联机迁移到本地。用户在迁移后需要重新安排这些会议。

    HostingProvider 属性更新的 DNS 记录和所有用户被都定向到内部部署后，指示用户使用 SRV 记录，或将其应用到在线提供商"sipfed.online.lync.com。"

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>本地移动到联机用户 （人员最初在本地）
<a name="BKMK_originallyonprem"> </a>

本节仅适用于用户创建和启用内部部署，然后从内部部署移动到 online。

- 运行以下 cmdlet 来移动用户从 Skype 的业务联机回内部部署，替换更正值为您的环境使用**Identity**和**目标**参数的值：

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

**HostedMigrationOverrideUrl**参数指定的 URL 的格式必须为托管迁移服务正在运行，采用以下格式的池的 URL:

 _Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc_。 您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>确定 Office 365 租户的托管迁移服务 URL

1. 以管理员身份登录到 Office 365 租户。

2. 打开“Skype for Business 管理中心”****。

3. 显示“Skype for Business 管理中心”**** 后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. 将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：

     `https://admin0a.online.lync.com`

5. 向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。

    结果的 URL，即**HostedMigrationOverrideUrl**的值应如下所示：

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


