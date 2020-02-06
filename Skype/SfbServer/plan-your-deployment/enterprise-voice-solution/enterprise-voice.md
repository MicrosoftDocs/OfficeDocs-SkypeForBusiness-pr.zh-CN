---
title: Skype for business Server 中的 "规划企业语音"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for business 服务器中的企业语音规划基础知识，包括网站、区域、网站之间的网络链接和估计语音使用流量。
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802892"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Skype for business Server 中的 "规划企业语音"
 
Skype for business 服务器中的企业语音规划基础知识，包括网站、区域、网站之间的网络链接和估计语音使用流量。
  
企业语音的部署过程取决于你的现有拓扑、基础结构和你希望支持的企业语音功能。 所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。
  
通常，请考虑要部署的网站的类型和数量以及它们的地理位置、每个网站的调用卷、连接网站的网络链接的类型，无论你是否希望为每个网站提供语音功能的冗余和故障转移网站，以及是否希望使用现有的 PBX 设备。 将 Skype for business 服务器规划为整体时，应考虑一些事项（如高可用性）。 这些注意事项将根据需要在本部分中的主题中进行讨论。
  
## <a name="sites-and-regions"></a>站点和区域

首先，确定你的拓扑中的网站，你将在这些网站中部署企业语音和这些网站所属的网络区域。 特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。 由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。 确定本地部署网关的位置（将部署 Survivable 分支装置（SBAs）），以及你可以在哪里将 SIP 中继（本地或中央网站）配置为 Internet 电话服务提供商（ITSP）。
  
## <a name="network-links-between-sites"></a>站点之间的网络链路

您还需要考虑您的中心站点与其分支站点之间网络链接所期望的带宽使用情况。 如果你拥有或计划在网站之间部署弹性 WAN 链接，我们建议你在每个分支站点上部署网关，以便为用户在这些网站上提供本地直接向内拨号（已）终止。 如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。 如果您没有弹性 WAN 链接，在您的分支站点上托管的用户少于1000个用户，并且没有本地训练有素的 Skype for business 服务器管理员可用，我们建议您在分支站点部署 Survivable 分支装置。 如果你在分支站点上的1000和5000用户之间托管，缺少弹性 WAN 连接，并且有训练有素的 Skype for business 服务器管理员可用，我们建议你在分支站点上使用小型网关部署 Survivable 分支服务器。 如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。
  
## <a name="estimating-voice-usage-and-traffic"></a>估计语音使用和流量

Microsoft Lync Server 2013、计划工具使用以下指标估计每个站点上的用户流量以及支持该流量所需的端口数。
  
> 对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
> 
> 对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
> 
> 对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数依次确定所需中介服务器和网关的数量。 大多数组织考虑将范围从2个端口部署到最多960端口的公共交换电话网络（PSTN）网关。 （甚至更大的网关，但主要由电话服务提供商使用。）
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>企业语音的组件、功能和选项

有关规划企业语音部署的详细信息，请参阅以下部分。
  
- [Skype for business Server 中的企业语音所需的组件](components-required-for-enterprise-voice.md)
    
- [在 Skype for Business 服务器中规划 PSTN 连接](pstn-connectivity-0.md)
    
- [Skype for Business Server 中的高级企业语音功能的网络设置](network-settings-for-advanced-features.md)
    
- [在 Skype for Business 服务器中规划呼叫许可控制](call-admission-control.md)
    
- [Skype for business Server 中的紧急服务计划](emergency-services.md)
    
- [在 Skype for Business 中规划媒体旁路](media-bypass.md)
    
- [通过 Skype for Business 规划私人电话线](private-telephone-lines.md)
    
- [在 Skype for Business 中规划基于位置的路由](location-based-routing.md)
    
- [在 Skype for Business 中规划通话管理功能](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

