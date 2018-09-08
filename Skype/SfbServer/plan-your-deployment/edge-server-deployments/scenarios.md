---
title: 边缘服务器方案中 Skype 业务服务器
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要： 查看这些方案可帮助您规划边缘服务器拓扑中 Skype 业务 Server。
ms.openlocfilehash: 6343c69c493992656b17aaadb5e1450baec85560
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885178"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>边缘服务器方案中 Skype 业务服务器
 
**摘要：** 查看可帮助您规划业务 Server 边缘服务器拓扑中 Skype 这些方案。
  
我们有一些方案关系图，以帮助将可视化和决定哪些 Skype 您想要实现的业务 Server 边缘服务器拓扑。 选择合适的候选方案后，可以继续阅读需要满足的环境要求。 以下内容适用于任何方案，所以我们先讲这些内容。
  
下面的图仅作为示例显示（因此包含示例 IPv4 和 IPv6 数据），它们不表示实际通信流，而是表示可能的流量的高级视图。另外，可以在下面每个方案的端口图中找到端口详细信息。
  
这些图对外部接口显示 .com，对内部显示 .net，这也是示例资料；当然，在你组合出自己的最终边缘方案时，你自己的条目可能很不一样。
  
在任何图，我们不包括控制器 （这是可选组件），但您可以单独阅读有关的 （它中提到的其他规划主题）。
  
如前所述，图中有示例 IPv6 数据。 [规划业务服务器 Skype 中的边缘服务器部署](edge-server-deployments.md)中的文档的大多数将引用 IPv4，但一定支持如果您想要使用 IPv6。 请注意，在分配的地址空间中，需要有 IPv6 地址，与 IPv4 IP 一样，它们也需要能用于内部和外部寻址。 多亏有了 Windows，你可以采用双协议栈功能，即 IPv4 和 IPv6 两个单独而不同的网络协议栈。 如果需要，这能让你同时分配 IPv4 和 IPv6 地址。
  
有 NAT64 允许的 NAT 设备 (IPv6 到 IPv4) 和 NAT66 (到 IPv6 的 IPv6))，这是用于与业务服务器 Skype 有效和。
  
> [!IMPORTANT]
> 如果使用呼叫允许控制 (CAC)，就必须在内部接口上使用 IPv4 才能使 CAC 可供正常使用。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>单一的合并 Skype 业务 Server 边缘服务器与专用 IP 地址和 NAT

此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。
  
![单个合并边缘的边缘方案（使用 NAT 通过专用 IP）](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供单一的合并边缘服务器的端口的图。
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>单一的合并 Skype 业务 Server 边缘服务器使用公共 IP 地址

此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。
  
![使用公共 IP 的单个合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供单一的合并边缘服务器的端口的图。
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>扩展的合并的 Skype 业务服务器边缘池的 dns 负载平衡和专用 IP 地址和 NAT

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（使用 NAT 通过专用 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供有 DNS 负载平衡的扩展的合并边缘池的图。
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>扩展的合并的 Skype 业务服务器边缘池的 dns 负载平衡和公共 IP 地址

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（通过公共 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供有 DNS 负载平衡的扩展的合并边缘池的图。
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>扩展的合并的 Skype 对于业务服务器边缘池，采用硬件负载平衡

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![带有 HLB 的扩展合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>端口图

我们还可以采用硬件负载平衡的扩展合并边缘池的图表
  
![边缘服务器外围网络端口和协议](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

