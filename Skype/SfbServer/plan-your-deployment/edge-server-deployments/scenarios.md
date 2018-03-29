---
title: Skype for Business Server 2015 中的边缘服务器方案
ms.author: heidip
author: microsoftheidi
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要： 审查这些方案，以帮助您规划业务服务器 2015 Skype 在边缘服务器拓扑。
ms.openlocfilehash: 30bce96e1764a608bf7bc8daeec3d918b9e5912c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-scenarios-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的边缘服务器方案
 
**摘要：**检查这些方案，以帮助您规划业务服务器 2015 Skype 在边缘服务器拓扑。
  
我们有一些方案图来帮助可视化和决定上什么 Skype 业务服务器边缘服务器拓扑结构您要实现的。 选择合适的候选方案后，可以继续阅读需要满足的环境要求。 以下内容适用于任何方案，所以我们先讲这些内容。
  
下面的图仅作为示例显示（因此包含示例 IPv4 和 IPv6 数据），它们不表示实际通信流，而是表示可能的流量的高级视图。另外，可以在下面每个方案的端口图中找到端口详细信息。
  
这些图对外部接口显示 .com，对内部显示 .net，这也是示例资料；当然，在你组合出自己的最终边缘方案时，你自己的条目可能很不一样。
  
在任何关系图中，我们不包括控制器 （这是一个可选组件），但可以单独阅读有关的 （它在规划中的其他主题中提到）。
  
如前所述，图中有示例 IPv6 数据。 大部分[计划业务服务器 2015年的 Skype 在边缘服务器部署](edge-server-deployments.md)中的文档将指向 IPv4，但当然支持如果您想要使用 IPv6。 请注意，在分配的地址空间中，需要有 IPv6 地址，与 IPv4 IP 一样，它们也需要能用于内部和外部寻址。 多亏有了 Windows，你可以采用双协议栈功能，即 IPv4 和 IPv6 两个单独而不同的网络协议栈。 如果需要，这能让你同时分配 IPv4 和 IPv6 地址。
  
没有允许 NAT64 的 NAT 设备 (IPv4 向 IPv6) 和 NAT66 (到 IPv6 IPv6))，这是有效使用 Skype 业务服务器。
  
> [!IMPORTANT]
> 如果使用呼叫允许控制 (CAC)，就必须在内部接口上使用 IPv4 才能使 CAC 可供正常使用。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>单与专用的 IP 地址和 NAT 的业务服务器边缘服务器整合 Skype

此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。
  
![单个合并边缘的边缘方案（使用 NAT 通过专用 IP）](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们也有单个统一的边缘服务器端口的图。
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>单个合并的 Skype 业务服务器边缘服务器与公用 IP 地址

此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。
  
![使用公共 IP 的单个合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们也有单个统一的边缘服务器端口的图。
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>缩放后的统一的 Skype 业务服务器边缘池与 DNS 负载平衡和专用 IP 地址和 NAT

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（使用 NAT 通过专用 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供有 DNS 负载平衡比例统一边缘池的图。
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>缩放后的统一的 Skype 业务服务器边缘池与 DNS 负载平衡和公用 IP 地址

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（通过公共 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供有 DNS 负载平衡比例统一边缘池的图。
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>缩放统一的 Skype 业务服务器边缘池，使用硬件负载平衡

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![带有 HLB 的扩展合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>端口图

我们还必须使用硬件负载平衡的比例统一边缘池的图
  
![边缘服务器外围网络端口和协议](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

