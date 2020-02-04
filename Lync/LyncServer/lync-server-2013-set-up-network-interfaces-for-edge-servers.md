---
title: Lync Server 2013：设置边缘服务器的网络接口
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中设置边缘服务器的网络接口

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

每个边缘服务器都是具有外部接口和内部接口的多宿主计算机。 适配器域名系统（DNS）设置取决于外围网络中是否存在 DNS 服务器。 如果外围设备存在 DNS 服务器，则它们必须具有一个区域，其中包含下一跃点服务器或池（即 Director 或指定的前端池）的一个或多个 DNS A 记录，并且对于外部查询，它们引用其他公共 DNS 服务器的名称查找。 如果外围设备中不存在任何 DNS 服务器，则边缘服务器使用外部 DNS 服务器解析 Internet 名称查找，并且每台边缘服务器使用主机将下一个跃点服务器名称解析为 IP 地址。

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全说明：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>出于安全考虑，我们建议你不要让 Edge 服务器访问位于内部网络中的 DNS 服务器。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>在外围网络中配置具有 DNS 服务器的接口

1.  为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。
    
    <div>
    

    > [!IMPORTANT]  
    > 内部子网和外部子网不得相互路由。

    
    </div>

2.  在外部接口上，在外部外围网络（也称为 DMZ、隔离区和屏蔽子网）子网中配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。 将适配器 DNS 设置配置为指向一对外围 DNS 服务器。
    
    <div>
    

    > [!NOTE]  
    > 可以为此接口使用最少的一个 IP 地址，但要执行此操作，您需要将端口分配更改为非标准值。 在拓扑生成器中创建拓扑时，可以确定此情况。

    
    </div>

3.  在内部接口上，在内部外围网络子网中配置一个静态 IP 地址，不要设置默认网关。 将适配器 DNS 设置配置为指向至少一个 DNS 服务器，最好是一对外围 DNS 服务器。

4.  在内部接口上为客户端、Lync Server 2013 和 Exchange 统一消息（UM）服务器所驻留的所有内部网络创建永久静态路由。

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>在外围网络中配置没有 DNS 服务器的接口

1.  为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。
    
    <div>
    

    > [!IMPORTANT]  
    > 内部子网和外部子网不得相互路由。

    
    </div>

2.  在外部接口上，在外部外围网络子网中配置三个静态 IP 地址。 您还可以在外部接口上配置默认网关。 例如，将面向 Internet 的路由器或外部防火墙定义为默认网关。 将 DNS 设置配置为指向 DNS 服务器，最好使用一对外部 DNS 服务器。
    
    <div>
    

    > [!NOTE]  
    > 可以使用，但不推荐使用一个 IP 地址作为外部接口。 若要允许此操作，你需要将端口分配更改为非标准值，并离开默认端口443（通常为客户端通信 "防火墙友好"）。 在拓扑生成器中创建拓扑时，确定 IP 地址设置和端口设置。

    
    </div>

3.  在内部接口上，在内部外围网络子网中配置一个静态 IP 地址，不要设置默认网关。 将适配器 DNS 设置保留为空。

4.  在内部接口上为运行 Lync Server 2013 的 Lync 客户端或服务器所驻留的所有内部网络创建永久静态路由。

5.  编辑每台边缘服务器上的主机文件，以包含下一个跃点服务器或虚拟 IP （VIP）的记录（该记录将是 Director、标准版服务器，或在拓扑结构生成器中配置为边缘服务器下一跃点服务器的前端池）。 如果你使用的是 DNS 负载平衡，请为下一个跃点池的每个成员包含一行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

