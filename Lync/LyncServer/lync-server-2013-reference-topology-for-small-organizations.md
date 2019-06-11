---
title: 适用于小型组织的 Lync Server 2013 参考拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06a3585a342ecc7fa7c41ff2b2b2682d2b8a0c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>小型组织中 Lync Server 2013 的参考拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

小型组织的参考拓扑显示如何通过仅部署三台运行 Lync Server 的服务器来部署强健、高可用性的解决方案。

**小型组织的参考拓扑**

![部署三个服务器图的引用拓扑](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "部署三个服务器图的引用拓扑")

  - **部署此组织的标准版服务器对**   其中心网站有4000用户。 组织部署了两个标准版服务器并将它们配对在一起以支持高可用性和灾难恢复。 Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. 有关 Lync Server 2013 中的高可用性和灾难恢复功能的详细信息, 请参阅[Lync server 2013 中的 "规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)"。

  - **建议使用边缘服务器部署。**   尽管内部即时消息、状态和会议不需要部署边缘服务器, 但我们建议你在小型部署中使用。 你可以通过部署边缘服务器来为当前组织防火墙外部的用户提供服务, 从而最大化 Lync 服务器投资。 其优点包括：
    
      - 如果您的组织的用户在家里工作或在路上工作, 您的组织的用户可以使用 Lync Server 功能。
    
      - 您的用户可以邀请外部用户参加会议。
    
      - 如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织, 则可以与该组织建立*联盟关系*。 然后, 您的 Lync 服务器部署将识别该联合组织的用户, 从而更好地协作。
    
      - 用户可以与公共 IM 服务的用户交换即时消息, 包括以下任何或所有内容: Windows Live、AOL、Yahoo\!和 Google 通话。 对于使用这些服务的公共 IM 连接, 可能需要单独的许可证。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</P>
        > <LI>
        > <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>

        
        </div>

  - **分支网站留存。**   此组织正在运行 Lync Server 的企业语音功能的试点计划。 某些用户使用 Lync Server 作为其唯一的语音解决方案。 其中一些语音试点用户位于分支站点。 分支站点没有指向中心网站的可靠广域网 (WAN) 链接, 因此 Survivable 分支装置将部署在此处。 这样一来，如果 WAN 链路出现故障，分支站点上的用户仍然可以发出和接收呼叫（组织内的呼叫和 PSTN 呼叫），继续使用语音邮件功能，并使用双方即时消息 (IM) 进行通信。 当 WAN 链路不可用时，仍然能够对用户进行身份验证。

  - **Exchange UM 部署。** 此参考拓扑包括一个 Exchange 统一消息 (UM) 服务器, 该服务器运行 Microsoft Exchange Server, 而不是 Lync Server。
    
    有关 Exchange UM 的详细信息, 请参阅规划文档中的 lync [server 2013 中的 "规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)" 和 " [lync server 2013" 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。

  - **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 Office Web Apps 服务器使 PowerPoint 幻灯片可以在 Web 会议中显示。 有关详细信息, 请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

</div>

<span> </span>

</div>

</div>

</div>

