---
title: Lync Server 2013：将 Lync Online 用户迁移到本地 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fb8d24a2bb112ab07d35097414141b9eaaa606
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="4b779-102">将 Lync Online 用户迁移到 Lync Server 2013 中的本地 Lync</span><span class="sxs-lookup"><span data-stu-id="4b779-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b779-103">_**主题上次修改时间：** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="4b779-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="4b779-104">这些步骤仅适用于将最初在 Lync Online 中启用 Lync 的用户帐户迁移到本地部署之前。</span><span class="sxs-lookup"><span data-stu-id="4b779-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="4b779-105">若要移动最初在本地启用 Lync 的用户，然后将其移动到 Lync Online，请参阅<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">管理混合 Lync Server 2013 部署中的用户</A>。</span><span class="sxs-lookup"><span data-stu-id="4b779-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="4b779-106">此外，所迁移的全部用户都必须拥有本地 Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="4b779-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="4b779-107">将最初在 Lync Online 中启用的用户帐户迁移到本地 Lync</span><span class="sxs-lookup"><span data-stu-id="4b779-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="4b779-108">首先，请确保您的组织已配置混合。</span><span class="sxs-lookup"><span data-stu-id="4b779-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="4b779-109">安装 Azure Active Directory 同步工具。</span><span class="sxs-lookup"><span data-stu-id="4b779-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="4b779-110">有关详细信息，请参阅 <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。</span><span class="sxs-lookup"><span data-stu-id="4b779-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="4b779-111">若要使你的用户能够使用 Lync Online 的单一登录，请安装 Active Directory 联合<http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="4b779-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="4b779-112">在本地部署中，在 Lync Server 命令行管理程序中键入以下 cmdlet，为 Lync Online 创建托管提供程序：</span><span class="sxs-lookup"><span data-stu-id="4b779-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="4b779-113">在本地边缘服务器上确认你的证书链支持与 Lync Online 的连接，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="4b779-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="4b779-114">可在此处下载此链：https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="4b779-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4b779-115">证书</span><span class="sxs-lookup"><span data-stu-id="4b779-115">Certificate</span></span></th>
    <th><span data-ttu-id="4b779-116">证书存储</span><span class="sxs-lookup"><span data-stu-id="4b779-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4b779-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="4b779-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="4b779-118">受信任根 CA</span><span class="sxs-lookup"><span data-stu-id="4b779-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4b779-119">Microsoft Internet Authority（新 CA 证书）</span><span class="sxs-lookup"><span data-stu-id="4b779-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="4b779-120">中间 CA</span><span class="sxs-lookup"><span data-stu-id="4b779-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4b779-121">MSIT Machine Auth CA2（新颁发的 CA2）</span><span class="sxs-lookup"><span data-stu-id="4b779-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="4b779-122">中间 CA</span><span class="sxs-lookup"><span data-stu-id="4b779-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="4b779-123">在本地 Active Directory 中，为本地 Lync 启用受影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4b779-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="4b779-124">为此，可以单独为每个相关用户键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4b779-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="4b779-125">也可以创建一个脚本，从文件中读取用户名，并将其作为输入提供给 Enable-CsUser cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4b779-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="4b779-126">运行 DirSync 将 Lync Online 用户与更新后的 Lync 本地用户同步。</span><span class="sxs-lookup"><span data-stu-id="4b779-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="4b779-127">更新一些 DNS 记录以将所有 SIP 流量定向到本地 Lync：</span><span class="sxs-lookup"><span data-stu-id="4b779-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="4b779-128">将 **lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4b779-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="4b779-129">更新 \*\**\_sip *。\_** 要解析为本地 Lync 的访问边缘服务的公共 IP 地址或 VIP 地址的 Tls.contoso.com SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4b779-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="4b779-130">更新 \*\**\_sipfederationtls *。\_** 要解析为本地 Lync 的访问边缘服务的公共 IP 地址或 VIP 地址的 Tcp.contoso.com SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="4b779-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="4b779-131">如果您的组织使用拆分 DNS（有时也称为“裂脑 DNS”），请确保将通过内部 DNS 区域解析名称的用户指向前端池。</span><span class="sxs-lookup"><span data-stu-id="4b779-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="4b779-132">键入`Get-CsUser` cmdlet 以检查要移动的用户的一些属性。</span><span class="sxs-lookup"><span data-stu-id="4b779-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="4b779-133">您希望确保 HostingProviderProxyFQDN 已设置为`"sipfed.online.lync.com"`且正确设置了 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="4b779-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="4b779-134">将 Lync Online 用户移动到本地 Lync。</span><span class="sxs-lookup"><span data-stu-id="4b779-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="4b779-135">要移动单个用户，请键入：</span><span class="sxs-lookup"><span data-stu-id="4b779-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="4b779-136">您可以使用 **Get-CsUSer** cmdlet 移动多名用户，通过 -Filter 参数选择有特定属性的用户。</span><span class="sxs-lookup"><span data-stu-id="4b779-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="4b779-137">例如，你可以通过筛选 {托管提供商-eq "sipfed.online.lync.om"} 选择所有 Lync Online 用户。</span><span class="sxs-lookup"><span data-stu-id="4b779-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="4b779-138">然后，可以用管道将返回的用户传递给 **Move-CsUSer** cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4b779-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="4b779-139">为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： *Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc*。</span><span class="sxs-lookup"><span data-stu-id="4b779-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="4b779-140">您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="4b779-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="4b779-141">确定 Office 365 租户的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="4b779-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="4b779-142">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="4b779-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="4b779-143">打开**Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="4b779-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="4b779-144">在显示**Lync 管理中心**的情况下，在地址栏中选择并将 URL 复制到**lync.com**。</span><span class="sxs-lookup"><span data-stu-id="4b779-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="4b779-145">示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b779-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="4b779-146">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="4b779-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="4b779-147">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="4b779-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="4b779-148">得到的 URL 是 **HostedMigrationOverrideUrl** 的值，应类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="4b779-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="4b779-149">rtcxds 数据库事务日志文件的默认大小上限为 16 GB。</span><span class="sxs-lookup"><span data-stu-id="4b779-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="4b779-150">如果您要一次性移动大量用户，特别是在启用镜像的情况下，这样的大小可能不够。</span><span class="sxs-lookup"><span data-stu-id="4b779-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="4b779-151">为解决此问题，您可以扩大文件大小，或者定期备份日志文件。</span><span class="sxs-lookup"><span data-stu-id="4b779-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="4b779-152">有关详细信息，请参阅 <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>。</span><span class="sxs-lookup"><span data-stu-id="4b779-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="4b779-153">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="4b779-153">This is an optional step.</span></span> <span data-ttu-id="4b779-154">如果需要集成 Exchange 2013 Online，那么需要使用额外的托管服务提供商。</span><span class="sxs-lookup"><span data-stu-id="4b779-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="4b779-155">有关详细信息，请参阅[配置本地 Lync Server 2013 与 Exchange Online 集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="4b779-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="4b779-p110">现在用户已经移动。为核查下表所示的用户属性具有正确的值，键入此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4b779-p110">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="4b779-158">Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="4b779-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="4b779-159">属性名称</span><span class="sxs-lookup"><span data-stu-id="4b779-159">Attribute name</span></span></th>
    <th><span data-ttu-id="4b779-160">Lync Online 用户的正确值</span><span class="sxs-lookup"><span data-stu-id="4b779-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="4b779-161">Lync on-本地用户的正确值</span><span class="sxs-lookup"><span data-stu-id="4b779-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4b779-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="4b779-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="4b779-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="4b779-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="4b779-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b779-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="4b779-165">SRV：</span><span class="sxs-lookup"><span data-stu-id="4b779-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4b779-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="4b779-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="4b779-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="4b779-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="4b779-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b779-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4b779-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b779-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4b779-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="4b779-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="4b779-171">已启用</span><span class="sxs-lookup"><span data-stu-id="4b779-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="4b779-172">True</span><span class="sxs-lookup"><span data-stu-id="4b779-172">True</span></span></p></td>
    <td><p><span data-ttu-id="4b779-173">True</span><span class="sxs-lookup"><span data-stu-id="4b779-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="4b779-174">已移动的每个用户都需要注销 Lync，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="4b779-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="4b779-175">登录时，用户应验证联系人列表，在必要情况下添加联系人。</span><span class="sxs-lookup"><span data-stu-id="4b779-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="4b779-176">请注意，计划的会议不会从 Lync Online 迁移到本地 Lync。</span><span class="sxs-lookup"><span data-stu-id="4b779-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="4b779-177">用户在迁移后需要重新安排这些会议。</span><span class="sxs-lookup"><span data-stu-id="4b779-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="4b779-178">更新 DNS 记录并将所有用户定向到本地时，HostingProvider 属性指示 Lync 用户使用 SRV 记录或将其定向到联机提供程序 "sipfed.online.lync.com"。</span><span class="sxs-lookup"><span data-stu-id="4b779-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

