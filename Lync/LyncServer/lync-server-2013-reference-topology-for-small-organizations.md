---
title: 适用于小型组织的 Lync Server 2013 参考拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726056b63dfa37864171a77913b5126c23b27045
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>小型组织中 Lync Server 2013 的参考拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

小型组织的参考拓扑显示了如何通过仅部署运行 Lync Server 的三台服务器来部署强健、高可用性的解决方案。

**小型组织的参考拓扑**

![部署三个服务器关系图的引用拓扑](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "部署三个服务器关系图的引用拓扑")

  - **部署此组织的一对标准版服务器**   在其中央站点有4000个用户。 组织已部署两个 Standard Edition 服务器并将它们配对在一起，以实现高可用性和灾难恢复。 每台服务器住宅2000用户，但在两台服务器之间同步所有用户的相关信息。 如果一台服务器出现故障，管理员可以将这些用户故障转移到其他服务器，并至少对用户造成中断。 有关 Lync Server 2013 中的高可用性和灾难恢复功能的详细信息，请参阅[在 Lync server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

  - **建议使用边缘服务器部署。**   尽管内部 IM、状态和会议不需要部署边缘服务器，但我们建议您在小型部署中进行部署。 您可以部署边缘服务器以向当前组织防火墙外部的用户提供服务，从而最大化 Lync Server 投资。 优势包括：
    
      - 如果您的组织的用户在家中或在路上工作，则您的组织自己的用户可以使用 Lync Server 功能。
    
      - 您的用户可以邀请外部用户参加会议。
    
      - 如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立*联合关系*。 然后，你的 Lync Server 部署将识别来自该联合组织的用户，从而实现更好的协作。
    
      - 您的用户可以与公共 IM 服务的用户交换即时消息，包括以下任一或所有内容： Windows Live、AOL、Yahoo\!和 Google 谈话。 对于使用这些服务的公共 IM 连接，可能需要单独的许可证。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
        > <LI>
        > <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>

        
        </div>

  - **分支站点的留存能力。**   此组织正在运行 Lync Server 的企业语音功能的试点计划。 某些用户使用 Lync Server 作为其唯一的语音解决方案。 其中一些语音试点用户位于分支站点。 分支站点没有到中央站点的可靠广域网（WAN）链接，因此在此部署了 Survivable 分支设备。 在部署此功能的情况下，如果 WAN 链接断开，分支站点的用户仍可以拨打和接听呼叫（组织中的呼叫和 PSTN 呼叫），具有语音邮件功能，并与两方即时消息（IM）进行通信。 此外，在 WAN 链接不可用时，也可以对用户进行身份验证。

  - **Exchange UM 部署。** 此参考拓扑包括一个 Exchange 统一消息（UM）服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的在 lync server [2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和[lync server 2013 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。

  - **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 Office Web Apps Server 使 PowerPoint 幻灯片可以显示在 Web 会议中。 有关详细信息，请参阅[配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

</div>

<span> </span>

</div>

</div>

</div>

