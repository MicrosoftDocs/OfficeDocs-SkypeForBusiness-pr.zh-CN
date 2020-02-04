---
title: 中型组织的 Lync Server 2013 参考拓扑
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
ms.openlocfilehash: da4c29107a6ca3d33e76708be9eec07297eeaf93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>中型组织中的 Lync Server 2013 参考拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-07_

具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。下图中的具体拓扑用于拥有 20,000 个用户的组织。

**中型组织的参考拓扑**

![用于单个数据中心的参考拓扑图示](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "用于单个数据中心的参考拓扑图示")

  - **通过添加更多前端服务器来容纳更多用户。**   此图中的确切拓扑具有三个前端服务器，可提供对20000用户的支持。 如果具有一个中央站点和更多用户，则只需将更多前端服务器添加到池中。 每个池最多可支持 80,000 个用户，可包含 12 台前端服务器。
    
    但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。

  - **可以添加灾难恢复。**   对于此组织，其 Lync Server 服务的高可用性是必需的功能，但灾难恢复不是。 其部署的前端服务器池可提供高可用性。
    
    如果需要添加灾难恢复功能，可以考虑建立另一个数据中心并添加另一个前端池，同时将其当前数据中心内的前端池配对。之后，如果发生影响其主池的灾难，则管理员可以将用户故障转移到备份池。

  - **对后端服务器进行镜像**   以提供基本用户功能的更高可用性，组织为每个前端池部署了镜像对后端服务器。 这是 Lync Server 2013 的新拓扑选项，它是可选的。 可以改为选择部署一台后端服务器。

  - **监视服务器数据库选项。**   此组织已部署监控，以确保企业语音通话质量和 A/V 会议的质量。 在每个前端服务器上部署监控，并且监控数据库将与后端服务器并置。 我们还支持监控数据库在其中位于单独的服务器上的拓扑。

  - **边缘服务器高可用性**    在此示例组织中，对于20000用户，只有一台边缘服务器才足够性能。 但是，部署了两个边缘服务器的池来提供高可用性。

  - **分支站点部署选项。**   此拓扑中的组织已将企业语音部署为其语音解决方案。 分支站点1没有指向中心站点的复原广域网（WAN）链接，因此它具有一个 Survivable 分支设备，可用于维护许多 Lync 服务器功能，以防指向中央站点的 WAN 链接断开。 但是，分支站点 2 具有可恢复 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。 该处部署的 PSTN 网关支持媒体旁路，因此分支站点 2 上不需要中介服务器。 有关决定在分支站点部署哪些内容的详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

  - **DNS 负载平衡。**   前端池 andEdge 服务器池已部署 SIP 流量的 DNS 负载平衡。 这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关 DNS 负载平衡的详细信息，请参阅规划文档中[Lync Server 2013 中的 "DNS 负载平衡](lync-server-2013-dns-load-balancing.md)"。

  - **Exchange UM 部署。** 此参考拓扑包括一个 Exchange 统一消息（UM）服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的 lync [server 2013 中的 "规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)" 和 " [lync server 2013" 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。

  - **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。 有关详细信息，请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **推荐使用边缘服务器。**   虽然不需要部署边缘服务器，但我们建议在任何规模的部署中使用。 你可以通过部署边缘服务器来为当前组织防火墙外部的用户提供服务，从而最大化 Lync 服务器投资。 其优点包括：
    
      - 如果您的组织的用户在家里工作或在路上工作，您的组织的用户可以使用 Lync Server 功能。
    
      - 您的用户可以邀请外部用户参加会议。
    
      - 如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立*联盟关系*。 然后，您的 Lync 服务器部署将识别该联合组织的用户，从而更好地协作。
    
      - 用户可以与公共 IM 服务的用户交换即时消息，包括以下任何或所有内容： Windows Live、AOL、Yahoo\!和 Google 通话。 对于使用这些服务的公共 IM 连接，可能需要单独的许可证。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
        > <LI>
        > <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>

        
        </div>

  - **可以添加董事。**   如果此组织希望帮助增强安全以防拒绝服务攻击，它还可以部署一个控制器池。 Director 是 Lync Server 中的一种独立的可选服务器角色，它不会家庭用户帐户，也不能提供状态或会议服务。 它充当一个内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。 控制器对入站请求进行预身份验证，并将其重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 控制器可帮助将前端服务器与恶意流量（如拒绝服务（DoS）攻击）隔离。 如果网络被此类攻击中的无效外部通信所淹没，则流量将在 Director 处结束。

  - **建议使用 System Center Operations Manager。**  我们建议你监视 Lync Server 部署的运行状况，以帮助确保最终用户的服务可用性。 你可以使用适用于 Microsoft 的免费下载，通过适用于 Lync 的 System Center Operations Manager 管理包监控 Lync。 使用 Lync 管理包，你可以在出现问题时主动获得实时警报，运行合成事务以测试端到端 Lync 功能，获取有关服务可用性的报告等。 This helps you to proactively respond to issues with your deployment before end-users experience them.

</div>

<span> </span>

</div>

</div>

</div>

