---
title: 在 Skype for Business 服务器中规划即时消息和状态
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要：了解如何规划 Skype for Business 服务器中的即时消息和状态。
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815900"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划即时消息和状态
 
**摘要：** 了解如何规划 Skype for Business 服务器中的即时消息和状态。
  
在 Skype for Business 服务器中规划即时消息和状态。 若要了解特定的部署选项（如启用或禁用脱机即时消息（IM）），请参阅[在 Skype For Business 服务器中部署即时消息和状态](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划即时消息和状态

前端服务器提供核心 Skype for business 服务器功能，如即时消息（IM）和联机状态，并且包括在每个 Skype for Business 服务器部署中。 有两个可用的版本： Skype for business Server 企业版，主要针对较大型组织和 Skype for business Server Standard Edition 进行设计，它主要用于需要较小的小型组织硬件投资，不需要完整的高可用性选项。 这两个版本都支持所有 Skype for Business 服务器工作负载，包括即时消息、状态、会议和企业语音。
  
通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。 支持双方和多方之间的 IM 会话。 双方 IM 对话中的一方可以随时将第三方参与者加入对话中。 发生这种情况时，对话窗口会做出相应改变以支持会议功能。
  
状态向用户提供网络中其他人的状态信息。 用户的状态提供有助于其他人决定是否应尝试联系用户以及是否使用即时消息、电话或电子邮件的信息。 只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。 此状态在 Skype for Business 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office）中显示为状态图标。 "状态" 图标表示用户的当前可用性和通信意愿。 
  
### <a name="technical-requirements"></a>技术要求

即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。 有关受支持的硬件、操作系统和数据库软件的信息，请参阅[认证网关](../../SfbPartnerCertification/certification/infra-gateways.md)、skype for business [2015 环境的要求](requirements-for-your-environment/requirements-for-your-environment.md)和[skype For Business Server 2019 的基础结构要求](../../SfBServer2019/plan/system-requirements.md)。
  
### <a name="enabling-communication-with-external-users"></a>启用与外部用户的通信

通过使你的用户能够与外部用户进行通信，你可以大大增加 Skype for business 服务器的投资带来的好处。 外部用户可能包括：
  
- 远程用户：你的组织自己的用户，当他们在防火墙外部工作时使用笔记本或其他 Skype for business 服务器设备。
    
- 联盟用户：与同时运行 Skype for business Server 的用户进行协作的公司用户。 要使用户轻松与这些用户联系，应与这些公司建立联盟关系。 
    
- Skype 用户：Skype for Business 用户可使用 IM、语音和视频联系 Skype 上的数亿用户。
    
> [!NOTE]
> 不再支持 AOL、Yahoo 和 Google Talk。 
  
> [!NOTE]
> 若要启用任何或所有这些方案，你需要部署边缘服务器以帮助在 Skype for Business 服务器部署和外部用户之间实现安全通信。 你的组织的远程用户和联合组织中的用户将能够使用 IM 查看彼此的状态和通信。 
  
> [!NOTE]
> 可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。 
  
### <a name="archiving-im-content"></a>存档 IM 内容

如果您的组织必须遵守合规性法规，则 Skype for business 服务器提供可以使用的功能。 你可以使用存档功能为组织中的所有用户或仅为你指定的特定用户存档 IM 消息的内容。 有关详细信息，请参阅[在 Skype For Business 服务器中规划存档](archiving/archiving.md)。 
  
如果你还部署了 Microsoft Exchange Server 2013，你可以将 Exchange 数据的存档与 Skype for Business 服务器数据的存档进行集成，并使用单个工具搜索两种类型的已存档数据。 有关详细信息，请参阅[配置 Skype For Business 服务器以使用 Exchange Server 存档](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。
  
### <a name="topologies-and-components"></a>拓扑和组件

即时消息 (IM) 和状态所需的唯一组件是：
  
- 组织的前端服务器（称为池）或标准版服务器。 将始终在这些服务器上启用 IM 和状态功能。 有关前端池拓扑和管理的详细信息，请参阅[前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。
    
- 负载平衡器（如果您拥有 Enterprise Edition 前端池）。
    
### <a name="supported-collocation"></a>支持的并置

并置指的是，在单个服务器或一组服务器上安装多个角色。 有关 collocation 的详细信息，请参阅[Skype for Business 服务器的拓扑基础知识](topology-basics/topology-basics.md)。 
  

