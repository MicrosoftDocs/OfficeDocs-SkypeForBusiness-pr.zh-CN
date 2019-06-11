---
title: Lync Server 2013：配置网络适配器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3469e9d5fa3f7aeb45bc8f35ff692d97d09b8481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>在 Lync Server 2013 中配置网络适配器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-07_

必须将一个或多个 IP 地址分配给外部网络适配器, 并将至少一个 IP 地址分配给内部网络适配器。

在以下过程中, 运行 Forefront 威胁管理网关 (TMG) 2010 或 Internet Information Server 应用程序请求路由的服务器具有两个网络适配器:

  - 用于尝试连接到您的网站 (通常通过 Internet) 的客户端的公共网络适配器或外部网络适配器。

  - 运行 Lync Server 托管 Web 服务的内部服务器的专用网络接口或内部网络接口。

<div>


> [!IMPORTANT]  
> 与边缘服务器类似, 仅在外部网络适配器上设置默认网关。 默认网关将是路由器的 IP 地址或将流量定向到 Internet 的面向外部的防火墙。 对于发往面向内部网络适配器的反向代理的流量, 必须对包含 web 发布规则所引用的服务器的所有子网使用永久静态路由 (如 Windows Server 中的 route 命令)。 设置持久路由不会导致计算机成为路由器。 如果未启用 IP 转发, 则计算机仅适用于将其他网络的特定流量定向到相应的接口。 这基本上是设置两个网关-一个是指向外部网络的默认网关, 另一个用于发送到内部接口和路由器或其他网络的通信。<BR>但是, 如果您的网络路由器配置为概括路由, 则可能不需要为所有子网创建持久路由。 创建到定义路由器的网络的永久路由, 并将该路由器用作默认网关。 如果不确定您的网络的配置方式, 并且需要有关需要创建的持久路由的指南, 请咨询贵公司的网络工程师。<BR>反向代理服务器必须能够解析内部控制器或前端服务器的 DNS 主机 (A) 记录和 web 发布规则中使用的下一个跃点池 Fqdn。 与边缘服务器一样, 出于安全考虑, 我们建议你不要将反向代理配置为使用位于内部网络中的 DNS 服务器。 这意味着你需要在外围服务器中加入 DNS 服务器, 或者你需要将这些 Fqdn 解析为服务器内部 IP 地址的反向代理上的主机文件条目。



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>在反向代理计算机上配置网络适配器卡

1.  在 Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 或运行为反向代理的 Windows Server 2012 R2 服务器上, 通过单击 "**开始**", 指向 **"控制面板**", 单击 "网络", 打开 "**更改适配器设置**"。 **和 "共享中心**", 然后单击 "**更改适配器设置**"。

2.  右键单击要用于外部接口的外部网络连接, 然后单击 "**属性**"。

3.  在 "**属性**" 页上, 单击 "**网络**" 选项卡, 单击 "**此连接使用下列项目"** 列表中的 " **Internet 协议版本 4 (TCP/IPv4)** ", 然后单击 "**属性**"。

4.  在 " **Internet 协议 (tcp/ip) 属性**" 页上, 根据需要为连接网络适配器的网络子网配置 IP 地址。
    
    <div>
    

    > [!NOTE]  
    > 如果反向代理已由使用 HTTPS/TCP/443 的其他应用程序使用, 例如用于发布 Outlook Web Access, 则需要添加另一个 IP 地址, 以便你可以在 HTTPS/TCP/443 上发布 Lync Server 2013 Web 服务, 而不会干扰使用现有规则和 web 侦听器, 或者需要将现有证书替换为将新的外部 FQDN 名称添加到使用者备用名称的证书。

    
    </div>

5.  单击 **"确定**", 然后单击 **"确定"**。

6.  在 "**网络连接**" 中, 右键单击要用于内部接口的内部网络连接, 然后单击 "**属性**"。

7.  重复步骤3到步骤5配置内部网络连接。

</div>

</div>

<span> </span>

</div>

</div>

</div>

