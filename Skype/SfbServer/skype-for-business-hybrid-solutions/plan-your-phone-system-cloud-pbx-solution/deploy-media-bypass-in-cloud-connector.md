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
description: 阅读本主题，了解使用云连接器版本2.0 版和更高版本部署媒体旁路的步骤。
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359308"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中部署媒体旁路
 
> [!Important]
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。

阅读本主题，了解使用云连接器版本2.0 版和更高版本部署媒体旁路的步骤。 
  
通过媒体旁路，客户端可以将媒体直接发送到公用电话交换网 (PSTN) 下一跃点（网关或会话边界控制器 (SBC) ），并从媒体路径中消除云连接器版本组件。 另请参阅 [在云连接器版本中规划媒体旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。
  
## <a name="enable-media-bypass"></a>启用媒体旁路

若要启用媒体旁路，必须配置媒体旁路 web 服务的 DNS 名称，并在租户配置中启用媒体旁路功能。 媒体旁路 web 服务在每个中介服务器上自动部署。 租户管理员必须为混合语音服务 (网站) 选择名称，此名称应来自为混合语音注册的 SIP 域。 无论客户端位置如何，所有云连接器设备和所有 PSTN 站点的服务名称应相同。 Web 服务应仅在网络内部可用。
  
租户管理员必须在内部生产 Active Directory 中配置 DNS A 记录。 如果有复杂的多站点环境，请参阅 [示例：在复杂的多站点环境中使用媒体旁路网站 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。 DNS 记录应仅解析内部网络客户端;它不应解析外部网络客户端。
  
配置 DNS 后，通过使用带 Skype for Business 管理员凭据的远程 PowerShell 连接到 Skype for business Online。 有关详细信息，请参阅 [设置适用于 Windows PowerShell 的计算机](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) 。
  
在 PowerShell 会话中，输入以下命令以启用媒体旁路：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

启用媒体旁路的过程分为两个步骤。 CsNetworkMedia cmdlet 不会立即保存新的配置;它仅在内存中创建设置。 必须将此 cmdlet 创建的对象保存到变量，然后将其分配给网络配置的 MediaBypassSettings 属性。 有关详细信息，请参阅 [示例：复杂多站点环境中的媒体旁路网站 DNS 记录](deploy-media-bypass-in-cloud-connector.md#Example)。
  
在内部部署和联机组件之间进行复制可能需要长达24小时，因此 Microsoft 建议您在启用用户之前运行必要的命令。
  
## <a name="confirm-media-bypass-settings"></a>确认媒体旁路设置

您可以按如下所示检查媒体旁路设置。 
  
若要将联机复制检查到租户池，请在远程 PowerShell 中运行以下命令：
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

若要检查本地复制，请连接到云连接器中介服务器，在 PowerShell 中运行以下命令，并确认 Enabled = True 和 AlwaysBypass = True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

若要检查客户端设置，请注销 Skype for Business 客户端，重新登录，然后确认客户端已收到服务 URL，如下所示：
  
1. 打开%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。 
    
2. 搜索 hybridconfigserviceinternalurl 并确认 URL 匹配您定义的 URL。
    
## <a name="change-media-bypass-parameters"></a>更改媒体旁路参数

租户管理员可以通过运行以下 cmdlet 来更改 web 服务的 DNS 名称：
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 客户端需要注销并登录才能获取新的服务名称并识别更改。 
  
## <a name="temporarily-disable-media-bypass"></a>暂时禁用媒体旁路

此方案可能对故障排除或维护很有用。 若要禁用该服务，请运行以下 cmdlet：
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

进行更改后，可能需要一段时间才能将更改复制到所有云连接器。 若要检查复制的状态，请在云连接器中介服务器上的 PowerShell 中运行以下 cmdlet： 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

在更改复制之后，中介服务器上的 web 服务将开始拒绝媒体旁路服务的客户端请求。
  
## <a name="disable-media-bypass-permanently"></a>永久禁用媒体旁路

若要永久禁用媒体旁路功能，租户管理员需要运行以下命令： 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

管理员还需要从内部 DNS 服务器中删除媒体旁路的 web 地址。 进行更改后，可能需要一段时间才能将更改复制到所有云连接器设备。 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>示例：复杂的多站点环境中的媒体旁路网站 DNS 记录
<a name="Example"> </a>

客户端将从内部 DNS 服务器接收媒体旁路 web 服务的 web 地址。 在所有云连接器设备和云连接器 PSTN 站点中，web 服务的名称将相同。 在复杂的多站点环境中，我们建议对基于地理位置的流量管理使用 Windows 2016 DNS 策略，以便客户端可以重定向到其网络的本地 web 服务。 
  
有关 Windows 2016 DNS 策略的详细信息，请参阅 [将 Dns 策略用于基于地理位置的流量管理与主服务器](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)。
  
下面是一个公司的配置示例，其中包含多个网站（针对基于地理位置的流量管理使用 Windows 2016 DNS 策略）。
  
旁路服务的名称为 "hybridvoice.adatum.biz"。
  
包含以下中介服务器 IP 地址的四个云连接器设备部署在阿姆斯特丹中的网站：
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
西雅图的站点有三个云连接器设备部署了以下中介服务器 IP 地址：
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
使用基于地理位置的流量管理，将按如下所示配置 DNS 服务器：
  
1. 为阿姆斯特丹和西雅图子网创建 DNS 客户端子网。
    
2. 为阿姆斯特丹和西雅图的 adatum.biz 创建 DNS 区域作用域。
    
3. 在每个 DNS 区域作用域中创建 DNS 记录。
    
    阿姆斯特丹
    
   - 键入 A;
    
   - Name： adatum.biz DNS 区域中的为 hybridvoice
    
   - 目标：192.168.1.45
    
     为其他中介服务器创建其他记录
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     」
    
   - 键入 A
    
   - Name： adatum.biz DNS 区域中的为 hybridvoice
    
   - 目标：10.10.1。8
    
     为其他中介服务器创建其他记录
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. 创建将客户端子网连接到相应区域作用域的 DNS 策略，以确保所需的 DNS 解析。
    
在这种情况下，从 hybridvoice.adatum.biz 子网进行 DNS 查询的客户端将返回192.168.1.45、192.168.1.46、192.168.1.47 和192.168.1.48 地址，而在西雅图建立相同查询表单的客户端将返回10.10.1.8、10.10.1.9 和10.10.1.10。

> [!NOTE]
> 如果 CCE 设备似乎未获取更新的设置，请检查设备是否能够通过远程 PowerShell 联系租户。 您可以使用远程 PowerShell 通过 CsHybridPSTNAppliance 检查设备状态，或在 CCE 主机上使用 PowerShell 检查 CcApplianceStatus 的状态。

  
## <a name="see-also"></a>另请参阅
<a name="Example"> </a>

[云连接器版本中的媒体旁路规划](plan-for-media-bypass-in-cloud-connector-edition.md)
