---
title: Lync Server 2013 初始规划决策
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013 的初始规划决策

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

规划过程的第一部分是确定你的组织需要哪些 Lync Server 工作负荷和主要功能。

1.  **您是否需要内部部署或联机部署？**   Lync Server 支持这两种部署方案。 有关做出此决定的详细信息, 请参阅本部分前面的[确定如何部署 Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)。

2.  **您是否需要物理或虚拟化拓扑？**   Lync Server 支持物理和虚拟拓扑中的所有工作负荷和服务器角色。 用户容量和可伸缩性在物理拓扑和虚拟拓扑之间可能有所不同。 有关详细信息, 请参阅[在虚拟服务器上运行 Lync Server 2013](lync-server-2013-running-lync-server-on-virtual-servers.md)。

3.  **即时消息 *(IM)* 和*状态*始终处于启用状态。**   在任何 Lync 服务器部署中, 默认情况下安装并启用即时消息 (IM) 和状态工作负荷。 IM 使用户能够与实时文本消息进行通信, 并且联机状态允许他们查看网络上其他用户的状态。 用户的状态提供信息以帮助其他人决定是否应尝试联系用户以及采取何种方式。 有关详细信息, 请参阅规划文档中的在[Lync Server 2013 中规划前端服务器、即时消息和状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。

4.  **是否要部署任何会议模式？**   会议是 Lync Server 的另一核心功能。 支持多种会议模式。 你可以选择部署所有受支持的会议类型, 或仅部署其中一部分。 *网络会议*使用户可以查看文件, 例如, 使用 Microsoft PowerPoint 演示文稿图形程序创建的幻灯片放映。 *应用程序共享*使用户能够实时共享其全部或部分桌面。 有*了 A/V 式会议*, 用户可以向其会议和对等通信添加音频 (也可能是视频)。 *电话拨入式会议*使用户能够使用标准的 PSTN 电话加入组织中托管的会议的音频部分。 有关详细信息, 请参阅规划文档中的[在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md)。
    
    在 Lync Server 2013 中, 如果你部署 Web 会议, 你还必须规划与 Office Web Apps 服务器集成, 以在会议中启用 Powerpoint 共享和查看。 有关详细信息, 请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

5.  **如果你部署了 A/V 会议, 还应监视这些会议的音频质量。**   许多因素影响 Lync Server A/V 会议的音频和视频质量。 通过使用监视, 您可以监控通话和会议的 A/V 质量。 你可以检测影响媒体质量的问题, 并确保你的用户可以获得最佳的媒体体验。 有关详细信息, 请参阅[在 Lync Server 2013 中进行监视规划](lync-server-2013-planning-for-monitoring.md)。

6.  **您的 IM、状态和会议服务器是否需要高可用性？**   如果在提供即时消息、状态和会议功能的网站上只有一台服务器, 则如果该服务器出现故障, 用户的工作效率会受到严重影响。 通过为这些功能部署至少三台服务器的企业版*池*, 即使服务器不可用, Lync Server 也可以继续正常运行所有这些功能。
    
    对于有5000或更少用户需要高可用性的组织, 另一个选项是部署两台运行 Lync Server 标准版并将这些服务器配对在一起的用户。 有关详细信息, 请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

7.  **是否需要灾难恢复选项？**   如果你有两个数据中心, 并且需要灾难恢复选项以使你的用户能够在一个数据中心中的所有服务器或多台服务器停机时继续工作, 你可以在考虑灾难恢复时部署你的服务器。 对于此部署, 你可以将一个数据中心的服务器池与另一个数据中心中的相应池进行配对。 如果一个数据中心出现故障, 则该对中的另一个池可以通过最少的服务中断为两个池中的用户提供服务。 有关详细信息, 请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

8.  **是否要使你的用户能够与外部用户进行通信和协作？**   启用与外部用户的通信和协作可以增加 Lync Server 中的投资回报。 这样, 你的组织自身的用户可以从 Lync Server 功能中受益, 即使他们在组织的防火墙之外工作时也是如此。 您也可以与运行 Lync Server 的合作伙伴或客户组织联盟。 通过执行此操作, 你的用户和联盟伙伴用户可以轻松地发送和接收即时消息、邀请他们加入会议, 并查看彼此的状态。 此外, 你的用户可以使用电子邮件邀请特定外部用户加入他们组织的会议。 有关详细信息, 请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

9.  **是否要部署企业语音？**    *企业语音*是 Lync Server 提供的 IP 语音 (VoIP) 解决方案。 它为传统的基于 PBX 的电话提供了一种有吸引力的替代方法。 通过单击 Outlook 或 Lync Server 中的联系人, 企业语音允许用户将呼叫从其计算机或 VoIP 电话中。 他们可以通过 IP 网络将呼叫放在计算机、计算机到电话或电话到计算机上。 用户可以通过其计算机上的所有通信选项 (语音、电子邮件、IM 和会议) 获益。 有关详细信息, 请参阅规划文档中的[Lync Server 2013 中的 "规划企业语音](lync-server-2013-planning-for-enterprise-voice.md)"。

10. **如果部署企业语音, 还应监视这些呼叫的音频质量。**   如果部署企业语音, 建议使用监视来确保企业语音通话的音频质量。 有关详细信息, 请参阅[在 Lync Server 2013 中进行监视规划](lync-server-2013-planning-for-monitoring.md)。

11. **是否需要出于合规性目的对 IM 内容或会议内容进行存档？**   如果你的组织必须出于合规性目的对 IM 内容或会议内容进行存档, 则可以部署存档。 有关详细信息, 请参阅[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

12. **是否要部署持久聊天？**   如果你希望让你的用户能够拥有可随时持续的实时对话, 你可以部署持久聊天。 有关详细信息, 请参阅[在 Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

13. **是否已部署 Microsoft Exchange？**   如果你的组织为其电子邮件服务使用 Microsoft Exchange Server, 你可以启用多个功能来增强 Lync Server 和 Microsoft Exchange Server 的实用性。 其中一些称为 Exchange 统一消息 (UM) 的功能, 包括允许用户接收语音邮件通知和从 Outlook 或 Outlook Web Access 收听语音邮件、使用电话访问 Microsoft Exchange 邮箱以及在中接收传真其 Microsoft Exchange 邮箱。 此外, 如果你已部署 Exchange 2013, 你可以为两个系统之间的用户集成联系人存储, 使用 Exchange 存储更高分辨率的联系人照片, 并集成电子邮件和即时消息的存档。 有关详细信息, 请参阅[规划与 Lync server 2013 的 Exchange Server 集成](lync-server-2013-planning-for-exchange-server-integration.md)。

14. **您的组织中是否有分支机构？**   如果你的组织具有分支机构, Lync Server 支持多种支持它们的方式, 并确保其对语音和其他功能的复原。 尤其是, 在没有到数据中心的弹性 WAN 链接的分支办公室中, 你可以安装 Survivable 分支装置或 Survivable 分支服务器, 以便在广域网 (WAN) 链接关闭的情况下保持企业语音支持。 有关详细信息, 请参阅[在 Lync Server 2013 中规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

</div>

<span> </span>

</div>

</div>

</div>

