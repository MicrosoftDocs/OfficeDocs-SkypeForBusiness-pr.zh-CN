---
title: Skype for Business 服务器的拓扑基础知识
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：选择 Skype for business 服务器的拓扑。 了解 Skype for business 服务器的服务器 collocation。
ms.openlocfilehash: b3f45a37bde409dcda38f3047e60776ebc8560e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801692"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Skype for Business 服务器的拓扑基础知识

**摘要：** 选择 Skype for business 服务器的拓扑。 了解 Skype for business 服务器的服务器 collocation。

在准备任何其他内容之前，您需要了解您正在为 Skype for business 服务器的部署规划合适的拓扑。 你需要确定的第一件事是，如果你打算使用 Skype for Business Server 的内部部署，或者你想要将其与混合部署中的 Skype for business Server Online 部署结合使用。 无论是哪种情况，您都要进一步阅读，因为我们将在此处详细介绍本地拓扑，但混合详细信息记录在其各自的部分中。

您还可以在[Skype for Business 服务器的参考拓扑](reference-topologies.md)中查看一些示例拓扑。

## <a name="sites"></a>站点

在 Skype for Business 服务器中，你可以在网络上定义包含 Skype for Business 服务器组件的网站。 站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。 请注意，Skype for business 服务器网站是来自 Active Directory 域服务站点和 Microsoft Exchange Server 站点的独立概念。 您的 Skype for Business 服务器网站不需要对应于您的 Active Directory 站点。

Skype for Business 服务器支持可根据高可用性和位置要求进行缩放的一个或多个网站的本地部署。

你的部署将至少有一个中心网站（也称为数据中心），这是所有位于它的服务器的数据中心，并且你的部署中的每个中心网站都将具有一个标准版服务器或至少一个企业版前端池。 您可以在以下每个选项中了解其中的差异：

- 标准版服务器包括 collocated SQL Server Express 数据库。

- 企业版前端池包括：

  - 一个或多个前端服务器（理想情况下，至少三个是可伸缩性），最大值为12。 对于多个服务器，需要提供负载平衡。

  - 单独的后端服务器。

您可以在此部分了解有关各种服务器角色的更多信息。

除了你的中心网站，你还可能最终拥有一个或多个与你的中心网站相关联的分支网站。 他们在中心网站上的几乎所有功能都依赖于中心网站，因此它们的用途完全相同？

- Survivable 分支装置，将公共交换电话网络（PSTN）网关与某些 Skype for business 服务器功能结合使用。

- Survivable 分支服务器，它是运行 Windows Server 且安装了 Skype for Business 服务器注册机构和中介服务器软件的服务器。

- 独立 PSTN 网关（不是 Survivable 分支装置的一部分）。

- 独立中介服务器或独立中介服务器池（如果你不想将此角色与 Survivable 分支装置 collocate。）

## <a name="whats-in-a-skype-for-business-server-site"></a>Skype for business 服务器网站中有哪些内容？

若要了解更多详细信息，中心网站还可以具有：

- 多个前端池，位于同一个域或不同域中（请记住，在计划中，前端池中的所有前端服务器以及池的后端服务器都必须位于同一域中。

- 多个标准版服务器。

- Office Web Apps 服务器，与 Skype for Business 服务器中的 Office Web Apps 一起使用，用于共享和呈现 PowerPoint 演示文稿。

- 边缘服务器或边缘池（在外围网络中）。 如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关以及远程用户访问，则需要此组件。 有关详细信息，请参阅 Edge 服务器规划文档。

- 持久聊天服务器。 如果您希望用户能够参与多方、基于主题的持久对话，则此组件将提供帮助。 有关规划持久聊天服务器主题的详细信息。

- 监控。 用于支持音频/视频（A/V）体验质量（QoE）的数据收集，以及部署中的企业语音和音频/视频会议的详细录制（CDR）。 我们将在“规划监控”主题中详细谈论这一内容。

- 导演或控制器池。 不需要，但如果你想要提高复原能力并启用将 Skype for Business 用户请求重定向到用户的主池，这种方法非常有用。 如果你想要部署控制器，每个池中最多支持10个。 如果这是你需要的内容，请务必继续阅读 "规划董事" 主题。

- 反向代理。 这不是 Skype for Business 服务器组件，但是如果你想要支持联合用户共享 web 内容，如果你想要支持移动通信，如果你的远程用户想要使用通讯簿、加入会议等，则可以希望在你的环境中拥有。 设置反向代理服务器主题时，你可以查看更多详细信息，准备就绪。

有关这些服务器的并置的其他信息，请参见以下内容。

在中心网站上部署的所有前端池和标准版服务器（假定已部署）如下所示：

||||
|:-----|:-----|:-----|
|导演或控制器池  <br/> |独立中介服务器或中介服务器池  <br/> |Office Web Apps Server  <br/> |
|边缘服务器或边缘池  <br/> |持久聊天服务器或持久聊天服务器池  <br/> |监控  <br/> |

此列表中的 Exchange 统一消息（UM）服务器在哪里？ 当然，如果您想要与 Exchange UM 集成，但它不是 Skype for business Server 网站的组件，则可以使用它与 Skype for business 服务器配合使用，这样就不会在此处提及。

你可能计划有多个中心网站，如果是这样，则他们可以共享以下服务器和角色（如果它们已部署在你的中心网站上）：

|||
|:-----|:-----|
|独立中介服务器或中介服务器池  <br/> |边缘服务器或边缘池  <br/> |
|持久聊天服务器或持久聊天服务器池  <br/> |监控  <br/> |

与最后一个列表一样，我们不会在此处包括 Exchange UM 服务器，因为它不是 Skype for Business Server 部署的一部分，但也属于同一类别。

当然，部署中还包含其他一些组件和选项。

|||||
|:-----|:-----|:-----|:-----|
|防火墙  <br/> |PSTN 网关（如果部署企业语音）  <br/> |Exchange UM 服务器（如果想要与 Exchange UM 集成）  <br/> |DNS 负载平衡  <br/> |
|硬件负载平衡器  <br/> |SQL Server 数据库  <br/> |文件共享  <br/> ||

## <a name="server-roles"></a>服务器角色

运行 Skype for Business 服务器的每台服务器都运行一个或多个服务器角色。 服务器角色是指由服务器提供的一组已定义的 Skype for business 服务器功能。 无需在网络中部署所有可用服务器角色。 只安装包含您想要的功能的服务器角色。

对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。 池中的每台服务器必须运行一个或多个相同的服务器角色。 对于 Skype for Business 服务器中的大多数类型的池，必须部署负载平衡器以在池中的各种服务器之间传播流量。 Skype for Business 服务器支持域名系统（DNS）负载平衡和硬件负载平衡器。

### <a name="front-end-server-and-back-end-server"></a>前端服务器和后端服务器

在 Skype for business Server 企业版中，前端服务器是核心服务器角色，并且运行许多基本的 Skype for business 服务器功能。 前端服务器和后端服务器是指在任何 Skype for Business Server 部署中都需要的唯一服务器角色。

前端池是一组前端服务器（配置相同），它们协同工作以为一组常见用户提供服务。 由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。

前端服务器包括以下内容：

- 用户身份验证和注册。

- 状态信息和联系人卡片交换。

- 通讯簿服务和通讯组列表扩展。

- IM 功能，包括多方 IM 会议。

- Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）。

- 应用程序托管，适用于 Skype for Business 服务器（如会议助理和响应组应用程序）和第三方应用程序随附的两个应用程序。

- （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。 此信息提供有关媒体质量（音频和视频）对您的网络进行企业语音通话和 A/V 会议的标准的衡量指标。

- 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。

- （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。有关详细信息，请参阅规划文档中的[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)。

    在 Lync Server 2010 和早期版本中，监视和存档是独立的服务器角色，而不是前端服务器上的 collocated。

- （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。

前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。

此外，部署中的一个前端服务器还运行中央管理服务器，该服务器对运行 Skype for business 服务器的所有服务器管理和部署基本配置数据。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。

后端服务器是运行 Microsoft SQL Server 的数据库服务器，它为前端池提供数据库服务。 后端服务器充当池用户和会议数据的备份存储，并且是其他数据库（如响应组数据库）的主要存储。 你可以拥有一台后端服务器，但建议使用[Skype For Business 服务器的后端服务器高可用性](../high-availability-and-disaster-recovery/back-end-server.md)进行故障转移。 后端服务器不运行任何 Skype for Business 服务器软件。

> [!IMPORTANT]
> 我们不建议将 Skype for business Server 数据库与其他数据库 collocating。 如果您这样做，可能会影响可用性和性能。

> [!NOTE]
> 在 Skype for Business Server 2015 中可以使用 SQL 镜像，但 Skype for Business Server 2019 不再支持该功能。 对于 Skype for Business Server 2019，首选 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法。

存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。

### <a name="edge-server"></a>边缘服务器

边缘服务器使用户能够与组织防火墙外的用户进行通信和协作。 这些外部用户可以包括组织的自己的用户，这些用户当前正在进行异地工作、来自联盟合作伙伴组织的用户以及已被邀请加入 Skype for business Server 部署中的会议的外部用户。

部署边缘服务器还支持移动服务，这些服务支持移动设备上的 Lync 功能。 用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备支持某些企业语音功能，例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。 移动功能还支持针对不支持在后台运行的应用程序的移动设备的推送通知。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。

边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。 你可以将这些 XMPP 组件配置为允许 Skype for Business 服务器用户从基于 XMPP 的合作伙伴添加联系人，以便发送即时消息和状态。

> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用，但 Skype for business Server 2019 不再支持。 有关详细信息，请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。

### <a name="mediation-server"></a>中介服务器

中介服务器是实现企业语音、通过工作电话和拨入式会议进行通话所必需的组件。 中介服务器转换信号，在某些配置中，在内部 Skype for business 服务器基础结构和公共交换电话网络（PSTN）网关、IP PBX 或会话初始协议（SIP）主干之间的媒体。 你可以在前端服务器所在的同一台服务器上运行中介服务器 collocated，或将其分到独立的中介服务器池中。

有关详细信息，请参阅[Skype For Business 服务器中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。

### <a name="video-interop-server"></a>视频互操作服务器

视频互操作服务器是 Skype for business Server 2015 的新角色。 它使您能够将 Skype for Business 服务器部署与特定的第三方 VTC （视频 Teleconferencing 系统）解决方案集成。 VIS 充当第三方电话会议系统和 Skype for business 服务器部署之间的媒介。 对于此版本，VIS 专用于实现与 Cisco/Tandberg 视频系统之间的互操作性。

有关详细信息，请参阅[在 Skype For Business 服务器中规划视频互操作服务器](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>控制器

控制器可以验证 Skype for business 服务器用户请求，但他们不能在家用户帐户或提供状态或会议服务。 控制器对于增强支持外部用户访问的部署中的安全性最有用。 控制器可在将请求发送到内部服务器之前对请求进行身份验证。 对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。

### <a name="persistent-chat-server-roles"></a>持久聊天服务器角色

> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。

运行 Skype for business Server 标准版的服务器也可以在同一台服务器上运行永久聊天 collocated。 不能将持久聊天前端服务器 collocate 到企业版前端服务器。

有关详细信息，请参阅[在 Skype for Business server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性和灾难恢复支持

Skype for business 服务器通过池划分提供了服务器冗余的高可用性。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。

Skype for business 服务器还通过启用池配对来提供灾难恢复措施。 如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。 如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。

Skype for Business 服务器还支持用于后端服务器高可用性的多个选项。 其中包括以下内容：

- 数据库镜像

- AlwaysOn 可用性组

- AlwaysOn 故障转移群集实例（FCI）

- SQL 故障转移群集

有关池配对和后端服务器高可用性的详细信息，请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

## <a name="server-collocation-in-skype-for-business-server"></a>Skype for Business 服务器中的服务器 collocation

我们已使用过术语 collocate，但这意味着什么？ 通过 Skype for Business 服务器，你可以在同一台服务器（collocation）上找到一些服务器角色和功能，但在启动标准版或企业版服务器时可能会令人混淆。部署（它们各自都附带有自己的规则）。 为帮助你进行规划，我们在标准版服务器部署和企业版前端池部署中包括服务器 collocation （在大多数情况下，此信息是相同的，而在哪里不同，则特别明确）。

### <a name="collocation-of-server-roles"></a>服务器角色的并置

标准版服务器具有下列角色 collocated （但需要额外配置），在企业版前端池中，此角色可以是 collocated，或者部署到单独的服务器：

- 中介

以下服务器角色必须分别部署在不同的服务器上：

- 控制器

- Edge

- 视频互操作服务器

- Office Web Apps

### <a name="databases"></a>数据库

这是标准版服务器部署和企业版服务器池部署之间的实际差异的区域，因此我们将有两个部分，后跟这两个部分的其他规则。

#### <a name="standard"></a>Standard

由于 SQL Server Express 在标准版服务器上 collocated，因此不能移动，这相当简单。 此外，如果在标准版服务器上部署持久聊天服务器，你也可以在标准版服务器上 collocate 持久聊天和持久聊天合规性数据库，但不必这样做。

> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。

这些不能在标准版服务器上 collocated，但可以在单个数据库服务器上执行以下操作：

- 监控数据库

- 存档数据库

- 适用于企业版前端池的任何后端数据库

#### <a name="enterprise"></a>Enterprise

以下数据库可以在同一后端 SQL Server 上 collocated：

- 后端数据库

- 监控数据库

- 存档数据库

- 持久聊天数据库

- 持久聊天合规性数据库

#### <a name="both"></a>两者

现在，在单个 SQL 实例中或在同一 SQL Server 数据库中的多个 SQL 实例中 collocating Skype for business 服务器数据库时，还需遵循一些其他规则：

- 每个 SQL 实例只能包含企业版前端池、单个监视数据库、单个存档数据库、单个持久聊天数据库和单个持久聊天合规性数据库的单个后端数据库。

- 数据库服务器无法支持多个企业版前端池、一个运行存档的服务器、一个运行监视的服务器、单个持久聊天数据库和单个持久聊天合规性数据库，但它可以支持其中一个无论数据库使用的是相同的 SQL Server 实例还是 SQL Server 的单独实例。

    > [!NOTE]
    > Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。

### <a name="file-shares"></a>文件共享

文件共享可以是在独立的服务器上，您也可以将其并置到与以下任何或所有组件相同的服务器上：

- 数据库服务器，包括企业版前端池的后端服务器

- 监控数据库

- 存档数据库

- 持久聊天数据库

- 持久聊天合规性数据库

> [!CAUTION]
> 请注意，虽然可以在这些服务器上并置文件共享，但是有必要指出的是，我们不建议这样做。 如果你与任何其他服务器角色 collocating 文件共享，请确保你定期监视磁盘空间和性能问题。

### <a name="keep-in-mind"></a>请注意

- 不能 collocate 不是 Skype for business Server 组件的反向代理服务器，也不能在拓扑中使用。 如果你想要为联盟用户支持 web 内容的共享以及其他许多其他内容，则需要反向代理。 如果需要，可通过配置你的组织中已存在由其他应用程序使用的现有反向代理服务器，继续执行并为 Skype for business 服务器执行反向代理支持。

- 您不能通过任何 Skype for Business 服务器角色 collocate 任何 Exchange UM 组件或 SharePoint Server 组件。

## <a name="see-also"></a>另请参阅

[Skype for Business 服务器的参考拓扑](reference-topologies.md)
