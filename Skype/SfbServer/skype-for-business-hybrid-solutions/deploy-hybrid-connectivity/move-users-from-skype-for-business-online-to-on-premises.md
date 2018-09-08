---
title: Skype 业务 online 到本地移动用户
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 摘要： 了解如何移动用户帐户从联机到本地 Skype 中的业务服务器。
ms.openlocfilehash: 77ef2ad5cf22632d3f81f35fc0c3a20054303e96
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884529"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="e4dd9-103">Skype 业务 online 到本地移动用户</span><span class="sxs-lookup"><span data-stu-id="e4dd9-103">Move users from Skype for Business Online to on premises</span></span>

<span data-ttu-id="e4dd9-104">**摘要：** 了解如何移动用户帐户从联机到本地 Skype 中的业务服务器。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>

<span data-ttu-id="e4dd9-105">您可能需要将用户帐户从联机到移动本地以确保用户驻留在线和本地是到另一个可供搜索。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="e4dd9-106">若要向其他可供搜索，所有用户必须都具有内部部署 Active Directory 中的状态。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="e4dd9-107">有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="e4dd9-108">您可能需要 online 将用户移动到在本地，例如，如果：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-108">You might want to move online users to on premises, for example, if:</span></span>

- <span data-ttu-id="e4dd9-109">您必须是在本地创建，然后移到云中所需要的新用户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>

- <span data-ttu-id="e4dd9-110">您的组织部署业务 online Skype，其业务服务器部署 Skype 之前。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="e4dd9-111">因此，您有首先，创建在云中的用户，并且现在需要移至本地移动到 Skype 业务 online 才能。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span>

<span data-ttu-id="e4dd9-112">本主题介绍两种方案：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-112">This topic describes two scenarios:</span></span>

- [<span data-ttu-id="e4dd9-113">移动 online 用户 — 谁是最初联机 — 为本地</span><span class="sxs-lookup"><span data-stu-id="e4dd9-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [<span data-ttu-id="e4dd9-114">本地移动到联机用户 （人员最初在本地）</span><span class="sxs-lookup"><span data-stu-id="e4dd9-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="e4dd9-115">移动 online 用户 — 谁是最初联机 — 为本地</span><span class="sxs-lookup"><span data-stu-id="e4dd9-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="e4dd9-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="e4dd9-116"></span></span>

<span data-ttu-id="e4dd9-117">本节仅适用于用户创建和启用联机状态，但用户在本地 Active Directory 中没有帐户的用户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span>

<span data-ttu-id="e4dd9-118">开始将联机用户迁移到本地环境之前，请检查确保符合以下全部条件：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>

- <span data-ttu-id="e4dd9-119">本地环境必须完全完成部署并通过验证。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="e4dd9-120">有关详细信息，请参阅[Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx)或[部署的 Business Server 2015 的 Skype](../../deploy/deploy.md)，具体取决于哪个版本将在本地。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-120">For more information, see [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span>

- <span data-ttu-id="e4dd9-121">远程 PowerShell 访问，必须配置您的 online 租户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-121">Your online tenant must be configured for remote PowerShell access.</span></span>

    <span data-ttu-id="e4dd9-122">若要执行此操作，首先安装 for Business 联机连接器模块 Skype 用于 Windows PowerShell，您可以在此处获取： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>

    <span data-ttu-id="e4dd9-123">安装本模块后，您可以通过键入以下 cmdlet Skype 中的业务 Server 命令行管理程序建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>

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

    <span data-ttu-id="e4dd9-124">有关使用 PowerShell 和 Skype 业务 online 的详细信息，请参阅[Windows PowerShell 将计算机设置](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e4dd9-124">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>

- <span data-ttu-id="e4dd9-125">必须为共享的 SIP 地址空间配置您的 online 租户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-125">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="e4dd9-126">若要执行此操作，首先开始远程 Powershell 会话 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-126">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="e4dd9-127">然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-127">Then run the following cmdlet:</span></span>

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="e4dd9-128">在本地保留 SharedSipAddressSpace 属性需要保留搕 Rue 联机移动到是最终的直到和任何用户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-128">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span>

<span data-ttu-id="e4dd9-129">完成这些步骤后，您可以迁移用户帐户，如下面的过程中所述：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-129">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="e4dd9-130">移动最初部署到的本地部署 online 启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="e4dd9-130">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="e4dd9-131">首先，确保组织配置为混合，包括 Azure Active Directory Connect 和同步工具。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-131">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="e4dd9-132">有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-132">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>

  - <span data-ttu-id="e4dd9-133">有关您的本地部署、 业务 Server Management Shell，Skype 中键入以下 cmdlet 以创建业务联机 Skype 承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-133">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="e4dd9-134">可以对 Identity 和 Name 参数使用您想要的任何值。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-134">You can use whatever value you want for the Identity and Name parameters.</span></span>

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="e4dd9-135">确认在内部部署边缘服务器，您有证书链，连接到 Skype 业务 online 下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-135">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="e4dd9-136">您可以下载此链此处： [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-136">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>

|<span data-ttu-id="e4dd9-137">**证书**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-137">**Certificate**</span></span>|<span data-ttu-id="e4dd9-138">**证书存储**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-138">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e4dd9-139">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="e4dd9-139">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="e4dd9-140">受信任根 CA</span><span class="sxs-lookup"><span data-stu-id="e4dd9-140">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="e4dd9-141">Microsoft Internet Authority（新 CA 证书）</span><span class="sxs-lookup"><span data-stu-id="e4dd9-141">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="e4dd9-142">中间 CA</span><span class="sxs-lookup"><span data-stu-id="e4dd9-142">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="e4dd9-143">MSIT Machine Auth CA2（新颁发的 CA2）</span><span class="sxs-lookup"><span data-stu-id="e4dd9-143">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="e4dd9-144">中间 CA</span><span class="sxs-lookup"><span data-stu-id="e4dd9-144">Intermediate CA</span></span>  <br/> |

3. <span data-ttu-id="e4dd9-145">您的本地 Active Directory 中，为本地业务服务器 2015年启用的 Skype 受影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-145">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="e4dd9-146">为此，可以单独为每个相关用户键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-146">You can do this for an individual user by typing the following cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="e4dd9-147">也可以创建一个脚本，从文件中读取用户名，并将其作为输入提供给 Enable-CsUser cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-147">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="e4dd9-148">更新内部部署用户同步联机用户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-148">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="e4dd9-149">有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-149">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>

5. <span data-ttu-id="e4dd9-150">更新定向到内部部署的所有 SIP 流量的以下 DNS 记录：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-150">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>

  - <span data-ttu-id="e4dd9-151">将 **lyncdiscover.contoso.com** A 记录更新为指向本地反向代理服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-151">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>

  - <span data-ttu-id="e4dd9-152">更新***_sip* 。 _tls.contoso.com** SRV 记录来解析到 Lync 内部部署的访问边缘服务公用 IP 或 VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-152">Update the ***_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>

  - <span data-ttu-id="e4dd9-153">更新***_sipfederationtls* 。 _tcp.contoso.com** SRV 记录以的业务服务器 2015年本地解析为 Skype 的访问边缘服务公用 IP 或 VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-153">Update the ***_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>

  - <span data-ttu-id="e4dd9-154">如果组织使用拆分 DNS （有时称为"拆分式 DNS"），请确保用户解析名称通过内部 DNS 区域时转到 Front End Pool。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-154">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6. <span data-ttu-id="e4dd9-155">键入`Get-CsUser`cmdlet 来检查您将移动的用户的某些属性。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-155">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="e4dd9-156">您需要确保 HostingProviderProxyFQDN 设置为`"sipfed.online.lync.com"`，且 SIP 地址设置正确。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-156">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7. <span data-ttu-id="e4dd9-157">联机将用户移动到本地。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-157">Move online users to on premises.</span></span>

    <span data-ttu-id="e4dd9-158">要移动单个用户，请键入：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-158">To move a single user, type this:</span></span>

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="e4dd9-159">您可以通过使用**Get-csuser** cmdlet 移动多个用户使用-Filter 参数，选择与特定属性的用户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-159">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="e4dd9-160">例如，您无法通过筛选 {宿主提供商-eq"sipfed.online.lync.om"} 选择所有联机用户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-160">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="e4dd9-161">您可以通过管道返回的用户到**Move-csuser** cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-161">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="e4dd9-162">指定的**HostedMigrationOverrideUrl**参数必须为托管迁移服务正在运行，采用以下格式的池的 URL 的 url 格式： _Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-162">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>

    <span data-ttu-id="e4dd9-163">您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-163">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="e4dd9-164">确定 Office 365 租户的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="e4dd9-164">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="e4dd9-165">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-165">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="e4dd9-166">打开“Skype for Business 管理中心”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-166">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="e4dd9-p112">显示“Skype for Business 管理中心”\*\*\*\* 后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="e4dd9-169">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="e4dd9-170">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="e4dd9-171">结果的 URL，即**HostedMigrationOverrideUrl**的值应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > <span data-ttu-id="e4dd9-172">rtcxds 数据库事务日志文件的默认大小上限为 16 GB。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="e4dd9-173">这可能不是足够大，如果要同时移动大量用户尤其在您必须启用镜像。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="e4dd9-174">为解决此问题，您可以扩大文件大小，或者定期备份日志文件。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="e4dd9-175">有关详细信息，请参阅[https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span>

8. <span data-ttu-id="e4dd9-176">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-176">This is an optional step.</span></span> <span data-ttu-id="e4dd9-177">如果需要集成 Exchange 2013 Online，那么需要使用额外的托管服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="e4dd9-178">有关详细信息，请参阅[Configure 集成业务服务器 2015年和 Outlook Web App 的内部部署 Skype](../../deploy/integrate-with-exchange-server/outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>

9. <span data-ttu-id="e4dd9-p115">现在用户已经移动。为核查下表所示的用户属性具有正确的值，键入此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="e4dd9-181">**Active Directory 属性**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-181">**Active Directory attribute**</span></span>|<span data-ttu-id="e4dd9-182">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-182">**Attribute name**</span></span>|<span data-ttu-id="e4dd9-183">**Online 用户的正确值**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-183">**Correct value for Online user**</span></span>|<span data-ttu-id="e4dd9-184">**内部部署用户的正确值**</span><span class="sxs-lookup"><span data-stu-id="e4dd9-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4dd9-185">msRTCSIP DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="e4dd9-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="e4dd9-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="e4dd9-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="e4dd9-187">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e4dd9-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="e4dd9-188">SRV：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="e4dd9-189">msRTCSIP PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="e4dd9-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="e4dd9-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="e4dd9-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="e4dd9-191">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4dd9-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="e4dd9-192">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4dd9-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="e4dd9-193">msRTCSIP UserEnabled</span><span class="sxs-lookup"><span data-stu-id="e4dd9-193">msRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="e4dd9-194">已启用</span><span class="sxs-lookup"><span data-stu-id="e4dd9-194">Enabled</span></span>  <br/> |<span data-ttu-id="e4dd9-195">True</span><span class="sxs-lookup"><span data-stu-id="e4dd9-195">True</span></span>  <br/> |<span data-ttu-id="e4dd9-196">True</span><span class="sxs-lookup"><span data-stu-id="e4dd9-196">True</span></span>  <br/> |

10. <span data-ttu-id="e4dd9-p116">每个已迁移的用户需要先注销，然后重新登录。登录时，用户应验证联系人列表，在必要情况下添加联系人。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>

    <span data-ttu-id="e4dd9-p117">请注意，排定的会议不会从联机迁移到本地。用户在迁移后需要重新安排这些会议。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>

    <span data-ttu-id="e4dd9-201">HostingProvider 属性更新的 DNS 记录和所有用户被都定向到内部部署后，指示用户使用 SRV 记录，或将其应用到在线提供商"sipfed.online.lync.com。"</span><span class="sxs-lookup"><span data-stu-id="e4dd9-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="e4dd9-202">本地移动到联机用户 （人员最初在本地）</span><span class="sxs-lookup"><span data-stu-id="e4dd9-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="e4dd9-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="e4dd9-203"></span></span>

<span data-ttu-id="e4dd9-204">本节仅适用于用户创建和启用内部部署，然后从内部部署移动到 online。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span>

- <span data-ttu-id="e4dd9-205">运行以下 cmdlet 来移动用户从 Skype 的业务联机回内部部署，替换更正值为您的环境使用**Identity**和**目标**参数的值：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="e4dd9-206">**HostedMigrationOverrideUrl**参数指定的 URL 的格式必须为托管迁移服务正在运行，采用以下格式的池的 URL:</span><span class="sxs-lookup"><span data-stu-id="e4dd9-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

 <span data-ttu-id="e4dd9-207">_Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="e4dd9-208">您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="e4dd9-209">确定 Office 365 租户的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="e4dd9-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="e4dd9-210">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-210">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="e4dd9-211">打开“Skype for Business 管理中心”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-211">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="e4dd9-p119">显示“Skype for Business 管理中心”\*\*\*\* 后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="e4dd9-214">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-214">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="e4dd9-215">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="e4dd9-215">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="e4dd9-216">结果的 URL，即**HostedMigrationOverrideUrl**的值应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4dd9-216">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


