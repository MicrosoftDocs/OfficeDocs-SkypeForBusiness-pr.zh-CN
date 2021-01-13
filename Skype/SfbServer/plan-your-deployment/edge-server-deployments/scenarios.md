---
title: Skype for Business Server 中的边缘服务器方案
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要：查看这些方案，帮助你在 Skype for Business Server 中规划边缘服务器拓扑。
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813788"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Skype for Business Server 中的边缘服务器方案
 
**摘要：** 查看这些方案有助于在 Skype for Business Server 中规划边缘服务器拓扑。
  
我们具有一些方案图，可帮助可视化和确定要实现哪些 Skype for Business Server 边缘服务器拓扑。 选择好候选人后，可以继续阅读需要满足的环境要求。 下面适用于任何方案，因此我们首先提到它。
  
这些图仅供 (所示，因此包含示例 IPv4 和 IPv6) ，并不表示实际的通信流，而是可能流量的高级别视图。 还可以在下面的每个方案的端口图中查看端口详细信息。
  
图中显示了外部接口的 .com 和内部接口的 .net，这也是示例材料;当然，在将自己的最终边缘计划放在一起时，你自己的条目可能会截然不同。
  
我们未在任何图中 (作为可选组件) 的 Director) ，但您可以单独阅读 (其他规划主题中) 。
  
如上所述，图表中有示例 IPv6 数据。 Skype [for Business Server](edge-server-deployments.md) 中"规划边缘服务器部署"中的大多数文档将引用 IPv4，但如果你想要使用 IPv6，则当然支持你。 请注意，你将需要分配的地址空间中的 IPv6 地址，并且它们将需要与 IPv4 IP 一样处理内部和外部寻址。 借助 Windows，你可以采用双协议栈功能，这是适用于 IPv4 和 IPv6 的单独且不同的网络堆栈。 如果需要，这将允许你同时分配 IPv4 和 IPv6 地址。
  
存在允许 NAT64 (IPv6 到 IPv4) 和 NAT66 (IPv6 到 IPv6) ) 的 NAT 设备，这适用于 Skype for Business Server。
  
> [!IMPORTANT]
> 如果使用呼叫允许控制 (CAC) 您必须在内部接口上使用 IPv4，它可以使用。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>具有专用 IP 地址和 NAT 的单个合并 Skype for Business Server 边缘服务器

在此方案中，没有高可用性选项。 这意味着在硬件上花费更少，部署更简单。 如果必须高可用性，请查看下面的扩展合并方案。
  
![使用 NAT 使用专用 IP 的单一合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还具有单个合并边缘服务器的端口关系图。
  
![边缘方案单一合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>具有公用 IP 地址的单一合并 Skype for Business Server 边缘服务器

在此方案中，没有高可用性选项。 这意味着在硬件上花费更少，部署更简单。 如果必须高可用性，请查看下面的扩展合并方案。
  
![使用公共 IP 的单一合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还具有单个合并边缘服务器的端口关系图。
  
![边缘方案单一合并边缘的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>扩展的合并 Skype for Business Server 边缘池，具有 DNS 负载平衡以及专用 IP 地址和 NAT

通过此方案，可以在边缘部署中实现高可用性，从而为您提供可伸缩性和故障转移支持的优势。
  
![扩展合并边缘（使用 NAT 使用专用 IP 的 DNS LB）的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还有一个包含 DNS 负载平衡的扩展合并边缘池的图。
  
![使用 DNS LB 扩展的合并边缘的边缘方案的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>扩展的合并 Skype for Business Server 边缘池，具有 DNS 负载平衡和公共 IP 地址

通过此方案，可以在边缘部署中实现高可用性，从而为您提供可伸缩性和故障转移支持的优势。
  
![扩展合并边缘的边缘方案（使用公共 IP 的 DNS LB）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>端口图

我们还有一个包含 DNS 负载平衡的扩展合并边缘池的图。
  
![使用 DNS LB 扩展的合并边缘的边缘方案的网络外围](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>扩展的合并 Skype for Business Server 边缘池，具有硬件负载平衡

通过此方案，可以在边缘部署中实现高可用性，从而为您提供可伸缩性和故障转移支持的优势。
  
![使用 HLB 扩展的合并边缘的边缘方案](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
