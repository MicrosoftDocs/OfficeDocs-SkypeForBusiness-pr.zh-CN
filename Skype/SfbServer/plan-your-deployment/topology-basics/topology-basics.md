---
title: 拓扑的 Skype 业务服务器的基础知识
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要： 业务服务器 Skype 选择您的拓扑。 了解有关的 Skype 业务服务器的服务器并置。
ms.openlocfilehash: 303954cc030d2caf61528e1c5b1076b6c1ef5d0d
ms.sourcegitcommit: dba47a65b0725806c98702bb7362a1b105cc93df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2018
ms.locfileid: "21249356"
---
# <a name="topology-basics-for-skype-for-business-server"></a>拓扑的 Skype 业务服务器的基础知识
 
**摘要：** 选择您的拓扑的 Skype 业务服务器上。 了解有关的 Skype 业务服务器的服务器并置。
  
之前准备任何其他操作，您需要知道您的业务服务器 Skype 的部署计划右拓扑。 如果您将对业务服务器拥有 Skype 的内部部署或您打算将这与在混合部署中的业务 Server 联机部署的 Skype 相结合的首先需要决定。 两种方法，您将需要进一步，阅读，我们将详细介绍在本地拓扑在这里，但混合详细信息记录在各自的部分。
  
您还可以参见[业务服务器 Skype 的参考拓扑](reference-topologies.md)中的一些示例拓扑。
  
## <a name="sites"></a>站点

Skype 业务服务器，在网站定义包含 Skype 业务服务器组件在网络上。 站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。 请注意，业务 Server 网站的 Skype 从 Active Directory 域服务站点和 Microsoft Exchange Server 网站的一个单独的概念。 您的业务 Server 网站的 Skype 不需要对应于您的 Active Directory 站点。
  
Skype 业务服务器支持的本地部署可根据您的高可用性和位置要求进行扩展的一个或多个网站。
  
您部署都将具有至少一个中央站点 （也称为数据中心，这是一个数据中心的位于它的所有服务器），并部署中的每个中央站点具有一台 Standard Edition 服务器或至少一个 Enterprise Edition 前端池。 您可以在以下每个选项中了解其中的差异：
  
- Standard Edition server 包括一个并置的 SQL Server Express 数据库。
    
- Enterprise Edition 前端池包括：
    
  - 一个或多个前端服务器 （理想情况下至少三个，为实现可伸缩性），最多为 12 个。 对于多个服务器，需要提供负载平衡。
    
  - 单独后端服务器。
    
您可以在此部分了解有关各种服务器角色的更多信息。
  
除了中央站点，可能还都有一个或多个与中央站点关联的分支站点。 他们取决于其几乎所有的功能的中央站点，以便他们组成，完全是什么？
  
- Survivable Branch Appliance，与业务服务器功能的一些 Skype 结合使用公用电话交换网 (pstn) 网关。
    
- Survivable Branch Server，它是运行 Windows Server 具有 Skype 业务服务器注册器和安装中介服务器软件的服务器。
    
- 独立 PSTN 网关 （其不是 Survivable Branch Appliance 的一部分）。
    
- 独立的中介服务器或独立中介服务器池 （如果您不想要将此角色并置与 Survivable Branch Appliance）。
    
## <a name="whats-in-a-skype-for-business-server-site"></a>Skype 业务 Server 网站中是什么？

要获取到更多详细信息，请中央站点还可以：
  
- 多个前端池，在同一个或多个不同域 （记住规划所有前端服务器在前端池中后, 端服务器池，以及处于同一个域）。
    
- 多个 Standard Edition 服务器。
    
- Office Web Apps Server，用于与 Office Web Apps 中 Skype 业务服务器共享和呈现的 PowerPoint 演示文稿。
    
- 边缘服务器或边缘池 （在外围网络中）。 如果希望部署支持联盟伙伴、公共 IM 连接、可扩展消息传递和状态协议 (XMPP) 网关以及远程用户访问，则需要此组件。 边缘服务器规划文档中，可以找到更多详细信息。
    
- 持久聊天服务器。 如果您希望用户能够参与多方、基于主题的持久对话，则此组件将提供帮助。 没有位于 Planning for Persistent Chat Server 主题的详细信息。
    
- 监控。 用于支持数据收集的音频/视频 (A / V) 的用户体验质量 (QoE) 和呼叫详细记录 (CDR) 信息的企业语音和 A / V 会议部署中的。 我们将在“规划监控”主题中详细谈论这一内容。
    
- 控制器或控制器池。 不需要，但有用如果您想要提高恢复能力和启用业务用户对用户的主池的请求的 Skype 重定向。 如果您想要部署控制器，则支持最大值 10 每个池。 如果这是一个需要肯定控制器主题规划在继续阅读。
    
- 反向代理。 这不是 Skype 对于业务服务器组件，但如果您想要支持共享的联盟用户的 web 内容，如果您打算支持移动的通信，如果您的远程用户想要使用通讯簿、 加入会议，等等，这是将的内容希望您的环境中。 没有设置可以签出的详细信息，当您准备好的反向代理服务器主题。
    
有关这些服务器的并置的其他信息，请参见以下内容。
  
所有前端池和 Standard Edition 服务器部署在中央站点上都共享以下内容，假定您已经部署了它们：
  
||||
|:-----|:-----|:-----|
|控制器或控制器池  <br/> |独立的中介服务器或中介服务器池  <br/> |Office Web Apps Server  <br/> |
|边缘服务器或边缘池  <br/> |持久聊天服务器或持久聊天服务器池  <br/> |监控  <br/> |
   
此列表中的 Exchange 统一消息 (UM) 服务器在哪里 喔，您可以一定使用它 Skype 业务服务器如果您希望与 Exchange UM 集成，但它不是业务 Server 网站，Skype 的组件，因此我们不此处提及它。
  
可能规划您具有多个中央站点，并且如果是这样，他们可以共享的以下服务器和角色，如果在管理中心网站上部署：
  
|||
|:-----|:-----|
|独立的中介服务器或中介服务器池  <br/> |边缘服务器或边缘池  <br/> |
|持久聊天服务器或持久聊天服务器池  <br/> |监控  <br/> |
   
就像最后一个列表中，我们不包括在 Exchange UM 服务器此处，因为它不是对于业务服务器部署，Skype 的一部分，但它太属于同一类别此处。
  
当然，部署中还包含其他一些组件和选项。
  
|||||
|:-----|:-----|:-----|:-----|
|防火墙  <br/> |PSTN 网关（如果部署企业语音）  <br/> |Exchange UM 服务器 （如果您想要与 Exchange UM 集成）  <br/> |DNS 负载平衡  <br/> |
|硬件负载平衡器  <br/> |SQL Server 数据库  <br/> |文件共享  <br/> ||
   
## <a name="server-roles"></a>服务器角色

运行 Business Server Skype 每台服务器运行一个或多个服务器角色。 服务器角色是一组业务服务器功能的服务器所提供的定义的 Skype。 无需在网络中部署所有可用服务器角色。 只安装包含您想要的功能的服务器角色。
  
对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。 池中的每台服务器必须运行一个或多个相同的服务器角色。 对于大多数类型的 Skype 业务服务器中的池，则必须部署负载平衡器分布在池中的各个服务器之间的通信。 Skype 业务服务器支持域名系统 (DNS) 负载平衡和硬件负载平衡器。
  
### <a name="front-end-server-and-back-end-server"></a>前端服务器和后端服务器

对于业务 Server Enterprise Edition 的 Skype，在前端服务器是核心服务器角色，并运行许多基本 Skype 的业务服务器功能。 前端服务器、 后端服务器，以及是仅需要出现在任何 Skype 业务 Server Enterprise Edition 部署的服务器角色。 
  
前端池是一套前端服务器，配置相同，协同工作为公用组用户提供服务。 由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。
  
前端服务器包括以下组件：
  
- 用户身份验证和注册。
    
- 状态信息和联系人卡片交换。
    
- 通讯簿服务和通讯组列表扩展。
    
- IM 功能，包括多方 IM 会议。
    
- Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）。
    
- 将承载应用程序的业务服务器 （例如会议助理和响应组应用程序），包括与 Skype 的应用程序和第三方应用程序。
    
- （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。 此信息提供有关 （音频和视频） 的媒体质量指标遍历网络企业语音呼叫和 A / V 会议。
    
- 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。
    
- （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。 有关详细信息，请参阅规划文档中的[Planning for Archiving](http://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) 。
    
    在 Lync Server 2010 和早期版本中，监控和存档是两个单独的服务器角色，未并置在前端服务器上。
    
- （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。
    
前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。
  
此外，一台前端服务器部署中也运行中央管理服务器，其管理和运行 Business Server Skype 的所有服务器部署基本配置数据。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。
  
后端服务器是运行 Microsoft SQL Server 提供的前端池的数据库服务的数据库服务器。 后端服务器充当备份存储的池的用户和会议数据，并且其他数据库，如数据库响应组的主存储。 您可以将单个后端服务器，但[Skype 业务服务器后端服务器高可用性](../high-availability-and-disaster-recovery/back-end-server.md)建议的故障转移。 后端服务器不会运行任何 Skype 业务服务器软件。
  
> [!IMPORTANT]
> 建议不要对业务服务器数据库与其他数据库并置 Skype。 如果您这样做，可能会影响可用性和性能。 

> [!NOTE]
> SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。
  
存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。
  
### <a name="edge-server"></a>边缘服务器

边缘服务器，您的用户进行通信和协作与组织的防火墙之外的用户。 这些外部用户可以包括目前使用非现场、 来自联盟的伙伴组织的用户和外部用户的已被邀请加入您 Skype 业务服务器部署上承载的会议的组织的用户。
  
部署边缘服务器还允许 mobility service 的移动设备上支持 Lync 功能。 用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备支持某些企业语音功能，例如单击加入会议，通过工作，一号通，语音邮件的呼叫和错过的呼叫。 移动功能还支持针对不支持在后台运行的应用程序的移动设备的推送通知。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。
  
边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。 您可以配置这些 XMPP 组件，才能启用业务 Server 用户您 Skype 即时消息和状态为从基于 XMPP 的合作伙伴添加联系人。

> [!NOTE]
> XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
  
### <a name="mediation-server"></a>中介服务器

中介服务器是用于实现企业语音、 呼叫通过单位电话和电话拨入式会议的必需组件。 中介服务器转换信号，以及在某些配置，您内部 Skype Business Server 基础结构之间的媒体和公共交换电话交换网 (PSTN) 网关、 IP-PBX 或会话初始协议 (SIP) 中继。 您可以运行中介服务器并置在前端服务器所在的服务器上或分为独立的中介服务器池。
  
有关详细信息，请参阅[Skype 业务服务器中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。
  
### <a name="video-interop-server"></a>视频互操作服务器

视频互操作服务器是截止业务服务器 2015年的 Skype 新角色。 使您可以将您的业务服务器部署的 Skype 集成使用某些第三方 VTC （视频电话会议系统） 解决方案。 VIS 作为中介的第三方电话会议系统和 Skype 业务服务器部署。 对于此版本，VIS 着重实现了与 Cisco/Tandberg 视频系统之间的互操作性。
  
有关详细信息，请参阅[规划视频中的业务服务器 Skype 的互操作服务器](../../plan-your-deployment/video-interop-server.md)。
  
### <a name="director"></a>控制器

控制器可以对进行身份验证 Skype 企业服务器用户请求，但它们不承载用户帐户，或者提供状态或会议服务。 控制器对于增强支持外部用户访问的部署中的安全性最有用。 控制器可在将请求发送到内部服务器之前对请求进行身份验证。 对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。
  
### <a name="persistent-chat-server-roles"></a>持久聊天服务器角色

> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。
  
运行 Skype 的业务 Server Standard Edition 还可以运行持久聊天服务器并置在同一台服务器上。 不能将持久聊天前端服务器与 Enterprise Edition 前端服务器并置。
  
有关详细信息，请参阅[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。
  
## <a name="high-availability-and-disaster-recovery-support"></a>高可用性和灾难恢复支持

Skype 业务服务器的服务器冗余性通过池提供高可用性。 如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。 这适用于前端服务器、边缘服务器、中介服务器和控制器。
  
Skype 业务服务器还提供了灾难恢复度量值通过启用池配对。 如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。 如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。
  
Skype 业务 server 还支持后端服务器高可用性的几个选项。 其中包括以下内容：
  
- 数据库镜像
    
- AlwaysOn 可用性组
    
- AlwaysOn 故障转移集群实例 (FCI)
    
- SQL 故障转移群集
    
有关池配对和后端服务器高可用性的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
## <a name="server-collocation-in-skype-for-business-server"></a>Skype 中的业务服务器的服务器并置

我们使用术语将并置，但这意味着什么？ Skype 业务服务器可以找到某些服务器角色和功能，在同一服务器上，这是并置，或在不同服务器上，但它可以是令人费解何时您刚开始出，以及是否正在制作 Standard Edition 或 Enterprise Edition server部署 （每个附带于自己的规则）。 为了帮助您规划，之所以包括服务器并置在 Standard Edition 服务器部署，Enterprise Edition 前端池部署 （在大多数情况下此信息是相同的并且其中它是不同的它调用专门）。
  
### <a name="collocation-of-server-roles"></a>服务器角色的并置

Standard Edition server 具有以下角色并置在一起 （其他配置为需要上述），在 Enterprise Edition 前端池中，此角色可以并置，或部署到单独的服务器：
  
- 中介
    
以下服务器角色必须分别部署在不同的服务器上：
  
- 控制器
    
- Edge
    
- 视频互操作服务器
    
- Office Web Apps
    
### <a name="databases"></a>数据库

这是实际区别 Standard Edition 服务器部署，Enterprise Edition server 池部署中，区域，因此我们将有两个部分下面，同后跟某些其他规则。
  
#### <a name="standard"></a>Standard

由于 SQL Server Express 已并置在 Standard Edition 服务器上，并且不能移动，这是相当简单。 此外，如果您在 Standard Edition server 上部署持久聊天服务器，您还可以将持久聊天和 Standard Edition server 上的持久聊天合规性数据库并置，但您没有。
  
    > [!NOTE] 
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015. 

这些不能并置在 Standard Edition 服务器上，但可以继续在自己的一台数据库服务器上：
  
- 监控数据库
    
- 存档数据库
    
- 对于 Enterprise Edition 前端池的任何后端数据库
    
#### <a name="enterprise"></a>Enterprise

以下数据库可以并置在相同的后端 SQL Server 上：
  
- 后端数据库
    
- 监控数据库
    
- 存档数据库
    
- 持久聊天数据库
    
- 持久聊天合规性数据库
    
#### <a name="both"></a>两者

现在，有其他一些并置在单一的 SQL 实例，或在同一 SQL Server 数据库中的多个 SQL 实例中的业务服务器数据库的 Skype 时应遵循的规则：
  
- 每个 SQL 实例只能包含单个后端数据库的 Enterprise Edition 前端池、 一个监控数据库、 一个存档数据库、 一个持久聊天数据库和单个持久聊天合规性数据库。
    
- 数据库服务器不支持多个 Enterprise Edition 前端池、 一台服务器运行存档，一台服务器运行监控、 一个持久聊天数据库和单个持久聊天合规性数据库，但它可以支持的每个，一个无论是否数据库使用相同的 SQL Server 实例或单独的 SQL Server 实例。
    
    > [!NOTE] 
    > 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 

### <a name="file-shares"></a>文件共享

文件共享可以是在独立的服务器上，您也可以将其并置到与以下任何或所有组件相同的服务器上：
  
- 数据库服务器，包括 Enterprise Edition 前端池的后端服务器
    
- 监控数据库
    
- 存档数据库
    
- 持久聊天数据库
    
- 持久聊天合规性数据库
    
> [!CAUTION]
> 请注意，虽然可以在这些服务器上并置文件共享，但是有必要指出的是，我们不建议这样做。如果将文件共享与任何其他服务器角色并置，请确保经常监视磁盘空间和性能问题。 
  
### <a name="keep-in-mind"></a>请注意

- 不能并置反向代理服务器，其中不业务服务器组件，Skype 和甚至可能不是在拓扑中。 如果您想要支持共享的联盟用户，以及其他许多内容的 web 内容，您将需要反向代理。 如果需要继续操作，并通过配置现有反向代理服务器已经是您正在使用其他应用程序的组织中实现业务服务器 Skype 的反向代理支持。
    
- 您不能并置任何 Exchange UM 组件或 SharePoint Server 组件与任何 Skype 业务服务器角色。
    
## <a name="see-also"></a>另请参阅

[Skype 业务服务器的参考拓扑](reference-topologies.md)