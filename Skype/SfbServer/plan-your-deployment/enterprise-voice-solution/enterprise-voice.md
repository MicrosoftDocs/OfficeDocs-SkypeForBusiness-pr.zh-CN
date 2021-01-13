---
title: 规划企业语音 Skype for Business Server 中的服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 企业语音 Skype for Business Server 中的规划基础知识，包括站点、区域、站点之间的网络链接以及估计语音使用流量。
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825672"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>规划企业语音 Skype for Business Server 中的服务
 
企业语音 Skype for Business Server 中的规划基础知识，包括站点、区域、站点之间的网络链接以及估计语音使用流量。
  
部署的部署企业语音取决于现有拓扑、基础结构和企业语音支持的功能。 所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。
  
通常，请考虑要部署的站点的类型和数量及其地理位置、每个站点的呼叫量、连接站点的网络链接类型、是否要为每个站点的语音功能提供冗余和故障转移，以及是否要使用现有 PBX 设备。 规划整个 Skype for Business Server 时应考虑某些注意事项，例如高可用性。 根据需要，本节中的主题将讨论这些注意事项。
  
## <a name="sites-and-regions"></a>站点和地区

首先，在拓扑中标识要部署企业语音的站点以及这些站点所属的网络区域。 特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。 由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。 确定将在本地部署网关、部署 Survivable Branch Appliances (SBA) 以及在本地或中央站点 (配置 SIP 中继) 到 Internet 电话服务提供商 (ITSP) 。
  
## <a name="network-links-between-sites"></a>站点之间的网络链接

您还需要考虑中央站点及其分支站点之间的网络链路上预计的带宽使用量。 如果您有或计划部署站点之间的可恢复 WAN 链路，我们建议您在每个分支站点部署网关，为这些站点中的用户提供本地外线直拨 (DID) 终止。 如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。 如果没有可恢复的 WAN 链路，分支站点上承载的用户少于 1000，并且没有本地经过培训的 Skype for Business Server 管理员，我们建议您在分支站点部署 Survivable Branch Appliance。 如果你在分支站点托管 1000 到 5000 个用户，缺少可恢复的 WAN 连接，并且有经过培训的 Skype for Business Server 管理员可用，我们建议您在分支站点部署具有小网关的 Survivable Branch Server。 如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。
  
## <a name="estimating-voice-usage-and-traffic"></a>估计语音使用和流量

Microsoft Lync Server 2013 规划工具使用下列指标来估计每个站点上的用户流量以及支持该流量所需的端口数。
  
> 对于 **低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
> 
> 对于 **中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
> 
> 对于 **高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数反过来决定所需的中介服务器和网关的数量。 公用电话交换网 (PSTN) 网关，大多数组织都考虑部署大小范围从 2 个端口到最多 960 个端口。  (还有更大的网关，但这些网关主要由电话服务提供商使用。) 
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>应用程序的组件、功能和企业语音

有关规划部署部署企业语音部分。
  
- [Skype for Business Server 企业语音所需的组件](components-required-for-enterprise-voice.md)
    
- [在 Skype for Business Server 中规划 PSTN 连接](pstn-connectivity-0.md)
    
- [Skype for Business Server 中高级企业语音功能的网络设置](network-settings-for-advanced-features.md)
    
- [在 Skype for Business Server 中规划呼叫允许控制](call-admission-control.md)
    
- [在 Skype for Business Server 中规划紧急服务](emergency-services.md)
    
- [在 Skype for Business 中规划媒体旁路](media-bypass.md)
    
- [使用 Skype for Business 规划专用电话线路](private-telephone-lines.md)
    
- [在 Skype for Business Location-Based路由计划](location-based-routing.md)
    
- [在 Skype for Business 中规划呼叫管理功能](call-management-features.md)
    
- [规划 skype for Business Server 企业语音恢复能力](enterprise-voice-resiliency.md)
    

