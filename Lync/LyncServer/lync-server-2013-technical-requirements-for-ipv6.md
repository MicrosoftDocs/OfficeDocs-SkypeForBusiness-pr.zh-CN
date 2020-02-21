---
title: Lync Server 2013 IPv6 的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

如果您计划为 IPv6 配置 Lync Server 2013，请记住以下要求：

  - 若要将 IPv6 地址与 Lync Server 一起使用，您需要为必须发现和解析为 IPv6 地址的记录创建域名系统（DNS）记录。 IPv6 DNS 使用主机 AAAA (4A) 记录。 如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。 即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。
    
    您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。 如果客户端或服务器不使用 IPv6，该记录不会被引用。 切换技术将根据切换技术配置和策略决定使用哪条记录。

  - 每个 IPv6 地址都有一个作用域。 可用于 IPv6 寻址的三个作用域是 IPv6 全局地址（类似于公用 IPv4 地址）、IPv6 唯一本地地址（类似于专用 IPv4 地址范围）以及 IPv6 链路本地地址（类似于中的自动专用 IP 地址）。适用于 IPv4 的 Windows Server）。 池内所有服务器都应该具有作用域相同的 IPv6 地址。

<div>


> [!IMPORTANT]  
> IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以帮助确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址按预期工作。 请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。



</div>

<div>

## <a name="see-also"></a>另请参阅


[IP 版本6寻址体系结构](https://tools.ietf.org/html/rfc4291)  
[IPv6 全局单播地址格式](https://tools.ietf.org/html/rfc3587)  
[唯一的本地 IPv6 单播地址](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

