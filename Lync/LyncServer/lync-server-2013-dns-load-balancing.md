---
title: Lync Server 2013： DNS 负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47469a8b47273c077a96196b06b827ac13a0e336
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 负载平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-01-15_

Lync Server 支持 DNS 负载平衡，这是一种可显著降低网络上负载平衡的管理开销的软件解决方案。 DNS 负载平衡将平衡 Lync Server 特有的网络流量，如 SIP 流量和媒体流量。

如果您部署了 DNS 负载平衡，则组织的硬件负载平衡器的管理开销将会最小化。 此外，还可以免除解决 SIP 流量负载平衡器配置错误相关问题的复杂过程。 您还可以阻止服务器连接以使服务器脱机。 同时，DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量的元素，例如基本呼叫路由。

与为所有类型的流量使用硬件负载平衡器相比，使用 DNS 负载平衡还可以降低您购买硬件负载平衡器的成本。 应使用与 Lync Server 的互操作性限定测试的负载平衡器。 有关负载平衡器互操作性测试的详细信息，请参阅 at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)中的 "Lync Server 2010 负载平衡器合作伙伴"。

前端池、边缘服务器池、控制器池和独立的中介服务器池都支持 DNS 负载平衡。

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端池和控制器池中的 DNS 负载平衡

您可以使用 DNS 负载平衡来平衡前端池和控制器池中的 SIP 流量。部署 DNS 负载平衡后，仍需要对这些池使用硬件负载平衡器，但仅用于客户端到服务器的 HTTPS 流量。硬件负载平衡器用于通过端口 443 和 80 从客户端传入的 HTTPS 流量。

尽管这些池中仍需要硬件负载平衡器，但这些负载平衡器的安装和管理主要用于硬件负载平衡器管理员熟悉的 HTTPS 流量。

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>支持旧客户端和服务器并对其进行 DNS 负载平衡

DNS 负载平衡仅支持运行 Lync Server 2013 或 Lync Server 2010 的服务器以及 Lync 2013 和 Lync 2010 客户端的自动故障转移。 早期版本的客户端和 Office 通信服务器仍可以连接到运行 DNS 负载平衡的池，但如果无法连接到 DNS 负载平衡所引用的第一台服务器，则它们无法故障转移到池中的另一台服务器.

此外，如果您使用的是 Exchange UM，则必须至少使用 Exchange 2010 SP1 以获取对 Lync Server DNS 负载平衡的支持。 如果使用的是早期版本的 Exchange，则用户将不会具有这些 Exchange UM 方案的故障转移功能：

  - 在其电话上播放“企业语音”语音邮件

  - 转接来自 Exchange UM 自动助理的呼叫

其他所有 Exchange UM 方案将正常工作。

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端池和控制器池中部署 DNS 负载平衡

在前端池和控制器池中部署 DNS 负载平衡时，需要使用 FQDN 和 DNS 记录执行一些额外步骤。

  - 使用 DNS 负载平衡的池必须具有两个 FQDN：一个是 DNS 负载平衡使用的常规池 FQDN（例如 pool01.contoso.com），它解析为该池中服务器的物理 IP；另一个是池的 Web 服务的 FQDN（例如 web01.contoso.com），它解析为该池的虚拟 IP 地址。
    
    在拓扑生成器中，如果要为池部署 DNS 负载平衡，若要为池的 Web 服务创建此额外的 FQDN，必须选中 "**覆盖内部 Web 服务池 FQDN** " 复选框，并在 "**指定此池的 Web 服务 url** " 页中键入 FQDN。

  - 要支持 DNS 负载平衡使用的 FQDN，必须设置 DNS，以便将池 FQDN（例如 pool01.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。您应该仅包含当前部署的服务器的 IP 地址。
    
    <div>
    

    > [!WARNING]  
    > 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>，则不能将<STRONG>pool01.contoso.com</STRONG>用于另一个前端池或前端服务器。 如果还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器都是唯一的。 如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>边缘服务器池中的 DNS 负载平衡

您可以在边缘服务器池中部署 DNS 负载平衡。如果要进行部署，则必须了解以下注意事项。

在边缘服务器中使用 DNS 负载平衡会导致以下方案中丧失故障转移功能：

  - 与运行在 Lync Server 2010 之前发布的 Office 通信服务器版本的组织进行联盟。

  - 与公共即时消息（IM）服务 AOLand Yahoo\!的用户进行即时消息交换，以及基于 XMPP 的提供程序和服务器（如 Google 谈话）。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google 谈话目前是唯一受支持的 XMPP 合作伙伴。</P>
    > <LI>
    > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P></LI></UL>

    
    </div>

只要池中的所有边缘服务器都在运行，这些方案就会正常工作；但是如果某台边缘服务器不可用，则发送到该服务器的对这些方案的所有请求都将失败，而不会路由到其他边缘服务器。

如果使用的是 Exchange UM，则必须至少使用 Exchange 2013 以获取对边缘上的 Lync Server DNS 负载平衡的支持。 如果使用较早版本的 Exchange，则远程用户对这些 Exchange UM 方案不具有故障转移功能：

  - 在其电话上播放“企业语音”语音邮件

  - 转接来自 Exchange UM 自动助理的呼叫

其他所有 Exchange UM 方案将正常工作。

内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在边缘服务器池中部署 DNS 负载平衡

要在边缘服务器池的外部接口上部署 DNS 负载平衡，需要具有以下 DNS 条目：

  - 对于访问边缘服务，池中的每台服务器都需要一个条目。 每个条目都必须将访问边缘服务的 FQDN （例如，sip.contoso.com）解析为池中某个边缘服务器上的访问边缘服务的 IP 地址。

  - 对于 Web 会议边缘服务，池中的每台服务器都需要一个条目。 每个条目都必须将 Web 会议边缘服务的 FQDN （例如，webconf.contoso.com）解析为池中某个边缘服务器上的 Web 会议边缘服务的 IP 地址。

  - 对于 "音频/视频边缘" 服务，池中的每台服务器都需要一个条目。 每个条目都必须将音频/视频边缘服务（例如，av.contoso.com）的 FQDN 解析为池中的一台边缘服务器上的 A/V 边缘服务的 IP 地址。

要在边缘服务器池的内部接口上部署 DNS 负载平衡，必须添加一条将此边缘服务器池的内部 FQDN 解析为该池中每台服务器的 IP 地址的 DNS A 记录。

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中介服务器池中使用 DNS 负载平衡

可以在独立的中介服务器池上使用 DNS 负载平衡。所有 SIP 和媒体流量都通过 DNS 负载平衡进行平衡。

要在中介服务器池中部署 DNS 负载平衡，必须设置 DNS，以便将池 FQDN（例如 mediationpool1.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 负载平衡阻止到服务器的通信

如果使用 DNS 负载平衡，并且需要阻止到特定计算机的流量，则只需从池 FQDN 中删除 IP 地址条目是不够的。 您还必须删除计算机的 DNS 条目。

请注意，对于服务器到服务器的流量，Lync Server 2013 使用拓扑感知负载平衡。 服务器在中央管理存储中读取已发布的拓扑，以获取拓扑中的服务器的 Fqdn，并自动在服务器之间分布流量。 若要阻止服务器接收服务器到服务器的流量，则必须从拓扑中删除该服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

