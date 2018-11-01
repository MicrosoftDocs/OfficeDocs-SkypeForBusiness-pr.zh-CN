---
title: 小型组织的 Lync Server 2013 参考拓扑
TOCTitle: 小型组织的参考拓扑
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398095(v=OCS.15)
ms:contentKeyID: 49311851
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 小型组织中 Lync Server 2013 的参考拓扑

 

_**上一次修改主题：** 2013-10-07_

小型组织的参考拓扑显示了如何通过只部署三台运行 Lync Server 的服务器来部署一个稳固、高度可用的解决方案。

**小型组织的参考拓扑**

![用于部署三台服务器的参考拓扑图示](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "用于部署三台服务器的参考拓扑图示")

  - **部署 标准版 服务器对**    此组织的中央站点具有 4,000 个用户。该组织部署了两台 标准版 服务器，并将它们配成对来实现高可用性和灾难恢复。每台服务器承载 2,000 个用户，但是所有用户的信息会在两台服务器之间同步。如果一台服务器出现故障，管理员可以进行故障转移，由另一台服务器继续为这些用户提供服务，从而将对用户造成的干扰降到最低。有关 Lync Server 2013 中的高可用性和灾难恢复功能的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

  - **建议部署边缘服务器。** 尽管对于内部 IM、状态和会议，部署边缘服务器不是必需的，但我们建议进行部署，即使是小型的部署。通过部署边缘服务器来向目前位于组织防火墙之外的用户提供服务，可以最大限度地提高 Lync Server 投资回报。其优点包括：
    
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

  - **分支站点生存能力。** 该组织正在运行 Lync Server 的企业语音功能的试点计划。有些用户使用 Lync Server 作为其唯一的语音解决方案。其中一些语音试点用户位于分支站点。分支站点没有可靠的广域网 (WAN) 链路连接到中央站点，所以在那里部署了一个 Survivable Branch Appliance。这样一来，如果 WAN 链路出现故障，分支站点上的用户仍然可以发出和接收呼叫（组织内的呼叫和 PSTN 呼叫），继续使用语音邮件功能，并使用双方即时消息 (IM) 进行通信。当 WAN 链路不可用时，仍然能够对用户进行身份验证。

  - **Exchange UM 部署。** 此参考拓扑包括一个 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server 而非 Lync Server。
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和[Lync Server 2013 中的托管 Exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。

  - **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。有关更多信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

