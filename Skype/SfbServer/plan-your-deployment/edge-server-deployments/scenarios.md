---
title: Skype for Business 服务器中的 Edge 服务器方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要：查看这些方案，帮助你在 Skype for Business Server 中规划 Edge 服务器拓扑。
ms.openlocfilehash: 64d38b5c9b4a32991bf87bd6ba8af87c92db115f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754162"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Skype for Business 服务器中的 Edge 服务器方案
 
**摘要：** 查看这些方案以帮助你在 Skype for Business 服务器中规划 Edge 服务器拓扑。
  
我们有一些方案图可帮助可视化和确定要实现的 Skype for business Server Edge 服务器拓扑。 选择合适的候选方案后，可以继续阅读需要满足的环境要求。 以下内容适用于任何方案，所以我们先讲这些内容。
  
下面的图仅作为示例显示（因此包含示例 IPv4 和 IPv6 数据），它们不表示实际通信流，而是表示可能的流量的高级视图。另外，可以在下面每个方案的端口图中找到端口详细信息。
  
这些图对外部接口显示 .com，对内部显示 .net，这也是示例资料；当然，在你组合出自己的最终边缘方案时，你自己的条目可能很不一样。
  
我们不在任何图表中包含 Director （这是一个可选组件），但您可以单独阅读（在其他规划主题中提及）。
  
如前所述，图中有示例 IPv6 数据。 [在 Skype for Business 服务器中规划 Edge 服务器部署中](edge-server-deployments.md)的大部分文档将引用 IPv4，但如果你希望使用 IPv6，则可以使用此操作。 请注意，在分配的地址空间中，需要有 IPv6 地址，与 IPv4 IP 一样，它们也需要能用于内部和外部寻址。 多亏有了 Windows，你可以采用双协议栈功能，即 IPv4 和 IPv6 两个单独而不同的网络协议栈。 如果需要，这能让你同时分配 IPv4 和 IPv6 地址。
  
存在允许 NAT64 （IPv6 到 IPv4）和 NAT66 （IPv6 到 IPv6）的 NAT 设备，并且这可用于 Skype for Business 服务器。
  
> [!IMPORTANT]
> 如果使用呼叫允许控制 (CAC)，就必须在内部接口上使用 IPv4 才能使 CAC 可供正常使用。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>具有专用 IP 地址和 NAT 的单个统一 Skype for business 服务器边缘服务器

此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。
  
![单个合并边缘的边缘方案（使用 NAT 通过专用 IP）](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还为单个统一边缘服务器的端口提供了一个图表。
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>具有公共 IP 地址的单个统一 Skype for business 服务器边缘服务器

此方案没有高可用性选项。这意味着硬件花费更少，部署更简单。如果必须要高可用性，请查看下面的扩展合并方案。
  
![使用公共 IP 的单个合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还为单个统一边缘服务器的端口提供了一个图表。
  
![边缘方案单个合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>缩放的合并 Skype for business Server Edge 池，具有 DNS 负载平衡以及专用 IP 地址和 NAT

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（使用 NAT 通过专用 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供了一个图表，用于使用 DNS 负载平衡缩放的合并的边缘池。
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>缩放的合并 Skype for business 服务器 Edge 池，具有 DNS 负载平衡和公共 IP 地址

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（通过公共 IP 进行 DNS 负载平衡）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还提供了一个图表，用于使用 DNS 负载平衡缩放的合并的边缘池。
  
![使用 DNS 负载平衡的边缘方案扩展合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>缩放的合并 Skype for business Server Edge 池，硬件负载平衡

使用此方案，可以在边缘部署中获得高可用性，这带来了可伸缩性和故障转移支持的优势。
  
![带有 HLB 的扩展合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
