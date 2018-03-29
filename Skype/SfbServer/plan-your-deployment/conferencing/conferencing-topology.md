---
title: 规划 Skype for Business Server 2015 的会议拓扑
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要： 请阅读本主题，以了解有关业务服务器 2015年计划在 Skype 会议拓扑。
ms.openlocfilehash: b81a8eeb1300fa6bad887ba923c28fc4d2676fe8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server-2015"></a>规划 Skype for Business Server 2015 的会议拓扑
 
**摘要：**阅读本主题以了解有关业务服务器 2015年计划在 Skype 会议拓扑。
  
本主题描述 Skype for Business Server 2015 中会议拓扑的基础知识：
  
- 支持的拓扑
    
- 电话拨入式会议注意事项
    
- Web 会议注意事项
    
- 大型会议的要求
    
有关硬件和软件要求的详细信息，请参阅[硬件和软件的要求，对于在商业服务器 2015年的 Skype 的会议](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>支持的拓扑

在 Skype 业务服务器，运行会议服务的服务器是总是搭配使用前端服务器或标准版服务器。 当部署 Skype 业务服务器上时，会自动部署 IM 会议功能。 可以使用拓扑生成器来指定是否要部署 Web、音频和视频 (A/V) 以及电话拨入式会议。 还可以使用拓扑生成器将会议添加到现有部署。 拓扑的基本知识和配置有关的详细信息的情况下，请参见[业务服务器 2015年的 Skype 的拓扑结构基础](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
可以在以下拓扑和配置中部署会议：
  
- Skype 业务 Server 标准版
    
- Skype 业务服务器的企业版
    
- 使用或不使用企业语音
    
## <a name="dial-in-conferencing-considerations"></a>电话拨入式会议注意事项

如果要部署电话拨入式会议，必须考虑以下事项：
  
-  拨入会议之间业务服务器的 Skype 和 PSTN 网关，并在 PSTN 网关转换信号和中介服务器和 PSTN 网关之间的媒体要求中介服务器转换信号 （和在某些配置的介质）.
    
    需要先部署企业语音或中介服务器以及至少以下某项，然后才能配置电话拨入式会议：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
- 可以在中央站点上部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能部署在分支站点上。
    
- 您必须部署在哪里部署 Skype 业务服务器会议的每个池中的拨入会议。 无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。 这一要求支持记录的名称功能，当用户从一个池加入不同池中的业务服务器大会 Skype 呼叫的访问号码。 
    
有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在拨入会议](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 会议注意事项

Web 会议需要以下条件： 
  
- 访问文件存储，文件存储用于存储 Web 会议内容。
    
- 与 Office Web Apps Server/Office Online Server 集成，这是在会议期间要共享 PowerPoint 文件时需执行的步骤。
    
> [!NOTE]
> Office Web 应用程序服务器的最新小版本名为 Office 联机服务器，它受业务服务器 2015 Skype。 有关详细信息，请参阅[Office 联机服务器的文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
Skype 业务服务器提供以下方法配置 Office Web 应用程序服务器/Office 联机服务器。 根据你的需要，你可以：
  
- **安装两个 Skype 的业务服务器和 Office Web 应用程序服务器/Office 联机服务器内部组织的防火墙，并在相同的网络区域。** 借助此拓扑，将通过反向代理服务器提供对 Office Web Apps Server/Office Online Server 的外部访问权限。 理想情况下，您应该安装 Office Web 应用程序服务器/Office 联机服务器在相同的 Skype 网络分区业务服务器。
    
    外部 Skype 业务客户端可以连接到企业服务器的 Skype 和 Office Web 应用程序服务器/Office 联机服务器通过使用反向代理服务器，它是从互联网获取请求，并将它们转发到内部网络的服务器。 （内部客户端不需要使用反向代理服务器，因为它们可以直接连接到 Office Web 应用程序服务器/办公室在线服务器。）如果您想要使用的业务服务器仅由 Skype 使用专用的 Office Web 应用程序服务器/Office 联机服务器场，此拓扑的效果最佳。
    
- **使用外部部署的 Office Web 应用程序服务器/Office 联机服务器。** 在此拓扑中，Skype 业务服务器部署的内部，并使用 Office Web 应用程序服务器/办公室在线服务器部署到企业服务器网络区域的 Skype 之外。 Office Web 应用程序服务器/Office 联机服务器在公司中的多个应用程序间共享并要求业务服务器使用 Office Web 应用程序服务器/Office 联机服务器的外部接口的 Skype 网络中部署时可能会发生这种情况反之亦然。
    
    您不需要安装一个反向代理服务器。相反，所有从 Office Web 应用程序服务器/Office 联机服务器对请求 Skype 业务服务器通过边缘服务器路由。 内部和您外部 Skype 业务客户端连接到 Office 应用程序服务器/Office 联机使用 Web 服务器的外部 URL。
    
    如果 Office Web Apps Server/Office Online Server 部署在内部防火墙之外，那么在拓扑生成器中，请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps Server**”。
    
有关详细信息，请参阅[配置集成具有的业务服务器 2015 Skype 在 Office Web 应用程序服务器](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
无论你选择什么拓扑，打开正确的防火墙端口至关重要。 您必须确保该 DNS 名称、 IP 地址和端口不防火墙阻止的 Office Web 应用程序服务器/Office 联机服务器、 负载平衡器或 Skype 业务服务器。
  
> [!NOTE]
> 提供对 Office Web Apps Server/Office Online Server 外部访问权限的另一个选项是在外围网络中部署服务器。如果选择执行此操作，请记住，Office Web Apps Server/Office Online Server 安装要求该服务器计算机是 Active Directory 域的成员。除非网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则，建议不要在外围网络中安装 Office Web Apps Server/Office Online Server，而应在内部网络中安装 Office Web Apps Server/Office Online Server，并向外部用户提供通过反向代理服务器的访问权限。 
  
## <a name="topology-requirements-for-large-meetings"></a>大型会议的拓扑要求

一个大型会议至少需要一个前端服务器和一个后端服务器。但为了提供高可用性，建议采用带镜像后端服务器的双前端服务器池，如下图所示：
  
**大型会议拓扑**

![大型会议拓扑](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
承载大型会议的用户必须具有用户帐户驻留在前结束池。 但是，我们不建议您承载此池中的其他用户帐户。 相反，它仅用于大型会议。 最佳做法是仅用于主机大型会议此池中创建特殊的用户帐户。 由于大型会议设置的性能进行了优化，将其作为普通用户可能会遇到问题，如无法提升到会议的 P2P 会话涉及 PSTN 终结点时。
  
在管理恰好包含两个前端服务器的池时，有一些特别注意事项。 有关详细信息，请参阅[业务服务器 2015年的 Skype 的拓扑结构基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)和[业务服务器 2015年的 Skype 的引用拓扑](../../plan-your-deployment/topology-basics/reference-topologies.md)。
  
此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。 有关详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
附加说明有关拓扑包括：
  
- 文件共享是存储会议内容所必需的，如果已部署和启用存档服务器，则文件共享是存储存档文件所必需的。 文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。 有关配置文件共享的详细信息，请参阅[创建文件共享中的业务服务器 2015 Skype](../../deploy/install/create-a-file-share.md)。
    
- Office Web Apps Server/Office Online Server 是在大型会议中启用 PowerPoint 演示文稿功能所必需的。 Office Web Apps Server/Office Online Server 可专用于大型会议池，也可以是已部署专用池的站点中的其他池所使用的同一个 Office Web Apps Server/Office Online Server。 有关详细信息，请参阅[配置集成具有的业务服务器 2015 Skype 在 Office Web 应用程序服务器](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- 若要实现前端服务器的负载平衡，需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。 建议对 SIP 流量实现 DNS 负载平衡。 有关详细信息请参阅[负载平衡对 Skype 的业务要求](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 如果您想要使用专用的大型会议池监视服务器，我们建议用于监视服务器和共享其数据库中您 Skype 的前端服务器池的所有业务服务器部署。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在监视](../../plan-your-deployment/monitoring.md)。
    

