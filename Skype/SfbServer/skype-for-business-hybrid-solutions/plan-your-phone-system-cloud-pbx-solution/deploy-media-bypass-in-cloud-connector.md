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
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中部署媒体旁路
 
阅读本主题，了解有关步骤来部署媒体绕过云连接器版 2.0 及更高版本。 
  
媒体回避允许客户端直接与公共交换电话网络 (PSTN) 的下一跃点发送媒体 — — 网关或会话边框控制器 (SBC) — — 并消除通过媒体路径中的云连接器版组件。 请参阅[媒体计划绕过云连接器版中](plan-for-media-bypass-in-cloud-connector-edition.md)。
  
## <a name="enable-media-bypass"></a>启用媒体旁路

要启用媒体旁路，你必须在租户配置中配置媒体旁路 Web 服务的 DNS 名称并打开媒体旁路。 媒体旁路 Web 服务会自动在每台中介服务器上部署。 租户管理员必须为混合语音服务（站点）选取名称，此名称应来自为混合语音注册的 SIP 域。 服务名称应跨所有云接头装置和任何客户端位置的所有 PSTN 站点上都是相同的。 Web 服务应仅在网络内部可用。
  
租户管理员必须在内部生产 Active Directory 中配置 DNS A 记录。 如果您有一个复杂的多站点环境，请参阅中的示例[示例： 媒体绕过 web 站点在复杂环境中多站点的 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS 记录应只为内部网络客户端解析，不应为外部网络客户端解析。
  
配置完 DNS 之后，通过远程 PowerShell 使用 Skype for Business 管理员凭据连接到 Skype for Business Online。 有关详细信息，请参阅[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
  
在 PowerShell 会话中，输入以下命令，以启用媒体旁路：
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

启用媒体旁路的过程分为两个步骤。 New-CsNetworkMedia cmdlet 不会立即保存新配置；它只在内存中创建设置。 必须将此 cmdlet 创建的对象保存到一个变量中，再将其分配给网络配置的 MediaBypassSettings 属性。 有关详细信息，请参阅[示例： 媒体绕过 web 站点在复杂环境中多站点的 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。
  
内部部署和联机的组件之间的复制可以达 24 小时，因此 Microsoft 建议您在启用用户之前运行必要的命令。
  
## <a name="confirm-media-bypass-settings"></a>确认媒体旁路设置

可按如下所述检查媒体旁路设置。 
  
要检查在线复制到租户池，请在远程 PowerShell 运行下面的命令：
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

检查内部复制、 连接到云连接器中介服务器、 继续，运行下面的命令并确认该启用 = True 和 AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

要检查的客户端设置，业务客户端登录 Skype、 重新登录，并确认，客户端收到的服务 URL，如下所示：
  
1. 打开 %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。 
    
2. Hybridconfigserviceinternalurl 搜索并确认 URL 匹配您定义。
    
## <a name="change-media-bypass-parameters"></a>更改媒体旁路参数

租户管理员能够通过运行以下 cmdlet 来更改 Web 服务的 DNS 名称：
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 客户端需要注销并登录，以获取新服务名称并识别更改。 
  
## <a name="temporarily-disable-media-bypass"></a>暂时禁用媒体旁路

此方案可能对故障排除或维护有用。要禁用该服务，请运行以下 cmdlet：
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

进行更改后，可能需要经过一段时间，才能将更改复制到所有云连接器。 若要检查复制状态，运行以下 cmdlet PowerShell 云连接器中介服务器上： 
  
```
Get- CsNetworkConfiguration -LocalStore
```

复制完更改后，中介服务器上的 Web 服务将开始拒绝对于媒体旁路服务的客户端请求。
  
## <a name="disable-media-bypass-permanently"></a>永久禁用媒体旁路

要永久禁用媒体旁路，租户管理员需要运行以下命令： 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

管理员还需要从内部 DNS 服务器中删除用于媒体旁路的 Web 地址。 之后进行更改，可能需要一些时间的更改将复制到所有的云接口装置。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>示例：复杂多站点环境中的媒体旁路网站 DNS 记录
<a name="Example"> </a>

客户端将从内部 DNS 服务器收到媒体旁路 Web 服务的 Web 地址。 Web 服务的名称将跨所有云接头装置和云连接器 PSTN 站点上都是相同的。 在复杂多站点环境中，建议将 Windows 2016 DNS 策略用于基于地理位置的流量管理，这样客户端便可重定向到网络本地的 Web 服务。 
  
有关 Windows 2016 DNS 策略的详细信息，请参阅[使用 DNS 与主服务器的地理位置基于流量管理策略](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location)。
  
下面是具有多个站点的公司使用 Windows 2016 DNS 策略进行基于地理位置的流量管理的配置示例。
  
绕过服务的名称是 hybridvoice.adatum.biz。
  
在阿姆斯特丹的网站有四个云接头装置部署以下的中介服务器 IP 地址：
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
在西雅图站点有三个云接头装置部署以下的中介服务器 IP 地址：
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
使用基于地理位置的流量管理时，DNS 服务器的配置如下：
  
1. 为阿姆斯特丹和西雅图子网创建 DNS 客户端子网。
    
2. 为用于阿姆斯特丹和西雅图的 adatum.biz 创建 DNS 区域范围。
    
3. 在每个 DNS 区域范围内创建 DNS 记录。
    
    阿姆斯特丹
    
  - Type A;
    
  - Name : hybridvoice in the adatum.biz DNS zone
    
  - Target: 192.168.1.45
    
    为其他中介服务器创建附加记录
    
  - 192.168.1.46
    
  - 192.168.1.47
    
  - 192.168.1.48
    
    西雅图
    
  - Type A
    
  - Name : hybridvoice in adatum.biz DNS zone
    
  - Target: 10.10.1.8
    
    为其他中介服务器创建附加记录
    
  - 10.10.1.9
    
  - 10.10.1.10
    
4. 创建可将客户端子网连接至相应区域范围以确保所需 DNS 解析的 DNS 策略。
    
此时，从 hybridvoice.adatum.biz 的阿姆斯特丹子网进行 DNS 查询的客户端将返回 192.168.1.45、192.168.1.46、192.168.1.47 和 192.168.1.48 地址，而从西雅图进行相同查询的客户端将返回 10.10.1.8、10.10.1.9 和 10.10.1.10。
  
## <a name="see-also"></a>另请参阅
<a name="Example"> </a>

#### 

[计划在云连接器版的媒体跳过](plan-for-media-bypass-in-cloud-connector-edition.md)

