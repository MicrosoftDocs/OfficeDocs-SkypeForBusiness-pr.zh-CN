---
title: 将 Lync Online 用户迁移至本地 Lync
TOCTitle: 将 Lync Online 用户迁移至本地 Lync
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62247371
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Online 用户迁移至本地 Lync

 

_**上一次修改主题：** 2016-12-08_

> [!IMPORTANT]
> 只有迁移最初部署本地 Lync 之前在 Lync Online 中启用 Lync 的用户帐户时才需要执行这些步骤。要迁移最初为本地 Lync 启用的用户，以便将其迁移至 Lync Online，请参阅 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">管理混合 Lync Server 2013 部署中的用户</a>。<br />
> 此外，所迁移的全部用户都必须拥有本地 Active Directory 帐户。


## 将最初在 Lync Online 中启用的用户帐户迁移到本地 Lync

1.  首先，确保您的组织已配置混合部署。
    
      - 安装 Windows Azure Active Directory 同步工具。如需了解详细信息，请参阅 <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。
    
      - 若要允许用户为 Lync Online 使用单一登录，请安装 Active Directory 联合身份验证服务 <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>。
    
      - 在本地部署中，在 Lync Server 命令行管理程序 内键入以下 cmdlet，为 Lync Online 创建托管提供者：
        
            Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true

           &nbsp;
        
            New-CSHostingProvider -Identity LyncOnline -Name LyncOnlin -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

2.  确认您的本地边缘服务器上具有支持连接到 Lync Online 的证书链，如下表所示。您可以从此处下载证书链：[https://corp.sts.microsoft.com/Onboard/ADFS\_Onboarding\_Pack/corp\_sts\_certs.zip](https://corp.sts.microsoft.com/onboard/adfs_onboarding_pack/corp_sts_certs.zip)。
    
    
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


3.  在本地 Active Directory 中，为本地 Lync 启用受影响的用户帐户。为此，可以单独为每个相关用户键入以下 cmdlet：
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    也可以创建一个脚本，从文件中读取用户名，并将其作为输入提供给 Enable-CsUser cmdlet：
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  运行 DirSync 将 Lync Online 用户与更新后的本地 Lync 用户同步。

5.  更新部分 DNS 记录，将所有 SIP 通信引向本地 Lync：
    
      - 更新 **lyncdiscover.contoso.com** A 记录，指向本地反向代理服务器的 FQDN。
    
      - 更新 ***\_sip*.\_tls.contoso.com** SRV 记录，使之解析为本地 Lync 的访问边缘服务公共 IP 地址或 VIP 地址。
    
      - 更新 ***\_sipfederationtls*.\_tcp.contoso.com** SRV 记录，使之解析为本地 Lync 的访问边缘服务公共 IP 地址或 VIP 地址。
    
      - 如果您的组织使用拆分 DNS（有时也称为“裂脑 DNS”），请确保将通过内部 DNS 区域解析名称的用户指向前端池。

6.  键入 `Get-CsUser` cmdlet 查看您正在移动的用户的部分属性。您需要确保 HostingProviderProxyFQDN 设置为 `"sipfed.online.lync.com"`，且 SIP 地址设置正确。

7.  将 Lync Online 用户迁移至本地 Lync。
    
    要移动单个用户，请键入：
    
        $cred = Get-Credential

       &nbsp;
    
        Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
    
    您可以使用 **Get-CsUSer** cmdlet 移动多名用户，通过 –Filter 参数选择具有特定属性的用户。例如，可以通过筛选 {Hosting Provider –eq “sipfed.online.lync.om”} 选择全部 Lync Online 用户。然后，可以将返回的用户传递给 **Move-CsUSer** cmdlet，如下所示。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    为 **HostedMigrationOverrideUrl** 参数指定的 URL 的格式必须为托管迁移服务在其中运行的池的 URL，格式如下：*Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc*。
    
    您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。
    
    ## 确定 Office 365 租户的托管迁移服务 URL
    
    1.  以管理员身份登录到 Office 365 租户。
    
    2.  打开“Lync 管理中心”。
    
    3.  显示“Lync 管理中心”后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：
        
        `https://admin0a.online.lync.com`
    
    5.  向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。
        
        得到的 URL 是 **HostedMigrationOverrideUrl** 的值，应类似于以下形式：
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]  
    > rtcxds 数据库事务日志文件的默认大小上限为 16 GB。如果您要一次性移动大量用户，特别是在启用镜像的情况下，这样的大小可能不够。为解决此问题，您可以扩大文件大小，或者定期备份日志文件。如需了解详细信息，请参阅 <a href="http://support.microsoft.com/kb/2756725" class="uri">http://support.microsoft.com/kb/2756725</a>。
    


8.  这是一个可选步骤。如果您需要集成 Exchange 2013 Online，则需要使用额外的托管服务提供商。有关详细信息，请参阅 [配置本地 Lync Server 2013 与 Exchange Online 的集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。

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
    <th>本地 Lync 用户的正确值</th>
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
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Enabled</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 各已迁移用户必须首先注销 Lync，然后重新登录。登录时，用户应检查联系人列表，在必要情况下添加联系人。
    
    请注意，计划会议不会从 Lync Online 迁移到本地 Lync。用户需要在迁移后重新安排这些会议。
    
    DNS 记录更新后，所有用户都将被引向本地部署，HostingProvider 属性会指示 Lync 用户使用 SRV 记录，或指示用户使用在线提供者“sipfed.online.lync.com”。

