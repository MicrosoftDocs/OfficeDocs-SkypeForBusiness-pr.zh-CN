---
title: 在云连接器中部署多个站点
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 了解有关在云连接器版本中部署多个 PSTN 站点的信息。
ms.openlocfilehash: 04af3ffa69a0ba452277d497544d4ba6708b5cb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>在云连接器中部署多个站点
 
了解有关在云连接器版本中部署多个 PSTN 站点的信息。
  
本节介绍如何部署多个公用电话交换网 (PSTN) 站点。这些站点通过使用与部署单个站点相同的步骤，以每次一个的方式进行部署。本主题介绍多站点部署中的注意事项以及各站点之间的差异。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>多个公用电话交换网 (PSTN) 站点

下面显示了一个示例配置不同的 PSTN 站点部署业务云连接器版的 Skype。 开始部署之前，请确保你的配置设置正确无误。
  
PSTN 站点 1
  
```
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
  
```
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

对于每个要添加的 PSTN 站点，请按照[部署云连接器中单个网站](deploy-a-single-site-in-cloud-connector.md)中的步骤操作。
  
> [!IMPORTANT]
> 每个 PSTN 站点应具有单独的用于准备高可用性 (HA) 的共享文件夹。 不同 PSTN 站点**必须**使用不同的共享文件夹。 对于多个网站。 不使用相同的共享的文件夹 > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>支持高可用性 (HA) 的单站点部署与多站点部署比较
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

下表列出了支持 HA 的单站点部署与多站点部署之间的差异。
  
|**类别**|**项目**|**单站点与 HA**|**多站点**|
|:-----|:-----|:-----|:-----|
|设置  <br/> |共享文件夹  <br/> |要求在整个装置**所在**的共享的文件夹 <br/> |不同设备需要**不同**的共享文件夹 <br/> |
|配置  <br/> |VirtualMachineDomain  <br/> |不同设备需要**相同**的域 <br/> |不同 PSTN 站点需要**相同**的域 <br/> |
|配置  <br/> |SIP 域  <br/> |域的名称和顺序应该是**同一个**装置 <br/> |域的名称和顺序应**相同**跨 PSTN 站点 <br/> |
|配置  <br/> |站点名称  <br/> |不同设备具有**相同**的站点名称 <br/> |不同 PSTN 站点具有**不同**的站点名称 <br/> |
|配置  <br/> |服务器名称  <br/> |设备之间**不同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |内部池 FQDN  <br/> |设备之间**相同** <br/> |PSTN 站点之间**相同** <br/> |
|配置  <br/> |内部 IP  <br/> |设备之间**不同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |外部 FQDN  <br/> |设备之间**相同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |外部 IP  <br/> |设备之间**不同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |PSTN 网关设置  <br/> |设备之间**相同** <br/> |PSTN 站点之间**不同** <br/> |
|配置  <br/> |DNS 记录  <br/> |添加具有**相同**外部访问 Fqdn 记录和**不同**的 IP 地址 <br/> |添加包含**不同**外部访问 FQDN 和**不同** IP 地址的记录 <br/> |
|设置  <br/> |混合的租户  <br/> |设置 HybridPSTNSite  <br/> 设置用于回退的 PeerDestination  <br/> |设置 HybridPSTNSite  <br/> 设置用于回退的 PeerDestination  <br/> |
|设置  <br/> |网关  <br/> |此站点中采用 MS GW **M:N** 映射 <br/> |每个 PSTN 站点中的 PSTN 网关应只连接到同一站点中的中介服务器  <br/> |
|设置  <br/> |用户  <br/> |设置 UserPSTNSettings  <br/> |设置 UserPSTNSettings  <br/> |
   

