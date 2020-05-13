---
title: Lync Server 2013：将 Lync Online 用户迁移到 Lync 本地
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efc642ea326765df138f19fde4e691aa94d6b3b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>将 Lync Online 用户迁移到 Lync Server 2013 中的 Lync 本地

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 这些步骤只是在部署 Lync 本地之前为 lync Online 中最初启用 Lync 的用户帐户所必需的。 若要移动最初为本地启用 Lync 的用户，然后将其移动到 Lync Online，请参阅<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理用户</A>。<BR>此外，要移动的所有用户都必须在本地 Active Directory 中拥有帐户。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>将 Lync Online 中最初启用的用户帐户迁移到本地 Lync

1.  首先，请确保您的组织已配置了混合。
    
      - 安装 Azure Active Directory 同步工具。 有关详细信息，请参阅 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。
    
      - 若要使用户能够使用 Lync Online 的单一登录，请安装 Active Directory 联合身份验证服务 <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> 。
    
      - 在本地部署中，在 Lync Server 命令行管理程序中，键入以下 cmdlet 以创建 Lync Online 的托管提供程序：
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  确认在本地边缘服务器上，您具有允许连接到 Lync Online 的证书链，如下表所示。 你可以在此处下载此链：https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>证书</th>
    <th>证书存储</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>受信任的根 CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet 颁发机构（新 CA 证书）</p></td>
    <td><p>中间 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 （新颁发 CA2）</p></td>
    <td><p>中间 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  在本地 Active Directory 中，为本地 Lync 启用受影响的用户帐户。 您可以通过键入以下 cmdlet 为单个用户执行此操作：
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    或者，您可以创建一个脚本，从文件中读取用户名并将其作为 Get-csuser cmdlet 的输入提供：
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  运行 DirSync 以将 Lync Online 用户与更新的 Lync 本地用户同步。

5.  更新一些 DNS 记录以将所有 SIP 流量定向到本地 Lync：
    
      - 将**Lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。
    
      - 更新 *** \_ sip *。 \_** 要解析为本地 Lync 服务访问边缘服务的公共 IP 或 VIP 地址的 Tls.contoso.com SRV 记录。
    
      - 更新 *** \_ sipfederationtls *。 \_** 要解析为本地 Lync 服务访问边缘服务的公共 IP 或 VIP 地址的 Tcp.contoso.com SRV 记录。
    
      - 如果您的组织使用拆分 DNS （有时称为 "split-大脑 DNS"），请确保通过内部 DNS 区域解析名称的用户被定向到前端池。

6.  键入 `Get-CsUser` cmdlet 以检查您要移动的用户的一些属性。 您希望确保将 HostingProviderProxyFQDN 设置为 `"sipfed.online.lync.com"` ，并且正确设置了 SIP 地址。

7.  将 Lync Online 用户移动到本地 Lync。
    
    若要移动单个用户，请键入：
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    您可以通过使用带有– Filter 参数的**get-csuser** cmdlet 来移动多个用户，以选择具有特定属性的用户。 例如，可以通过筛选 {托管提供商– eq "sipfed.online.lync.om"} 选择所有 Lync Online 用户。 然后可以将返回的用户通过管道传递给**get-csuser** cmdlet，如下所示。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： *Https:// \< pool FQDN \> /HostedMigration/hostedmigrationService.svc*。
    
    您可以通过查看适用于 Microsoft 365 或 Office 365 组织帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a>确定您的 organizaton 的托管迁移服务 URL
    
    1.  以管理员身份登录到你的 Microsoft 365 或 Office 365 组织。
    
    2.  打开**Lync 管理中心**。
    
    3.  在 " **Lync 管理中心**" 显示的情况下，选择并将地址栏中的 URL 复制到**lync.com**。 示例 URL 的外观类似于以下内容：
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  将 URL 中的**webdir**替换为**admin**，从而产生以下结果：
        
        `https://admin0a.online.lync.com`
    
    5.  将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。
        
        生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Rtcxds 数据库的事务日志文件的默认最大大小为 16 GB。 如果一次移动大量用户，尤其是在启用了镜像的情况下，这可能不够大。 若要解决此情况，可以增加文件大小，也可以定期备份日志文件。 有关详细信息，请参阅 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 。

    
    </div>

8.  这是一个可选步骤。 如果需要与 Exchange 2013 Online 集成，则需要使用其他承载提供程序。 有关详细信息，请参阅[配置本地 Lync Server 2013 与 Exchange Online 集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。

9.  现在将移动用户。 若要检查用户是否具有下表中所示属性的正确值，请键入以下 cmdlet：
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Active Directory 属性</th>
    <th>属性名</th>
    <th>Lync Online 用户的正确值</th>
    <th>Lync on –本地用户的正确值</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-Msrtcsip-userenabled</p></td>
    <td><p>已启用</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 已移动的每个用户都需要注销 Lync，然后重新登录。 当他们登录时，应验证其联系人列表，并在需要时添加联系人。
    
    请注意，安排的会议不会从 Lync Online 迁移到本地 Lync。 用户需要在移动后重新安排这些会议。
    
    更新 DNS 记录并将所有用户定向到本地时，HostingProvider 属性指示 Lync 用户是使用 SRV 记录，还是将其定向到联机提供程序 "sipfed.online.lync.com"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

