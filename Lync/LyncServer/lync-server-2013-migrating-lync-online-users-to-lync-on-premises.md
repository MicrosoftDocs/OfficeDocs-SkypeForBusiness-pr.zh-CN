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

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="3c3b2-102">将 Lync Online 用户迁移到 Lync Server 2013 中的 Lync 本地</span><span class="sxs-lookup"><span data-stu-id="3c3b2-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c3b2-103">_**上次修改的主题：** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="3c3b2-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="3c3b2-104">这些步骤只是在部署 Lync 本地之前为 lync Online 中最初启用 Lync 的用户帐户所必需的。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="3c3b2-105">若要移动最初为本地启用 Lync 的用户，然后将其移动到 Lync Online，请参阅<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理用户</A>。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="3c3b2-106">此外，要移动的所有用户都必须在本地 Active Directory 中拥有帐户。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="3c3b2-107">将 Lync Online 中最初启用的用户帐户迁移到本地 Lync</span><span class="sxs-lookup"><span data-stu-id="3c3b2-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="3c3b2-108">首先，请确保您的组织已配置了混合。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="3c3b2-109">安装 Azure Active Directory 同步工具。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="3c3b2-110">有关详细信息，请参阅 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="3c3b2-111">若要使用户能够使用 Lync Online 的单一登录，请安装 Active Directory 联合身份验证服务 <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="3c3b2-112">在本地部署中，在 Lync Server 命令行管理程序中，键入以下 cmdlet 以创建 Lync Online 的托管提供程序：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="3c3b2-113">确认在本地边缘服务器上，您具有允许连接到 Lync Online 的证书链，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="3c3b2-114">你可以在此处下载此链：https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="3c3b2-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="3c3b2-115">证书</span><span class="sxs-lookup"><span data-stu-id="3c3b2-115">Certificate</span></span></th>
    <th><span data-ttu-id="3c3b2-116">证书存储</span><span class="sxs-lookup"><span data-stu-id="3c3b2-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="3c3b2-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="3c3b2-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-118">受信任的根 CA</span><span class="sxs-lookup"><span data-stu-id="3c3b2-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3c3b2-119">Microsoft Internet 颁发机构（新 CA 证书）</span><span class="sxs-lookup"><span data-stu-id="3c3b2-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-120">中间 CA</span><span class="sxs-lookup"><span data-stu-id="3c3b2-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3c3b2-121">MSIT Machine Auth CA2 （新颁发 CA2）</span><span class="sxs-lookup"><span data-stu-id="3c3b2-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-122">中间 CA</span><span class="sxs-lookup"><span data-stu-id="3c3b2-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="3c3b2-123">在本地 Active Directory 中，为本地 Lync 启用受影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="3c3b2-124">您可以通过键入以下 cmdlet 为单个用户执行此操作：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="3c3b2-125">或者，您可以创建一个脚本，从文件中读取用户名并将其作为 Get-csuser cmdlet 的输入提供：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="3c3b2-126">运行 DirSync 以将 Lync Online 用户与更新的 Lync 本地用户同步。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="3c3b2-127">更新一些 DNS 记录以将所有 SIP 流量定向到本地 Lync：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="3c3b2-128">将**Lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="3c3b2-129">更新 \*\*\* \_ sip *。 \_*\* 要解析为本地 Lync 服务访问边缘服务的公共 IP 或 VIP 地址的 Tls.contoso.com SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="3c3b2-130">更新 \*\*\* \_ sipfederationtls *。 \_*\* 要解析为本地 Lync 服务访问边缘服务的公共 IP 或 VIP 地址的 Tcp.contoso.com SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="3c3b2-131">如果您的组织使用拆分 DNS （有时称为 "split-大脑 DNS"），请确保通过内部 DNS 区域解析名称的用户被定向到前端池。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="3c3b2-132">键入 `Get-CsUser` cmdlet 以检查您要移动的用户的一些属性。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="3c3b2-133">您希望确保将 HostingProviderProxyFQDN 设置为 `"sipfed.online.lync.com"` ，并且正确设置了 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="3c3b2-134">将 Lync Online 用户移动到本地 Lync。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="3c3b2-135">若要移动单个用户，请键入：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="3c3b2-136">您可以通过使用带有– Filter 参数的**get-csuser** cmdlet 来移动多个用户，以选择具有特定属性的用户。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="3c3b2-137">例如，可以通过筛选 {托管提供商– eq "sipfed.online.lync.om"} 选择所有 Lync Online 用户。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="3c3b2-138">然后可以将返回的用户通过管道传递给**get-csuser** cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="3c3b2-139">为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： *Https:// \< pool FQDN \> /HostedMigration/hostedmigrationService.svc*。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="3c3b2-140">您可以通过查看适用于 Microsoft 365 或 Office 365 组织帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="3c3b2-141">确定您的 organizaton 的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="3c3b2-141">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="3c3b2-142">以管理员身份登录到你的 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-142">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="3c3b2-143">打开**Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="3c3b2-144">在 " **Lync 管理中心**" 显示的情况下，选择并将地址栏中的 URL 复制到**lync.com**。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="3c3b2-145">示例 URL 的外观类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="3c3b2-146">将 URL 中的**webdir**替换为**admin**，从而产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="3c3b2-147">将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="3c3b2-148">生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="3c3b2-149">Rtcxds 数据库的事务日志文件的默认最大大小为 16 GB。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="3c3b2-150">如果一次移动大量用户，尤其是在启用了镜像的情况下，这可能不够大。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="3c3b2-151">若要解决此情况，可以增加文件大小，也可以定期备份日志文件。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="3c3b2-152">有关详细信息，请参阅 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="3c3b2-153">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-153">This is an optional step.</span></span> <span data-ttu-id="3c3b2-154">如果需要与 Exchange 2013 Online 集成，则需要使用其他承载提供程序。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="3c3b2-155">有关详细信息，请参阅[配置本地 Lync Server 2013 与 Exchange Online 集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="3c3b2-156">现在将移动用户。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-156">The users are now moved.</span></span> <span data-ttu-id="3c3b2-157">若要检查用户是否具有下表中所示属性的正确值，请键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3c3b2-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="3c3b2-158">Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="3c3b2-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="3c3b2-159">属性名</span><span class="sxs-lookup"><span data-stu-id="3c3b2-159">Attribute name</span></span></th>
    <th><span data-ttu-id="3c3b2-160">Lync Online 用户的正确值</span><span class="sxs-lookup"><span data-stu-id="3c3b2-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="3c3b2-161">Lync on –本地用户的正确值</span><span class="sxs-lookup"><span data-stu-id="3c3b2-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="3c3b2-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3c3b2-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="3c3b2-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c3b2-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-165">SRV</span><span class="sxs-lookup"><span data-stu-id="3c3b2-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3c3b2-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3c3b2-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="3c3b2-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3c3b2-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3c3b2-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3c3b2-170">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="3c3b2-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-171">已启用</span><span class="sxs-lookup"><span data-stu-id="3c3b2-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-172">True</span><span class="sxs-lookup"><span data-stu-id="3c3b2-172">True</span></span></p></td>
    <td><p><span data-ttu-id="3c3b2-173">True</span><span class="sxs-lookup"><span data-stu-id="3c3b2-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="3c3b2-174">已移动的每个用户都需要注销 Lync，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="3c3b2-175">当他们登录时，应验证其联系人列表，并在需要时添加联系人。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="3c3b2-176">请注意，安排的会议不会从 Lync Online 迁移到本地 Lync。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="3c3b2-177">用户需要在移动后重新安排这些会议。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="3c3b2-178">更新 DNS 记录并将所有用户定向到本地时，HostingProvider 属性指示 Lync 用户是使用 SRV 记录，还是将其定向到联机提供程序 "sipfed.online.lync.com"。</span><span class="sxs-lookup"><span data-stu-id="3c3b2-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

