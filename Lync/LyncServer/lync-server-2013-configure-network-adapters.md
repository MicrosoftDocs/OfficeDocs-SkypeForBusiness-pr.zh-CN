---
title: Lync Server 2013：配置网络适配器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2609c8b8a900b9c970943a2f24bc0462eafb85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>在 Lync Server 2013 中配置网络适配器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

必须向外部网络适配器分配一个或多个 IP 地址，并向内部网络适配器分配至少一个 IP 地址。

在下面的过程中，运行 Forefront 威胁管理网关（TMG）2010或 Internet Information Server 应用程序请求路由的服务器具有两个网络适配器：

  - 一个公用或外部网络适配器，用于尝试连接到您的网站的客户端（通常在 Internet 上）。

  - 一个专用的或内部的网络接口，用于运行承载 Web 服务的 Lync Server 的内部服务器。

<div>


> [!IMPORTANT]  
> 与边缘服务器类似，您只需要在外部网络适配器上设置默认网关。 默认网关将是将流量定向到 Internet 的路由器或面向外部的防火墙的 IP 地址。 对于从反向代理发送到面向内部的网络适配器的流量，必须对包含 web 发布规则所引用的服务器的所有子网使用永久静态路由（如 Windows Server 中的 route 命令）。 设置持久路由不会导致计算机成为路由器。 如果未启用 IP 转发，则计算机将仅作用为将其他网络的特定通信定向到适当的接口。 实际上，这是设置两个网关，一个是指向外部网络的默认网关，另一个用于发往内部接口和路由器或其他网络的通信。<BR>但是，如果将网络路由器配置为汇总路由，则可能不需要为所有子网创建持久路由。 创建到定义了路由器的网络的持久路由，并将该路由器用作默认网关。 如果您不确定网络的配置方式，并需要有关需要创建的持久路由的指南，请咨询贵公司的网络工程师。<BR>反向代理必须能够解析内部控制器或前端服务器的 DNS 主机（A）记录，以及 web 发布规则中使用的下一个跃点池 Fqdn。 与边缘服务器一样，出于安全考虑，我们建议您不要将反向代理配置为使用位于内部网络中的 DNS 服务器。 这意味着，您需要在外围中包含 DNS 服务器，或者需要反向代理上的主机文件条目，将这些 Fqdn 解析为服务器的内部 IP 地址。



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>在反向代理计算机上配置网络适配器卡

1.  在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 服务器上运行作为反向代理，单击 "**开始**"，指向 **"控制面板**"，单击 "**网络和共享中心**"，然后单击 "**更改适配器设置**"，以打开 "**更改适配器设置**"。

2.  右键单击要用于外部接口的外部网络连接，然后单击 "**属性**"。

3.  在 "**属性**" 页上，单击 "**网络**" 选项卡，单击 "**此连接使用下列项目**" 列表中的 " **Internet 协议版本4（TCP/IPv4）** "，然后单击 "**属性**"。

4.  在 " **Internet 协议（tcp/ip）属性**" 页上，配置与网络适配器连接到的网络子网对应的 IP 地址。
    
    <div>
    

    > [!NOTE]  
    > 如果反向代理已由其他使用 HTTPS/TCP/443 的应用程序使用，例如，对于发布 Outlook Web Access，您需要添加另一个 IP 地址，以便可以在 HTTPS/TCP/443 上发布 Lync Server 2013 Web 服务，而不会影响现有的规则和 Web 侦听器，或者需要将现有证书替换为将新的外部 FQDN 名称添加到使用者替代名称的现有证书。

    
    </div>

5.  单击 **"确定**"，然后单击 **"确定"**。

6.  在 "**网络连接**" 中，右键单击要用于内部接口的内部网络连接，然后单击 "**属性**"。

7.  重复步骤3到5以配置内部网络连接。

</div>

</div>

<span> </span>

</div>

</div>

</div>

