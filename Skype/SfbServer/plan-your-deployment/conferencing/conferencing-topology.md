---
title: 规划业务 Server Skype 的会议拓扑
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要： 阅读本主题可了解有关规划业务服务器中 Skype 会议拓扑。
ms.openlocfilehash: d8e3d771eadfe47ee1d7ec15eb68051b717643bf
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "25375955"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>规划业务 Server Skype 的会议拓扑
 
**摘要：** 阅读本主题可了解如何规划业务服务器中 Skype 会议拓扑。
  
本主题介绍为企业服务器拓扑的 Skype 中的会议的基础知识：
  
- 支持的拓扑
    
- 电话拨入式会议注意事项
    
- Web 会议注意事项
    
- 大型会议的要求
    
有关硬件和软件要求的详细信息，请参阅[Skype 业务服务器中的会议的硬件和软件要求](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>支持的拓扑

在业务服务器 Skype，运行会议服务的服务器是始终与并置的前端服务器或 Standard Edition 服务器。 在部署 Skype 业务服务器时，会自动部署 IM 会议功能。 可以使用拓扑生成器来指定是否要部署 Web、音频和视频 (A/V) 以及电话拨入式会议。 还可以使用拓扑生成器将会议添加到现有部署。 有关详细信息拓扑基础知识和并置方案，请参阅[拓扑的 Skype 业务服务器的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
可以在以下拓扑和配置中部署会议：
  
- 对于业务 Server Standard Edition 的 Skype
    
- 对于业务 Server Enterprise Edition 的 Skype
    
- 使用或不使用企业语音
    
## <a name="dial-in-conferencing-considerations"></a>电话拨入式会议注意事项

如果要部署电话拨入式会议，必须考虑以下事项：
  
- 电话拨入式会议 Skype 业务服务器和 PSTN 网关和 PSTN 网关翻译中介服务器与 PSTN 网关之间信号和媒体之间需要中介服务器转换信号 （和媒体的一些配置）.
    
   需要先部署企业语音或中介服务器以及至少以下某项，然后才能配置电话拨入式会议：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
- 可以在中央站点上部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能部署在分支站点上。
    
- 您必须部署中每个池部署 Skype Business Server 会议电话拨入式会议。 无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。 当用户从一个池加入 Business Server 会议池中不同 Skype 呼叫访问号码，这一要求支持录制的名称功能。 
    
有关详细信息，请参阅[规划中的业务服务器的 Skype 电话拨入式会议](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 会议注意事项

Web 会议需要以下条件： 
  
- 访问文件存储，文件存储用于存储 Web 会议内容。
    
- 与 Office Web Apps Server/Office Online Server 集成，这是在会议期间要共享 PowerPoint 文件时需执行的步骤。
    
> [!NOTE]
> Office Web Apps Server 的最新小名为 Office Online Server，业务服务器支持的 Skype。 有关详细信息，请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
Skype 业务服务器提供了下列方式来配置 Office Web Apps Server/Office Online Server。 根据你的需要，你可以：
  
- **安装 Business Server 和 Office Web Apps Server/Office Online Server 内部部署组织的防火墙背后处于和相同的网络区域中的两个 Skype。** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. 理想情况下，您应安装 Office Web Apps Server/Office Online Server 在同一个网络区域中作为 Skype 业务服务器。
    
    外部 Skype 业务客户端可以使用反向代理服务器，它是从 Internet 接受请求，并将它们转发到内部网络的服务器连接到业务服务器 Skype 和 Office Web Apps Server/Office Online Server。 （内部客户端不需要使用反向代理服务器，因为他们可以直接连接到 Office Web Apps Server/Office Online Server。）如果您想要使用的业务服务器仅由 Skype 使用专用的 Office Web Apps Server/Office Online Server 服务器场，这种拓扑最有效。
    
- **使用外部部署的 Office Web Apps Server/Office Online 服务器。** 在此拓扑中，Skype 业务服务器部署在内部部署，并使用 Office Web Apps Server/Office Online Server Business Server 网络区域的 Skype 外部部署。 Office Web Apps Server/Office Online Server 跨公司中的多个应用程序共享和需要 Skype 供业务服务器使用 Office Web Apps Server/Office Online 服务器的外部接口的网络中部署时可能发生这种情况反之亦然。
    
    不需要安装一个反向代理服务器。相反，所有与 Office Web Apps Server/Office Online Server 对请求的企业服务器的 Skype 通过边缘服务器进行路由。 内部和您的业务客户端的外部 Skype 连接到 Office 应用程序服务器/Office Online 使用 Web 服务器的外部 URL。
    
    如果 Office Web Apps Server/Office Online Server 部署在内部防火墙之外，那么在拓扑生成器中，请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps Server**”。
    
有关详细信息，请参阅[配置与 Skype 的业务服务器中的 Office Web Apps Server 的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
无论你选择什么拓扑，打开正确的防火墙端口至关重要。 您必须确保的 DNS 名称、 IP 地址和端口不会被阻止的 Office Web Apps Server/Office Online Server、 负载平衡器或 Skype 上的防火墙业务服务器。
  
> [!NOTE]
> 提供对 Office Web Apps Server/Office Online Server 外部访问权限的另一个选项是在外围网络中部署服务器。如果选择执行此操作，请记住，Office Web Apps Server/Office Online Server 安装要求该服务器计算机是 Active Directory 域的成员。除非网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则，建议不要在外围网络中安装 Office Web Apps Server/Office Online Server，而应在内部网络中安装 Office Web Apps Server/Office Online Server，并向外部用户提供通过反向代理服务器的访问权限。 
  
## <a name="topology-requirements-for-large-meetings"></a>大型会议的拓扑要求

一个大型会议至少需要一个前端服务器和一个后端服务器。但为了提供高可用性，建议采用带镜像后端服务器的双前端服务器池，如下图所示：
  
**大型会议拓扑**

![大型会议拓扑](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
承载大型会议的用户必须具有其用户帐户驻留在前端池。 但是，我们不建议您承载此池中的其他用户帐户。 相反，仅对大型会议使用它。 最佳做法是仅对主机大型会议使用此池中创建特殊用户帐户。 由于性能进行了优化的大型会议设置，使用作为普通用户可能会遇到问题，如无法升级到会议的 P2P 会话时涉及的 PSTN 方终结点。
  
在管理恰好包含两个前端服务器的池时，有一些特别注意事项。有关详细信息，请参阅 [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) 和 [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md)。
  
此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。 有关详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
有关拓扑的其他说明包括：
  
- 文件共享是存储会议内容所必需的，如果已部署和启用存档服务器，则文件共享是存储存档文件所必需的。 文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。 有关配置文件共享的详细信息，请参阅[创建文件共享中的业务服务器 2015 Skype](../../deploy/install/create-a-file-share.md)。
    
- Office Web Apps Server/Office Online Server 是在大型会议中启用 PowerPoint 演示文稿功能所必需的。 Office Web Apps Server/Office Online Server 可专用于大型会议池，也可以是已部署专用池的站点中的其他池所使用的同一个 Office Web Apps Server/Office Online Server。 有关详细信息，请参阅[配置与 Skype 的业务服务器中的 Office Web Apps Server 的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- 若要实现前端服务器的负载平衡，需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。建议对 SIP 流量实现 DNS 负载平衡。有关详细信息，请参阅 [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 如果您想要使用专用的大型会议池的监控服务器，我们建议对业务服务器部署中您 Skype 的前端服务器池的所有使用监控服务器和共享其数据库。 有关详细信息，请参阅[规划中的业务服务器 Skype 监控](../../plan-your-deployment/monitoring.md)。
    

