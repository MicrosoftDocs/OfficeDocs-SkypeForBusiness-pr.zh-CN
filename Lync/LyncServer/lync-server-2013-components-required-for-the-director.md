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
ms.openlocfilehash: 1a1461e7edb0b90d7cb3bf3a7238e764a900e50b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502409"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中的控制器所需的组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

创建和配置控制器所需的唯一组件是部署控制器服务器角色。 为此，请使用拓扑生成器，并在 "控制器池" 节点中定义单个计算机池或多台计算机池。 定义控制器池或控制器池之后，在将成为控制器的计算机上运行 Lync Server 部署向导。 对于控制器池，在将成为池成员的每台服务器上运行 Lync Server 部署向导。

<div>

## <a name="topologies"></a>拓扑

您可以实现单个控制器服务器或一个控制器池。 Director 始终是一个单独的服务器或池，而不是并置与 Lync Server 2013 中的任何其他服务器角色。

<div>


> [!NOTE]  
> 如果不部署控制器，前端服务器或前端池将承担控制器角色。



</div>

必须对控制器池进行负载平衡。 可选择下列方法之一：

  - 创建一个拓扑，以便使用硬件负载平衡器对其他流量类型实现 Web 服务和域名系统 (DNS) 负载平衡。
    
    [Lync Server 2013 中的扩展控制器池-DNS 负载平衡和硬件负载平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 创建使用硬件负载平衡器进行控制器池所需的负载平衡的拓扑。
    
    [Lync Server 2013 中的扩展控制器池-硬件负载平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

