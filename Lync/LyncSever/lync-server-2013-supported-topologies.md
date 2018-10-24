---
title: Lync Server 2013 支持的拓扑
TOCTitle: 支持的拓扑
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425833(v=OCS.15)
ms:contentKeyID: 49312450
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中支持的拓扑

 

_**上一次修改主题：** 2014-01-14_

Lync Server 2013 支持在组织内部部署站点以及将内部部署与 Skype for Business Online 部署集成，这称为混合部署。在混合部署中，有些用户驻留在内部部署中，有些用户驻留在联机部署中。

对于内部部署， Lync Server 2013 支持部署一个或多个可通过扩展满足高可用性和位置要求的站点。可以构造这些站点及其组件来满足组织的访问和复原要求。

Lync Server 2013 内部部署由以下几个部分组成：

  - 部署中必须至少包含一个中央站点（也称为数据中心）。每个中央站点必须至少包含一个 Enterprise Edition 前端池或一个 Standard Edition 服务器。由以下内容构成：
    
      - Enterprise Edition 前端池，它由一台或多台前端服务器（出于可伸缩性考虑，通常至少包括两台前端服务器）和一台单独的后端服务器构成。前端池最多可包含十二台前端服务器。多台前端服务器需要负载平衡。对于 SIP 流量，建议使用 DNS 负载平衡，但也支持硬件负载平衡。如果对 SIP 流量使用 DNS 负载平衡，您仍需对 HTTP 流量使用硬件负载平衡器。建议使用 SQL Server 镜像来实现数据库的高可用性。后端数据库需要一个单独的实例，但可将存档数据库、监控数据库、持久聊天数据库和持久聊天合规性数据库与其并置。Lync Server 2013 还支持将共享群集用于部署中的文件共享。有关数据库存储要求的详细信息，请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。有关文件存储要求的详细信息，请参阅[Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。
        
        > [!IMPORTANT]  
        > 如果您将 Lync Server 数据库与其他数据库并置在一起，则强烈建议您评估可能影响可用性和性能的所有因素。若要验证故障转移功能，建议您测试所有故障转移方案。
    
      - Standard Edition Server，包含一个并置的 SQL Server Express 数据库。

  - 部署中还可以有一个或多个与中央站点关联的分支站点。

本节介绍 Lync Server 2013 部署的站点和组件。有关 Lync Server 2013 站点、拓扑和组件规划的详细信息，请参阅规划文档中的 [规划 Lync Server 2013 之前必须知道的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)和 [Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)。有关以前版本的组件集成的详细信息，请参阅 [Lync Server 2013 中支持的迁移路径和共存方案](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。

> [!NOTE]  
> 前端、边缘、中介和控制器服务器角色不支持扩展池。


## 中央站点拓扑和组件（本地）

尽管中央站点拓扑必须包含一个前端池或一个 Standard Edition 服务器，但每个中央站点还可以包含以下内容：

  - 多个前端池，可位于同一个域或不同的域。尽管如此，前端池中的所有前端服务器和该池的后端服务器必须位于同一域中。

  - 多个 Standard Edition 服务器。

  - Office Web Apps Server，与 Lync Server 2013 中的 Office Web Applications 结合使用，以处理 Microsoft PowerPoint 演示文稿的共享和呈现。

  - 外围网络中的边缘服务器或边缘池（如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关、远程用户访问、匿名用户参与会议或 Exchange 统一消息 (UM)）。不能将其他任何服务器角色与边缘服务器并置。建议根据需要使用 DNS 负载平衡，但也支持硬件负载平衡。内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。有关负载平衡要求和支持的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和部署文档中的 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

  - 中介服务器或池（如果要在中央站点的前端池中支持企业语音或电话拨入式会议）。可以并置前端池中的中介服务器（默认）或部署独立的中介服务器或池，具体取决于部署企业语音支持的方式。可以使用 DNS、硬件或应用程序负载平衡（适用时）从中介服务器池的对等网关（包括 PSTN 网关、IP-PBX 或 SIP 中继会话边界控制 (SBC)）分散流量。有关规划合适的中介服务器拓扑的详细信息，请参阅规划文档中的 [Lync Server 2013 中介服务器部署准则](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

  - 持久聊天服务器（如果您希望用户能够参与多方、基于主题的持久对话）。为提供更大的容量和更高的可靠性，您的拓扑可以包含多台运行 持久聊天服务器的计算机。不能将 持久聊天服务器与企业池中的其他服务器角色并置。但是，可在 Standard Edition 服务器上并置 持久聊天服务器。持久聊天需要一个数据库，如果实现持久聊天合规性，还需要一个持久聊天合规性数据库，但这些数据库可以与存档数据库或监控数据库并置，或者位于 Enterprise Edition 前端池的后端服务器上。有关规划适当的 持久聊天服务器拓扑的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

  - 监控（如果要在部署中收集有关企业语音和 A/V 会议的音频/视频用户体验质量 (QoE) 和呼叫详细记录 (CDR) 的数据）。或者，也可以安装 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager），它能够使用监控 CDR 和 QoE 数据来生成近乎实时的警报，显示呼叫可靠性和媒体质量的状况。监控功能（如果部署）可位于前端服务器或 Standard Edition 服务器上。监控需要一个数据库，但该数据库可与存档数据库、持久聊天数据库或持久聊天合规性数据库并置，或者位于 Enterprise Edition 前端池的后端服务器上。

  - 存档（如果要在部署中存档 IM 通信和会议内容（出于合规性考虑））。存档（如果部署）可并置在前端服务器或 Standard Edition 服务器上。存档存储要求部署存档数据库或与 Exchange 2013 存储集成。如果同时使用两者（称为 *混合模式* ）， Exchange 2013 存储将用于为驻留在 Exchange 2013 上的用户存储存档数据，存档数据库用于为部署中的所有其他用户存档数据。如果需要存档数据库，则该数据库可以与监控数据库、持久聊天数据库或持久聊天合规性数据库并置，或者位于前端池的后端服务器上。有关规划合适的存档拓扑的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

  - 控制器或控制器池，如果要加快复原并加速将 Lync Server 2013 用户请求重定向到用户的主池（可以是 Enterprise Edition 前端池或 Standard Edition Server）。我们建议您在支持外部用户访问的每个中央站点和部署一个或多个前端池的每个中央站点部署控制器或控制器池。每个控制器池最多可包含十个控制器。控制器无法与其他任何服务器角色并置。有关规划合适的控制器拓扑的详细信息，请参阅规划文档中的 [Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)。

  - 反向代理，它不是 Lync Server 2013 组件，而只是您希望支持联盟用户共享 Web 内容或支持移动性流量时需要使用的服务器。您不能将反向代理服务器与任何 Lync Server 2013 服务器角色并置，但可以通过在组织中配置对用于其他应用程序的现有反向代理服务器的支持来为 Lync Server 2013 部署实现该支持。有关反向代理服务器的详细信息，请参阅部署文档中的 [为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)。

> [!NOTE]  
> 在 Lync Server 2013 中，A/V 会议、监控和存档运行在前端服务器上，不再是单独的服务器角色。


在中央站点部署的所有前端池和 Standard Edition Server 共享为中央站点部署的以下任何内容：

  - 控制器或控制器池

  - 独立的中介服务器或池

  - Office Web Apps Server

  - 边缘服务器或边缘池

  - 持久聊天服务器或池

  - 监控

  - 存档

> [!NOTE]  
> 如果要支持 Exchange 2013 统一消息集成，则可在 Lync Server 2013 部署中实施 Exchange UM Server，但它并不是 Lync Server 2013 站点的组件。


多个中央站点还可以共享在一个中央站点部署的以下任何内容：

  - 独立的中介服务器或池

  - 边缘服务器或边缘池

  - 持久聊天服务器或池

  - 存档

  - 监控

> [!NOTE]  
> 可在 Lync Server 2013 部署中实施 Exchange UM Server，并在多个中央站点上共享，但它并不是 Lync Server 2013 站点的组件。


有关 Lync Server 2013 服务器角色和功能的详细信息，请参阅规划文档中的 [Lync Server 2013 中的服务器角色](lync-server-2013-server-roles.md)。

有关 Lync Server 2013 服务器并置支持的摘要，请参阅 [Lync Server 2013 中支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

除了本节前面介绍的服务器角色和功能之外， Lync Server 2013 还提供其他组件和选项，包括以下内容中的部分或全部：

  - 防火墙

  - PSTN 网关（如果部署企业语音）

  - Exchange UM Server

  - DNS 负载平衡

  - 硬件负载平衡器

  - SQL Server 数据库

  - 文件共享

有关所有 Lync Server 2013 功能、组件和选项的详细信息，请参阅规划文档。

## 分支站点拓扑和组件（本地）

分支站点与中央站点关联，分支站点中的每个 Survivable Branch Appliance 均与关联中央站点中的 Enterprise Edition 前端池或 Standard Edition 服务器相关联。分支站点的大多数功能都取决于中央站点，因此分支站点的组件仅包含以下内容：

  - Survivable Branch Appliance，它将公用电话交换网 (PSTN) 网关与某些 Lync Server 功能组合在一起。中介服务器可与 Survivable Branch Appliance 上的注册器实例并置，并且您可以部署独立的中介服务器或中介服务器池。

  - Survivable Branch Server，它是运行 Windows Server 且已安装 Lync Server 2013 注册器和中介服务器软件的服务器。

  - 独立的 PSTN 网关（不是 Survivable Branch Appliance 的一部分）和独立的中介服务器。

Survivable Branch Server 的要求与任何 Lync Server 2013 服务器角色的要求相同。

