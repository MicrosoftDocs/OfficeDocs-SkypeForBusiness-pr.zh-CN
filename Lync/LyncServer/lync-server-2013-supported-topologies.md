---
title: Lync Server 2013 支持的拓扑
description: Lync Server 2013 支持的拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c19577fbda7e377e145abfd473d2cf8e6d4a1a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558018"
---
# <a name="supported-topologies-in-lync-server-2013"></a>Lync Server 2013 中支持的拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-01-14_

Lync Server 2013 支持在组织内部部署网站，并将本地部署与 Lync Online 部署（称为混合部署）集成。 在混合部署中，有些用户驻留在内部部署中，有些用户驻留在联机部署中。

对于本地部署，Lync Server 2013 支持部署一个或多个可进行扩展的网站，以满足高可用性和位置要求。 可以构造这些站点及其组件来满足组织的访问和复原要求。

Lync Server 2013 本地部署包含以下内容：

  - 部署中必须至少包含一个中央站点（也称为数据中心）。每个中央站点必须至少包含一个 Enterprise Edition 前端池或一个 Standard Edition 服务器。由以下内容构成：
    
      - Enterprise Edition 前端池，它由一台或多台前端服务器（出于可伸缩性考虑，通常至少包括两台前端服务器）和一台单独的后端服务器构成。 前端池最多可以包含12台前端服务器。 多台前端服务器需要负载平衡。 对于 SIP 流量，建议使用 DNS 负载平衡，但也支持硬件负载平衡。 如果对 SIP 流量使用 DNS 负载平衡，您仍需对 HTTP 流量使用硬件负载平衡器。 我们建议 SQL Server 镜像以实现数据库的高可用性。 后端数据库需要一个单独的实例，但可将存档数据库、监控数据库、持久聊天数据库和持久聊天合规性服务器与其并置。 Lync Server 2013 支持对部署中的文件共享使用共享群集。 有关数据库存储要求的详细信息，请参阅 [Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。 有关文件存储要求的详细信息，请参阅 [Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果您并置 Lync Server 数据库，我们强烈建议评估可能影响可用性和性能的所有因素。 若要验证故障转移功能，建议您测试所有故障转移方案。

        
        </div>
    
      - Standard Edition Server，包含一个并置的 SQL Server Express 数据库。

  - 部署中还可以有一个或多个与中央站点关联的分支站点。

本节介绍 Lync Server 2013 部署的网站和组件。 有关 Lync Server 2013 站点、拓扑和组件规划的详细信息，请参阅规划文档中规划 lync server 2013 和[Lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)[之前必须了解的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)。 有关以前版本的组件集成的详细信息，请参阅 [Lync Server 2013 中支持的迁移路径和共存方案](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。

<div>


> [!NOTE]  
> 前端、边缘、中介和控制器服务器角色不支持延伸池。



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>中央站点拓扑和组件（本地）

尽管中央站点拓扑必须包含一个前端池或一个 Standard Edition 服务器，但每个中央站点还可以包含以下内容：

  - 多个前端池，可位于同一个域或不同的域。尽管如此，前端池中的所有前端服务器和该池的后端服务器必须位于同一域中。

  - 多个 Standard Edition 服务器。

  - Office Web Apps Server，用于 Lync Server 2013 中的 Office Web 应用程序，用于处理 Microsoft PowerPoint 演示文稿的共享和呈现。

  - 边缘服务器或边缘池在外围网络中，如果您希望部署支持联盟伙伴、公共 IM 连接、可扩展消息和状态协议 (XMPP) 网关、远程用户访问、参与会议的匿名用户或 Exchange 统一消息 (UM) 。 不能将其他任何服务器角色与边缘服务器并置。 建议根据需要使用 DNS 负载平衡，但也支持硬件负载平衡。 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。 有关负载平衡要求和支持的详细信息，请参阅部署文档中的规划文档和在[Lync server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中的 "[在 lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)"。

  - 中介服务器或池，如果您想要在中央站点的前端池中支持企业语音或电话拨入式会议。 根据您部署企业语音支持的方式，您可以在 (默认) 或部署独立中介服务器或池的前端池中并置中介服务器。 当适当的) 从中介服务器池的网关对等分发流量（包括 PSTN 网关、ip-pbx 或 SIP 中继会话边界控制 (SBC) ）时，可以使用 DNS、硬件或应用程序负载平衡 (。有关规划相应中介服务器拓扑的详细信息，请参阅规划文档中的 [Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md) 。

  - 持久聊天服务器（如果您希望用户能够参与在一段时间内保持的基于主题的会话）。 为了提供更大的容量并提高可靠性，拓扑可以包含多台运行持久聊天服务器的计算机。 您不能并置持久聊天服务器与企业版池中的其他服务器角色。 不过，您可以在 Standard Edition 服务器上并置持久聊天服务器。 持久聊天需要一个数据库，如果实现持久聊天合规性，还需要一个持久聊天合规性数据库，但这些数据库可以与存档数据库或监控数据库并置，或者位于 Enterprise Edition 前端池的后端服务器上。 有关规划适当的持久聊天服务器拓扑的详细信息，请参阅规划文档中的在 [Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md) 。

  - 监控（如果要在部署中收集有关企业语音和 A/V 会议的音频/视频用户体验质量 (QoE) 和呼叫详细记录 (CDR) 的数据）。 （可选）可以将 Microsoft System Center Operations Manager 安装 (以前的 Microsoft Operations Manager) ，它使用监视 CDR 和 QoE 数据生成临近的实时警报，以显示呼叫可靠性和媒体质量的运行状况。 监控功能（如果部署）可位于前端服务器或 Standard Edition 服务器上。 监控需要一个数据库，但该数据库可与存档数据库、持久聊天数据库或持久聊天合规性数据库并置，或者位于 Enterprise Edition 前端池的后端服务器上。

  - 存档（如果要在部署中存档 IM 通信和会议内容（出于合规性考虑））。 存档（如果部署）可并置在前端服务器或 Standard Edition 服务器上。 存档存储需要部署存档数据库或与 Exchange 2013 存储集成。 如果同时使用这两种方式（称为 *混合模式*），则 exchange 2013 存储用于存储驻留在 Exchange 2013 上的用户的存档数据，而存档数据库用于存档部署中所有其他用户的数据。 如果需要存档数据库，则该数据库可以与监控数据库、持久聊天数据库或持久聊天合规性数据库并置，或者位于前端池的后端服务器上。 有关规划适当的存档拓扑的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md) 。

  - Director 或 Director pool，如果要促进 Lync Server 2013 用户请求对用户主池（可以是企业版前端池或 Standard Edition 服务器）的恢复和重定向。 我们建议您在支持外部用户访问的每个中央站点和部署一个或多个前端池的每个中央站点部署控制器或控制器池。 每个控制器池最多可包含十个控制器。 控制器无法与其他任何服务器角色并置。 有关规划相应控制器拓扑的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md) 。

  - 反向代理不是 Lync Server 2013 组件，但如果要支持联合用户共享 web 内容或支持移动流量，则此代理是必需的。 您不能并置具有任何 Lync Server 2013 服务器角色的反向代理服务器，但您可以通过在组织中对其他应用程序使用的现有反向代理服务器上配置支持，从而实现对 Lync Server 2013 部署的反向代理支持。 有关反向代理服务器的详细信息，请参阅部署文档中的 [为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md) 。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，A/V 会议、监视和存档运行在前端服务器上，不再是单独的服务器角色。



</div>

在中央站点部署的所有前端池和 Standard Edition Server 共享为中央站点部署的以下任何内容：

  - 控制器或控制器池

  - 独立的中介服务器或池

  - Office Web Apps Server

  - 边缘服务器或边缘池

  - 持久聊天服务器或池

  - 监控

  - 存档

<div>


> [!NOTE]  
> 如果要支持 Exchange 2013 统一消息的集成，但它不是 Lync Server 2013 网站的组件，则可以在 Lync Server 2013 部署中实施 Exchange UM 服务器。



</div>

多个中央站点还可以共享在一个中央站点部署的以下任何内容：

  - 独立的中介服务器或池

  - 边缘服务器或边缘池

  - 持久聊天服务器或池

  - 存档

  - 监控

<div>


> [!NOTE]  
> Exchange UM 服务器可通过 Lync Server 2013 部署实施，并由多个中央站点共享，但它不是 Lync Server 2013 网站的组件。



</div>

有关 Lync Server 2013 服务器角色和功能的详细信息，请参阅规划文档中的 " [Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md) "。

有关 Lync Server 2013 Server 并置支持的摘要，请参阅 [Lync server 2013 中的受支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

除了本节前面所述的服务器角色和功能之外，Lync Server 2013 还提供了其他组件和选项，其中可能包括以下部分或全部选项：

  - 道

  - PSTN 网关（如果部署企业语音）

  - Exchange UM 服务器

  - DNS 负载平衡

  - 硬件负载平衡器

  - SQL Server 数据库

  - 文件共享

有关所有 Lync Server 2013 功能、组件和选项的详细信息，请参阅规划文档。

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>分支站点拓扑和组件（本地）

分支站点与中央站点关联，分支站点中的每个 Survivable Branch Appliance 均与关联中央站点中的 Enterprise Edition 前端池或 Standard Edition 服务器相关联。分支站点的大多数功能都取决于中央站点，因此分支站点的组件仅包含以下内容：

  - Survivable 分支设备，它将公共交换电话网络与某些 Lync Server 功能结合 (PSTN) 网关。 中介服务器可以与 Survivable 分支设备上的注册器实例并置，也可以部署独立的中介服务器或中介服务器池。

  - 一个 Survivable 分支服务器，它是一个运行 Windows Server 且安装了 Lync Server 2013 注册器和中介服务器软件的服务器。

  - 独立的 PSTN 网关（不是 Survivable Branch Appliance 的一部分）和独立的中介服务器。

Survivable 分支服务器的要求与对任何 Lync Server 2013 服务器角色的要求相同。

</div>

</div>

<span> </span>

</div>

</div>

</div>

