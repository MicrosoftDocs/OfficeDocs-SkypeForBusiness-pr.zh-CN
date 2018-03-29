---
title: 在 Skype for Business Server 2015 中规划企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 企业语音业务服务器规划在 Skype 的基础知识，包括站点、 区域、 站点之间的网络链接和估计语音使用通信。
ms.openlocfilehash: a04c379e3a616a511306db62fd908af26e325418
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划企业语音
 
企业语音业务服务器规划在 Skype 的基础知识，包括站点、 区域、 站点之间的网络链接和估计语音使用通信。
  
企业语音的部署过程取决于您现有的拓扑结构、 基础架构和您想要支持的企业语音功能。 所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。
  
一般情况下，考虑的类型和数量要部署的站点和其地理位置、 每个站点的话务量、 连接站点的网络链接的类型是否为每个提供语音功能的冗余和故障切换站点，以及是否希望使用现有的 PBX 设备。 有一些特定的事项，例如高可用性、 业务服务器作为一个整体的规划为 Skype 时应考虑的。 根据需要在本部分中，整个主题讨论这些事项。
  
## <a name="sites-and-regions"></a>站点和区域

首先，要确定拓扑结构将部署企业语音和这些站点属于网络区域中的站点。 特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。 由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。 决定将本地部署网关的位置，将部署高存活力的分支装置 (Sba) 的位置，在其中您可以配置 SIP 中继 （本地或从中心站点） 到互联网电话服务提供程序 (ITSP)。
  
## <a name="network-links-between-sites"></a>站点之间的网络链路

您还需要考虑您希望网络链路中央网站和它的分支站点之间的带宽使用率。 如果有，或准备部署时，站点间的弹性 WAN 链接我们建议您部署网关，每个分支站点提供对这些站点的用户的本地向内直拨 (DID) 终止。 如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。 如果没有可恢复的 WAN 链接，承载分支站点，少于 1000 个用户，而且没有本地培训的 Skype 业务服务器管理员可用，我们建议您部署分支站点高存活力的分支装置。 如果要承载网站分支在 1000年和 5000 用户之间，缺乏弹性的 WAN 连接，并为业务服务器管理员可用，我们建议您部署自动恢复的分支服务器在分部地点的小型网关具有经过培训的 Skype。 如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。
  
## <a name="estimating-voice-usage-and-traffic"></a>估计语音使用和流量

Microsoft Lync Server 2013、 规划工具使用以下指标来估计用户通信： 每个站点支持该通讯所需的端口数。
  
> 对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
    
> 对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
    
> 对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
端口数又确定中介服务器和网关所需的数目。 大多数组织考虑部署范围的大小从 2 个端口到端口多达 960 公用交换的电话网络 (PSTN) 网关。 （有更大的网关，但这些都主要由电话服务提供程序）。
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>组件、 功能和企业语音的选项

有关规划企业语音部署，请参阅以下各部分的详细信息。
  
- [企业语音在 Skype 的业务服务器 2015年所需的组件](components-required-for-enterprise-voice.md)
    
- [在 Skype 的 PSTN 连接的业务服务器 2015年计划](pstn-connectivity-0.md)
    
- [Skype 在高级的企业语音功能的业务服务器 2015年的网络设置](network-settings-for-advanced-features.md)
    
- [在 Skype 呼叫许可控制业务服务器 2015年计划](call-admission-control.md)
    
- [紧急服务 Skype 业务服务器 2015年计划](emergency-services.md)
    
- [在业务 2015年的 Skype 的媒体跳过计划](media-bypass.md)
    
- [规划业务 2015年的 Skype 使用专用电话线路](private-telephone-lines.md)
    
- [基于位置的路由在 Skype 的业务 2015年计划](location-based-routing.md)
    
- [规划业务 2015年的 Skype 通话管理功能](call-management-features.md)
    
- [企业语音在 Skype 的恢复能力的业务服务器 2015年计划](enterprise-voice-resiliency.md)
    

