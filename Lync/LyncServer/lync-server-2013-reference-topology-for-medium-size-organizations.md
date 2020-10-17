---
title: Lync Server 2013 针对中型组织的参考拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2549acbf8b5eac2ac909eb213d6d73e8233b0a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536699"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>中型组织中 Lync Server 2013 的参考拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。 下图中的具体拓扑适用于20000用户的组织。

**中型组织的参考拓扑**

![单一数据中心图表的参考拓扑](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "单一数据中心图表的参考拓扑")

  - **通过添加更多前端服务器来容纳更多用户。**    此图中的具体拓扑包含三台前端服务器，以支持20000用户。 如果您有一个中央站点和更多用户，则只需向池中添加更多的前端服务器即可。 每个池的最大用户数为80000，使用12台前端服务器。
    
    但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。

  - **可以添加灾难恢复。**    对于此组织，其 Lync Server 服务的高可用性是必需的功能，但不需要进行灾难恢复。 他们已部署的前端服务器池可提供高可用性。
    
    如果他们想要添加灾难恢复能力，他们可以考虑建立另一个数据中心并在其中添加另一个前端池，并将其与当前数据中心中的前端池配对。 然后，如果存在影响其主池的灾难，则管理员可以将用户故障转移到备份池。

  - **对后端服务器进行镜像**    为为基本用户功能提供更高的可用性，组织已为每个前端池部署了一个镜像对后端服务器。 这是 Lync Server 2013 的新拓扑选项，它是可选的。 您可以选择部署一台后端服务器。

  - **监视服务器数据库选项。**    此组织已部署监控，以确保企业语音呼叫和 A/V 会议的质量。 监视部署在每台前端服务器上，监视数据库与后端服务器并置。 此外，我们还支持监视数据库位于单独服务器上的拓扑。

  - **边缘服务器高可用性**    在此示例中，有20000个用户的组织，只要一台边缘服务器的性能就足够了。 但是，部署了两台边缘服务器的池以提供高可用性。

  - **分支站点部署选项。**    此拓扑中的组织已将企业语音部署为其语音解决方案。 分支站点1没有可 (WAN) 链接到中央站点的弹性广域网络，因此它部署了一个 Survivable 分支设备来维护许多 Lync Server 功能，以防指向中央站点的 WAN 链接断开。 但是，分支站点 2 具有可恢复 WAN 链接，因此只需一个公用电话交换网 (PSTN) 网关。 该处部署的 PSTN 网关支持媒体绕过，因此分支站点 2 上不需要中介服务器。 有关决定在分支站点部署的内容的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 。

  - **DNS 负载平衡。**    前端池 andEdge 服务器池具有部署的 SIP 流量的 DNS 负载平衡。 这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md) 。

  - **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) 服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的在 lync server [2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 和 [lync server 2013 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 。

  - **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。 有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **建议使用边缘服务器。**    尽管不需要部署边缘服务器，但我们建议将其用于任意规模的部署。 您可以部署边缘服务器以向当前组织防火墙外部的用户提供服务，从而最大化 Lync Server 投资。 优势包括：
    
      - 如果您的组织的用户在家中或在路上工作，则您的组织自己的用户可以使用 Lync Server 功能。
    
      - 您的用户可以邀请外部用户参加会议。
    
      - 如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立 *联合关系* 。 然后，你的 Lync Server 部署将识别来自该联合组织的用户，从而实现更好的协作。
    
      - 您的用户可以与公共 IM 服务的用户交换即时消息，包括以下任一或所有内容： Windows Live、AOL、Yahoo \! 和 Google 谈话。 对于使用这些服务的公共 IM 连接，可能需要单独的许可证。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
        > <LI>
        > <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>

        
        </div>

  - 可**添加控制器。**    如果此组织希望帮助提高抵御拒绝服务攻击的安全性，它还可以部署一个控制器池。 Director 是 Lync Server 中的一个单独的可选服务器角色，它不会家庭用户帐户，也不提供状态或会议服务。 它充当内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。 控制器对入站请求进行预身份验证，并将其重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 控制器可帮助将前端服务器与恶意流量（如拒绝服务 (DoS) 攻击）隔离。 如果网络在此类攻击中遇到无效的外部通信，则流量将在 Director 处结束。

  - **建议使用 System Center Operations Manager。**   建议您监视 Lync Server 部署的运行状况，以帮助确保最终用户的服务可用性。 您可以使用可从 Microsoft 免费下载的 Lync 的 System Center Operations Manager 管理包监视 Lync。 使用 Lync 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Lync 功能以及获取服务可用性的报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。

</div>

<span> </span>

</div>

</div>

</div>

