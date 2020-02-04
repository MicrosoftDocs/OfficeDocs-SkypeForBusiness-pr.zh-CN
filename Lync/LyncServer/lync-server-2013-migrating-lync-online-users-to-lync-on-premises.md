---
title: Lync Server 2013：将 Lync Online 用户迁移到本地 Lync
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
ms.openlocfilehash: e76f8c0c40e13d0d9c6b19dee118e1513390d7e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>将 Lync Online 用户迁移到 Lync Server 2013 中的本地 Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 这些步骤仅适用于将最初在 Lync Online 中启用 Lync 的用户帐户迁移到本地部署之前。 若要移动最初在本地启用 Lync 的用户，然后将其移动到 Lync Online，请参阅<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">管理混合 Lync Server 2013 部署中的用户</A>。<BR>此外，所迁移的全部用户都必须拥有本地 Active Directory 帐户。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>将最初在 Lync Online 中启用的用户帐户迁移到本地 Lync

1.  首先，请确保您的组织已配置混合。
    
      - 安装 Azure Active Directory 同步工具。 有关详细信息，请参阅 <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。
    
      - 若要使你的用户能够使用 Lync Online 的单一登录，请安装 Active Directory 联合<http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>身份验证服务。
    
      - 在本地部署中，在 Lync Server 命令行管理程序中键入以下 cmdlet，为 Lync Online 创建托管提供程序：
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  在本地边缘服务器上确认你的证书链支持与 Lync Online 的连接，如下表所示。 可在此处下载此链：https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>受信任根 CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority（新 CA 证书）</p></td>
    <td><p>中间 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2（新颁发的 CA2）</p></td>
    <td><p>中间 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  在本地 Active Directory 中，为本地 Lync 启用受影响的用户帐户。 为此，可以单独为每个相关用户键入以下 cmdlet：
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    也可以创建一个脚本，从文件中读取用户名，并将其作为输入提供给 Enable-CsUser cmdlet：
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  运行 DirSync 将 Lync Online 用户与更新后的 Lync 本地用户同步。

5.  更新一些 DNS 记录以将所有 SIP 流量定向到本地 Lync：
    
      - 将 **lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。
    
      - 更新 ***\_sip *。\_** 要解析为本地 Lync 的访问边缘服务的公共 IP 地址或 VIP 地址的 Tls.contoso.com SRV 记录。
    
      - 更新 ***\_sipfederationtls *。\_** 要解析为本地 Lync 的访问边缘服务的公共 IP 地址或 VIP 地址的 Tcp.contoso.com SRV 记录。
    
      - 如果您的组织使用拆分 DNS（有时也称为“裂脑 DNS”），请确保将通过内部 DNS 区域解析名称的用户指向前端池。

6.  键入`Get-CsUser` cmdlet 以检查要移动的用户的一些属性。 您希望确保 HostingProviderProxyFQDN 已设置为`"sipfed.online.lync.com"`且正确设置了 SIP 地址。

7.  将 Lync Online 用户移动到本地 Lync。
    
    要移动单个用户，请键入：
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    您可以使用 **Get-CsUSer** cmdlet 移动多名用户，通过 -Filter 参数选择有特定属性的用户。 例如，你可以通过筛选 {托管提供商-eq "sipfed.online.lync.om"} 选择所有 Lync Online 用户。 然后，可以用管道将返回的用户传递给 **Move-CsUSer** cmdlet，如下所示。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： *Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc*。
    
    您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>确定 Office 365 租户的托管迁移服务 URL
    
    1.  以管理员身份登录到 Office 365 租户。
    
    2.  打开**Lync 管理中心**。
    
    3.  在显示**Lync 管理中心**的情况下，在地址栏中选择并将 URL 复制到**lync.com**。 示例 URL 如下所示：
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：
        
        `https://admin0a.online.lync.com`
    
    5.  向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。
        
        得到的 URL 是 **HostedMigrationOverrideUrl** 的值，应类似于以下形式：
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > rtcxds 数据库事务日志文件的默认大小上限为 16 GB。 如果您要一次性移动大量用户，特别是在启用镜像的情况下，这样的大小可能不够。 为解决此问题，您可以扩大文件大小，或者定期备份日志文件。 有关详细信息，请参阅 <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>。

    
    </div>

8.  这是一个可选步骤。 如果需要集成 Exchange 2013 Online，那么需要使用额外的托管服务提供商。 有关详细信息，请参阅[配置本地 Lync Server 2013 与 Exchange Online 集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。

9.  现在用户已经移动。为核查下表所示的用户属性具有正确的值，键入此 cmdlet：
    
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
    <th>属性名称</th>
    <th>Lync Online 用户的正确值</th>
    <th>Lync on-本地用户的正确值</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV：</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>已启用</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 已移动的每个用户都需要注销 Lync，然后重新登录。 登录时，用户应验证联系人列表，在必要情况下添加联系人。
    
    请注意，计划的会议不会从 Lync Online 迁移到本地 Lync。 用户在迁移后需要重新安排这些会议。
    
    更新 DNS 记录并将所有用户定向到本地时，HostingProvider 属性指示 Lync 用户使用 SRV 记录或将其定向到联机提供程序 "sipfed.online.lync.com"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

