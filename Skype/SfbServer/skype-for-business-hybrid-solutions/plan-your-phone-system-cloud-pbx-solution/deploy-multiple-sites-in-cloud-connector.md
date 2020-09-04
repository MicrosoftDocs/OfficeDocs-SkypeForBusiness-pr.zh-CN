---
title: 在云连接器中部署多个站点
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 了解如何在云连接器版本中部署多个 PSTN 站点。
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358918"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>在云连接器中部署多个站点

> [!Important] 
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。

了解如何在云连接器版本中部署多个 PSTN 站点。
  
本节介绍如何将多个公用电话交换电话网络 (PSTN) 站点部署。 使用与部署单个网站相同的步骤一次部署一个网站。 本主题介绍多站点部署中的网站之间的注意事项和差异。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a> (PSTN) 站点的多个公用电话交换电话网络

下面显示了为不同 PSTN 站点部署 Skype for Business 云连接器版本的示例配置。 在开始部署之前，请确保您的配置设置正确。
  
PSTN 站点1
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

PSTN 站点2
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

对于要添加的每个 PSTN 站点，按照 "在 [云连接器中部署单个站点](deploy-a-single-site-in-cloud-connector.md)" 中的步骤操作。
  
> [!IMPORTANT]
> 为每个 PSTN 站点准备高可用性 (HA) 的共享文件夹。 PSTN 站点之间的共享文件夹 **必须** 不同。 请勿对多个网站使用相同的共享文件夹。 > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>与多站点部署相比具有高可用性 (HA) 的单个站点
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

下表列出了具有 HA 支持的单站点和多站点部署之间的差异。
  
|**类别**|**项**|**具有 HA 的单站点**|**多站点**|
|:-----|:-----|:-----|:-----|
|配置  <br/> |设备主机名 <br/> |跨设备**不同** <br/> |PSTN 站点之间**不同** <br/> |
|设置  <br/> |共享文件夹  <br/> |跨设备需要 **相同** 的共享文件夹 <br/> |跨设备需要 **不同** 的共享文件夹 <br/> |
|配置  <br/> |VirtualMachineDomain  <br/> |跨设备需要 **相同** 的域 <br/> |在 PSTN 站点上需要 **相同** 的域 <br/> |
|配置  <br/> |SIPDomains  <br/> |跨设备的域名和顺序应**相同** <br/> |PSTN 站点之间的域名和顺序应**相同** <br/> |
|配置  <br/> |网站名称  <br/> |**相同** 跨设备的站点名称 <br/> |**不同** PSTN 站点之间的站点名称 <br/> |
|配置  <br/> |服务器名称  <br/> |跨设备**不同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |内部池 Fqdn  <br/> |跨设备**相同** <br/> |PSTN 站点之间**相同** <br/> |
|配置  <br/> |内部 Ip  <br/> |跨设备**不同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |外部 FQDN  <br/> |跨设备**相同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |外部 Ip  <br/> |跨设备**不同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |PSTN GW 设置  <br/> |跨设备**相同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |DNS 记录  <br/> |添加具有 **相同** 外部访问 fqdn 和 **不同** IP 地址的记录 <br/> |添加具有 **不同** 外部访问 fqdn 和 **不同** IP 地址的记录 <br/> |
|设置  <br/> |混合租户  <br/> |设置 HybridPSTNSite  <br/> 设置 PeerDestination 以进行回退  <br/> |设置 HybridPSTNSite  <br/> 设置 PeerDestination 以进行回退  <br/> |
|设置  <br/> |网关  <br/> |此站点中的 MS GW **M:N** 映射 <br/> |PSTN 网关 (s) 在每个 PSTN 站点中只应连接到同一站点中的中介服务器 (s)   <br/> |
|设置  <br/> |User  <br/> |设置 UserPSTNSettings  <br/> |设置 UserPSTNSettings  <br/> |
   

