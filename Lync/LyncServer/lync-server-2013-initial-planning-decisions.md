---
title: Lync Server 2013 初始规划决策
TOCTitle: 初始规划决策
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398855(v=OCS.15)
ms:contentKeyID: 49314260
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的初始规划决策

 

_**上一次修改主题：** 2012-10-01_

规划过程的第一部分是确定组织需要哪些 Lync Server 工作负荷和主要功能。

1.  **需要内部部署还是联机部署？**    Lync Server 支持这两种部署方案。有关做出此决策的详细信息，请参阅本节前面的 [确定如何部署 Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)

2.  **需要物理拓扑还是虚拟拓扑？** Lync Server 支持物理拓扑和虚拟拓扑中的所有工作负荷和服务器角色。物理拓扑与虚拟拓扑在用户容量和可伸缩性上有所不同。有关详细信息，请参阅 [在虚拟服务器上运行 Lync Server](lync-server-2013-running-lync-server-on-virtual-servers.md)。

3.  **即时消息 *(IM)* 和 *状态* 始终处于启用状态。** 在任何 Lync Server 部署中，默认情况下都会安装并启用即时消息 (IM) 和状态工作负荷。通过 IM，用户可以使用实时文本消息进行通信；通过状态，用户可以查看网络上其他用户的状态。用户的状态提供的信息有助于其他用户决定是否应尝试联系该用户以及以何种方式联系。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划前端服务器、即时消息和状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。

4.  **是否要部署任何会议模式？** 会议是 Lync Server 的另一项核心功能。支持多种会议模式。可以选择部署所有支持的会议类型，也可以选择部署其中的几种。通过 *Web 会议* ，用户可以查看文件，例如要演示的使用 Microsoft PowerPoint 演示文稿图形程序创建的幻灯片组。通过 *应用程序共享* ，用户可以实时相互共享全部或部分桌面。通过 *A/V 会议* ，用户可以将音频（也可以和视频一起）添加到其会议和对等通信中。通过 *电话拨入式会议* ，用户可以使用标准 PSTN 电话加入组织承载的会议的音频部分。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md)。
    
    在 Lync Server 2013 中，如果部署 Web 会议，还必须规划与 Office Web Apps Server 的集成，以在会议中启用 Powerpoint 共享和查看。有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

5.  **如果部署 A/V 会议，则还应监控这些会议的音频质量。** 许多因素会影响 Lync Server A/V 会议的音频和视频质量。通过使用监控，可以监控呼叫和会议的 A/V 质量。还可以检测影响媒体质量的问题，从而确保用户拥有可能的最佳媒体体验。有关更多信息，请参阅 [在 Lync Server 2013 中规划监控](lync-server-2013-planning-for-monitoring.md)。

6.  **是否需要 IM、状态以及会议服务器的高可用性？** 如果站点中只有一台服务器提供 IM、状态和会议功能，则当该服务器出现故障时用户的工作效率将受到极大影响。通过为 企业版*池* 中的至少三台服务器部署这些功能，即使某台服务器不可用， Lync Server 也仍可以继续运行所有这些功能。
    
    对于具有 5000 名或更少需要高可用性的用户的组织，另一个选项是部署两台运行 Lync Server标准版 的服务器并将这两台服务器组成一对。有关详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

7.  **是否需要灾难恢复选项？**   如果有两个数据中心，并且需要灾难恢复选项使用户可在一个数据中心的所有或多台服务器出现故障时能继续工作，则可以考虑为服务器部署灾难恢复。在这种部署中，将一个数据中心的一个服务器池与另一个数据中心中的相应池组成一对。如果一个数据中心出现故障，组对的另一个池可以为两个池的用户提供服务，从而将服务中断降至最低。有关详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

8.  **是否要使用户可以与外部用户通信和协作？** 启用与外部用户的通信与协作可以提高 Lync Server 的投资回报率，从而使组织自己的用户可以从 Lync Server 功能中获益，即使他们在组织的防火墙之外工作也是如此。还可以与运行 Lync Server 的伙伴或客户组织建立联盟。这样，您的用户和联盟伙伴的用户就可以轻松地发送和接收 IM 消息、邀请彼此参加会议以及查看彼此的状态。此外，您的用户还可以使用电子邮件邀请特定的外部用户参加其组织的会议。有关详细信息，请参阅 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

9.  **是否要部署企业语音？** *企业语音* 是 Lync Server 提供的 IP 语音 (VoIP) 解决方案。它是基于 PBX 的传统电话的出色替代品。借助于企业语音，用户可以从自己的计算机或 VoIP 电话通过单击 Outlook 或 Lync Server 中的联系人来发出呼叫。他们可以通过 IP 网络从计算机向计算机、从计算机向电话或从电话向计算机发出呼叫。用户会从在自己的计算机中集成所有可用通信选项（语音、电子邮件、IM 和会议）中受益匪浅。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划企业语音](lync-server-2013-planning-for-enterprise-voice.md)。

10. **如果部署企业语音，则还应监控这些呼叫的音频质量。** 建议使用监控来确保企业语音呼叫的音频质量（如果部署企业语音）。有关详细信息，请参阅 [在 Lync Server 2013 中规划监控](lync-server-2013-planning-for-monitoring.md)。

11. **是否出于合规性目的而需要存档 IM 内容或会议内容？** 如果组织出于合规性目的必须存档 IM 内容或会议内容，则可以部署存档服务器。有关详细信息，请参阅 [在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

12. **是否需要部署持久聊天？**   如果想要使用户进行可持续的实时对话，则可以部署持久聊天。有关详细信息，请参阅 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

13. **是否要部署 Exchange UM？** 如果组织将 Microsoft Exchange Server 用于其电子邮件服务，则可以启用多种功能来增强 Lync Server 和 Microsoft Exchange Server 的实用性。其中一些功能（称为 Exchange 统一消息 (UM)）包括使用户接收语音邮件通知和收听 Outlook 或 Outlook Web Access 中的语音邮件、使用电话访问其 Microsoft Exchange 邮箱以及在其 Microsoft Exchange 邮箱中接收传真。此外，如果部署 Exchange 2013，可以集成两个系统之间用户的联系人存储库、使用 Exchange 存储更高分辨率的联系人照片以及集成电子邮件和即时消息的存档。有关详细信息，请参阅 [规划 Exchange Server 集成](lync-server-2013-planning-for-exchange-server-integration.md)。

14. **组织中是否有分支机构？** 如果组织中有分支机构， Lync Server 可以通过多种方式支持这些分支机构，并确保其语音以及其他功能的恢复能力。特别是，在没有指向数据中心的可恢复 WAN 链路的分支机构中，可以安装 Survivable Branch Appliance 或 Survivable Branch Server 来维护企业语音支持，以防广域网 (WAN) 链接出现故障。有关详细信息，请参阅 [在 Lync Server 2013 中规划分支站点语音恢复能力](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

