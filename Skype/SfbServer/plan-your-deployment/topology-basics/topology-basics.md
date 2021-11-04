---
title: 拓扑结构Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要：选择用于部署Skype for Business Server。 了解服务器并置Skype for Business Server。
ms.openlocfilehash: 3b6e1ce1038b9b5dbc39955f774660cfbdce1291
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770050"
---
# <a name="topology-basics-for-skype-for-business-server"></a>拓扑结构Skype for Business Server

**摘要：** 选择拓扑结构Skype for Business Server。 了解服务器并置Skype for Business Server。

在准备任何其他内容之前，你需要知道你正在规划正确的拓扑，以用于部署Skype for Business Server。 首先需要确定的是，是要部署 Skype for Business Server 本地部署，还是要将其与混合部署中的 Skype for Business Server Online 部署相结合。 无论采用哪种方式，您都想进一步阅读，因为我们将在此处详细介绍本地拓扑，但混合详细信息记录在其自己的部分中。

You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).

## <a name="sites"></a>网站

在Skype for Business Server中，定义网络上包含这些组件Skype for Business Server站点。 站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。 请注意，Skype for Business Server是一个独立于 Active Directory 域服务站点和网站Microsoft Exchange Server概念。 您的Skype for Business Server站点无需与 Active Directory 站点对应。

Skype for Business Server支持一个或多个网站本地部署，这些站点可根据高可用性和位置要求进行扩展。

您的部署将具有至少一个中央站点 (也称为数据中心，这是位于) 中所有服务器的数据中心，部署中的每个中央站点将具有一台 Standard Edition 服务器或至少一个 Enterprise Edition 前端池。 您可以在以下每个选项中查看差异：

- Standard Edition服务器包括并SQL Server Express数据库。

- Enterprise Edition前端池包括：

  - 一个或多个前端服务器 (至少三台，用于可伸缩性) 最多 12 台。 多个服务器需要负载平衡。

  - 单独的后端服务器。

您可以在本节稍后部分了解有关各种服务器角色的更多内容。

除了中央站点之外，您最终可能还具有一个或多个与中央站点关联的分支站点。 它们依靠中央网站来几乎实现其所有功能，那么它们由什么具体决定？

- Survivable Branch Appliance，它将公用电话交换网与 PSTN (网关) ，具有一些Skype for Business Server功能。

- Survivable Branch Server 是运行 Windows Server 的服务器，Skype for Business Server注册器和中介服务器软件。

- 不是 Survivable Branch Appliance (一部分的独立的 PSTN 网关) 。

- 如果您不想将此角色与 Survivable Branch Appliance 服务器并 (，则独立中介服务器或独立的中介服务器池) 。

## <a name="whats-in-a-skype-for-business-server-site"></a>网站中有什么Skype for Business Server？

要获取更多详细信息，中央站点还可以具有：

- 同一个域或不同域中的多个前端池 (请记住，在规划时，前端池中的所有前端服务器以及池的后端服务器必须位于同一个域) 。

- 多个 Standard Edition 服务器。

- OfficeWeb Apps Server，与 Office Web Apps Skype for Business Server共享和呈现PowerPoint演示文稿。

- 外围网络中 (边缘服务器或边缘) 。 如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关和远程用户访问，则需要此配置。 可以在边缘服务器规划文档中找到更多详细信息。

- 持久聊天服务器。 如果你希望用户能够参与基于主题的多方对话，这种对话会持续一段时间，则非常有用。 有关详细信息，请参阅规划持久聊天服务器主题。

- 监视。 用于支持对部署中的 企业语音 和 A/V 会议的音频/视频 (A/V) 用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 进行数据收集。 我们将在规划监控主题中详细讨论此内容。

- 控制器或控制器池。 不是必需的，但如果您希望提高复原能力并启用用户请求Skype for Business用户请求重定向到用户主池，则非常有用。 如果要部署控制器，则每个池最多支持 10 个控制器。 如果需要这样做，一定要继续阅读规划控制器主题。

- 反向代理。 这不是一个 Skype for Business Server 组件，但是如果您想要支持联盟用户共享 Web 内容，如果您打算支持移动通信，如果您的远程用户想要使用通讯簿、加入会议等，则这是您希望在环境中拥有的内容。 有一个设置反向代理服务器主题，可以在准备就绪时查看更多详细信息。

有关这些服务器并置的其他信息，请参阅下文。

在中央站点部署的所有Standard Edition池和前端服务器共享以下内容（假定已部署它们）：

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|控制器或控制器池   |独立的中介服务器或中介服务器池   |Office Web Apps Server   |
|边缘服务器或边缘池   |持久聊天服务器或持久聊天服务器池   |监控   |

在此列表中Exchange统一消息 (UM) 服务器在哪里？ 如果你想与 Exchange UM 集成，当然可以将其与 Exchange 一起使用，但它不是 Skype for Business Server 网站的一个组件，因此此处我们未提及它。 Skype for Business Server

您可能计划具有多个中央站点，如果是这样，它们可以共享以下服务器和角色（如果它们部署在中央站点上）：

|&nbsp;|&nbsp;|
|:-----|:-----|
|独立的中介服务器或中介服务器池   |边缘服务器或边缘池   |
|持久聊天服务器或持久聊天服务器池   |监控   |

就像最后一个列表一样，我们这里没有包括 Exchange UM 服务器，因为它不是 Skype for Business Server 部署的一部分，但是它在此处也属于同一类别。

当然，还有一些其他组件和选项会进入部署。

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|
|防火墙   |PSTN 网关 (部署时企业语音   |Exchange如果要 (UM 服务器集成，EXCHANGE UM)    |DNS 负载平衡   |
|硬件负载平衡器   |SQL Server 数据库   |文件共享   ||

## <a name="server-roles"></a>服务器角色

每台运行 Skype for Business Server运行一个或多个服务器角色。 服务器角色是由该服务器Skype for Business Server定义的一组角色功能。 无需在网络中部署所有可用的服务器角色。 只安装包含您想要的功能的服务器角色。

对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。 池中的每台服务器必须运行一个或多个相同的服务器角色。 对于池中的大多数Skype for Business Server，您必须部署负载平衡器以在池中的各个服务器之间分布流量。 Skype for Business Server域名系统 (DNS) 负载平衡和硬件负载平衡器。

### <a name="front-end-server-and-back-end-server"></a>前端服务器和后端服务器

在Skype for Business Server Enterprise Edition，前端服务器是核心服务器角色，并运行许多基本Skype for Business Server功能。 前端服务器和后端服务器是任何部署中唯一需要的Skype for Business Server Enterprise Edition角色。

“前端池”是一组配置相同的前端服务器，其协同工作为公用组用户提供服务。由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。

前端服务器包括以下功能：

- 用户身份验证和注册。

- 状态信息和联系人卡片交换。

- 通讯簿服务和通讯组列表扩展。

- IM 功能，包括多方 IM 会议。

- Web 会议、PSTN 电话拨入式会议和 A/V 会议 (部署在) 。

- 应用程序承载，对于应用程序中包含的两Skype for Business Server (，例如会议助理响应组应用程序) 应用程序，以及第三方应用程序。

- （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。 此信息提供有关音频和视频会议在 (通话和 A/V) 遍历网络的企业语音质量的指标。

- 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。

- （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。有关详细信息，请参阅规划文档中的[Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving)。

    在 Lync Server 2010 和早期版本中，监控和存档是单独的服务器角色，不会并排在前端服务器上。

- （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。

前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。

此外，部署中的一台前端服务器还运行中央管理服务器，中央管理服务器管理基本配置数据，并部署到所有运行 Skype for Business Server。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。

后端服务器是运行数据库Microsoft SQL Server，可为前端池提供数据库服务。 后端服务器用作池的用户和会议数据的备份存储，是其他数据库（如响应组数据库）的主存储。 可以有一台后端服务器，但建议Skype for Business Server[](../high-availability-and-disaster-recovery/back-end-server.md)后端服务器高可用性。 后端服务器不会运行任何Skype for Business Server软件。

> [!IMPORTANT]
> 建议不要将数据库与其他Skype for Business Server并并。 如果您这样做，可能会影响可用性和性能。

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。

存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。

### <a name="edge-server"></a>边缘服务器

边缘服务器使用户可以与组织防火墙之外的用户进行通信和协作。 这些外部用户可以包括当前在外部工作的组织内部用户、来自联盟伙伴组织的用户以及受邀加入 Skype for Business Server 部署上承载的会议的外部用户。

部署边缘服务器还将启用移动服务，此服务支持移动设备上的 Lync 功能。 用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。 移动功能还支持针对不支持在后台运行的应用程序的移动设备的推送通知。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。

边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。 您可以配置这些 XMPP 组件，以使 Skype for Business Server用户能够添加来自基于 XMPP 的合作伙伴的联系人，以实现即时消息和状态。

> [!NOTE]
> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。

### <a name="mediation-server"></a>中介服务器

中介服务器是实施电话企业语音电话拨入式会议的必要组件。 中介服务器转换内部 Skype for Business Server 基础结构与公用电话交换网 (PSTN) 网关、IP-PBX 或会话初始协议 (SIP) 中继之间的信号（在某些配置中）媒体。 您可以运行在前端服务器所在的服务器上并置的中介服务器，也可以运行分隔到单独的中介服务器池中的中介服务器。

有关详细信息，请参阅中介[服务器组件Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)

### <a name="video-interop-server"></a>视频互操作服务器

视频互操作服务器是自 2015 年 2015 Skype for Business Server一个新角色。 它使你能够将你的 Skype for Business Server 部署与某些第三方 VTC (视频电话会议系统) 解决方案。 VIS 充当第三方电话会议系统和会议部署之间的Skype for Business Server中介。 对于此版本，VIS 侧重于与 Cisco/Tandberg 视频系统的互操作性。

有关详细信息，请参阅 Plan [for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>主管

控制器可以Skype for Business Server用户请求进行身份验证，但它们不驻留用户帐户或提供状态或会议服务。 控制器对于增强支持外部用户访问的部署中的安全性最有用。 控制器可在将请求发送到内部服务器之前对请求进行身份验证。 对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。

### <a name="persistent-chat-server-roles"></a>持久聊天服务器角色

> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。

运行 Skype for Business Server Standard Edition 还可以运行在同一台服务器上并插的持久聊天。 不能将持久聊天前端服务器与 Enterprise Edition前端服务器并排。

有关详细信息，请参阅[Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性和灾难恢复支持

Skype for Business Server通过池实现服务器冗余，实现高可用性。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Skype for Business Server启用池配对，从而提供灾难恢复措施。 如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。 如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。

Skype for Business Server还支持用于后端服务器高可用性的几个选项。 其中包括以下项：

- 数据库镜像

- AlwaysOn 可用性组

- AlwaysOn 故障转移群集实例 (FCI) 

- SQL故障转移群集

有关池配对和后端服务器高可用性的详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

## <a name="server-collocation-in-skype-for-business-server"></a>服务器中的服务器并Skype for Business Server

我们已使用并集术语，但这意味着什么？ Skype for Business Server 使您可以在同一台服务器（并置）上或在不同的服务器上查找某些服务器角色和功能，但当您开始部署时，以及执行 Standard Edition 还是 Enterprise Edition 服务器部署时，这一点可能会令人困惑 (它们各自都有各自的规则) 。 为了帮助您进行规划，我们将服务器并置包括在 Standard Edition 服务器部署和 Enterprise Edition 前端池部署 (在大多数情况下，此信息是相同的，并且信息不同，我们专门将此信息称为) 。

### <a name="collocation-of-server-roles"></a>服务器角色并置

Standard Edition 服务器具有以下角色并 (通过) 需要其他配置，而在 Enterprise Edition 前端池中，可以并并此角色，或将其部署到单独的服务器：

- 中介

这些服务器角色必须分别部署在单独的服务器上：

- 主管

- Microsoft Edge

- 视频互操作服务器

- Office Online

### <a name="databases"></a>Databases

这是一个在部署服务器Standard Edition部署和Enterprise Edition池部署之间存在实际差异的区域，因此我们将在下面介绍两个部分，后跟针对这两者的其他一些规则。

#### <a name="standard"></a>标准

由于SQL Server Express服务器上并Standard Edition，并且无法移动，因此这非常简单。 此外，如果在 Standard Edition 服务器上部署持久聊天服务器，还可以在 Standard Edition 服务器上并并持久聊天和持久聊天合规性数据库，但不必这样。

> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。

这些服务器不能并Standard Edition服务器，但可以单独单独数据库服务器服务器：

- 监控数据库

- 存档数据库

- 前端池的任何Enterprise Edition数据库

#### <a name="enterprise"></a>企业版

以下数据库可以并位于同一后端SQL Server：

- 后端数据库

- 监控数据库

- 存档数据库

- 持久聊天数据库

- 持久聊天合规性数据库

#### <a name="both"></a>两者都有

现在，在单个 SQL 实例或同一数据库的多个 SQL 实例中并Skype for Business Server数据库时，需要遵循一些SQL Server规则：

- 每个 SQL 实例只能包含一个 Enterprise Edition 前端池的后端数据库、一个监控数据库、一个存档数据库、一个持久聊天数据库和一个持久聊天合规性数据库。

- 数据库服务器 不能支持多个 Enterprise Edition 前端池、一台存档服务器、一台监控服务器、一个持久聊天数据库和一个持久聊天合规性数据库，但它可以支持每个前端池，无论数据库是使用相同的 SQL Server 实例还是使用单独的 SQL Server 实例。

    > [!NOTE]
    > 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。

### <a name="file-shares"></a>文件共享

文件共享可以位于单独的服务器上，也可以与以下任一或所有文件共享在同一服务器上：

- 数据库服务器，包括 Enterprise Edition 前端池的后端服务器

- 监控数据库

- 存档数据库

- 持久聊天数据库

- 持久聊天合规性数据库

> [!CAUTION]
> 请注意，虽然可以在这些服务器上并集文件共享，但必须注意，我们不建议这样做。 如果要将文件共享与任何其他服务器角色并并，请确保定期监视磁盘空间和性能问题。

### <a name="keep-in-mind"></a>记住

- 不能并并反向代理服务器，该服务器不是Skype for Business Server组件，甚至可能不在拓扑中。 如果要支持联盟用户共享 Web 内容等，则需要反向代理。 如果需要，请继续操作，通过配置组织中已有的正由其他应用程序使用的现有反向代理服务器，为 Skype for Business Server 实现反向代理支持。

- 不能将任何 UM 组件Exchange或SharePoint服务器组件与任何Skype for Business Server并。

## <a name="see-also"></a>另请参阅

[参考拓扑Skype for Business Server](reference-topologies.md)