---
title: 在云连接器版本中部署媒体旁路
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 阅读本主题，了解使用云连接器版本 2.0 版及更高版本部署媒体旁路的步骤。
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119361"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="d3a33-103">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="d3a33-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="d3a33-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="d3a33-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="d3a33-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="d3a33-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d3a33-106">阅读本主题，了解使用云连接器版本 2.0 版及更高版本部署媒体旁路的步骤。</span><span class="sxs-lookup"><span data-stu-id="d3a33-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="d3a33-107">媒体旁路允许客户端将媒体直接发送到公用电话交换网 (PSTN) 下一个跃点（网关或会话边界控制器 (SBC) ）并消除媒体路径中的云连接器版本组件。</span><span class="sxs-lookup"><span data-stu-id="d3a33-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="d3a33-108">另请参阅 [在云连接器版本中规划媒体旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="d3a33-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="d3a33-109">启用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="d3a33-109">Enable media bypass</span></span>

<span data-ttu-id="d3a33-110">若要启用媒体旁路，必须配置媒体旁路 Web 服务的 DNS 名称，并启用租户配置中的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="d3a33-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="d3a33-111">媒体旁路 Web 服务会在每个中介服务器上自动部署。</span><span class="sxs-lookup"><span data-stu-id="d3a33-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="d3a33-112">租户管理员必须为混合语音服务选择一个 (站点) ，并且此名称应来自为混合语音注册的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="d3a33-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="d3a33-113">无论客户端位置如何，服务名称在所有云连接器设备和所有 PSTN 站点中都应相同。</span><span class="sxs-lookup"><span data-stu-id="d3a33-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="d3a33-114">Web 服务应仅在网络内部可用。</span><span class="sxs-lookup"><span data-stu-id="d3a33-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="d3a33-115">租户管理员必须在内部生产 Active Directory 中配置 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="d3a33-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="d3a33-116">如果您具有复杂的多站点环境，请参阅示例：复杂多站点环境中媒体旁路网站 [DNS 记录中的示例](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="d3a33-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="d3a33-117">DNS 记录应仅为内部网络客户端解析;它不应解析为外部网络客户端。</span><span class="sxs-lookup"><span data-stu-id="d3a33-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="d3a33-118">配置 DNS 后，使用远程 PowerShell 和 Skype for Business 管理员凭据连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="d3a33-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="d3a33-119">有关详细信息，请参阅为[计算机设置Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d3a33-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="d3a33-120">在 PowerShell 会话中，输入以下命令以启用媒体旁路：</span><span class="sxs-lookup"><span data-stu-id="d3a33-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="d3a33-121">启用媒体旁路是一个两步过程。</span><span class="sxs-lookup"><span data-stu-id="d3a33-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="d3a33-122">此New-CsNetworkMedia cmdlet 不会立即保存新配置;它仅在内存中创建设置。</span><span class="sxs-lookup"><span data-stu-id="d3a33-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="d3a33-123">此 cmdlet 创建的对象必须保存到变量中，然后分配给网络配置的 MediaBypassSettings 属性。</span><span class="sxs-lookup"><span data-stu-id="d3a33-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="d3a33-124">有关详细信息，请参阅 [示例：复杂](deploy-media-bypass-in-cloud-connector.md#Example)多站点环境中媒体旁路网站 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="d3a33-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="d3a33-125">内部部署组件和联机组件之间的复制最多可能需要 24 小时，因此 Microsoft 建议您先运行必要的命令，然后再启用用户。</span><span class="sxs-lookup"><span data-stu-id="d3a33-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="d3a33-126">确认媒体旁路设置</span><span class="sxs-lookup"><span data-stu-id="d3a33-126">Confirm media bypass settings</span></span>

<span data-ttu-id="d3a33-127">可以按如下所示检查媒体旁路设置。</span><span class="sxs-lookup"><span data-stu-id="d3a33-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="d3a33-128">若要检查到租户池的联机复制，请在远程 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d3a33-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="d3a33-129">要检查本地复制，请连接到云连接器中介服务器，在 PowerShell 中运行以下命令，并确认 Enabled=True 和 AlwaysBypass=True</span><span class="sxs-lookup"><span data-stu-id="d3a33-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="d3a33-130">要检查客户端设置，请注销 Skype for Business 客户端，重新登录并确认客户端已收到服务 URL，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3a33-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="d3a33-131">打开 %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。</span><span class="sxs-lookup"><span data-stu-id="d3a33-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="d3a33-132">搜索 hybridconfigserviceinternalurl 并确认 URL 与定义的 URL 匹配。</span><span class="sxs-lookup"><span data-stu-id="d3a33-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="d3a33-133">更改媒体旁路参数</span><span class="sxs-lookup"><span data-stu-id="d3a33-133">Change media bypass parameters</span></span>

<span data-ttu-id="d3a33-134">租户管理员能够通过运行以下 cmdlet 更改 Web 服务的 DNS 名称：</span><span class="sxs-lookup"><span data-stu-id="d3a33-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="d3a33-135">客户端需要注销并登录才能获取新服务名称并识别更改。</span><span class="sxs-lookup"><span data-stu-id="d3a33-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="d3a33-136">暂时禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="d3a33-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="d3a33-137">此方案对于疑难解答或维护可能很有用。</span><span class="sxs-lookup"><span data-stu-id="d3a33-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="d3a33-138">若要禁用该服务，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d3a33-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="d3a33-139">进行更改后，可能需要一些时间才能将更改复制到所有云连接器。</span><span class="sxs-lookup"><span data-stu-id="d3a33-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="d3a33-140">若要检查复制状态，请在云连接器中介服务器的 PowerShell 中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d3a33-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="d3a33-141">复制更改后，中介服务器上 Web 服务将开始拒绝媒体旁路服务的客户端请求。</span><span class="sxs-lookup"><span data-stu-id="d3a33-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="d3a33-142">永久禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="d3a33-142">Disable media bypass permanently</span></span>

<span data-ttu-id="d3a33-143">若要永久禁用媒体旁路，租户管理员需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d3a33-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="d3a33-144">管理员还需要从内部 DNS 服务器中删除媒体旁路的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="d3a33-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="d3a33-145">进行更改后，可能需要一些时间才能将更改复制到所有云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="d3a33-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="d3a33-146">示例：复杂多站点环境中媒体旁路网站 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="d3a33-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="d3a33-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="d3a33-147"><a name="Example"> </a></span></span>

<span data-ttu-id="d3a33-148">客户端将接收来自内部 DNS 服务器的媒体旁路 Web 服务的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="d3a33-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="d3a33-149">Web 服务的名称在所有云连接器设备和云连接器 PSTN 站点中都相同。</span><span class="sxs-lookup"><span data-stu-id="d3a33-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="d3a33-150">在复杂的多站点环境中，我们建议对基于 Geo-Location 的流量管理使用 Windows 2016 DNS 策略，以便客户端可以重定向到其网络的本地 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="d3a33-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="d3a33-151">Fore more information about Windows 2016 DNS Policies， see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="d3a33-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="d3a33-152">下面是使用 Windows 2016 DNS 策略进行基于流量管理Geo-Location公司的配置示例。</span><span class="sxs-lookup"><span data-stu-id="d3a33-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="d3a33-153">绕过服务的名称为"hybridvoice.adatum.biz"。</span><span class="sxs-lookup"><span data-stu-id="d3a33-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="d3a33-154">位于阿姆斯特丹的站点具有四个部署有以下中介服务器 IP 地址的云连接器设备：</span><span class="sxs-lookup"><span data-stu-id="d3a33-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="d3a33-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="d3a33-155">192.168.1.45</span></span>
    
- <span data-ttu-id="d3a33-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="d3a33-156">192.168.1.46</span></span>
    
- <span data-ttu-id="d3a33-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="d3a33-157">192.168.1.47</span></span>
    
- <span data-ttu-id="d3a33-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="d3a33-158">192.168.1.48</span></span>
    
<span data-ttu-id="d3a33-159">西雅图的站点具有三个部署有以下中介服务器 IP 地址的云连接器设备：</span><span class="sxs-lookup"><span data-stu-id="d3a33-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="d3a33-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="d3a33-160">10.10.1.8</span></span>
    
- <span data-ttu-id="d3a33-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="d3a33-161">10.10.1.9</span></span>
    
- <span data-ttu-id="d3a33-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="d3a33-162">10.10.1.10</span></span>
    
<span data-ttu-id="d3a33-163">使用Geo-Location流量管理"配置 DNS 服务器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3a33-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="d3a33-164">为阿姆斯特丹和西雅图子网创建 DNS 客户端子网。</span><span class="sxs-lookup"><span data-stu-id="d3a33-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="d3a33-165">为阿姆斯特丹和西雅图 adatum.biz DNS 区域范围。</span><span class="sxs-lookup"><span data-stu-id="d3a33-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="d3a33-166">在每个 DNS 区域范围创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="d3a33-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="d3a33-167">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="d3a33-167">Amsterdam</span></span>
    
   - <span data-ttu-id="d3a33-168">键入 A;</span><span class="sxs-lookup"><span data-stu-id="d3a33-168">Type A;</span></span>
    
   - <span data-ttu-id="d3a33-169">名称 ：dns 区域 adatum.biz hybridvoice</span><span class="sxs-lookup"><span data-stu-id="d3a33-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="d3a33-170">目标：192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="d3a33-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="d3a33-171">为其他中介服务器创建其他记录</span><span class="sxs-lookup"><span data-stu-id="d3a33-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="d3a33-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="d3a33-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="d3a33-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="d3a33-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="d3a33-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="d3a33-174">192.168.1.48</span></span>
    
     <span data-ttu-id="d3a33-175">西雅图</span><span class="sxs-lookup"><span data-stu-id="d3a33-175">Seattle</span></span>
    
   - <span data-ttu-id="d3a33-176">键入 A</span><span class="sxs-lookup"><span data-stu-id="d3a33-176">Type A</span></span>
    
   - <span data-ttu-id="d3a33-177">名称 ：dns 区域中 adatum.biz hybridvoice</span><span class="sxs-lookup"><span data-stu-id="d3a33-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="d3a33-178">目标：10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="d3a33-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="d3a33-179">为其他中介服务器创建其他记录</span><span class="sxs-lookup"><span data-stu-id="d3a33-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="d3a33-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="d3a33-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="d3a33-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="d3a33-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="d3a33-182">创建将客户端子网连接到相应区域范围的 DNS 策略，以确保所需的 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="d3a33-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="d3a33-183">此时，从阿姆斯特丹子网进行 DNS 查询的客户端 hybridvoice.adatum.biz 返回 192.168.1.45， 192.168.1.46、192.168.1.47 和 192.168.1.48 地址，而进行相同查询的客户端 Seattle 将返回 10.10.1.8、10.10.1.9 和 10.10.1.10。</span><span class="sxs-lookup"><span data-stu-id="d3a33-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="d3a33-184">如果 CCE 设备似乎未获得更新的设置，请检查该设备能否通过远程 PowerShell 与租户联系。</span><span class="sxs-lookup"><span data-stu-id="d3a33-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="d3a33-185">可以使用远程 PowerShell 通过 Get-CsHybridPSTNAppliance设备状态，或在 CCE 主机上使用 PowerShell 检查 Get-CcApplianceStatus 的状态。</span><span class="sxs-lookup"><span data-stu-id="d3a33-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="d3a33-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3a33-186">See also</span></span>
<span data-ttu-id="d3a33-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="d3a33-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="d3a33-188">云连接器版本中的媒体旁路规划</span><span class="sxs-lookup"><span data-stu-id="d3a33-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)