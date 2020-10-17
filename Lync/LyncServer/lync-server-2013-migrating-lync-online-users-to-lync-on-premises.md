---
title: Lync Server 2013：将 Lync Online 用户迁移到 Lync 本地
description: Lync Server 2013：将 Lync Online 用户迁移到本地 Lync。
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
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560998"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="301bd-103">将 Lync Online 用户迁移到 Lync Server 2013 中的 Lync 本地</span><span class="sxs-lookup"><span data-stu-id="301bd-103">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="301bd-104">_**上次修改的主题：** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="301bd-104">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="301bd-105">这些步骤只是在部署 Lync 本地之前为 lync Online 中最初启用 Lync 的用户帐户所必需的。</span><span class="sxs-lookup"><span data-stu-id="301bd-105">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="301bd-106">若要移动最初为本地启用 Lync 的用户，然后将其移动到 Lync Online，请参阅 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理用户</A>。</span><span class="sxs-lookup"><span data-stu-id="301bd-106">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="301bd-107">此外，要移动的所有用户都必须在本地 Active Directory 中拥有帐户。</span><span class="sxs-lookup"><span data-stu-id="301bd-107">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="301bd-108">将 Lync Online 中最初启用的用户帐户迁移到本地 Lync</span><span class="sxs-lookup"><span data-stu-id="301bd-108">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="301bd-109">首先，请确保您的组织已配置了混合。</span><span class="sxs-lookup"><span data-stu-id="301bd-109">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="301bd-110">安装 Azure Active Directory 同步工具。</span><span class="sxs-lookup"><span data-stu-id="301bd-110">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="301bd-111">有关详细信息，请参阅 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。</span><span class="sxs-lookup"><span data-stu-id="301bd-111">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="301bd-112">若要使用户能够使用 Lync Online 的单一登录，请安装 Active Directory 联合身份验证服务 <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="301bd-112">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="301bd-113">在本地部署中，在 Lync Server 命令行管理程序中，键入以下 cmdlet 以创建 Lync Online 的托管提供程序：</span><span class="sxs-lookup"><span data-stu-id="301bd-113">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="301bd-114">确认在本地边缘服务器上，您具有允许连接到 Lync Online 的证书链，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="301bd-114">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="301bd-115">你可以在此处下载此链： https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="301bd-115">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="301bd-116">证书</span><span class="sxs-lookup"><span data-stu-id="301bd-116">Certificate</span></span></th>
    <th><span data-ttu-id="301bd-117">证书存储</span><span class="sxs-lookup"><span data-stu-id="301bd-117">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="301bd-118">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="301bd-118">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="301bd-119">受信任的根 CA</span><span class="sxs-lookup"><span data-stu-id="301bd-119">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="301bd-120">Microsoft Internet 颁发机构 (新的 CA 证书) </span><span class="sxs-lookup"><span data-stu-id="301bd-120">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="301bd-121">中间 CA</span><span class="sxs-lookup"><span data-stu-id="301bd-121">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="301bd-122">MSIT Machine Auth CA2 (新的颁发 CA2) </span><span class="sxs-lookup"><span data-stu-id="301bd-122">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="301bd-123">中间 CA</span><span class="sxs-lookup"><span data-stu-id="301bd-123">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="301bd-124">在本地 Active Directory 中，为本地 Lync 启用受影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="301bd-124">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="301bd-125">您可以通过键入以下 cmdlet 为单个用户执行此操作：</span><span class="sxs-lookup"><span data-stu-id="301bd-125">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="301bd-126">或者，您可以创建一个脚本，从文件中读取用户名并将其作为 Enable-CsUser cmdlet 的输入提供：</span><span class="sxs-lookup"><span data-stu-id="301bd-126">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="301bd-127">运行 DirSync 以将 Lync Online 用户与更新的 Lync 本地用户同步。</span><span class="sxs-lookup"><span data-stu-id="301bd-127">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="301bd-128">更新一些 DNS 记录以将所有 SIP 流量定向到本地 Lync：</span><span class="sxs-lookup"><span data-stu-id="301bd-128">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="301bd-129">将 **Lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="301bd-129">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="301bd-130">更新 \*\*\* \_ sip *。 \_*\* 要解析为本地 Lync 服务访问边缘服务的公共 IP 或 VIP 地址的 Tls.contoso.com SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="301bd-130">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="301bd-131">更新 \*\*\* \_ sipfederationtls *。 \_*\* 要解析为本地 Lync 服务访问边缘服务的公共 IP 或 VIP 地址的 Tcp.contoso.com SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="301bd-131">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="301bd-132">如果您的组织使用的是拆分 DNS (有时称为 "拆分的 DNS" ) ，请确保将通过内部 DNS 区域解析名称的用户定向到前端池。</span><span class="sxs-lookup"><span data-stu-id="301bd-132">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="301bd-133">键入 `Get-CsUser` cmdlet 以检查您要移动的用户的一些属性。</span><span class="sxs-lookup"><span data-stu-id="301bd-133">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="301bd-134">您希望确保将 HostingProviderProxyFQDN 设置为 `"sipfed.online.lync.com"` ，并且正确设置了 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="301bd-134">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="301bd-135">将 Lync Online 用户移动到本地 Lync。</span><span class="sxs-lookup"><span data-stu-id="301bd-135">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="301bd-136">若要移动单个用户，请键入：</span><span class="sxs-lookup"><span data-stu-id="301bd-136">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="301bd-137">您可以通过使用带有– Filter 参数的 **get-csuser** cmdlet 来移动多个用户，以选择具有特定属性的用户。</span><span class="sxs-lookup"><span data-stu-id="301bd-137">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="301bd-138">例如，可以通过筛选 {托管提供商– eq "sipfed.online.lync.om"} 选择所有 Lync Online 用户。</span><span class="sxs-lookup"><span data-stu-id="301bd-138">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="301bd-139">然后可以将返回的用户通过管道传递给 **get-csuser** cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="301bd-139">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="301bd-140">为 **HostedMigrationOverrideUrl** 参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： *Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*。</span><span class="sxs-lookup"><span data-stu-id="301bd-140">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="301bd-141">您可以通过查看适用于 Microsoft 365 或 Office 365 组织帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="301bd-141">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="301bd-142">确定您的 organizaton 的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="301bd-142">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="301bd-143">以管理员身份登录到你的 Microsoft 365 或 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="301bd-143">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="301bd-144">打开 **Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="301bd-144">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="301bd-145">在 " **Lync 管理中心** " 显示的情况下，选择并将地址栏中的 URL 复制到 **lync.com**。</span><span class="sxs-lookup"><span data-stu-id="301bd-145">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="301bd-146">示例 URL 的外观类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="301bd-146">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="301bd-147">将 URL 中的 **webdir** 替换为 **admin**，从而产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="301bd-147">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="301bd-148">将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="301bd-148">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="301bd-149">生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：</span><span class="sxs-lookup"><span data-stu-id="301bd-149">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="301bd-150">Rtcxds 数据库的事务日志文件的默认最大大小为 16 GB。</span><span class="sxs-lookup"><span data-stu-id="301bd-150">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="301bd-151">如果一次移动大量用户，尤其是在启用了镜像的情况下，这可能不够大。</span><span class="sxs-lookup"><span data-stu-id="301bd-151">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="301bd-152">若要解决此情况，可以增加文件大小，也可以定期备份日志文件。</span><span class="sxs-lookup"><span data-stu-id="301bd-152">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="301bd-153">有关详细信息，请参阅 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 。</span><span class="sxs-lookup"><span data-stu-id="301bd-153">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="301bd-154">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="301bd-154">This is an optional step.</span></span> <span data-ttu-id="301bd-155">如果需要与 Exchange 2013 Online 集成，则需要使用其他承载提供程序。</span><span class="sxs-lookup"><span data-stu-id="301bd-155">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="301bd-156">有关详细信息，请参阅 [配置本地 Lync Server 2013 与 Exchange Online 集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="301bd-156">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="301bd-157">现在将移动用户。</span><span class="sxs-lookup"><span data-stu-id="301bd-157">The users are now moved.</span></span> <span data-ttu-id="301bd-158">若要检查用户是否具有下表中所示属性的正确值，请键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="301bd-158">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="301bd-159">Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="301bd-159">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="301bd-160">属性名</span><span class="sxs-lookup"><span data-stu-id="301bd-160">Attribute name</span></span></th>
    <th><span data-ttu-id="301bd-161">Lync Online 用户的正确值</span><span class="sxs-lookup"><span data-stu-id="301bd-161">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="301bd-162">Lync on –本地用户的正确值</span><span class="sxs-lookup"><span data-stu-id="301bd-162">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="301bd-163">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="301bd-163">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="301bd-164">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="301bd-164">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="301bd-165">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="301bd-165">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="301bd-166">SRV</span><span class="sxs-lookup"><span data-stu-id="301bd-166">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="301bd-167">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="301bd-167">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="301bd-168">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="301bd-168">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="301bd-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="301bd-169">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="301bd-170">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="301bd-170">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="301bd-171">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="301bd-171">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="301bd-172">已启用</span><span class="sxs-lookup"><span data-stu-id="301bd-172">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="301bd-173">True</span><span class="sxs-lookup"><span data-stu-id="301bd-173">True</span></span></p></td>
    <td><p><span data-ttu-id="301bd-174">True</span><span class="sxs-lookup"><span data-stu-id="301bd-174">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="301bd-175">已移动的每个用户都需要注销 Lync，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="301bd-175">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="301bd-176">当他们登录时，应验证其联系人列表，并在需要时添加联系人。</span><span class="sxs-lookup"><span data-stu-id="301bd-176">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="301bd-177">请注意，安排的会议不会从 Lync Online 迁移到本地 Lync。</span><span class="sxs-lookup"><span data-stu-id="301bd-177">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="301bd-178">用户需要在移动后重新安排这些会议。</span><span class="sxs-lookup"><span data-stu-id="301bd-178">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="301bd-179">更新 DNS 记录并将所有用户定向到本地时，HostingProvider 属性指示 Lync 用户是使用 SRV 记录，还是将其定向到联机提供程序 "sipfed.online.lync.com"。</span><span class="sxs-lookup"><span data-stu-id="301bd-179">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

