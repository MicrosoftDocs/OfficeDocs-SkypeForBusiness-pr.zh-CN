---
title: 'Lync Server 2013: DNS 负载平衡'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4248815c2e896c6c4ce36d22fd6544c298527766
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 负载平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-01-15_

Lync Server 支持 DNS 负载平衡, 这是一个软件解决方案, 可显著降低网络上负载平衡的管理开销。 "DNS 负载平衡" 平衡 Lync 服务器特有的网络流量, 例如 SIP 流量和媒体流量。

如果你部署 DNS 负载平衡, 你的组织的硬件负载平衡器的管理开销将会最小化。 此外, 对 SIP 流量的负载平衡器配置错误相关的问题的复杂疑难解答将会被消除。 您也可以阻止服务器连接, 以便您可以使服务器脱机。 DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量 (如基本呼叫路由) 的元素。

如果使用 DNS 负载平衡, 您还可以购买成本较低的硬件负载平衡器, 而不是对所有类型的流量使用硬件负载平衡器。 你应该使用已通过互操作性鉴定测试的负载平衡器与 Lync Server。 有关负载平衡器互操作性测试的详细信息, 请参阅 "Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)负载平衡器合作伙伴"。

对于前端池、边缘服务器池、控制器池和独立的中介服务器池, DNS 负载平衡受支持。

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端池和控制器池上的 DNS 负载平衡

你可以对前端池和控制器池上的 SIP 流量使用 DNS 负载平衡。 在部署了 "DNS 负载平衡" 的情况下, 你还需要对这些池使用硬件负载平衡器, 但仅需要客户端到服务器的 HTTPS 流量。 硬件负载平衡器用于来自端口443和80的客户端的 HTTPS 流量。

尽管你仍需要这些池的硬件负载平衡器, 但其设置和管理主要用于 HTTPS 流量, 这些通信是硬件负载平衡器的管理员习惯的。

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 负载平衡和支持较旧的客户端和服务器

仅对于运行 Lync Server 2013 或 lync Server 2010 的服务器以及 Lync 2013 和 Lync 2010 客户端, DNS 负载平衡才支持自动故障转移。 早期版本的客户端和 Office 通信服务器仍然可以连接到运行 DNS 负载平衡的池, 但如果它们无法连接到 DNS 负载平衡所引用的第一台服务器, 则它们无法故障转移到池中的另一台服务器.

此外, 如果您使用的是 Exchange UM, 则必须至少使用 Exchange 2010 SP1, 才能获取对 Lync 服务器 DNS 负载平衡的支持。 如果你使用的是早期版本的 Exchange, 你的用户将不具有以下 Exchange UM 方案的故障转移功能:

  - 在手机上播放企业语音语音邮件

  - 转移来自 Exchange UM 自动助理的呼叫

所有其他 Exchange UM 方案都将正常工作。

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端池和控制器池上部署 DNS 负载平衡

在前端池和控制器池上部署 DNS 负载平衡需要使用 Fqdn 和 DNS 记录执行一些额外步骤。

  - 使用 DNS 负载平衡的池必须具有两个 Fqdn: 由 DNS 负载平衡使用的常规池 FQDN (如 pool01.contoso.com), 并解析为池中服务器的物理 Ip 以及该池的 Web 服务的其他 FQDN (如web01.contoso.com), 它解析为池的虚拟 IP 地址。
    
    在拓扑生成器中, 如果要为池部署 DNS 负载平衡, 若要为池的 Web 服务创建此额外的 FQDN, 必须选中 "**替代内部 Web 服务池 FQDN** " 复选框, 然后在 "**指定 Web 服务 url" 中键入 FQDN。此池**页面。

  - 若要支持 DNS 负载平衡使用的 FQDN, 必须预配 DNS 以将池 FQDN (如 pool01.contoso.com) 解析为池中所有服务器的 IP 地址 (例如192.168.1.1、192.168.1.2 等)。 应仅包含当前已部署的服务器的 IP 地址。
    
    <div>
    

    > [!WARNING]  
    > 如果您有多个前端池或前端服务器, 则外部 Web 服务 FQDN 必须是唯一的。 例如, 如果你将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>, 则不能将<STRONG>Pool01.contoso.com</STRONG>用于其他前端池或前端服务器。 如果你还部署控制器, 则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果决定使用自定义的 FQDN 替代内部 web 服务, 则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>边缘服务器池中的 DNS 负载平衡

你可以在 Edge 服务器池上部署 DNS 负载平衡。 如果执行此操作, 则必须注意一些事项。

在边缘服务器上使用 DNS 负载平衡会导致在以下情况下丢失故障转移能力:

  - 与运行在 Lync Server 2010 之前发布的 Office 通信服务器版本的组织进行联盟。

  - 除了基于 XMPP 的提供商和服务器 (如 Google 谈话) 之外,\!还可通过与公共即时消息 (IM) 服务 AOLand Yahoo 的用户进行即时消息交换。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google 通话目前是唯一受支持的 XMPP 合作伙伴。</P>
    > <LI>
    > <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P></LI></UL>

    
    </div>

只要池中的所有边缘服务器都已启动并正在运行, 这些方案就会正常运行, 但如果一台边缘服务器不可用, 则对发送给它的这些方案的任何请求都将失败, 而不是路由到另一台边缘服务器。

如果您使用的是 Exchange UM, 则必须使用 Exchange 2013 的最低限度, 才能获取有关对 Edge 的 Lync Server DNS 负载平衡的支持。 如果您使用的是早期版本的 Exchange, 则您的远程用户将不具有以下 Exchange UM 方案的故障转移功能:

  - 在手机上播放企业语音语音邮件

  - 转移来自 Exchange UM 自动助理的呼叫

所有其他 Exchange UM 方案都将正常工作。

内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在 Edge 服务器池上部署 DNS 负载平衡

若要在 Edge 服务器池的外部接口上部署 DNS 负载平衡, 需要以下 DNS 条目:

  - 对于访问边缘服务, 池中的每个服务器都需要一个条目。 每个条目都必须将访问边缘服务的 FQDN (例如, sip.contoso.com) 解析为池中某个边缘服务器上的访问边缘服务的 IP 地址。

  - 对于 Web 会议 Edge 服务, 池中的每台服务器都需要一个条目。 每个条目都必须将 Web 会议 Edge 服务 (例如, webconf.contoso.com) 的 FQDN 解析为池中的一个边缘服务器上的 Web 会议边缘服务的 IP 地址。

  - 对于音频/视频边缘服务, 池中的每台服务器都需要一个条目。 每个条目都必须将音频/视频边缘服务 (例如, av.contoso.com) 的 FQDN 解析为池中的一个边缘服务器上的 A/V 边缘服务的 IP 地址。

若要在 Edge 服务器池的内部接口上部署 DNS 负载平衡, 必须添加一个 DNS A 记录, 该记录将 Edge 服务器池的内部 FQDN 解析为池中每个服务器的 IP 地址。

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中介服务器池中使用 DNS 负载平衡

可以在独立的中介服务器池上使用 "DNS 负载平衡"。 所有 SIP 和媒体流量通过 "DNS 负载平衡" 平衡。

若要在中介服务器池中部署 DNS 负载平衡, 必须预配 DNS 以将池 FQDN (例如, mediationpool1.contoso.com) 解析为池中所有服务器的 IP 地址 (例如192.168.1.1、192.168.1.2 等)。

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 负载平衡阻止到服务器的通信

如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。

请注意, 对于服务器到服务器的流量, Lync Server 2013 使用拓扑感知负载平衡。 服务器在中央管理存储中读取已发布的拓扑, 以获取拓扑中服务器的 Fqdn, 并自动在服务器之间分配流量。 若要阻止服务器接收服务器到服务器的流量, 必须从拓扑结构中删除该服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

