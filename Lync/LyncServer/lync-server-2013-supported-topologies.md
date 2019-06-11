---
title: Lync Server 2013 支持的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Lync Server 2013 中支持的拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-01-14_

Lync Server 2013 支持在组织内部部署网站, 并使用 Lync Online 部署 (称为混合部署) 集成本地部署。 在混合部署中, 某些用户在本地托管, 某些用户是在线托管的。

对于本地部署, Lync Server 2013 支持部署一个或多个可缩放的网站, 以满足高可用性和位置要求。 你可以组织这些网站及其组件, 以满足你的组织的访问权限和复原要求。

Lync Server 2013 内部部署包含以下内容:

  - 你的部署必须包含至少一个中心网站 (也称为数据中心)。 每个中心网站必须包含至少一个企业版前端池或一个标准版服务器。 其中包括以下内容:
    
      - 企业版前端池, 由一个或多个前端服务器 (通常是至少两个前端服务器的可伸缩性) 和单独的后端服务器组成。 前端池最多可以包含十二个前端服务器。 对于多个前端服务器, 需要负载平衡。 对于 SIP 流量, 我们建议采用 DNS 负载平衡, 但硬件负载平衡也受支持。 如果你对 SIP 流量使用 DNS 负载平衡, 你仍然需要用于 HTTP 流量的硬件负载平衡器。 我们建议 SQL Server 镜像以实现数据库的高可用性。 后端数据库需要单独的实例, 但你可以将存档数据库、监视数据库、持久聊天数据库和持久聊天合规性数据库 collocate。 Lync Server 2013 支持对部署中的文件共享使用共享群集。 有关数据库存储要求的详细信息, 请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。 有关文件存储要求的详细信息, 请参阅[Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果您 collocate Lync Server 数据库, 我们强烈建议评估可能影响可用性和性能的所有因素。 若要验证故障转移功能，建议您测试所有故障转移方案。

        
        </div>
    
      - 标准版服务器, 其中包括 collocated SQL Server Express 数据库。

  - 您的部署还可以有一个或多个与中央站点相关联的分支站点。

本部分介绍 Lync Server 2013 部署的网站和组件。 有关 Lync Server 2013 网站、拓扑和组件规划的详细信息, 请参阅规划文档中 Lync server 2013 和[Lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)[之前必须了解的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)。 有关以前版本的组件集成的详细信息, 请参阅[Lync Server 2013 中支持的迁移路径和共存方案](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。

<div>


> [!NOTE]  
> 前端、Edge、中介和控制器服务器角色不支持延伸池。



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>中心网站拓扑和组件 (内部部署)

虽然中心站点拓扑必须包括一个前端池或一个标准版服务器, 但每个中心网站也可以包含以下内容:

  - 多个前端池, 可以位于同一个域或不同域中。 但是, 前端池中的所有前端服务器和该池的后端服务器必须位于同一个域中。

  - 多个标准版服务器。

  - Office Web Apps 服务器, 可与 Lync Server 2013 中的 Office Web 应用程序一起处理 Microsoft PowerPoint 演示文稿的共享和呈现。

  - 如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关、远程用户访问、参与会议中的匿名用户, 请在外围网络中使用边缘服务器或边缘池。或 Exchange 统一消息 (UM)。 您不能与 Edge 服务器 collocate 任何其他服务器角色。 我们建议在适当的情况下提供 DNS 负载平衡, 但硬件负载平衡也受支持。 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。 有关负载平衡要求和支持的详细信息, 请参阅部署文档中的 "在 lync server [2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)" 和 "[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。

  - 中介服务器或池, 如果你想要在中心网站上的前端池中支持企业语音或拨入式会议。 根据部署企业语音支持的方式, 你可以 collocate 前端池中的中介服务器 (默认) 或部署独立的中介服务器或池。 你可以使用 DNS、硬件或应用程序负载平衡 (如果适用) 来分配来自中介服务器池的网关对等的流量, 包括 PSTN 网关、IP PBX 或 SIP 中继会话边界控制 (SBC)。有关规划相应中介服务器拓扑的详细信息, 请参阅规划文档中[Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

  - 持久聊天服务器, 如果你希望用户能够参与多个基于主题的对话, 这些对话会随着时间的推移而保留。 为了提供更大的容量和增强的可靠性, 你的拓扑可以包括多台运行持久聊天服务器的计算机。 您不能将持久聊天服务器与企业版池中的其他服务器角色 collocate。 但是, 你可以在标准版服务器上 collocate 持久聊天服务器。 持久聊天需要数据库, 并且如果你实现持久聊天合规性数据库, 但数据库可以与存档数据库、监视数据库或企业版的后端服务器 collocated前端池。 有关规划合适的持久聊天服务器拓扑的详细信息, 请参阅规划文档中的在[Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

  - 监视: 如果你想要支持音频/视频体验质量 (QoE) 的数据收集, 并在你的部署中调用企业语音和 A/V 会议的详细录制 (CDR)。 或者, 你可以安装 Microsoft System Center Operations Manager (以前称为 Microsoft Operations Manager), 它使用监视 CDR 和 QoE 数据来生成接近的实时警报, 显示通话可靠性和媒体质量的运行状况。 监视 (部署后) 在前端服务器或标准版服务器上 collocated。 监视需要数据库, 但数据库可以与存档数据库、持久聊天数据库、持久聊天合规数据库或企业版前端池的后端服务器 collocated。

  - 存档: 如果你希望在你的部署中存档 IM 通信和会议内容 (出于合规性原因)。 存档 (部署后) 在前端服务器或标准版服务器上 collocated。 存档存储需要部署存档数据库或与 Exchange 2013 存储集成。 如果同时使用这两个 (即*混合模式*), exchange 2013 存储用于存储托管在 Exchange 2013 上的用户的存档数据, 而存档数据库用于存档部署中所有其他用户的数据。 如果需要存档数据库, 可以在监视数据库、持久聊天数据库、持久聊天合规数据库或前端池的后端服务器上 collocated 数据库。 有关规划相应的存档拓扑的详细信息, 请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

  - Director 或控制器池, 如果你想要方便将 Lync Server 2013 用户请求恢复和重定向到用户的主池, 它可以是企业版前端池或标准版服务器。 我们建议你在支持外部用户访问的每个中心网站以及你部署一个或多个前端池的每个中心网站中部署 Director 或控制器池。 每个控制器池最多可包含10个控制器。 Director 不能与任何其他服务器角色 collocated。 有关规划合适的控制器拓扑的详细信息, 请参阅规划文档中[Lync Server 2013 中的 Director 的方案](lync-server-2013-scenarios-for-the-director.md)。

  - 反向代理 (不是 Lync Server 2013 组件), 但如果您希望支持对联盟用户的 web 内容的共享或支持移动通信, 则该代理是必需的。 不能将反向代理服务器与任何 Lync Server 2013 服务器角色 collocate, 但你可以通过在你的组织中用于其他用户的现有反向代理服务器上配置支持, 为 Lync Server 2013 部署实现反向代理支持应用. 有关反向代理服务器的详细信息, 请参阅部署文档中[的 Lync Server 2013 的 "设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)"。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中, A/V 会议、监视和存档运行在前端服务器上, 不再是单独的服务器角色。



</div>

您在中心网站上部署的所有前端池和标准版服务器都将共享您为中心网站部署的以下任何内容:

  - 导演或控制器池

  - 独立中介服务器或池

  - Office Web Apps Server

  - 边缘服务器或边缘池

  - 持久聊天服务器或池

  - 监控

  - 存档

<div>


> [!NOTE]  
> 如果你想要支持 Exchange 2013 统一消息的集成, 但它不是 Lync Server 2013 网站的组件, 则可以使用 Lync Server 2013 部署实现 Exchange UM 服务器。



</div>

多个中心网站也可以共享在一个中心网站中部署的以下任何内容:

  - 独立中介服务器或池

  - 边缘服务器或边缘池

  - 持久聊天服务器或池

  - 存档

  - 监控

<div>


> [!NOTE]  
> Exchange UM 服务器可以通过 Lync Server 2013 部署实现并由多个中心网站共享, 但它不是 Lync Server 2013 网站的组件。



</div>

有关 Lync Server 2013 服务器角色和功能的详细信息, 请参阅规划文档中[Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。

有关 Lync Server 2013 服务器 collocation 支持的摘要, 请参阅[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md)。

除了本部分前面所述的服务器角色和功能之外, Lync Server 2013 还有其他组件和选项, 其中包括以下部分或全部选项:

  - 防火墙

  - PSTN 网关 (如果部署企业语音)

  - Exchange UM 服务器

  - DNS 负载平衡

  - 硬件负载平衡器

  - SQL Server 数据库

  - 文件共享

有关所有 Lync Server 2013 功能、组件和选项的详细信息, 请参阅规划文档。

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>分支站点拓扑和组件 (内部部署)

分支站点与中央站点相关联, 并且分支站点中的每个 Survivable 分支装置都与关联的中心网站中的企业版前端池或标准版服务器相关联。 分支站点依赖于中心网站查看大多数功能, 因此分支网站上的组件仅包含以下内容:

  - Survivable 分支设备, 它将公共交换电话网络 (PSTN) 网关与某些 Lync 服务器功能结合使用。 中介服务器可以与 Survivable 分支设备上的注册机构实例 collocated, 并且你可以部署独立的中介服务器或中介服务器池。

  - Survivable 分支服务器, 它是运行安装了 Lync Server 2013 注册机构和中介服务器软件的 Windows Server 的服务器。

  - 独立的 PSTN 网关 (不属于 Survivable 分支装置) 和独立中介服务器。

Survivable 分支服务器的要求与任何 Lync Server 2013 服务器角色的要求相同。

</div>

</div>

<span> </span>

</div>

</div>

</div>

