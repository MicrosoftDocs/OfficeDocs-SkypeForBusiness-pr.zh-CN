---
title: Lync Server 2013 初始规划决策
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fdc9b9e2494078a8db4b524e9ffb6b2794c545d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512569"
---
# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013 的初始规划决策

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

规划过程的第一部分是确定您的组织所需的 Lync Server 工作负载和主要功能。

1.  **您是否需要内部部署或联机部署？**    Lync Server 支持这两种部署方案。 有关做出此决定的详细信息，请参阅本部分前面的 [决定如何部署 Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)。

2.  **您是否需要物理或虚拟化拓扑？**    Lync Server 支持物理和虚拟化拓扑中的所有工作负荷和服务器角色。 物理拓扑与虚拟拓扑在用户容量和可伸缩性上有所不同。 有关详细信息，请参阅 [在虚拟服务器上运行 Lync Server 2013](lync-server-2013-running-lync-server-on-virtual-servers.md)。

3.  **即时消息* (IM) *和*状态*始终处于启用状态。**    在任何 Lync Server 部署中，默认情况下会安装并启用即时消息 (IM) 和状态工作负荷。 通过 IM，用户可以使用实时文本消息进行通信；通过状态，用户可以查看网络上其他用户的状态。 用户的状态提供的信息有助于其他用户决定是否应尝试联系该用户以及以何种方式联系。 有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划前端服务器、即时消息和状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) 。

4.  **是否要部署任何会议模式？**    会议是 Lync Server 的另一核心功能。 支持多种会议模式。 可以选择部署所有支持的会议类型，也可以选择部署其中的几种。 通过 *Web 会议*，用户可以查看文件，例如要演示的使用 Microsoft PowerPoint 演示文稿图形程序创建的幻灯片组。 通过 *应用程序共享*，用户可以实时相互共享全部或部分桌面。 通过 *A/V 会议*，用户可以将音频（也可以和视频一起）添加到其会议和对等通信中。 通过*电话拨入式会议*，用户可以使用标准 PSTN 电话加入组织承载的会议的音频部分。 有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md) 。
    
    在 Lync Server 2013 中，如果部署 Web 会议，还必须规划与 Office Web Apps Server 集成以在会议中启用 Powerpoint 共享和查看。 有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

5.  **如果部署 A/V 会议，还应监视这些会议的音频质量。**    许多因素会影响 Lync Server A/V 会议的音频和视频质量。 通过使用监控，可以监控呼叫和会议的 A/V 质量。 还可以检测影响媒体质量的问题，从而确保用户拥有可能的最佳媒体体验。 有关详细信息，请参阅 [在 Lync Server 2013 中规划监视](lync-server-2013-planning-for-monitoring.md)。

6.  **您是否希望为您的 IM、状态和会议服务器提供高可用性？**    如果在提供即时消息、状态和会议功能的站点上只有一台服务器，则当该服务器停止运行时，用户的工作效率会受到极大影响。 通过为这些功能部署至少三台服务器的企业版 *池* ，即使服务器不可用，Lync Server 也可以继续正常运行所有这些功能。
    
    对于有5000或更少用户需要高可用性的组织，另一种方法是部署两台运行 Lync Server Standard Edition 的服务器，并将这些服务器组合在一起。 有关详细信息，请参阅 [Lync Server 2013 中的规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

7.  **是否需要灾难恢复选项？**    如果你有两个数据中心，并且需要灾难恢复选项以使你的用户能够在某个数据中心的所有或多台服务器出现故障时继续工作，则可以在部署服务器时考虑灾难恢复。 在这种部署中，将一个数据中心的一个服务器池与另一个数据中心中的相应池组成一对。 如果一个数据中心出现故障，组对的另一个池可以为两个池的用户提供服务，从而将服务中断降至最低。 有关详细信息，请参阅 [Lync Server 2013 中的规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

8.  **您是否希望让您的用户与外部用户进行通信和协作？**    启用与外部用户的通信和协作可增加 Lync Server 的投资回报。 这样，贵组织自己的用户可以从 Lync Server 功能获益，即使他们在组织的防火墙外部工作也是如此。 您还可以与运行 Lync Server 的合作伙伴或客户组织联盟。 通过执行此操作，您的用户和联盟伙伴用户可以轻松地发送和接收即时消息，并相互邀请参加会议，并彼此查看状态。 此外，您的用户可以使用电子邮件将特定外部用户邀请他们组织的会议。 有关详细信息，请参阅 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

9.  **是否要部署企业语音？**    *企业语音* 是由 Lync Server 提供 (VoIP) 解决方案的 IP 语音。 它是基于 PBX 的传统电话的出色替代品。 使用企业语音，用户可以通过单击 Outlook 或 Lync Server 中的联系人，从其计算机或 VoIP 电话中发出呼叫。 他们可以通过 IP 网络从计算机向计算机、从计算机向电话或从电话向计算机发出呼叫。 用户会从在自己的计算机中集成所有可用通信选项（语音、电子邮件、IM 和会议）中受益匪浅。 有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划企业语音](lync-server-2013-planning-for-enterprise-voice.md) 。

10. **如果部署企业语音，则还应监视这些呼叫的音频质量。**    我们建议您使用监控，以确保企业语音呼叫的音频质量（如果部署企业语音）。 有关详细信息，请参阅 [在 Lync Server 2013 中规划监视](lync-server-2013-planning-for-monitoring.md)。

11. **您是否需要出于合规性目的来存档 IM 内容或会议内容？**    如果您的组织必须出于合规性目的对 IM 内容或会议内容进行存档，则可以部署存档。 有关详细信息，请参阅 [在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

12. **是否要部署持久聊天？**    如果您希望让您的用户具有可在一段时间内持续存在的实时会话，则可以部署持久聊天。 有关详细信息，请参阅 [在 Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

13. **是否已部署 Microsoft Exchange？**    如果您的组织将 Microsoft Exchange Server 用于其电子邮件服务，则可以启用多种功能，以增强 Lync Server 和 Microsoft Exchange Server 的有用性。 其中一些称为 Exchange 统一消息 (UM) 的功能包括允许用户接收语音邮件通知和收听来自 Outlook 或 Outlook Web Access 的语音邮件、使用电话访问其 Microsoft Exchange 邮箱以及在其 Microsoft Exchange 邮箱中接收传真。 此外，如果部署了 Exchange 2013，可以在两个系统之间集成用户的联系人存储，使用 Exchange 存储更高分辨率的联系人照片，并集成电子邮件和即时消息的存档。 有关详细信息，请参阅 [规划 Exchange Server 与 Lync server 集成 2013](lync-server-2013-planning-for-exchange-server-integration.md)。

14. **您的组织中是否有分支机构？**    如果你的组织具有分支机构，Lync Server 支持多种方式来支持它们，并确保其对语音和其他功能的恢复能力。 特别是，在没有到数据中心的弹性 WAN 链接的分支机构中，您可以安装 Survivable 分支装置或 Survivable 分支服务器，以维护企业语音支持 (WAN) 链接。 有关详细信息，请参阅 [Lync Server 2013 中的规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

</div>

<span> </span>

</div>

</div>

</div>

