---
title: 在 Skype for Business Server 2015 中规划持久聊天服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器。
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813662"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划持久聊天服务器
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器。
  
持久聊天服务器是一个可选角色，可让贵组织中多个用户参与持续一段时间的聊天室对话。 尽管用户可以在聊天会话期间实时通信，但每个会话的内容（包括文本、链接和文件）都是持久的，这意味着用户可以随时查看和搜索会话的所有内容。
  
持久聊天服务器可帮助改善组织内部的通信，方法为：
  
- 在整个组织中扩大信息意识和参与
    
- 启用高效的信息共享 
    
- 改善团队之间的通信，包括地理位置分散的跨职能团队
    
- 减少信息过载
    
- 通过选择性地部署持久聊天合规性服务遵循合规性法规

> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
    
## <a name="persistent-chat-server-high-level-architecture"></a>持久聊天服务器高级体系结构

下图显示了持久聊天服务器体系结构的高级别视图。 
  
![持久聊天服务器高级体系结构](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
持久聊天由提供持久聊天服务的前端服务器角色以及一个后端SQL数据库组件组成。 前端和后端组件都包含在专用的持久聊天池中。 承载持久聊天服务器的每台计算机都必须有权访问现有的 Skype for Business Server 2015 拓扑。 在此图中，有一个持久聊天服务器池 (A) ，它依赖于 Skype for Business Server 池 A 来将消息路由到该池。
  
您可以部署一个或多个持久聊天服务器池，每个池最多支持四个活动持久聊天服务器，支持多达 8 万个并发用户。
  
Skype for Business Server 2015 使用会话初始协议 (SIP) 与持久聊天服务进行通信，通过 SIP 协议扩展聊天通信 (XCCOS) 用于聊天。 
  
## <a name="persistent-chat-services"></a>持久聊天服务

下图显示了持久聊天服务器前端服务，以及这些服务与后端数据库组件通信的方式。 前端组件包括持久聊天服务和合规性服务。 后端组件包括持久聊天存储和持久聊天合规性存储。
  
![持久聊天服务器高级服务](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>聊天服务

聊天服务（也称为频道服务）是负责持久聊天服务器的核心服务。 聊天服务提供以下功能：
  
- 接受传入消息
    
- 注册并列出持久聊天室中的联机参与者
    
- 向其他通道订阅者重新传输消息
    
- 实现通道管理、聊天室邀请、搜索和新内容通知的逻辑
    
持久聊天服务使用持久聊天存储 (聊天室内容和其他系统元数据，) 规则等。 该服务将上载到聊天室的文件存储在持久聊天文件存储中。
  
### <a name="compliance-service"></a>合规性服务

如果您的组织规定需要存档持久聊天活动，您可以部署可选的持久聊天合规性服务。 合规性服务负责将聊天内容和事件（如加入和离开聊天室）存档到持久聊天合规性文件存储。 合规性服务安装在持久聊天池中的每台持久聊天服务器上。 
  
### <a name="web-services"></a>Web 服务

持久聊天 Web 服务在 Skype for Business 前端服务器上运行。 Web 服务依赖于 IIS Internet Information Services (，) 实现为 Web 组件：
  
- 用于文件上载和下载的持久聊天 Web 服务负责发布和检索聊天室中的文件。
    
- 用于聊天室管理的持久聊天 Web 服务负责为用户提供管理其聊天室和创建新聊天室的能力。
    
## <a name="defining-requirements-for-your-organization"></a>为组织定义要求

如果决定部署持久聊天服务器，则需要确定组织的业务需求，然后定义拓扑、基础结构和技术要求以支持业务需求。 若要优化部署，需要回答以下问题：
  
- 您是否正在从以前版本的群聊服务器或以前版本的持久聊天服务器迁移，还是首次部署持久聊天服务器？
    
- 谁可以使用持久聊天服务器？ 指定持久聊天策略以确定全局、站点或用户级别的用户访问。
    
- 有多少用户需要访问持久聊天服务器？ 持久聊天服务器支持 150，000 (策略) 启用的用户，以及最多 80，000 个并发用户。 一台持久聊天服务器可支持 20，000 个已连接用户，一个持久聊天服务器池可具有最多 4 个活动服务器，总共 80，000 个并发连接用户。
    
- 您希望如何控制范围、信息隔离边界和访问？ 您可以定义类别以隔离这些边界，并选择允许谁位于在每个类别中创建的聊天室中。
    
- 您希望如何控制可创建聊天室的用户？ 你可以定义可以创建聊天室的创建者。 创建者可以将其他成员分配为聊天室管理员，以持续管理聊天室。
    
- 您希望如何创建聊天室？ 持久聊天服务器提供用于创建和管理聊天室的基于 Web 的功能。 这可以从 Skype for Business 客户端启动。 可以选择定义实现业务需求和工作流的客户解决方案，并配置持久聊天服务器以将用户引导到自定义解决方案。
    
- 您希望设置哪一类外接程序？ 外接程序利用 Skype for Business 客户端中的扩展性窗格提供与聊天室相关的上下文，从而增强聊天室内体验。 您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。 聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。 
    
- 您具有哪一类高可用性和灾难恢复要求？ 持久聊天服务器SQL Server镜像和SQL Server群集实现高可用性。 对于灾难恢复，持久聊天服务器支持最多 8 台服务器 (4 个活动服务器，在拉伸池中支持 4) 备用服务器，SQL Server日志。 
    
- 是否有管理要求？ 如果您的公司位于需要将数据保留在国家/地区内的一个或多个国家/地区，您可能需要部署多个持久聊天服务器池，每个池都是特定地理位置的本地池。 聊天室、类别或外接程序不跨池，它仅属于一个持久聊天服务器池。 
    
    > [!NOTE]
    > 拥有多个持久聊天服务器池不会为您提供更多的扩展 (您在所有持久聊天服务器池中仍只能有 80，000 个并发) 。 支持多个持久聊天服务器池的主要原因是支持法规问题。 
  
## <a name="for-more-information"></a>详细信息

有关安装和配置持久聊天服务器的信息，请参阅下列主题：
  
- 若要详细了解如何部署持久聊天服务器，请参阅在 [Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)中部署持久聊天服务器。 
    
- 若要详细了解如何在持久聊天服务器部署上配置设置，请参阅"在 [Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md)中管理持久聊天服务器"。
    

