---
title: 规划即时消息和状态 Skype 业务 Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要： 了解如何规划即时消息和状态 Skype 业务服务器。
ms.openlocfilehash: f29464b9eaf725deb41c41cb9255a8b2f6737792
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907162"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>规划即时消息和状态 Skype 业务 Server
 
**摘要：** 了解如何规划即时消息和状态 Skype 业务 Server。
  
规划即时消息和状态 Skype 业务 Server。 若要了解有关具体的部署选项，如启用或禁用脱机即时消息 (IM)，请参阅[Deploy 即时消息和 Skype 业务服务器中的状态](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>规划即时消息和状态 Skype 业务 Server

前端服务器提供核心业务服务器功能，如即时消息 (IM) 和状态的 Skype 和都包含在每个 Skype 业务服务器部署。 有两个版本可用： 对于业务 Server Enterprise Edition，主要用于更大型组织，其中的 Skype 和业务 Server Standard Edition，其中主要用于较小的组织希望较小的 Skype硬件投资和不要求具备高可用性选项。 这两个版本的业务服务器工作负荷，包括 IM、 状态、 会议和企业语音支持所有 Skype。
  
通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。 支持双方和多方之间的 IM 会话。 双方 IM 对话中的一方可以随时将第三方参与者加入对话中。 发生这种情况时，对话窗口会做出相应改变以支持会议功能。
  
状态向用户提供网络中其他人的状态信息。 用户的状态提供有助于其他人决定自己是否应尝试与该用户联系，以及是否使用即时消息、 电话还是电子邮件的信息。 只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。 此状态在 Skype for Business 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office）中显示为状态图标。 状态图标表示用户的当前有空以及愿意进行交流。 
  
### <a name="technical-requirements"></a>技术要求

即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。 有关受支持的硬件、 操作系统和数据库软件的信息，请参阅[认证的网关](../../SfbPartnerCertification/certification/infra-gateways.md)、[您 Skype 业务 2015年环境的要求](requirements-for-your-environment/requirements-for-your-environment.md)和 for Business Server 2019 Skype 的[基础结构要求](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>启用与外部用户的通信

通过使您的用户可以与外部用户通信，会大大增加业务服务器 Skype 投资的好处。 外部用户可能包括：
  
- 远程用户： 您组织的内部用户，在防火墙外工作并使用其便携式计算机或其他 Skype 的业务服务器设备。
    
- 联盟用户： 从您使用的公司还业务服务器运行 Skype 的用户。 要使用户轻松与这些用户联系，应与这些公司建立联盟关系。 
    
- Skype 用户：Skype for Business 用户可使用 IM、语音和视频联系 Skype 上的数亿用户。
    
> [!NOTE]
> 不再支持 AOL、Yahoo 和 Google Talk。 
  
> [!NOTE]
> 若要启用任何或所有这些方案，您需要部署边缘服务器以帮助您实现您的业务服务器部署的 Skype 和外部用户之间的安全通信。 贵组织的远程用户和联盟组织的用户都将能够查看彼此的状态，并使用 IM 进行通信。 
  
> [!NOTE]
> 可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。 
  
### <a name="archiving-im-content"></a>存档 IM 内容

Skype 业务服务器提供如果您的组织必须遵守合规性要求，则可以使用的功能。 你可以使用存档功能为组织中的所有用户或仅为你指定的特定用户存档 IM 消息的内容。 有关详细信息，请参阅[Plan for Business Server 的 Skype 的存档](archiving/archiving.md)。 
  
如果您还可以部署 Microsoft Exchange Server 2013，您可以集成 Exchange 数据的存档与 Skype 的存档服务器业务数据和使用一个工具搜索两种类型的存档数据。 有关详细信息，请参阅[业务服务器要使用 Exchange Server 存档配置的 Skype](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。
  
### <a name="topologies-and-components"></a>拓扑和组件

即时消息 (IM) 和状态所需的唯一组件是：
  
- （称为池） 的组织的前端服务器或 Standard Edition server。 将始终在这些服务器上启用 IM 和状态功能。 在前端池拓扑结构和管理的详细信息，请参阅[前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。
    
- 负载平衡器（如果您拥有 Enterprise Edition 前端池）。
    
### <a name="supported-collocation"></a>支持的并置

并置指的是，在单个服务器或一组服务器上安装多个角色。 并置的详细信息，请参阅[拓扑的 Skype 业务服务器的基础知识](topology-basics/topology-basics.md)。 
  

