---
title: 中型组织的 Lync Server 2013 参考拓扑
TOCTitle: 中型组织的参考拓扑
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425939(v=OCS.15)
ms:contentKeyID: 49312692
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 中型组织中的 Lync Server 2013 参考拓扑

 

_**上一次修改主题：** 2013-10-07_

具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。下图中的具体拓扑用于拥有 20,000 个用户的组织。

**中型组织的参考拓扑**

![用于单个数据中心的参考拓扑图示](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "用于单个数据中心的参考拓扑图示")

  - **通过添加更多前端服务器来容纳更多用户。**    此图中的具体拓扑包含三台前端服务器，可支持 20,000 个用户。如果具有一个中央站点和更多用户，则只需将更多前端服务器添加到池中。每个池最多可支持 80,000 个用户，可包含 12 台前端服务器。
    
    但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。

  - **可以添加灾难恢复。**    对于此组织而言，其 Lync Server 服务的高可用性是一个必要功能，而灾难恢复则不是。此组织已部署的 前端服务器池提供了高可用性。
    
    如果需要添加灾难恢复功能，可以考虑建立另一个数据中心并添加另一个前端池，同时将其当前数据中心内的前端池配对。之后，如果发生影响其主池的灾难，则管理员可以将用户故障转移到备份池。

  - **后端服务器 进行镜像处理**   为了实现基础用户功能的更高可用性，此组织已为每个 前端池部署一个 后端服务器镜像对。这是针对 Lync Server 2013 的一个新的拓扑选项，并且是可选的。您可以选择改为部署单个 后端服务器。

  - **监控服务器数据库选项。**    此组织已部署监控以确保企业语音呼叫和 A/V 会议的质量。在每个前端服务器上部署监控，并且监控数据库将与后端服务器并置。我们还支持监控数据库在其中位于单独的服务器上的拓扑。

  - **边缘服务器高可用性**    在拥有 20,000 个用户的组织示例中，只需一台边缘服务器即可满足性能需求。但已提供一个部署了两个边缘服务器的池以便实现高可用性。

  - **分支站点部署选项。** 此拓扑中的组织已将企业语音部署为其语音解决方案。分支站点 1 没有指向中央站点的可恢复广域网 (WAN) 链接，因此该站点部署了 Survivable Branch Appliance，以在指向中央站点的 WAN 链路出现故障时，继续提供许多 Lync Server 功能。但是，分支站点 2 具有可恢复 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。该处部署的 PSTN 网关支持媒体旁路，因此分支站点 2 上不需要中介服务器。有关决定在分支站点上部署的内容的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划分支站点语音恢复能力](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

  - **DNS 负载平衡。** 前端池和边缘服务器池已经部署了用于 SIP 流量的 DNS 负载平衡。这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)。

  - **Exchange UM 部署。** 此参考拓扑包括一个 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server 而非 Lync Server。
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和 [Lync Server 2013 中的托管 Exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。

  - **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。有关更多信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **建议使用边缘服务器。** 尽管部署边缘服务器不是必需的，但我们建议对其进行任何规模的部署。通过部署边缘服务器来向目前位于组织防火墙之外的用户提供服务，可以最大限度地提高 Lync Server 投资回报。其优点包括：
    
      - 组织自己的用户在家工作或在旅途中时，可以使用 Lync Server 功能。
    
      - 您的用户可以邀请外部用户参加会议。
    
      - 如果您的合作伙伴、供应商或客户组织也使用 Lync Server，则可以与该组织建立*联盟关系*。之后，您的 Lync Server 部署便可以识别来自联盟组织的用户，从而促进协作。
    
      - 您的用户可以与公共 IM 服务（包括以下任意或所有服务：Windows Live、AOL、Yahoo\! 和 Google Talk）的用户交换即时消息。与这些服务建立公共 IM 连接可能需要单独的许可证。
        
        > [!IMPORTANT]  
		> <ul>
        > <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
        > <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
        > <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
        > </ul>

  - **可以添加控制器。** 如果此组织希望增强安全性以抵御拒绝服务攻击，也可以部署控制器池。在 Lync Server 中， 控制器是一个可选的单独服务器角色，它不承载用户帐户，也不提供状态或会议服务。控制器可用作内部的下一跃点服务器， 边缘服务器会将发往内部服务器的入站 SIP 流量路由到它。 控制器预先对入站请求进行身份验证，并将其重定向至用户的主池或主服务器。控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 控制器有助于使前端服务器免遭恶意流量（如拒绝服务 (DoS) 攻击）的侵袭。如果在此类攻击中网络中涌入大量无效外部流量，则这些流量将会在 控制器处终止。

  - **建议使用 System Center Operations Manager。**   建议您监控 Lync Server 部署的运行状况以帮助确保最终用户的服务可用性。您可使用 Microsoft 作为免费下载提供的适用于 Lync 的 System Center Operations Manager 管理包监控 Lync。使用 Lync 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Lync 功能以及获取服务可用性的报告等。这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。

