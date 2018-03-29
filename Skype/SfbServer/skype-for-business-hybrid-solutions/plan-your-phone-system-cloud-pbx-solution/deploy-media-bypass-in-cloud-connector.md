---
title: 在云连接器版本中部署媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 阅读本主题，了解有关步骤来部署媒体绕过云连接器版 2.0 及更高版本。
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="9a067-103">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9a067-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="9a067-104">阅读本主题，了解有关步骤来部署媒体绕过云连接器版 2.0 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="9a067-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="9a067-105">媒体回避允许客户端直接与公共交换电话网络 (PSTN) 的下一跃点发送媒体 — — 网关或会话边框控制器 (SBC) — — 并消除通过媒体路径中的云连接器版组件。</span><span class="sxs-lookup"><span data-stu-id="9a067-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="9a067-106">请参阅[媒体计划绕过云连接器版中](plan-for-media-bypass-in-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="9a067-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="9a067-107">启用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9a067-107">Enable media bypass</span></span>

<span data-ttu-id="9a067-108">要启用媒体旁路，你必须在租户配置中配置媒体旁路 Web 服务的 DNS 名称并打开媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9a067-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="9a067-109">媒体旁路 Web 服务会自动在每台中介服务器上部署。</span><span class="sxs-lookup"><span data-stu-id="9a067-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="9a067-110">租户管理员必须为混合语音服务（站点）选取名称，此名称应来自为混合语音注册的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="9a067-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="9a067-111">服务名称应跨所有云接头装置和任何客户端位置的所有 PSTN 站点上都是相同的。</span><span class="sxs-lookup"><span data-stu-id="9a067-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="9a067-112">Web 服务应仅在网络内部可用。</span><span class="sxs-lookup"><span data-stu-id="9a067-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="9a067-113">租户管理员必须在内部生产 Active Directory 中配置 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="9a067-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="9a067-114">如果您有一个复杂的多站点环境，请参阅中的示例[示例： 媒体绕过 web 站点在复杂环境中多站点的 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="9a067-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="9a067-115">DNS 记录应只为内部网络客户端解析，不应为外部网络客户端解析。</span><span class="sxs-lookup"><span data-stu-id="9a067-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="9a067-116">配置完 DNS 之后，通过远程 PowerShell 使用 Skype for Business 管理员凭据连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="9a067-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="9a067-117">有关详细信息，请参阅[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9a067-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="9a067-118">在 PowerShell 会话中，输入以下命令，以启用媒体旁路：</span><span class="sxs-lookup"><span data-stu-id="9a067-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="9a067-119">启用媒体旁路的过程分为两个步骤。</span><span class="sxs-lookup"><span data-stu-id="9a067-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="9a067-120">New-CsNetworkMedia cmdlet 不会立即保存新配置；它只在内存中创建设置。</span><span class="sxs-lookup"><span data-stu-id="9a067-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="9a067-121">必须将此 cmdlet 创建的对象保存到一个变量中，再将其分配给网络配置的 MediaBypassSettings 属性。</span><span class="sxs-lookup"><span data-stu-id="9a067-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="9a067-122">有关详细信息，请参阅[示例： 媒体绕过 web 站点在复杂环境中多站点的 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="9a067-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="9a067-123">内部部署和联机的组件之间的复制可以达 24 小时，因此 Microsoft 建议您在启用用户之前运行必要的命令。</span><span class="sxs-lookup"><span data-stu-id="9a067-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="9a067-124">确认媒体旁路设置</span><span class="sxs-lookup"><span data-stu-id="9a067-124">Confirm media bypass settings</span></span>

<span data-ttu-id="9a067-125">可按如下所述检查媒体旁路设置。</span><span class="sxs-lookup"><span data-stu-id="9a067-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="9a067-126">要检查在线复制到租户池，请在远程 PowerShell 运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="9a067-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

<span data-ttu-id="9a067-127">检查内部复制、 连接到云连接器中介服务器、 继续，运行下面的命令并确认该启用 = True 和 AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="9a067-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="9a067-128">要检查的客户端设置，业务客户端登录 Skype、 重新登录，并确认，客户端收到的服务 URL，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9a067-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="9a067-129">打开 %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。</span><span class="sxs-lookup"><span data-stu-id="9a067-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="9a067-130">Hybridconfigserviceinternalurl 搜索并确认 URL 匹配您定义。</span><span class="sxs-lookup"><span data-stu-id="9a067-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="9a067-131">更改媒体旁路参数</span><span class="sxs-lookup"><span data-stu-id="9a067-131">Change media bypass parameters</span></span>

<span data-ttu-id="9a067-132">租户管理员能够通过运行以下 cmdlet 来更改 Web 服务的 DNS 名称：</span><span class="sxs-lookup"><span data-stu-id="9a067-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="9a067-133">客户端需要注销并登录，以获取新服务名称并识别更改。</span><span class="sxs-lookup"><span data-stu-id="9a067-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="9a067-134">暂时禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9a067-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="9a067-p106">此方案可能对故障排除或维护有用。要禁用该服务，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9a067-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="9a067-137">进行更改后，可能需要经过一段时间，才能将更改复制到所有云连接器。</span><span class="sxs-lookup"><span data-stu-id="9a067-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="9a067-138">若要检查复制状态，运行以下 cmdlet PowerShell 云连接器中介服务器上：</span><span class="sxs-lookup"><span data-stu-id="9a067-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="9a067-139">复制完更改后，中介服务器上的 Web 服务将开始拒绝对于媒体旁路服务的客户端请求。</span><span class="sxs-lookup"><span data-stu-id="9a067-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="9a067-140">永久禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9a067-140">Disable media bypass permanently</span></span>

<span data-ttu-id="9a067-141">要永久禁用媒体旁路，租户管理员需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9a067-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="9a067-142">管理员还需要从内部 DNS 服务器中删除用于媒体旁路的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="9a067-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="9a067-143">之后进行更改，可能需要一些时间的更改将复制到所有的云接口装置。</span><span class="sxs-lookup"><span data-stu-id="9a067-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="9a067-144">示例：复杂多站点环境中的媒体旁路网站 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="9a067-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="9a067-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="9a067-145"></span></span>

<span data-ttu-id="9a067-146">客户端将从内部 DNS 服务器收到媒体旁路 Web 服务的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="9a067-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="9a067-147">Web 服务的名称将跨所有云接头装置和云连接器 PSTN 站点上都是相同的。</span><span class="sxs-lookup"><span data-stu-id="9a067-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="9a067-148">在复杂多站点环境中，建议将 Windows 2016 DNS 策略用于基于地理位置的流量管理，这样客户端便可重定向到网络本地的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="9a067-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="9a067-149">有关 Windows 2016 DNS 策略的详细信息，请参阅[使用 DNS 与主服务器的地理位置基于流量管理策略](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location)。</span><span class="sxs-lookup"><span data-stu-id="9a067-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="9a067-150">下面是具有多个站点的公司使用 Windows 2016 DNS 策略进行基于地理位置的流量管理的配置示例。</span><span class="sxs-lookup"><span data-stu-id="9a067-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="9a067-151">绕过服务的名称是 hybridvoice.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="9a067-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="9a067-152">在阿姆斯特丹的网站有四个云接头装置部署以下的中介服务器 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="9a067-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="9a067-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="9a067-153">192.168.1.45</span></span>
    
- <span data-ttu-id="9a067-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="9a067-154">192.168.1.46</span></span>
    
- <span data-ttu-id="9a067-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="9a067-155">192.168.1.47</span></span>
    
- <span data-ttu-id="9a067-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="9a067-156">192.168.1.48</span></span>
    
<span data-ttu-id="9a067-157">在西雅图站点有三个云接头装置部署以下的中介服务器 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="9a067-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="9a067-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="9a067-158">10.10.1.8</span></span>
    
- <span data-ttu-id="9a067-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="9a067-159">10.10.1.9</span></span>
    
- <span data-ttu-id="9a067-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="9a067-160">10.10.1.10</span></span>
    
<span data-ttu-id="9a067-161">使用基于地理位置的流量管理时，DNS 服务器的配置如下：</span><span class="sxs-lookup"><span data-stu-id="9a067-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="9a067-162">为阿姆斯特丹和西雅图子网创建 DNS 客户端子网。</span><span class="sxs-lookup"><span data-stu-id="9a067-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="9a067-163">为用于阿姆斯特丹和西雅图的 adatum.biz 创建 DNS 区域范围。</span><span class="sxs-lookup"><span data-stu-id="9a067-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="9a067-164">在每个 DNS 区域范围内创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9a067-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="9a067-165">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="9a067-165">Amsterdam</span></span>
    
  - <span data-ttu-id="9a067-166">Type A;</span><span class="sxs-lookup"><span data-stu-id="9a067-166">Type A;</span></span>
    
  - <span data-ttu-id="9a067-167">Name : hybridvoice in the adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="9a067-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="9a067-168">Target: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="9a067-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="9a067-169">为其他中介服务器创建附加记录</span><span class="sxs-lookup"><span data-stu-id="9a067-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="9a067-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="9a067-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="9a067-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="9a067-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="9a067-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="9a067-172">192.168.1.48</span></span>
    
    <span data-ttu-id="9a067-173">西雅图</span><span class="sxs-lookup"><span data-stu-id="9a067-173">Seattle</span></span>
    
  - <span data-ttu-id="9a067-174">Type A</span><span class="sxs-lookup"><span data-stu-id="9a067-174">Type A</span></span>
    
  - <span data-ttu-id="9a067-175">Name : hybridvoice in adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="9a067-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="9a067-176">Target: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="9a067-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="9a067-177">为其他中介服务器创建附加记录</span><span class="sxs-lookup"><span data-stu-id="9a067-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="9a067-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="9a067-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="9a067-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="9a067-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="9a067-180">创建可将客户端子网连接至相应区域范围以确保所需 DNS 解析的 DNS 策略。</span><span class="sxs-lookup"><span data-stu-id="9a067-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="9a067-181">此时，从 hybridvoice.adatum.biz 的阿姆斯特丹子网进行 DNS 查询的客户端将返回 192.168.1.45、192.168.1.46、192.168.1.47 和 192.168.1.48 地址，而从西雅图进行相同查询的客户端将返回 10.10.1.8、10.10.1.9 和 10.10.1.10。</span><span class="sxs-lookup"><span data-stu-id="9a067-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a067-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a067-182">See also</span></span>
<span data-ttu-id="9a067-183"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="9a067-183"></span></span>

#### 

[<span data-ttu-id="9a067-184">计划在云连接器版的媒体跳过</span><span class="sxs-lookup"><span data-stu-id="9a067-184">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)

