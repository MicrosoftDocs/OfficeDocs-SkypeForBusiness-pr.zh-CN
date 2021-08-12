---
title: 规划即时消息和即时消息中的Skype for Business Server
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要：了解如何在 Skype for Business Server 中规划即时消息和Skype for Business Server。
ms.openlocfilehash: c58cfbfdc7fbfbdff01b1a122ad5cd94ee6a991ab90b52bf86bb62894e4b72a5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284632"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>规划即时消息和即时消息中的Skype for Business Server
 
**摘要：** 了解如何在客户端中规划即时消息Skype for Business Server。
  
规划即时消息和即时消息中的Skype for Business Server。 若要了解特定的部署选项（如启用或禁用脱机即时消息 (IM) ，请参阅D部署即时消息和状态[Skype for Business Server](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>规划即时消息和即时消息中的Skype for Business Server

前端服务器提供核心Skype for Business Server功能，如即时消息 (IM) 和状态，并包含在每个Skype for Business Server部署中。 有两个版本可用：Skype for Business Server Enterprise Edition（主要面向大型组织）和 Skype for Business Server Standard Edition（主要针对需要较小硬件投资且不需要完整高可用性选项的较小组织设计）。 这两个版本都支持Skype for Business Server工作负载，包括 IM、状态、会议和企业语音。
  
通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。支持双方和多方之间的 IM 会话。双方 IM 对话中的一方可以随时将第三方参与者加入对话中。发生这种情况时，对话窗口会做出相应改变以支持会议功能。
  
状态会为用户提供有关网络上其他人的状态的信息。 用户的状态信息可帮助其他人决定是否应尝试与用户联系以及是使用即时消息、电话还是电子邮件。 只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。 此状态在 Skype for Business 和其他状态感知应用程序中显示为状态图标，包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office。 状态图标表示用户的当前可用性和通信愿意。 
  
### <a name="technical-requirements"></a>技术要求

即时消息 (IM) 和状态始终Enterprise Edition前端池和Standard Edition运行。 有关支持的硬件、操作系统和数据库软件的信息，请参阅 Certified [Gateways、Requirements](../../SfbPartnerCertification/certification/infra-gateways.md) [for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md)和 Infrastructure requirements for Skype for Business Server [2019。](../../SfBServer2019/plan/system-requirements.md)
  
### <a name="enabling-communication-with-external-users"></a>启用与外部用户的通信

通过允许用户与外部用户进行通信，可大大提高Skype for Business Server投资收益。 外部用户可能包括：
  
- 远程用户：组织自己的用户，当他们在防火墙外工作并且使用其便携式计算机或其他Skype for Business Server设备。
    
- 联盟用户：来自合作公司同时也运行联合Skype for Business Server。 若要使用户轻松与这些用户联系，请与这些公司建立联盟关系。 
    
- Skype：Skype for Business IM、语音和视频Skype数亿用户。
    
> [!NOTE]
> 不再支持 AOL、Yahoo 和 Google Talk。 
  
> [!NOTE]
> 若要启用任意或所有这些方案，您需要部署边缘服务器以帮助启用部署和外部用户Skype for Business Server通信。 贵组织的远程用户和联盟组织的用户将能够查看彼此的存在状态以及使用 IM 进行通信。 
  
> [!NOTE]
> 可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。 
  
### <a name="archiving-im-content"></a>存档 IM 内容

Skype for Business Server组织必须遵守合规性法规时，可以使用这些功能。 您可以使用存档来存档组织中所有用户或仅针对您指定的特定用户的 IM 消息内容。 有关详细信息，请参阅 Plan [for archiving in Skype for Business Server](archiving/archiving.md)。 
  
如果还部署了 Microsoft Exchange Server 2013，可以将 Exchange 数据的存档与 Skype for Business Server 数据的存档集成，并使用单个工具来搜索这两种类型的存档数据。 有关详细信息，请参阅 Configure [Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)。
  
### <a name="topologies-and-components"></a>拓扑和组件

即时消息 (IM) 和状态所需的唯一组件是：
  
- 组织的前端服务器称为 (池) 或Standard Edition服务器。 这些服务器中始终启用 IM 和状态功能。 有关前端池拓扑和管理的信息，请参阅 [前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。
    
- 负载平衡器（如果有Enterprise Edition前端池）。
    
### <a name="supported-collocation"></a>支持的并置

并置定义为安装了一台服务器或多组服务器，并安装了多个角色。 有关并置的详细信息，请参阅[Topology Basics for Skype for Business Server](topology-basics/topology-basics.md)。 
  

