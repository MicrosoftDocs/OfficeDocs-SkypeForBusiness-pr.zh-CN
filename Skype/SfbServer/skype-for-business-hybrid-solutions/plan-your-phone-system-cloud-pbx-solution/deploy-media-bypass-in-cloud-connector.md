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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 阅读本主题, 了解使用云连接器版本2.0 和更高版本部署媒体旁路的步骤。
ms.openlocfilehash: 6f3ad140d25d5f1d03196e576ac57dc56e905d44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287543"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="3ae78-103">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ae78-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="3ae78-104">阅读本主题, 了解使用云连接器版本2.0 和更高版本部署媒体旁路的步骤。</span><span class="sxs-lookup"><span data-stu-id="3ae78-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="3ae78-105">媒体绕过允许客户将媒体直接发送到公共交换式电话网络 (PSTN) 下一跃点 (即网关或会话边界控制器 (SBC)), 并从媒体路径中删除云连接器版本组件。</span><span class="sxs-lookup"><span data-stu-id="3ae78-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="3ae78-106">另请参阅[计划在云连接器版本中使用媒体旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="3ae78-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="3ae78-107">启用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ae78-107">Enable media bypass</span></span>

<span data-ttu-id="3ae78-108">要启用媒体旁路，你必须在租户配置中配置媒体旁路 Web 服务的 DNS 名称并打开媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="3ae78-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="3ae78-109">媒体旁路 Web 服务会自动在每台中介服务器上部署。</span><span class="sxs-lookup"><span data-stu-id="3ae78-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="3ae78-110">租户管理员必须为混合语音服务（站点）选取名称，此名称应来自为混合语音注册的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="3ae78-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="3ae78-111">无论客户端位置如何, 所有云连接器装置和所有 PSTN 站点的服务名称应该是相同的。</span><span class="sxs-lookup"><span data-stu-id="3ae78-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="3ae78-112">Web 服务应仅在网络内部可用。</span><span class="sxs-lookup"><span data-stu-id="3ae78-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="3ae78-113">租户管理员必须在内部生产 Active Directory 中配置 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="3ae78-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="3ae78-114">如果你有复杂的多站点环境, 请参阅示例: 在[复杂的多站点环境中使用媒体绕过网站 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="3ae78-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="3ae78-115">DNS 记录应只为内部网络客户端解析，不应为外部网络客户端解析。</span><span class="sxs-lookup"><span data-stu-id="3ae78-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="3ae78-116">配置完 DNS 之后，通过远程 PowerShell 使用 Skype for Business 管理员凭据连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="3ae78-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="3ae78-117">有关详细信息, 请参阅[设置适用于 Windows PowerShell 的计算机](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="3ae78-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="3ae78-118">在 PowerShell 会话中，输入以下命令，以启用媒体旁路：</span><span class="sxs-lookup"><span data-stu-id="3ae78-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="3ae78-119">启用媒体旁路的过程分为两个步骤。</span><span class="sxs-lookup"><span data-stu-id="3ae78-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="3ae78-120">New-CsNetworkMedia cmdlet 不会立即保存新配置；它只在内存中创建设置。</span><span class="sxs-lookup"><span data-stu-id="3ae78-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="3ae78-121">必须将此 cmdlet 创建的对象保存到一个变量中，再将其分配给网络配置的 MediaBypassSettings 属性。</span><span class="sxs-lookup"><span data-stu-id="3ae78-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="3ae78-122">有关详细信息, 请参阅[示例: 复杂的多站点环境中的媒体绕过网站 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="3ae78-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="3ae78-123">在本地和在线组件之间执行复制可能需要 24 小时，因此 Microsoft 建议你在启用用户之前先运行必要的命令。</span><span class="sxs-lookup"><span data-stu-id="3ae78-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="3ae78-124">确认媒体旁路设置</span><span class="sxs-lookup"><span data-stu-id="3ae78-124">Confirm media bypass settings</span></span>

<span data-ttu-id="3ae78-125">可按如下所述检查媒体旁路设置。</span><span class="sxs-lookup"><span data-stu-id="3ae78-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="3ae78-126">若要将联机复制检查到租户池, 请在远程 PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="3ae78-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="3ae78-127">若要检查本地复制, 请连接到云连接器中介服务器, 在 PowerShell 中运行以下命令, 并确认 Enabled = True 和 AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="3ae78-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="3ae78-128">若要查看客户端设置, 请注销 Skype for Business 客户端, 重新登录, 并确认客户端已收到服务 URL, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3ae78-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="3ae78-129">打开 %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。</span><span class="sxs-lookup"><span data-stu-id="3ae78-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="3ae78-130">搜索 hybridconfigserviceinternalurl 并确认该 URL 与你定义的 URL 匹配。</span><span class="sxs-lookup"><span data-stu-id="3ae78-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="3ae78-131">更改媒体旁路参数</span><span class="sxs-lookup"><span data-stu-id="3ae78-131">Change media bypass parameters</span></span>

<span data-ttu-id="3ae78-132">租户管理员能够通过运行以下 cmdlet 来更改 Web 服务的 DNS 名称：</span><span class="sxs-lookup"><span data-stu-id="3ae78-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="3ae78-133">客户端需要注销并登录，以获取新服务名称并识别更改。</span><span class="sxs-lookup"><span data-stu-id="3ae78-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="3ae78-134">暂时禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ae78-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="3ae78-p106">此方案可能对故障排除或维护有用。要禁用该服务，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3ae78-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="3ae78-137">进行更改后，可能需要经过一段时间，才能将更改复制到所有云连接器。</span><span class="sxs-lookup"><span data-stu-id="3ae78-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="3ae78-138">若要检查复制的状态, 请在云连接器中介服务器上的 PowerShell 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3ae78-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="3ae78-139">复制完更改后，中介服务器上的 Web 服务将开始拒绝对于媒体旁路服务的客户端请求。</span><span class="sxs-lookup"><span data-stu-id="3ae78-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="3ae78-140">永久禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3ae78-140">Disable media bypass permanently</span></span>

<span data-ttu-id="3ae78-141">要永久禁用媒体旁路，租户管理员需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3ae78-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="3ae78-142">管理员还需要从内部 DNS 服务器中删除用于媒体旁路的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="3ae78-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="3ae78-143">进行更改后, 将更改复制到所有云连接器装置可能需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="3ae78-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="3ae78-144">示例：复杂多站点环境中的媒体旁路网站 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="3ae78-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="3ae78-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="3ae78-145"></span></span>

<span data-ttu-id="3ae78-146">客户端将从内部 DNS 服务器收到媒体旁路 Web 服务的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="3ae78-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="3ae78-147">Web 服务的名称将在所有云连接器装置和云连接器 PSTN 站点上保持不变。</span><span class="sxs-lookup"><span data-stu-id="3ae78-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="3ae78-148">在复杂多站点环境中，建议将 Windows 2016 DNS 策略用于基于地理位置的流量管理，这样客户端便可重定向到网络本地的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3ae78-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="3ae78-149">有关 Windows 2016 DNS 策略的详细信息, 请参阅[使用主服务器的基于地理位置的流量管理的 DNS 策略](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)。</span><span class="sxs-lookup"><span data-stu-id="3ae78-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="3ae78-150">下面是具有多个站点的公司使用 Windows 2016 DNS 策略进行基于地理位置的流量管理的配置示例。</span><span class="sxs-lookup"><span data-stu-id="3ae78-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="3ae78-151">旁路服务的名称为 "hybridvoice.adatum.biz"。</span><span class="sxs-lookup"><span data-stu-id="3ae78-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="3ae78-152">阿姆斯特丹中的网站已部署了四个云连接器装置, 其中包含以下中介服务器 IP 地址:</span><span class="sxs-lookup"><span data-stu-id="3ae78-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="3ae78-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="3ae78-153">192.168.1.45</span></span>
    
- <span data-ttu-id="3ae78-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="3ae78-154">192.168.1.46</span></span>
    
- <span data-ttu-id="3ae78-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="3ae78-155">192.168.1.47</span></span>
    
- <span data-ttu-id="3ae78-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="3ae78-156">192.168.1.48</span></span>
    
<span data-ttu-id="3ae78-157">西雅图网站有三个云连接器装置, 其中部署了以下中介服务器 IP 地址:</span><span class="sxs-lookup"><span data-stu-id="3ae78-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="3ae78-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="3ae78-158">10.10.1.8</span></span>
    
- <span data-ttu-id="3ae78-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="3ae78-159">10.10.1.9</span></span>
    
- <span data-ttu-id="3ae78-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="3ae78-160">10.10.1.10</span></span>
    
<span data-ttu-id="3ae78-161">使用基于地理位置的流量管理时，DNS 服务器的配置如下：</span><span class="sxs-lookup"><span data-stu-id="3ae78-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="3ae78-162">为阿姆斯特丹和西雅图子网创建 DNS 客户端子网。</span><span class="sxs-lookup"><span data-stu-id="3ae78-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="3ae78-163">为用于阿姆斯特丹和西雅图的 adatum.biz 创建 DNS 区域范围。</span><span class="sxs-lookup"><span data-stu-id="3ae78-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="3ae78-164">在每个 DNS 区域范围内创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="3ae78-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="3ae78-165">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="3ae78-165">Amsterdam</span></span>
    
   - <span data-ttu-id="3ae78-166">Type A;</span><span class="sxs-lookup"><span data-stu-id="3ae78-166">Type A;</span></span>
    
   - <span data-ttu-id="3ae78-167">Name : hybridvoice in the adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="3ae78-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="3ae78-168">Target: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="3ae78-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="3ae78-169">为其他中介服务器创建附加记录</span><span class="sxs-lookup"><span data-stu-id="3ae78-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="3ae78-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="3ae78-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="3ae78-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="3ae78-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="3ae78-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="3ae78-172">192.168.1.48</span></span>
    
     <span data-ttu-id="3ae78-173">西雅图</span><span class="sxs-lookup"><span data-stu-id="3ae78-173">Seattle</span></span>
    
   - <span data-ttu-id="3ae78-174">Type A</span><span class="sxs-lookup"><span data-stu-id="3ae78-174">Type A</span></span>
    
   - <span data-ttu-id="3ae78-175">Name : hybridvoice in adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="3ae78-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="3ae78-176">Target: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="3ae78-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="3ae78-177">为其他中介服务器创建附加记录</span><span class="sxs-lookup"><span data-stu-id="3ae78-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="3ae78-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="3ae78-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="3ae78-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="3ae78-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="3ae78-180">创建可将客户端子网连接至相应区域范围以确保所需 DNS 解析的 DNS 策略。</span><span class="sxs-lookup"><span data-stu-id="3ae78-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="3ae78-181">此时，从 hybridvoice.adatum.biz 的阿姆斯特丹子网进行 DNS 查询的客户端将返回 192.168.1.45、192.168.1.46、192.168.1.47 和 192.168.1.48 地址，而从西雅图进行相同查询的客户端将返回 10.10.1.8、10.10.1.9 和 10.10.1.10。</span><span class="sxs-lookup"><span data-stu-id="3ae78-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="3ae78-182">如果 CCE 设备似乎未获得更新的设置, 请检查设备是否能够通过远程 PowerShell 联系租户。</span><span class="sxs-lookup"><span data-stu-id="3ae78-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="3ae78-183">你可以使用远程 PowerShell 在 CCE 主机上使用 CsHybridPSTNAppliance 或使用 PowerShell 检查装置状态, 以使用 CcApplianceStatus 检查状态。</span><span class="sxs-lookup"><span data-stu-id="3ae78-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="3ae78-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ae78-184">See also</span></span>
<span data-ttu-id="3ae78-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="3ae78-185"></span></span>

[<span data-ttu-id="3ae78-186">云连接器版本中的媒体旁路规划</span><span class="sxs-lookup"><span data-stu-id="3ae78-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
