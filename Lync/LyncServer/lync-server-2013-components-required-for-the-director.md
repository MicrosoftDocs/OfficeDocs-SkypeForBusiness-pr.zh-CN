---
title: Lync Server 2013：控制器所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中控制器所需的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

创建和配置 Director 所需的唯一组件是部署 Director 服务器角色。 可通过使用拓扑生成器并在 "控制器池" 节点中定义单个计算机池或多台计算机池来执行此操作。 定义 Director 或控制器池后，请在将成为 Director 的计算机上运行 Lync Server 部署向导。 在控制器池的情况下，你在将成为池成员的每台服务器上运行 Lync Server 部署向导。

<div>

## <a name="topologies"></a>朴

你可以实现单个控制器服务器或控制器池。 Director 始终是单独的服务器或池，而不是在 Lync Server 2013 中与任何其他服务器角色 collocated。

<div>


> [!NOTE]  
> 如果不部署控制器，前端服务器或前端池将承担 Director 角色。



</div>

控制器池必须进行负载平衡。 您可以执行下列操作之一：

  - 创建一个拓扑，该拓扑使用针对其他流量类型的 web 服务和域名系统（DNS）负载平衡的硬件负载平衡器。
    
    [Lync Server 2013 中扩展的控制器池 - DNS 负载平衡和硬件负载平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 创建一个拓扑，该拓扑使用硬件负载平衡器实现控制器池所需的负载平衡。
    
    [Lync Server 2013 中扩展的控制器池 - 硬件负载平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

