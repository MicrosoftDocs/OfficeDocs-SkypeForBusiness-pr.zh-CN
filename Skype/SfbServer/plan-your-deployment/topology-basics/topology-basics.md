---
title: Skype for Business Server 的拓扑基础知识
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要：选择 Skype for Business Server 的拓扑。 了解 Skype for Business Server 的服务器并置。
ms.openlocfilehash: 9b0dbe6a74a5982c2816c022e5ea7a99ba2abf07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831752"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Skype for Business Server 的拓扑基础知识

**摘要：** 选择 Skype for Business Server 的拓扑。 了解 Skype for Business Server 的服务器并置。

在准备任何其他内容之前，你需要知道你正在为 Skype for Business Server 的部署规划正确的拓扑。 需要确定的第一件事是，是准备部署本地 Skype for Business Server，还是要将其与混合部署中的 Skype for Business Server Online 部署相结合。 无论采用哪种方式，你均希望进一步阅读，因为我们将在此处详细介绍本地拓扑，但混合详细信息记录在各自的部分中。

You can also see some example topologies in [Reference topologies for Skype for Business Server.](reference-topologies.md)

## <a name="sites"></a>网站

在 Skype for Business Server 中，定义网络上包含 Skype for Business Server 组件的站点。 站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。 请注意，Skype for Business Server 站点是一个独立于 Active Directory 域服务站点和Microsoft Exchange Server概念。 Skype for Business Server 站点不需要与 Active Directory 站点对应。

Skype for Business Server 支持根据高可用性和位置要求缩放的一个或多个站点本地部署。

您的部署将具有至少一个中央站点 (也称为数据中心，这是位于) 中所有服务器的数据中心，部署中的每个中央站点将具有一台 Standard Edition Server 或至少一个 Enterprise Edition 前端池。 你可以在下面看到每个选项的差异：

- Standard Edition Server 包含并SQL Server Express 数据库。

- Enterprise Edition 前端池包括：

  - 一个或多个前端服务器 (至少三台，) ，最多为 12 台。 多个服务器需要负载平衡。

  - 单独的后端服务器。

您可以在本节稍后部分了解有关各种服务器角色的更多内容。

除了中央站点之外，您最终可能还具有一个或多个与中央站点关联的分支站点。 它们依赖于中央站点来了解其几乎所有功能，那么它们由什么决定？

- Survivable Branch Appliance，它将公用电话交换网 (PSTN) 网关，以及一些 Skype for Business Server 功能。

- Survivable Branch Server 是运行 Windows Server 的服务器，已安装 Skype for Business Server 注册器和中介服务器软件。

- 独立的 PSTN 网关 (Survivable Branch Appliance) 。

- 如果您不希望此角色与 Survivable Branch Appliance 服务器并 (，则独立中介服务器或独立中介服务器池) 。

## <a name="whats-in-a-skype-for-business-server-site"></a>Skype for Business Server 站点中有什么内容？

若要了解更多详细信息，中心网站还可以具有：

- 同一域或不同域中的多个前端池 (请记住，在规划前端池中的所有前端服务器以及池的后端服务器必须位于同一个域中) 。

- 多个 Standard Edition 服务器。

- Office Web Apps Server，与 Skype for Business Server 中的 Office Web Apps 一起用于共享和呈现 PowerPoint 演示文稿。

- 边缘服务器或边缘 (位于外围网络中) 。 如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关和远程用户访问，则需要此配置。 可以在边缘服务器规划文档中找到更多详细信息。

- 持久聊天服务器。 如果您希望用户能够参与多方、基于主题的持久对话，则非常有用。 有关规划持久聊天服务器的详细信息，请参阅"规划持久聊天服务器"主题。

- 监视。 用于在部署中为 企业语音 和 A/V 会议支持音频/视频 (A/V) 用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 。 我们将在"规划监控"主题中详细讨论它。

- 控制器或控制器池。 不是必需的，但如果你想要提高恢复能力并启用 Skype for Business 用户请求重定向到用户主池，则非常有用。 如果要部署控制器，则每个池最多支持 10 个控制器。 如果需要这样做，一定要继续阅读"规划控制器"主题。

- 反向代理。 这不是 Skype for Business Server 组件，但是如果你想要支持联盟用户共享 Web 内容，如果你打算支持移动流量，如果你的远程用户想要使用通讯簿、加入会议等，则这是你想要在你的环境中拥有的内容。 有一个"设置反向代理服务器"主题，可以在准备就绪后查看更多详细信息。

有关这些服务器的并置的其他信息，请参阅下文。

在中央站点部署的所有前端池和 Standard Edition 服务器共享以下内容（假定已部署它们）：

||||
|:-----|:-----|:-----|
|控制器或控制器池  <br/> |独立中介服务器或中介服务器池  <br/> |Office Web Apps Server  <br/> |
|边缘服务器或边缘池  <br/> |持久聊天服务器或持久聊天服务器池  <br/> |监控  <br/> |

Exchange 统一消息 (UM) 服务器在此列表中在哪里？ 如果你希望与 Exchange UM 集成，则当然可以将其与 Skype for Business Server 一起使用，但它不是 Skype for Business Server 网站的一个组件，因此我们在此处不提及它。

您可能计划具有多个中央站点，如果是这样，它们可以共享以下服务器和角色（如果它们部署在中央站点上）：

|||
|:-----|:-----|
|独立中介服务器或中介服务器池  <br/> |边缘服务器或边缘池  <br/> |
|持久聊天服务器或持久聊天服务器池  <br/> |监控  <br/> |

和最后一个列表一样，我们这里没有包括 Exchange UM Server，因为它不是 Skype for Business Server 部署的一部分，但它在此处也属于同一类别。

当然，还有一些进入部署的其他组件和选项。

|||||
|:-----|:-----|:-----|:-----|
|防火墙  <br/> |PSTN 网关 (部署 PSTN 网关企业语音  <br/> |如果要与 exchange UM (集成，Exchange UM Server)   <br/> |DNS 负载平衡  <br/> |
|硬件负载平衡器  <br/> |SQL Server 数据库  <br/> |文件共享  <br/> ||

## <a name="server-roles"></a>服务器角色

每台运行 Skype for Business Server 的服务器都运行一个或多个服务器角色。 服务器角色是由该服务器提供的一组定义的 Skype for Business Server 功能。 无需在网络中部署所有可用的服务器角色。 只安装包含您想要的功能的服务器角色。

对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。 池中的每台服务器必须运行一个或多个相同的服务器角色。 对于 Skype for Business Server 中的大多数类型的池，必须部署负载平衡器以在池中的各个服务器之间分布流量。 Skype for Business Server 支持域名系统 (DNS) 负载平衡和硬件负载平衡器。

### <a name="front-end-server-and-back-end-server"></a>前端服务器和后端服务器

在 Skype for Business Server Enterprise Edition 中，前端服务器是核心服务器角色，并运行许多基本的 Skype for Business Server 功能。 前端服务器和后端服务器是任何 Skype for Business Server Enterprise Edition 部署中唯一需要的服务器角色。

“前端池”是一组配置相同的前端服务器，其协同工作为公用组用户提供服务。 由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。

前端服务器包括以下功能：

- 用户身份验证和注册。

- 状态信息和联系人卡片交换。

- 通讯簿服务和通讯组列表扩展。

- IM 功能，包括多方 IM 会议。

- Web 会议、PSTN 电话拨入式会议和 A/V 会议 (部署) 。

- 应用程序托管，对于 Skype for Business Server (应用程序（例如，会议助理和响应组应用程序) 应用程序）和第三方应用程序。

- （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。 此信息提供有关音频和视频会议 (音频和视频) 通话和 A/V 会议企业语音媒体质量的指标。

- 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。

- （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。 有关详细信息，请参阅规划文档中的[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)。

    在 Lync Server 2010 和早期版本中，监控和存档是单独的服务器角色，未并排在前端服务器上。

- （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。

前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。

此外，部署中的一台前端服务器还运行中央管理服务器，中央管理服务器管理基本配置数据，并部署到所有运行 Skype for Business Server 的服务器。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。

后端服务器是运行为Microsoft SQL Server池提供数据库服务的数据库服务器。 后端服务器用作池的用户和会议数据的备份存储，是其他数据库（如响应组数据库）的主存储。 可以有一台后端服务器，但建议在 [Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) 中使用后端服务器高可用性进行故障转移。 后端服务器不运行任何 Skype for Business Server 软件。

> [!IMPORTANT]
> 建议不要将 Skype for Business Server 数据库与其他数据库并并。 如果您这样做，可能会影响可用性和性能。

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 的首选。

存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。

### <a name="edge-server"></a>边缘服务器

边缘服务器使用户可以与组织防火墙之外的用户进行通信和协作。 这些外部用户可以包括当前在外部工作的组织自己的用户、联盟伙伴组织的用户以及受邀加入 Skype for Business Server 部署上托管的会议的外部用户。

部署边缘服务器还将启用移动服务，此服务支持移动设备上的 Lync 功能。 用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。 移动功能还支持针对不支持在后台运行的应用程序的移动设备的推送通知。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。

边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。 你可以配置这些 XMPP 组件，以使 Skype for Business Server 用户能够添加来自基于 XMPP 的合作伙伴的联系人，用于即时消息和状态。

> [!NOTE]
> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息 [，请参阅"迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟"。

### <a name="mediation-server"></a>中介服务器

中介服务器是实施电话企业语音电话拨入式会议的必要组件。 中介服务器转换内部 Skype for Business Server 基础结构与公用电话交换网 (PSTN) 网关、IP-PBX 或会话初始协议 (SIP) 中继之间的信号（在某些配置中）媒体。 您可以运行在前端服务器所在的服务器上并置的中介服务器，也可以运行分隔到单独的中介服务器池中的中介服务器。

有关详细信息，请参阅 [Skype for Business Server 中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。

### <a name="video-interop-server"></a>视频互操作服务器

视频互操作服务器是自 Skype for Business Server 2015 起的新角色。 它使你能够将 Skype for Business Server 部署与某些第三方 VTC (视频电话会议系统) 解决方案。 VIS 充当第三方电话会议系统和 Skype for Business Server 部署之间的中介。 对于此版本，VIS 侧重于与 Cisco/Tandberg 视频系统的互操作性。

有关详细信息，请参阅规划 Skype [for Business Server 中的视频互操作服务器](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>主管

控制器可以验证 Skype for Business Server 用户请求，但它们不驻留用户帐户或提供状态或会议服务。 控制器对于增强支持外部用户访问的部署中的安全性最有用。 控制器可在将请求发送到内部服务器之前对请求进行身份验证。 对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。

### <a name="persistent-chat-server-roles"></a>持久聊天服务器角色

> [!NOTE]
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。

运行 Skype for Business Server Standard Edition 的服务器还可以运行并位于同一台服务器上的持久聊天。 不能将持久聊天前端服务器与 Enterprise Edition 前端服务器并排。

有关详细信息，请参阅 [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性和灾难恢复支持

Skype for Business Server 通过池服务器冗余提供高可用性。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Skype for Business Server 还通过启用池配对提供灾难恢复措施。 如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。 如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。

Skype for Business Server 还支持用于后端服务器高可用性的几个选项。 其中包括以下项：

- 数据库镜像

- AlwaysOn 可用性组

- FCI (AlwaysOn 故障转移群集) 

- SQL故障转移群集

有关池配对和后端服务器高可用性的详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

## <a name="server-collocation-in-skype-for-business-server"></a>Skype for Business Server 中的服务器并置

我们已使用并集术语，但这意味着什么？ Skype for Business Server 允许你在同一台服务器（即并置服务器）或不同服务器上查找某些服务器角色和功能，但当您开始部署时，以及执行 Standard Edition 还是 Enterprise Edition 服务器部署时，可能会令人困惑 (它们各自都提供自己的规则) 。 为了帮助进行规划，我们将服务器并置包括在 Standard Edition Server 部署和 Enterprise Edition 前端池部署 (在大多数情况下，此信息是相同的，如果该信息不同，则专门) 。

### <a name="collocation-of-server-roles"></a>服务器角色并置

通过) ，Standard Edition Server 具有以下并排角色 (需要其他配置，而在 Enterprise Edition 前端池中，可以并并此角色，也可以将其部署到单独的服务器：

- 中介

这些服务器角色必须分别部署在单独的服务器上：

- 主管

- Microsoft Edge

- 视频互操作服务器

- Office Online

### <a name="databases"></a>Databases

这是 Standard Edition Server 部署和 Enterprise Edition 服务器池部署之间实际差异的区域，因此我们将在下面介绍两个部分，后跟针对这两个部分的一些附加规则。

#### <a name="standard"></a>标准

由于 SQL Server Express 并位于 Standard Edition Server 上，并且无法移动，因此这非常简单。 此外，如果在 Standard Edition 服务器上部署持久聊天服务器，还可以将持久聊天和持久聊天合规性数据库并放在 Standard Edition 服务器上，但不必这样。

> [!NOTE]
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。

它们不能并放在 Standard Edition Server 上，但可以单独数据库服务器一个服务器：

- 监控数据库

- 存档数据库

- Enterprise Edition 前端池的任何后端数据库

#### <a name="enterprise"></a>企业版

以下数据库可以并放在同一后端SQL Server：

- 后端数据库

- 监控数据库

- 存档数据库

- 持久聊天数据库

- 持久聊天合规性数据库

#### <a name="both"></a>两者都有

现在，在单个 SQL 实例中或同一数据库的多个 SQL 实例中并并 Skype for Business Server 数据库时，还需要遵循一SQL Server规则：

- 每个SQL实例只能包含 Enterprise Edition 前端池的一个后端数据库、一个监控数据库、一个存档数据库、一个持久聊天数据库和一个持久聊天合规性数据库。

- 数据库服务器不能支持多个 Enterprise Edition 前端池、一台存档服务器、一台运行监控的服务器、一个持久聊天数据库和一个持久聊天合规性数据库，但它可以支持其中一个，无论数据库是使用相同的 SQL Server 实例还是单独的 SQL Server 实例。

    > [!NOTE]
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。

### <a name="file-shares"></a>文件共享

文件共享可以位于单独的服务器上，也可以与以下任一或所有文件共享并放在同一服务器上：

- 数据库服务器，包括 Enterprise Edition 前端池的后端服务器

- 监控数据库

- 存档数据库

- 持久聊天数据库

- 持久聊天合规性数据库

> [!CAUTION]
> 请注意，虽然您可以将文件共享并放在这些服务器上，但值得注意的是，我们不建议这样做。 如果要将文件共享与任何其他服务器角色并并，请确保定期监视磁盘空间和性能问题。

### <a name="keep-in-mind"></a>记住

- 无法并反向代理服务器，它不是 Skype for Business Server 组件，甚至可能不在拓扑中。 如果要支持为联盟用户共享 Web 内容，还需要反向代理。 如果需要，请继续操作，通过配置组织中已有的正由其他应用程序使用的现有反向代理服务器，为 Skype for Business Server 实现反向代理支持。

- 不能将任何 Exchange UM 组件或 SharePoint Server 组件与任何 Skype for Business Server 角色并联。

## <a name="see-also"></a>另请参阅

[Skype for Business Server 的参考拓扑](reference-topologies.md)
