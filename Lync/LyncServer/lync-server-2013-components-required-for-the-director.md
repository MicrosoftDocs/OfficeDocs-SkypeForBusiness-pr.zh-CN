---
title: Lync Server 2013：控制器所需的组件
TOCTitle: 控制器所需的组件
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398228(v=OCS.15)
ms:contentKeyID: 49312108
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中控制器所需的组件

 

_**上一次修改主题：** 2012-09-08_

创建和配置 控制器所需的唯一组件是部署 控制器服务器角色。为此，您可以使用 拓扑生成器，并在 控制器池节点中定义单计算机池或多计算机池。定义 控制器或 控制器池后，可以在将成为 控制器的计算机上运行 Lync Server 部署向导。如果定义了 控制器池，则可以在将成为池成员的每台服务器上运行 Lync Server 部署向导。

## 拓扑

您可以实现单个 控制器服务器或 控制器池池。 控制器始终是单独的服务器或池，不与 Lync Server 2013 中的其他任何服务器角色并置。

> [!NOTE]  
> 如果您未部署控制器，前端服务器或前端池将假定控制器角色。



必须对 控制器池进行负载平衡。可选择下列方法之一：

  - 创建一个拓扑，以便使用硬件负载平衡器对其他流量类型实现 Web 服务和域名系统 (DNS) 负载平衡。
    
    [Lync Server 2013 中扩展的控制器池 - DNS 负载平衡和硬件负载平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 创建一个拓扑，以便使用硬件负载平衡器实现控制器池所需的负载平衡。
    
    [Lync Server 2013 中扩展的控制器池 - 硬件负载平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

