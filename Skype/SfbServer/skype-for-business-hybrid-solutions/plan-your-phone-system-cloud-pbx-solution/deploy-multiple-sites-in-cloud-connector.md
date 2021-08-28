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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 了解如何在云连接器版本中部署多个 PSTN 站点。
ms.openlocfilehash: 7f771875605ffef130b430fd7c7a00d9d1a63873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613762"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>在云连接器中部署多个站点

> [!Important] 
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

了解如何在云连接器版本中部署多个 PSTN 站点。
  
本节介绍如何在 PSTN 站点中部署多个公用 (电话) 网络。 使用与部署单个网站相同的步骤，一次部署一个站点。 本主题介绍多站点部署中的注意事项以及网站之间的差异。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>多个公用电话交换网 (PSTN) 站点

下面显示了为不同 PSTN 站点部署Skype for Business 云连接器版本的示例配置。 在开始部署之前，请确保配置设置正确。
  
PSTN 站点 1
  
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

PSTN 站点 2
  
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

对于要添加的每个 PSTN 站点，请按照在云连接器 [中部署单个站点中的步骤操作](deploy-a-single-site-in-cloud-connector.md)。
  
> [!IMPORTANT]
> 用于准备高可用性的共享文件夹 (HA) PSTN 站点。 PSTN **站点之间的** 共享文件夹必须不同。 不要对多个网站使用相同的共享文件夹。> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>与多站点部署 (HA) 具有高可用性的单个站点
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

下表列出了支持 HA 的单站点和多站点部署之间的差异。
  
|**类别**|**项目**|**具有 HA 的单站点**|**多站点**|
|:-----|:-----|:-----|:-----|
|配置  <br/> |设备主机名 <br/> |**不同** 设备不同 <br/> |**不同** PSTN 站点 <br/> |
|安装  <br/> |共享文件夹  <br/> |需要跨 **设备** 使用相同的共享文件夹 <br/> |需要不同 **设备** 之间的不同共享文件夹 <br/> |
|配置  <br/> |VirtualMachineDomain  <br/> |需要跨 **设备** 相同的域 <br/> |需要跨 PSTN 站点相同的域 <br/> |
|配置  <br/> |SIPDomains  <br/> |不同设备域名和 **顺序** 应相同 <br/> |各个 PSTN 网站的域名 **和顺序** 应该相同 <br/> |
|配置  <br/> |网站名称  <br/> |**相同** 跨设备的网站名称 <br/> |**不同** 跨 PSTN 站点的站点名称 <br/> |
|配置  <br/> |服务器名称  <br/> |**不同** 设备不同 <br/> |**不同** PSTN 站点 <br/> |
|配置  <br/> |内部池 FQDN  <br/> |**在设备** 之间相同 <br/> |**在** PSTN 站点之间相同 <br/> |
|配置  <br/> |内部 IP  <br/> |**不同** 设备不同 <br/> |**不同** PSTN 站点 <br/> |
|配置  <br/> |外部 FQDN  <br/> |**在设备** 之间相同 <br/> |**不同** PSTN 站点 <br/> |
|配置  <br/> |外部 IP  <br/> |**不同** 设备不同 <br/> |**不同** PSTN 站点 <br/> |
|配置  <br/> |PSTN GW 设置  <br/> |**在设备** 之间相同 <br/> |**不同** PSTN 站点 <br/> |
|配置  <br/> |DNS 记录  <br/> |添加具有相同的外部 **访问** FQDN 和 **不同** IP 地址的记录 <br/> |添加具有不同的 **外部访问** FQN **和不同** IP 地址的记录 <br/> |
|安装  <br/> |混合租户  <br/> |设置 HybridPSTNSite  <br/> 设置用于回退的 PeerDestination  <br/> |设置 HybridPSTNSite  <br/> 设置用于回退的 PeerDestination  <br/> |
|安装  <br/> |网关  <br/> |此站点中的 MS GW **M：N** 映射 <br/> |每个 PSTN 站点 (PSTN 网关) 应仅连接到同一站点中的中介服务器 () 服务器  <br/> |
|安装  <br/> |用户  <br/> |设置 UserPSTNSettings  <br/> |设置 UserPSTNSettings  <br/> |
