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
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="26d89-103">从 Skype 业务联机到内部部署的移动用户</span><span class="sxs-lookup"><span data-stu-id="26d89-103">Move users from Skype for Business Online to on premises</span></span>
 
<span data-ttu-id="26d89-104">**摘要：**了解如何将用户帐户移到联机部署在 Skype 上业务服务器。</span><span class="sxs-lookup"><span data-stu-id="26d89-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>
  
<span data-ttu-id="26d89-105">您可能需要将用户帐户移到联机，内部部署，以确保用户在线穴，并在场所发现到另一个。</span><span class="sxs-lookup"><span data-stu-id="26d89-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="26d89-106">为可发现到另一个，所有用户必须都有内部部署 Active Directory 中存在。</span><span class="sxs-lookup"><span data-stu-id="26d89-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="26d89-107">有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="26d89-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="26d89-108">您可能想要在线将用户移动到在场所，例如，如果：</span><span class="sxs-lookup"><span data-stu-id="26d89-108">You might want to move online users to on premises, for example, if:</span></span> 
  
- <span data-ttu-id="26d89-109">有需要在内部部署中创建，然后移动到云的新用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>
    
- <span data-ttu-id="26d89-110">您的组织部署 Skype 业务联机之前该业务服务器部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="26d89-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="26d89-111">因此，第一，创建在云中的用户，现在需要转向内部部署，才能移动到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="26d89-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span> 
    
<span data-ttu-id="26d89-112">本主题介绍两种方案：</span><span class="sxs-lookup"><span data-stu-id="26d89-112">This topic describes two scenarios:</span></span>
  
- [<span data-ttu-id="26d89-113">将在线用户移动 — — 谁是最初在线 — — 为在部署</span><span class="sxs-lookup"><span data-stu-id="26d89-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [<span data-ttu-id="26d89-114">在场所移动到在线用户 （人最初是在场所）</span><span class="sxs-lookup"><span data-stu-id="26d89-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="26d89-115">将在线用户移动 — — 谁是最初在线 — — 为在部署</span><span class="sxs-lookup"><span data-stu-id="26d89-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="26d89-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="26d89-116"></span></span>

<span data-ttu-id="26d89-117">此部分仅适用于谁已创建和启用联机状态，但又不在内部部署 Active Directory 中具有帐户的用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span> 
  
<span data-ttu-id="26d89-118">开始将联机用户迁移到本地环境之前，请检查确保符合以下全部条件：</span><span class="sxs-lookup"><span data-stu-id="26d89-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>
  
- <span data-ttu-id="26d89-119">本地环境必须完全完成部署并通过验证。</span><span class="sxs-lookup"><span data-stu-id="26d89-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="26d89-120">有关详细信息，请参阅[部署 Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx)或[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md)，这取决于哪一个版本使用的场所。</span><span class="sxs-lookup"><span data-stu-id="26d89-120">For more information, see [Deploying Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span> 
    
- <span data-ttu-id="26d89-121">您在线租户必须配置为远程 PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="26d89-121">Your online tenant must be configured for remote PowerShell access.</span></span>
    
    <span data-ttu-id="26d89-122">若要执行此操作，首先安装 Skype 业务在线连接器模块 Windows PowerShell，您可以在此处： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="26d89-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
    
    <span data-ttu-id="26d89-123">安装本模块后，您可以通过键入以下 cmdlet Skype 业务服务器管理外壳程序的建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="26d89-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>
    
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

    <span data-ttu-id="26d89-124">有关如何建立远程 PowerShell 会话与 Skype 的在线业务的详细信息，请参阅[连接到 Lync 在线通过使用 Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx)。</span><span class="sxs-lookup"><span data-stu-id="26d89-124">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
    
    <span data-ttu-id="26d89-125">有关使用 Skype 业务在线连接器 PowerShell 模块的详细信息，请参阅[管理 Lync Online 对使用 Windows PowerShell](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx)。</span><span class="sxs-lookup"><span data-stu-id="26d89-125">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
    
- <span data-ttu-id="26d89-126">您在线租户必须配置为共享的 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="26d89-126">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="26d89-127">若要执行此操作，首先启动远程 Powershell 会话与 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="26d89-127">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="26d89-128">然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="26d89-128">Then run the following cmdlet:</span></span>
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="26d89-129">保持联机移动到最后，直到"真"，没有用户的 SharedSipAddressSpace 特性需求保持在场所。</span><span class="sxs-lookup"><span data-stu-id="26d89-129">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span> 
  
<span data-ttu-id="26d89-130">您完成这些步骤后，您可以迁移的用户帐户，如下面的过程所述：</span><span class="sxs-lookup"><span data-stu-id="26d89-130">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="26d89-131">最初到内部部署中启用联机移动用户帐户</span><span class="sxs-lookup"><span data-stu-id="26d89-131">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="26d89-132">首先，确保组织配置为混合，包括 Azure Active Directory Connect 和同步工具。</span><span class="sxs-lookup"><span data-stu-id="26d89-132">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="26d89-133">有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="26d89-133">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
    
  - <span data-ttu-id="26d89-134">在内部部署，为业务服务器管理外壳，Skype 键入以下 cmdlet 创建联机业务 Skype 的承载提供程序。</span><span class="sxs-lookup"><span data-stu-id="26d89-134">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="26d89-135">可以对 Identity 和 Name 参数使用您想要的任何值。</span><span class="sxs-lookup"><span data-stu-id="26d89-135">You can use whatever value you want for the Identity and Name parameters.</span></span>
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="26d89-136">确认内部部署边缘服务器上有证书链，使连接到 Skype 的在线业务下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="26d89-136">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="26d89-137">您可以下载此链此处： [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip)。</span><span class="sxs-lookup"><span data-stu-id="26d89-137">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>
    
|<span data-ttu-id="26d89-138">**证书**</span><span class="sxs-lookup"><span data-stu-id="26d89-138">**Certificate**</span></span>|<span data-ttu-id="26d89-139">**证书存储区**</span><span class="sxs-lookup"><span data-stu-id="26d89-139">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26d89-140">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="26d89-140">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="26d89-141">受信任根 CA</span><span class="sxs-lookup"><span data-stu-id="26d89-141">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="26d89-142">Microsoft Internet Authority（新 CA 证书）</span><span class="sxs-lookup"><span data-stu-id="26d89-142">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="26d89-143">中间 CA</span><span class="sxs-lookup"><span data-stu-id="26d89-143">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="26d89-144">MSIT Machine Auth CA2（新颁发的 CA2）</span><span class="sxs-lookup"><span data-stu-id="26d89-144">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="26d89-145">中间 CA</span><span class="sxs-lookup"><span data-stu-id="26d89-145">Intermediate CA</span></span>  <br/> |
   
3. <span data-ttu-id="26d89-146">在内部部署 Active Directory 为内部部署的业务服务器 2015年启用 Skype 为受影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="26d89-146">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="26d89-147">为此，可以单独为每个相关用户键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="26d89-147">You can do this for an individual user by typing the following cmdlet:</span></span> 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="26d89-148">也可以创建一个脚本，从文件中读取用户名，并将其作为输入提供给 Enable-CsUser cmdlet：</span><span class="sxs-lookup"><span data-stu-id="26d89-148">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="26d89-149">更新现有内部用户与同步在线的用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-149">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="26d89-150">有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。</span><span class="sxs-lookup"><span data-stu-id="26d89-150">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>
    
5. <span data-ttu-id="26d89-151">更新下面的 DNS 记录，将定向到内部部署的所有 SIP 通信：</span><span class="sxs-lookup"><span data-stu-id="26d89-151">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>
    
  - <span data-ttu-id="26d89-152">将 **lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="26d89-152">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
  - <span data-ttu-id="26d89-153">更新 * * *_sip* 。 _tls.contoso.com** SRV 记录解析为 Lync 部署的访问边缘服务的公共 IP 或 VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="26d89-153">Update the ** *_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
  - <span data-ttu-id="26d89-154">更新 * * *_sipfederationtls* 。 _tcp.contoso.com** SRV 记录的内部业务服务器 2015年到 Skype 的访问边缘服务的公共 IP 或 VIP 地址解析。</span><span class="sxs-lookup"><span data-stu-id="26d89-154">Update the ** *_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>
    
  - <span data-ttu-id="26d89-155">如果您的组织使用拆分 DNS （有时称为"分裂 DNS"），请确保通过内部 DNS 区域的名称解析的用户被定向到前结束池。</span><span class="sxs-lookup"><span data-stu-id="26d89-155">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>
    
6. <span data-ttu-id="26d89-156">类型`Get-CsUser`用于检查您将移动用户有关的某些属性。</span><span class="sxs-lookup"><span data-stu-id="26d89-156">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="26d89-157">您需要确保 HostingProviderProxyFQDN 设置为`"sipfed.online.lync.com"`，且 SIP 地址设置正确。</span><span class="sxs-lookup"><span data-stu-id="26d89-157">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>
    
7. <span data-ttu-id="26d89-158">在场所移动到在线用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-158">Move online users to on premises.</span></span>
    
    <span data-ttu-id="26d89-159">要移动单个用户，请键入：</span><span class="sxs-lookup"><span data-stu-id="26d89-159">To move a single user, type this:</span></span>
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="26d89-160">您可以通过使用**Get CsUSer** cmdlet 移动多个用户使用的筛选器参数选择具有特定属性的用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-160">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="26d89-161">例如，您可以通过筛选 {承载提供程序-eq"sipfed.online.lync.om"} 选择所有在线的用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-161">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="26d89-162">您可以通过管道**移动 CsUSer** cmdlet，返回的用户，如下所示。</span><span class="sxs-lookup"><span data-stu-id="26d89-162">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="26d89-163">指定**HostedMigrationOverrideUrl**参数必须到池承载迁移服务正在运行，按以下格式的 URL 的 URL 的格式： _Https://\<池的 FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="26d89-163">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
    
    <span data-ttu-id="26d89-164">您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="26d89-164">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="26d89-165">确定 Office 365 租户的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="26d89-165">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="26d89-166">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="26d89-166">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="26d89-167">打开“Skype for Business 管理中心”****。</span><span class="sxs-lookup"><span data-stu-id="26d89-167">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="26d89-168">显示“Skype for Business 管理中心”****后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="26d89-168">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="26d89-169">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="26d89-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="26d89-170">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="26d89-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="26d89-171">所生成的 URL，这是**HostedMigrationOverrideUrl**的值，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="26d89-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > <span data-ttu-id="26d89-172">rtcxds 数据库事务日志文件的默认大小上限为 16 GB。</span><span class="sxs-lookup"><span data-stu-id="26d89-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="26d89-173">这可能不是足够大，如果要移动大量的用户，尤其是如果您有启用镜像。</span><span class="sxs-lookup"><span data-stu-id="26d89-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="26d89-174">为解决此问题，您可以扩大文件大小，或者定期备份日志文件。</span><span class="sxs-lookup"><span data-stu-id="26d89-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="26d89-175">有关详细信息，请参阅[https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725)。</span><span class="sxs-lookup"><span data-stu-id="26d89-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span> 
  
8. <span data-ttu-id="26d89-176">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="26d89-176">This is an optional step.</span></span> <span data-ttu-id="26d89-177">如果需要集成 Exchange 2013 Online，那么需要使用额外的托管服务提供商。</span><span class="sxs-lookup"><span data-stu-id="26d89-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="26d89-178">有关详细信息，请参阅[配置业务服务器 2015年和 Outlook Web App 内部 Skype 之间的集成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="26d89-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>
    
9. <span data-ttu-id="26d89-p114">现在用户已经移动。为核查下表所示的用户属性具有正确的值，键入此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="26d89-p114">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span> 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="26d89-181">**活动目录属性**</span><span class="sxs-lookup"><span data-stu-id="26d89-181">**Active Directory attribute**</span></span>|<span data-ttu-id="26d89-182">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="26d89-182">**Attribute name**</span></span>|<span data-ttu-id="26d89-183">**在线用户的正确值**</span><span class="sxs-lookup"><span data-stu-id="26d89-183">**Correct value for Online user**</span></span>|<span data-ttu-id="26d89-184">**对于内部用户正确的值**</span><span class="sxs-lookup"><span data-stu-id="26d89-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26d89-185">msRTCSIP DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="26d89-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="26d89-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="26d89-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="26d89-187">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="26d89-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="26d89-188">SRV：</span><span class="sxs-lookup"><span data-stu-id="26d89-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="26d89-189">msRTCSIP PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="26d89-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="26d89-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="26d89-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="26d89-191">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="26d89-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="26d89-192">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="26d89-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="26d89-193">sRTCSIP UserEnabled</span><span class="sxs-lookup"><span data-stu-id="26d89-193">sRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="26d89-194">已启用</span><span class="sxs-lookup"><span data-stu-id="26d89-194">Enabled</span></span>  <br/> |<span data-ttu-id="26d89-195">True</span><span class="sxs-lookup"><span data-stu-id="26d89-195">True</span></span>  <br/> |<span data-ttu-id="26d89-196">True</span><span class="sxs-lookup"><span data-stu-id="26d89-196">True</span></span>  <br/> |
   
10. <span data-ttu-id="26d89-p115">每个已迁移的用户需要先注销，然后重新登录。登录时，用户应验证联系人列表，在必要情况下添加联系人。</span><span class="sxs-lookup"><span data-stu-id="26d89-p115">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="26d89-p116">请注意，排定的会议不会从联机迁移到本地。用户在迁移后需要重新安排这些会议。</span><span class="sxs-lookup"><span data-stu-id="26d89-p116">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="26d89-201">HostingProvider 属性更新 DNS 记录和所有用户将被都定向到内部部署后，指导用户使用 SRV 记录，或者将它们应用到的联机提供"sipfed.online.lync.com"。</span><span class="sxs-lookup"><span data-stu-id="26d89-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="26d89-202">在场所移动到在线用户 （人最初是在场所）</span><span class="sxs-lookup"><span data-stu-id="26d89-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="26d89-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="26d89-203"></span></span>

<span data-ttu-id="26d89-204">此部分仅适用于创建和启用内部部署，然后从内部部署移动到在线用户。</span><span class="sxs-lookup"><span data-stu-id="26d89-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span> 
  
- <span data-ttu-id="26d89-205">运行以下 cmdlet 以后退用户从 Skype 的在线业务到内部部署，替换更正您的环境的值**标识**和**目标**参数的值：</span><span class="sxs-lookup"><span data-stu-id="26d89-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="26d89-206">为**HostedMigrationOverrideUrl**参数指定的 URL 的格式必须是到池承载迁移服务正在运行，按以下格式的 URL:</span><span class="sxs-lookup"><span data-stu-id="26d89-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>
  
 <span data-ttu-id="26d89-207">_Https://\<池的 FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="26d89-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="26d89-208">您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="26d89-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="26d89-209">确定 Office 365 租户的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="26d89-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="26d89-210">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="26d89-210">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="26d89-211">打开“Skype for Business 管理中心”****。</span><span class="sxs-lookup"><span data-stu-id="26d89-211">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="26d89-212">显示“Skype for Business 管理中心”****后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="26d89-212">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="26d89-213">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="26d89-213">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="26d89-214">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="26d89-214">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="26d89-215">所生成的 URL，这是**HostedMigrationOverrideUrl**的值，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="26d89-215">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

