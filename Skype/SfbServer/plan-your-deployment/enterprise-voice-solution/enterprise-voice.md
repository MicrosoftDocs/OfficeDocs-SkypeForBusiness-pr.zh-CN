---
title: 在 Skype for Business Server 2015 中规划企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 企业语音规划业务服务器中 Skype 的基础知识，包括网站、 区域、 网络站点间的链接和估计语音用法流量。
ms.openlocfilehash: f1bd8f2f8514f34390cd085bd1407894e9788620
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划企业语音
 
企业语音规划业务服务器中 Skype 的基础知识，包括网站、 区域、 网络站点间的链接和估计语音用法流量。
  
企业语音的部署过程取决于您现有的拓扑和基础结构，您想要支持的企业语音功能。 所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。
  
一般情况下，应考虑的类型和数量您想要部署的网站和及其地理位置、 呼叫量在每个站点、 将网站，连接的网络链接的类型是否要为每个语音功能提供冗余和故障转移网站，并且是否想要使用现有的 PBX 设备。 有某些注意事项，例如业务服务器作为一个整体规划 Skype 时应考虑的高可用性。 根据需要在此部分中，整个主题讨论以下注意事项。
  
## <a name="sites-and-regions"></a>站点和区域

首先，确定您将在其中部署企业语音和这些网站所属的网络区域的拓扑中的网站。 特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。 由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。 确定将本地部署网关的位置，其中将部署 Survivable Branch Appliance (Sba)，以及可在其中配置 SIP 中继 （本地或中央站点） 到 Internet 电话服务提供商 (ITSP)。
  
## <a name="network-links-between-sites"></a>站点之间的网络链路

您还需要考虑您预期网络链路您中央站点和其分支站点之间的带宽使用率。 如果有，或计划部署，可恢复的 WAN 链接之间网站，我们建议您部署在每个分支站点提供这些网站的用户的本地外线直拨分机 (DID) 终止网关。 如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。 如果您没有可恢复的 WAN 链接，承载分支站点，少于 1000 位用户，且不具有本地培训的 Skype 业务服务器管理员可用，我们建议您部署 Survivable Branch Appliance 分支站点。 如果您承载 1000年到 5000 分支站点的用户，缺少可恢复的 WAN 连接，并且具有经过 Skype 培训为可用，我们建议您部署 Survivable Branch Server 与小型网关在分支站点的业务服务器管理员。 如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。
  
## <a name="estimating-voice-usage-and-traffic"></a>估计语音使用和流量

Microsoft Lync Server 2013、 规划工具使用以下任一指标来估计每个站点和支持该流量所需的端口数的用户通信。
  
> 对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。
    
> 对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。
    
> 对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。
    
反过来的端口数确定的中介服务器和网关都需要的数目。 大多数组织考虑部署大小在 2 端口到 960 端口公用电话交换网 (pstn) 网关。 （有更大的网关，但是这些主要由电话服务提供程序。）
  
例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>组件、 功能和企业语音的选项

规划企业语音部署，请参阅以下各节的详细信息。
  
- [所需的业务服务器 2015 Skype 中的企业语音组件](components-required-for-enterprise-voice.md)
    
- [规划业务服务器 2015 Skype 中的 PSTN 连接](pstn-connectivity-0.md)
    
- [Skype 中的高级企业语音功能的业务服务器 2015年网络设置](network-settings-for-advanced-features.md)
    
- [规划呼叫允许控制 Skype 中的业务服务器 2015](call-admission-control.md)
    
- [规划紧急服务中 Skype 业务服务器 2015](emergency-services.md)
    
- [规划媒体绕过中的业务 2015 Skype](media-bypass.md)
    
- [规划与业务 2015年的 Skype 的专用电话线路](private-telephone-lines.md)
    
- [规划基于位置的路由中的业务 2015 Skype](location-based-routing.md)
    
- [规划业务 2015年的 Skype 中呼叫管理功能](call-management-features.md)
    
- [规划业务服务器 2015 Skype 中的企业语音恢复能力](enterprise-voice-resiliency.md)
    

