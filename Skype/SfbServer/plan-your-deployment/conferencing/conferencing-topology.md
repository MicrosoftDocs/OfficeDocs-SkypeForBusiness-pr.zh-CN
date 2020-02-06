---
title: 规划 Skype for business Server 的会议拓扑
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要：阅读本主题，了解如何在 Skype for Business 服务器中规划会议拓扑。
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816011"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>规划 Skype for business Server 的会议拓扑
 
**摘要：** 阅读本主题，了解如何在 Skype for Business 服务器中规划会议拓扑。
  
本主题介绍 Skype for business Server 中的会议拓扑基础知识：
  
- 支持的拓扑
    
- 电话拨入式会议注意事项
    
- Web 会议注意事项
    
- 大型会议的要求
    
有关硬件和软件要求的详细信息，请参阅[Skype For Business 服务器中的会议硬件和软件要求](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>支持的拓扑

在 Skype for Business 服务器中，运行会议服务的服务器始终与前端服务器或标准版服务器 collocated。 部署 Skype for Business 服务器时，将自动部署即时消息会议功能。 可以使用拓扑生成器来指定是否要部署 Web、音频和视频 (A/V) 以及电话拨入式会议。 还可以使用拓扑生成器将会议添加到现有部署。 有关拓扑基础知识和 collocation 方案的详细信息，请参阅[Skype for Business 服务器的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
可以在以下拓扑和配置中部署会议：
  
- Skype for business 服务器标准版
    
- Skype for business Server 企业版
    
- 使用或不使用企业语音
    
## <a name="dial-in-conferencing-considerations"></a>电话拨入式会议注意事项

如果要部署电话拨入式会议，必须考虑以下事项：
  
- 电话拨入式会议需要中介服务器才能在 Skype for Business 服务器和 PSTN 网关之间转换信号（和媒体），以及用于在中介服务器和 PSTN 网关之间转换信号和媒体的 PSTN 网关.
    
   需要先部署企业语音或中介服务器以及至少以下某项，然后才能配置电话拨入式会议：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
- 可以在中央站点上部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能部署在分支站点上。
    
- 您必须在部署 Skype for Business Server 会议的每个池中部署电话拨入式会议。 无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。 当用户从一个池中调用访问号码以加入另一个池中的 Skype for Business Server 会议时，此要求支持录制的名称功能。 
    
有关详细信息，请参阅[在 Skype For Business 服务器中规划电话拨入式会议](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 会议注意事项

Web 会议需要以下条件： 
  
- 访问文件存储，文件存储用于存储 Web 会议内容。
    
- 与 Office Web Apps Server/Office Online Server 集成，这是在会议期间要共享 PowerPoint 文件时需执行的步骤。
    
> [!NOTE]
> Office Web Apps 服务器的最新小版本称为 "Office Online Server"，该服务器受 Skype for Business 服务器支持。 有关更多详细信息，请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
Skype for business 服务器提供以下方法来配置 Office Web Apps Server/Office Online Server。 根据你的需要，你可以：
  
- **在组织的防火墙后面和同一网络区域中安装本地的 Skype for business Server 和 Office Web Apps 服务器/Office Online 服务器。** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. 理想情况下，你应该在与 Skype for business 服务器相同的网络区域中安装 Office Web Apps Server/Office Online 服务器。
    
    外部 Skype for business 客户端可以使用反向代理服务器连接到 Skype for business 服务器和 Office Web Apps 服务器/Office Online 服务器，这是一个服务器，该服务器接受来自 Internet 的请求并将其转发到内部网络。 （内部客户端不需要使用反向代理服务器，因为它们可以直接连接到 Office Web Apps Server/Office Online 服务器。）如果你想要使用仅由 Skype for Business Server 使用的专用 Office Web Apps 服务器/Office Online 服务器场，此拓扑效果最佳。
    
- **使用外部部署的 Office Web Apps Server/Office Online 服务器。** 在此拓扑中，将在本地部署 Skype for business 服务器，并使用在 Skype for business 服务器网络区域外部部署的 Office Web Apps Server/Office Online 服务器。 如果 Office Web Apps 服务器/Office Online Server 在公司中的多个应用程序之间共享，并且部署在需要 Skype for Business 服务器的网络中使用 Office Web Apps Server/Office Online 服务器的外部接口，则可能会发生这种情况。
    
    无需安装反向代理服务器;而是从 Office Web Apps Server/Office Online server 到 Skype for Business 服务器的所有请求都通过 Edge 服务器进行路由。 您的内部和外部 Skype for business 客户端都使用外部 URL 连接到 Office Web Apps 服务器/Office Online 服务器。
    
    如果 Office Web Apps Server/Office Online Server 部署在内部防火墙之外，那么在拓扑生成器中，请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps Server**”。
    
有关详细信息，请参阅[在 Skype For Business 服务器中配置与 Office Web Apps 服务器的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
无论你选择什么拓扑，打开正确的防火墙端口至关重要。 你必须确保 DNS 名称、IP 地址和端口未被 Office Web Apps 服务器/Office Online 服务器、负载平衡器或 Skype for business 服务器上的防火墙阻止。
  
> [!NOTE]
> 提供对 Office Web Apps Server/Office Online Server 外部访问权限的另一个选项是在外围网络中部署服务器。如果选择执行此操作，请记住，Office Web Apps Server/Office Online Server 安装要求该服务器计算机是 Active Directory 域的成员。除非网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则，建议不要在外围网络中安装 Office Web Apps Server/Office Online Server，而应在内部网络中安装 Office Web Apps Server/Office Online Server，并向外部用户提供通过反向代理服务器的访问权限。 
  
## <a name="topology-requirements-for-large-meetings"></a>大型会议的拓扑要求

一个大型会议至少需要一个前端服务器和一个后端服务器。但为了提供高可用性，建议采用带镜像后端服务器的双前端服务器池，如下图所示：
  
**大型会议拓扑**

![大型会议拓扑](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
托管大型会议的用户必须将其用户帐户托管在前端池中。 但是，我们不建议你在此池中托管其他用户帐户。 而只是将其用于大型会议。 最佳做法是在此池中创建一个仅用于托管大型会议的特殊用户帐户。 由于大型会议设置已针对性能进行优化，因此将其用作普通用户可能会遇到问题，例如在涉及 PSTN 终结点时无法将 P2P 会话提升到会议。
  
在管理恰好包含两个前端服务器的池时，有一些特别注意事项。有关详细信息，请参阅 [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) 和 [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md)。
  
此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。 有关详细信息，请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
有关拓扑的其他说明包括：
  
- 文件共享是存储会议内容所必需的，如果已部署和启用存档服务器，则文件共享是存储存档文件所必需的。 文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。 有关配置文件共享的详细信息，请参阅[在 Skype For Business Server 2015 中创建文件共享](../../deploy/install/create-a-file-share.md)。
    
- Office Web Apps Server/Office Online Server 是在大型会议中启用 PowerPoint 演示文稿功能所必需的。 Office Web Apps Server/Office Online Server 可专用于大型会议池，也可以是已部署专用池的站点中的其他池所使用的同一个 Office Web Apps Server/Office Online Server。 有关详细信息，请参阅[在 Skype For Business 服务器中配置与 Office Web Apps 服务器的集成](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- 若要实现前端服务器的负载平衡，需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。建议对 SIP 流量实现 DNS 负载平衡。有关详细信息，请参阅 [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 如果要对专用大型会议池使用监视服务器，我们建议使用监视服务器及其在 Skype for Business Server 部署中的所有前端服务器池共享的数据库。 有关详细信息，请参阅[在 Skype For Business 服务器中规划监视](../../plan-your-deployment/monitoring.md)。
    

