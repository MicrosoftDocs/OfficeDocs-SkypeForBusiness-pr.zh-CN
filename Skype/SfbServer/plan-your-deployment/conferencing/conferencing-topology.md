---
title: 规划会议拓扑Skype for Business Server
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中规划会议Skype for Business Server。
ms.openlocfilehash: a4d458bf7bea512e773a09551e2fa0c72a982592
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737708"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>规划会议拓扑Skype for Business Server
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中规划会议Skype for Business Server。
  
本主题介绍用于会议的基本Skype for Business Server：
  
- 受支持的拓扑
    
- 电话拨入式会议注意事项
    
- Web 会议注意事项
    
- 大型会议的要求
    
有关硬件和软件要求的信息，请参阅 Skype for Business Server[中的会议硬件和软件要求](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>受支持的拓扑

在Skype for Business Server中，运行会议服务的服务器始终与前端服务器或Standard Edition并。 在部署Skype for Business Server时，将自动部署 IM 会议功能。 可以使用拓扑生成器指定是否 (A/V) 部署 Web、音频和视频以及电话拨入式会议。 还可以使用拓扑生成器向现有部署中添加会议。 有关拓扑基础知识和并置方案的详细信息，请参阅[Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
可以在以下拓扑和配置中部署会议：
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- 具有或不带企业语音
    
## <a name="dial-in-conferencing-considerations"></a>电话拨入式会议注意事项

如果要部署电话拨入式会议，则必须考虑以下事项：
  
- 电话拨入式会议需要中介服务器在 Skype for Business Server 和 PSTN 网关之间的某些配置) 中转换信号 (和媒体，需要 PSTN 网关在中介服务器和 PSTN 网关之间转换信号和媒体。
    
   在配置电话拨入式会议之前，您需要部署 企业语音 或中介服务器以及至少以下其中一项：
    
  - PSTN 网关
    
  - IP-PBX
    
  - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
- 可以在中央站点中会议助理应用程序应用程序服务会议公告应用程序应用程序服务，但不能在分支站点部署应用程序服务。
    
- 必须在部署电话拨入式会议的每一个池中Skype for Business Server电话拨入式会议。 无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。 当用户从一个池中呼叫访问号码以加入另一个池中的 Skype for Business Server 会议时，此要求支持记录的名称功能。 
    
有关详细信息，请参阅 Plan [for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 会议注意事项

Web 会议需要以下各项： 
  
- 访问文件存储，文件存储用于存储 Web 会议内容。
    
- 与 Office Web Apps Server/Office Online Server 集成，这是在会议期间共享PowerPoint文件所必需的。
    
> [!NOTE]
> Web Apps Server Office次迭代命名为 Office Online Server，它受 Skype for Business Server。 有关详细信息，请参阅Office Online Server[文档](/officeonlineserver/office-online-server)。 
  
Skype for Business Server提供了以下配置 Web Apps Office/Office Online Server。 根据您的需要，可以：
  
- **在Skype for Business Server Office网络Office Online Server安装 Web Apps Server/Office Web Apps Server/web Apps Server/Skype for Business Server Web Apps Server/Skype for Business Server Web Apps Server/Web Apps Server/Office Online Server Web Apps Server/Web Apps Server/Office Web Apps Server/** 借助此拓扑，Office反向代理服务器Office Online Server Web Apps Server/Office Online Server外部访问。 理想情况下，您应Office Web Apps Server/Office Online Server Web Apps Server/Skype for Business Server。
    
    外部 Skype for Business 客户端可以使用反向代理服务器连接到 Skype for Business Server 和 Office Web Apps Server/Office Online Server，反向代理服务器是一台从 Internet 接受请求并转发到内部网络的服务器。  (内部客户端不需要使用反向代理服务器，因为它们可以直接连接到 Office Web Apps Server/Office Online Server。) 如果要使用仅由 Skype for Business Server 使用的专用 Office Web Apps Server/Office Online Server 场，则此拓扑最有效。
    
- **使用 Web Apps Server/Office外部部署Office Online Server。** 在此拓扑中，Skype for Business Server本地部署，并使用 Office Web Apps Server/Office Online Server，该服务器部署在 Skype for Business Server 网络区域之外。 当 Office Web Apps Server/Office Online Server 在公司中的多个应用程序之间共享，并且部署在要求 Skype for Business Server 使用 Office Web Apps Server/Office Online Server 外部接口的网络中时，可能会发生这种情况，反之亦然。
    
    无需安装反向代理服务器;相反，来自 Office Web Apps Server/Office Online Server 的所有Skype for Business Server都通过边缘服务器进行路由。 内部客户端和外部 Skype for Business客户端都Office外部 URL Office Online Server Web Apps Server/Office Online Server Web Apps 服务器。
    
    如果 Office Web Apps Server/Office Online Server 部署在内部防火墙之外，则选择"在外部网络 **(（** 即拓扑生成器中的外围/Internet) ）中部署 Office Web Apps Server"选项。
    
有关详细信息，请参阅 Configure [integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
无论您选择什么拓扑，打开正确的防火墙端口至关重要。 必须确保 Office Web Apps Server/Office Online Server、负载平衡器或 Skype for Business Server 上的防火墙不会阻止 DNS 名称、IP 地址和端口。
  
> [!NOTE]
> 提供对 Web Apps Server/Office服务器Office Online Server的另一个选项是在外围网络中部署服务器。 如果选择这样做，请记住，Office Web Apps Server/Office Online Server安装程序要求服务器计算机是 Active Directory 域的成员。 除非您的网络策略允许外围网络中计算机成为 Active Directory 域成员，否则建议您不要将 Office Web Apps Server/Office Online Server 安装在外围网络中。 相反，您应Office Web Apps Server/Office Online Server Web Apps Server/Office Online Server，并通过反向代理服务器提供外部用户访问。 
  
## <a name="topology-requirements-for-large-meetings"></a>大型会议的拓扑要求

一个大型会议至少需要一台前端服务器和一台后端服务器。 但是，为了提供高可用性，我们建议使用两个包含镜像后端服务器的前端服务器池，如下图所示：
  
**大型会议拓扑**

![大型会议拓扑。](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
主持大型会议的用户必须将其用户帐户托管在前端池中。 但是，建议您不要在此池中承载其他用户帐户。 相反，请仅对大型会议使用它。 最佳做法是在此池中创建一个仅用于主持大型会议的特殊用户帐户。 由于大型会议设置已针对性能进行了优化，因此作为普通用户使用它可能会遇到一些问题，例如当涉及 PSTN 终结点时无法将 P2P 会话提升为会议。
  
管理正好具有两台前端服务器的池需要一些特殊注意事项。 有关详细信息，请参阅[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)和[Reference topologies for Skype for Business Server 2015。](../../plan-your-deployment/topology-basics/reference-topologies.md)
  
此外，如果要选择性地为用于大型会议的池提供灾难恢复备份和故障转移，可以将它与不同数据中心中类似的设置专用池配对。 有关详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
有关拓扑的其他说明包括：
  
- 文件共享是存储会议内容以及存档服务器（如果已部署并启用存档服务器）存储存档文件所需的。 文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。 有关配置文件共享的详细信息，请参阅 Create [a file share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md)。
    
- 需要Office Web Apps Server/Office Online Server，才能在大型会议中PowerPoint演示文稿功能。 Office Web Apps Server/Office Online Server 可以专用于大型会议池，也可以与部署专用池的站点的其他池使用的 Office Web Apps Server/Office Online Server 相同。 有关详细信息，请参阅 Configure [integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- 前端服务器的负载平衡要求对 HTTP 流量进行硬件负载平衡 (如会议内容下载) 。 建议对 SIP 流量实现 DNS 负载平衡。 有关详细信息，请参阅[Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 如果要将监控服务器用于专用大型会议池，我们建议使用监控服务器及其数据库，这些数据库在部署中跨所有前端服务器池Skype for Business Server共享。 有关详细信息，请参阅 Plan [for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md)。
