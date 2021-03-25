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
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中部署媒体旁路
 
> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

阅读本主题，了解使用云连接器版本 2.0 版及更高版本部署媒体旁路的步骤。 
  
媒体旁路允许客户端将媒体直接发送到公用电话交换网 (PSTN) 下一个跃点（网关或会话边界控制器 (SBC) ）并消除媒体路径中的云连接器版本组件。 另请参阅 [在云连接器版本中规划媒体旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。
  
## <a name="enable-media-bypass"></a>启用媒体旁路

若要启用媒体旁路，必须配置媒体旁路 Web 服务的 DNS 名称，并启用租户配置中的媒体旁路。 媒体旁路 Web 服务会在每个中介服务器上自动部署。 租户管理员必须为混合语音服务选择一个 (站点) ，并且此名称应来自为混合语音注册的 SIP 域。 无论客户端位置如何，服务名称在所有云连接器设备和所有 PSTN 站点中都应相同。 Web 服务应仅在网络内部可用。
  
租户管理员必须在内部生产 Active Directory 中配置 DNS A 记录。 如果您具有复杂的多站点环境，请参阅示例：复杂多站点环境中媒体旁路网站 [DNS 记录中的示例](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS 记录应仅为内部网络客户端解析;它不应解析为外部网络客户端。
  
配置 DNS 后，使用远程 PowerShell 和 Skype for Business 管理员凭据连接到 Skype for Business Online。 有关详细信息，请参阅为[计算机设置Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
在 PowerShell 会话中，输入以下命令以启用媒体旁路：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

启用媒体旁路是一个两步过程。 此New-CsNetworkMedia cmdlet 不会立即保存新配置;它仅在内存中创建设置。 此 cmdlet 创建的对象必须保存到变量中，然后分配给网络配置的 MediaBypassSettings 属性。 有关详细信息，请参阅 [示例：复杂](deploy-media-bypass-in-cloud-connector.md#Example)多站点环境中媒体旁路网站 DNS 记录。
  
内部部署组件和联机组件之间的复制最多可能需要 24 小时，因此 Microsoft 建议您先运行必要的命令，然后再启用用户。
  
## <a name="confirm-media-bypass-settings"></a>确认媒体旁路设置

可以按如下所示检查媒体旁路设置。 
  
若要检查到租户池的联机复制，请在远程 PowerShell 中运行以下命令：
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

要检查本地复制，请连接到云连接器中介服务器，在 PowerShell 中运行以下命令，并确认 Enabled=True 和 AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

要检查客户端设置，请注销 Skype for Business 客户端，重新登录并确认客户端已收到服务 URL，如下所示：
  
1. 打开 %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。 
    
2. 搜索 hybridconfigserviceinternalurl 并确认 URL 与定义的 URL 匹配。
    
## <a name="change-media-bypass-parameters"></a>更改媒体旁路参数

租户管理员能够通过运行以下 cmdlet 更改 Web 服务的 DNS 名称：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 客户端需要注销并登录才能获取新服务名称并识别更改。 
  
## <a name="temporarily-disable-media-bypass"></a>暂时禁用媒体旁路

此方案对于疑难解答或维护可能很有用。 若要禁用该服务，请运行以下 cmdlet：
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

进行更改后，可能需要一些时间才能将更改复制到所有云连接器。 若要检查复制状态，请在云连接器中介服务器的 PowerShell 中运行以下 cmdlet： 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

复制更改后，中介服务器上 Web 服务将开始拒绝媒体旁路服务的客户端请求。
  
## <a name="disable-media-bypass-permanently"></a>永久禁用媒体旁路

若要永久禁用媒体旁路，租户管理员需要运行以下命令： 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

管理员还需要从内部 DNS 服务器中删除媒体旁路的 Web 地址。 进行更改后，可能需要一些时间才能将更改复制到所有云连接器设备。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>示例：复杂多站点环境中媒体旁路网站 DNS 记录
<a name="Example"> </a>

客户端将接收来自内部 DNS 服务器的媒体旁路 Web 服务的 Web 地址。 Web 服务的名称在所有云连接器设备和云连接器 PSTN 站点中都相同。 在复杂的多站点环境中，我们建议对基于 Geo-Location 的流量管理使用 Windows 2016 DNS 策略，以便客户端可以重定向到其网络的本地 Web 服务。 
  
Fore more information about Windows 2016 DNS Policies， see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).
  
下面是使用 Windows 2016 DNS 策略进行基于流量管理Geo-Location公司的配置示例。
  
绕过服务的名称为"hybridvoice.adatum.biz"。
  
位于阿姆斯特丹的站点具有四个部署有以下中介服务器 IP 地址的云连接器设备：
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
西雅图的站点具有三个部署有以下中介服务器 IP 地址的云连接器设备：
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
使用Geo-Location流量管理"配置 DNS 服务器，如下所示：
  
1. 为阿姆斯特丹和西雅图子网创建 DNS 客户端子网。
    
2. 为阿姆斯特丹和西雅图 adatum.biz DNS 区域范围。
    
3. 在每个 DNS 区域范围创建 DNS 记录。
    
    阿姆斯特丹
    
   - 键入 A;
    
   - 名称 ：dns 区域 adatum.biz hybridvoice
    
   - 目标：192.168.1.45
    
     为其他中介服务器创建其他记录
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     西雅图
    
   - 键入 A
    
   - 名称 ：dns 区域中 adatum.biz hybridvoice
    
   - 目标：10.10.1.8
    
     为其他中介服务器创建其他记录
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. 创建将客户端子网连接到相应区域范围的 DNS 策略，以确保所需的 DNS 解析。
    
此时，从阿姆斯特丹子网进行 DNS 查询的客户端 hybridvoice.adatum.biz 返回 192.168.1.45， 192.168.1.46、192.168.1.47 和 192.168.1.48 地址，而进行相同查询的客户端 Seattle 将返回 10.10.1.8、10.10.1.9 和 10.10.1.10。

> [!NOTE]
> 如果 CCE 设备似乎未获得更新的设置，请检查该设备能否通过远程 PowerShell 与租户联系。 可以使用远程 PowerShell 通过 Get-CsHybridPSTNAppliance设备状态，或在 CCE 主机上使用 PowerShell 检查 Get-CcApplianceStatus 的状态。

  
## <a name="see-also"></a>另请参阅
<a name="Example"> </a>

[云连接器版本中的媒体旁路规划](plan-for-media-bypass-in-cloud-connector-edition.md)