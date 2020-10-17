---
title: Lync Server 2013：设置边缘服务器的网络接口
description: Lync Server 2013：设置边缘服务器的网络接口。
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
ms.openlocfilehash: 576ca8670a34be022e3df0a699edaf0df10f5b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550468"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中设置边缘服务器的网络接口

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

每台边缘服务器均是具有面向外部和内部的接口的多宿主计算机。适配器域名系统 (DNS) 设置取决于外围网络中是否有 DNS 服务器。如果外围中存在 DNS 服务器，则这些服务器必须有一个包含有关下一个跃点服务器或池（即，控制器或指定的前端池）的一个或多个 DNS A 记录的区域，而对于外部查询，则会对其他公共 DNS 服务器进行名称查找。如果外围中不存在 DNS 服务器，则边缘服务器将使用外部 DNS 服务器解析 Internet 名称查找，并且每个边缘服务器会使用 HOST 将下一个跃点服务器名称解析为 IP 地址。

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" />安全说明：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>为安全起见，建议不要让边缘服务器访问位于内部网络的 DNS 服务器。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>配置接口（外围网络中存在 DNS 服务器）

1.  为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。
    
    <div>
    

    > [!IMPORTANT]  
    > 内部子网和外部子网不得相互路由。

    
    </div>

2.  在外部接口上，在外部外围网络（也称为 DMZ、外围安全区域或屏蔽子网）子网上配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。配置适配器 DNS 设置以指向一对外围 DNS 服务器。
    
    <div>
    

    > [!NOTE]  
    > 可以只为此接口分配一个 IP 地址，但是这样做的话，您需要将端口分配更改为非标准值。 在拓扑生成器中创建拓扑时，可以确定这一点。

    
    </div>

3.  在内部接口上，在内部外围网络子网上配置一个静态 IP 地址，但不要设置默认网关。配置适配器 DNS 设置，以指向至少一台 DNS 服务器（最好是一对外围 DNS 服务器）。

4.  在内部接口上创建指向所有内部网络（客户端、Lync Server 2013 和 Exchange 统一消息 (UM) 服务器所驻留的所有内部网络）的永久静态路由。

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>配置接口（外围网络中不存在 DNS 服务器）

1.  为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。
    
    <div>
    

    > [!IMPORTANT]  
    > 内部子网和外部子网不得相互路由。

    
    </div>

2.  在外部接口上，在外部外围网络子网上配置三个静态 IP 地址。还可在外部接口上配置默认网关。例如，定义面向 Internet 的路由器或外部防火墙作为默认网关。将 DNS 设置配置为指向一台 DNS 服务器（最好是一对外部 DNS 服务器）。
    
    <div>
    

    > [!NOTE]  
    > 可以只对外部接口使用一个 IP 地址，但不建议这样做。 若要达到此目的，您需要将端口分配更改为非标准值，并且这个值不是通常对客户端通信“防火墙友好”的默认端口 443。 在拓扑生成器中创建拓扑时，可以确定 IP 地址设置和端口设置。

    
    </div>

3.  在内部接口上，在内部外围网络子网上配置一个静态 IP 地址，但不要设置默认网关。将适配器 DNS 设置留空。

4.  在内部接口上为运行 Lync Server 2013 的 Lync 客户端或服务器所驻留的所有内部网络创建永久静态路由。

5.  编辑每台边缘服务器上的主机文件，以包含下一个跃点服务器或虚拟 IP (VIP) 的记录 (该记录将是 Director、Standard Edition Server 或在拓扑生成器) 中配置为边缘服务器下一个跃点地址的前端池。 如果正在使用 DNS 负载平衡，请包含下一个跃点池中所有成员的行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

