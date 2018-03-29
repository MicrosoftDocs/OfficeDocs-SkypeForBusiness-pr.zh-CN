---
title: 规划 Skype for Business Server 2015 中的即时消息和状态
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要： 了解如何规划业务服务器 2015年的即时消息和 Skype 在状态。
ms.openlocfilehash: 1934f0308cda59b52073c47d1652ad2286bd6977
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>规划 Skype for Business Server 2015 中的即时消息和状态
 
**摘要：**了解如何规划 Skype for Business Server 2015 中的即时消息和状态。
  
规划 Skype for Business Server 2015 中的即时消息和状态。 若要了解有关特定的部署选项，例如启用或禁用脱机即时消息 (IM)，请参阅[部署即时消息和 Skype 的业务服务器 2015年遍布](../deploy/im-and-presence/im-and-presence.md)。
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>规划 Skype for Business Server 2015 中的即时消息和状态

前端服务器提供核心 Skype 的业务服务器功能，如即时消息 (IM) 和状态，包括在每一个 Skype 业务服务器部署。 有两种版本： Skype 业务服务器企业版，它主要用于较大的组织和 Skype 业务服务器标准版中，它主要用于较小的公司要小硬件的投资，而不需要完整的高可用性选项。 这两个版本支持所有 Skype 业务服务器工作负荷包括即时消息、 状态显示、 会议和企业语音。
  
通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。 支持双方和多方之间的 IM 会话。 双方 IM 对话中的一方可以随时将第三方参与者加入对话中。 发生这种情况时，对话窗口会做出相应改变以支持会议功能。
  
状态向用户提供网络中其他人的状态信息。 用户的状态提供信息以帮助其他人决定是否他们应该尝试联系用户，以及是否使用即时消息、 电话或电子邮件。 只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。 此状态在 Skype for Business 和其他可检测状态的应用程序（包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术和 Microsoft Office）中显示为状态图标。 状态图标表示该用户的当前可用性和意愿进行通信。 
  
### <a name="technical-requirements"></a>技术要求

即时消息 (IM) 和状态始终在 Enterprise Edition 前端池和 Standard Edition 服务器上运行。 有关受支持的硬件、 操作系统和数据库软件的信息，请参阅[基础结构以实现业务的 Skype](https://technet.microsoft.com/en-us/office/dn947483)和[为您的业务环境的 Skype 的要求](requirements-for-your-environment/requirements-for-your-environment.md)。
  
### <a name="enabling-communication-with-external-users"></a>启用与外部用户的通信

通过允许您的用户与外部用户进行通信，可大大增加在 Skype for Business Server 中投资的收益。外部用户可能包括：
  
- 远程用户： 组织自己的用户，您的防火墙之外工作和业务服务器设备笔记本电脑或其他 Skype 使用时。
    
- 联合用户： 在公司使用还为业务服务器运行 Skype 的用户。 要使用户轻松与这些用户联系，应与这些公司建立联盟关系。 
    
- Skype 用户：Skype for Business 用户可使用 IM、语音和视频联系 Skype 上的数亿用户。
    
> [!NOTE]
> 不再支持 AOL、Yahoo 和 Google Talk。 
  
> [!NOTE]
> 要实现任意或所有这些方案，需要部署边缘服务器以帮助启用 Skype for Business Server 部署和外部用户之间的安全通信。 您的组织的远程用户和联盟组织的用户将能够看到对方的状态并使用即时消息进行通信。 
  
> [!NOTE]
> 可扩展消息传递和状态协议 (XMPP) 仅支持统一功能协作平台 (UCCP) 联合互操作性测试命令 (JITC) 认证方案。 
  
### <a name="archiving-im-content"></a>存档 IM 内容

如果组织必须遵守合规性要求，Skype for Business Server 提供了您可以使用的功能。您可以使用存档功能为组织中的所有用户或仅为您指定的特定用户存档 IM 消息的内容。有关详细信息，请参阅规划文档中的“规划 Skype for Business Server 2015 中的存档”。 
  
如果您还部署了 Microsoft Exchange Server 2013，则可以将 Exchange 数据的存档与 Skype for Business Server 数据的存档进行集成，并使用一个工具同时搜索这两种类型的存档数据。 有关详细信息，请参阅配置为使用 Microsoft Exchange Server 2013年归档的业务服务器 2015年的 Skype。
  
### <a name="topologies-and-components"></a>拓扑和组件

即时消息 (IM) 和存在所需的唯一组件包括：
  
- 您的组织的前端服务器 （称为池） 或标准版服务器。 将始终在这些服务器上启用 IM 和状态功能。 前端池拓扑和管理的详细信息，请参阅[前结束池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。
    
- 负载平衡器（如果您拥有 Enterprise Edition 前端池）。
    
### <a name="supported-collocation"></a>支持的并置

并置指的是，在单个服务器或一组服务器上安装多个角色。 有关配置的详细信息，请参阅[有关业务服务器 2015年的 Skype 的拓扑结构基础](topology-basics/topology-basics.md)。 
  

