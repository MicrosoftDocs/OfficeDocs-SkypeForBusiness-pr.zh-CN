---
title: 规划持久聊天服务器拓扑
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。
ms.openlocfilehash: f50059617ca777b283a62eb8a487b59c3742327a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749931"
---
# <a name="plan-persistent-chat-server-topology"></a>规划持久聊天服务器拓扑
 
**摘要：** 阅读本主题以了解 2015 年 3 月持久聊天服务器Skype for Business Server拓扑。
  
持久聊天服务器支持单服务器和多服务器配置。 您可以将持久聊天服务器安装在 Skype for Business Server 2015 Enterprise Edition或 Standard Edition 服务器上。 

> [!NOTE] 
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 
  
## <a name="persistent-chat-server-components"></a>持久聊天服务器组件

持久聊天服务器由以下组件组成：
  
- 一台或多台计算机运行持久聊天服务器并提供以下服务：
    
  - 持久聊天服务
    
  - 合规性服务，在启用合规性时打开
    
- 如果使用镜像 (一台或多台服务器) 则运行 SQL Server 后端数据库以承载存储聊天室内容、聊天室和类别的持久聊天内容数据库。
    
    > [!NOTE]
    > 后端数据库存储聊天历史记录数据，包括有关创建的类别和持久聊天室的信息。 
  
- 如果启用了合规性，如果使用镜像 (一台或多台服务器) 则运行 SQL Server 后端数据库以承载持久聊天合规性数据库，其中存储了合规性目的的合规性事件和聊天内容。
    
有关持久聊天服务器的硬件和软件要求的详细信息，请参阅[Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)的服务器要求和[Skype for Business Server 2015](hardware-and-software-requirements.md)中的持久聊天服务器的硬件和软件要求。 
  
## <a name="persistent-chat-server-topologies"></a>持久聊天服务器拓扑

可以在单服务器或多服务器池中以及单池或多池拓扑中部署持久聊天服务器。 持久聊天服务器支持以下拓扑：
  
-  Standard Edition在前端服务器上并排持久聊天服务器的服务器
    
-  Standard Edition在单独的服务器上具有持久聊天服务器的服务器
    
-  Enterprise Edition在单独的服务器上具有单个持久聊天服务器的服务器
    
-  Enterprise Edition在单独的服务器上具有多个持久聊天服务器的服务器
    
尽管您可以在 Standard Edition 服务器上部署持久聊天服务器，但请注意，性能和规模将受到影响，并且高可用性不是一个选项。 因此，建议您在 Standard Edition 服务器上部署持久聊天，这主要用于概念证明和评估目的。 
  
Skype for Business Server 2015 支持多种并置方案，这样，如果您具有小型组织) ，您可以在一台服务器 (上运行多个组件，从而灵活节省硬件成本;如果您的组织规模较大，需要可伸缩性和性能) ，则您可以在不同的服务器 (上运行各个组件。 在决定是否并集组件之前，应考虑可伸缩性因素。 2015 Skype for Business Server服务器和 Enterprise Edition 服务器Standard Edition并置方案。 
  
以下各节更详细地介绍了拓扑，包括并置方案和后端数据库服务器的选项。 有关所有服务器角色和数据库并置的详细信息，请参阅[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition在前端服务器上并排持久聊天服务器的服务器

使用Standard Edition，您可以在前端服务器上并排持久聊天。 这是最简单和最基本的配置。 必须确保现有前端服务器具有足够的物理资源容量：CPU、内存、磁盘空间等。
  
此外，还可以将持久聊天服务器后端服务器和持久聊天合规性数据库并 (如果) 本地SQL Server Express服务器上。 还可以选择将单独的应用程序SQL Server专用实例。 
  
> [!IMPORTANT]
> 如果第一台持久聊天服务器与一台持久聊天服务器并排在一台前端服务器上，则不能向Standard Edition服务器池。 建议您将第一台服务器作为独立实例安装，以便以后可以添加更多服务器（如果需要）。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition在单独的服务器上安装了持久聊天服务器的服务器

使用 Standard Edition，您可以将持久聊天服务器安装为独立实例，并稍后根据需要添加更多服务器。 
  
可以将持久聊天服务器后端服务器和持久聊天合规性数据库并 (如果) 本地SQL Server Express服务器上。 还可以选择将单独的应用程序SQL Server专用实例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition具有单个持久聊天服务器的服务器

使用Enterprise Edition，您必须在单独的计算机上安装持久聊天服务器。 也就是说，您无法将持久聊天服务器并Enterprise Edition前端服务器上。 此部署需要一台单独的服务器来运行持久聊天服务器和合规性服务 (（如果启用) ）。
  
但是，您可以将持久SQL Server服务器的数据库并放在前端池的后端Enterprise Edition数据库上。
  
> [!NOTE]
> 如果计划使用适用于 HA DR SQL AlwaysOn 可用性组，请注意，持久聊天服务器数据库不支持此组。 
  
如果将持久聊天数据库与后端数据库并并，可以将单个 SQL Server 实例用于任意或所有数据库，也可以将 SQL Server 的单独实例用于每个数据库。
  
> [!IMPORTANT]
> 承载持久聊天数据库的服务器可以承载其他数据库。 但是，当您考虑将持久聊天数据库与其他数据库并并时，请注意，如果要存储多个用户的消息，则持久聊天数据库所需的磁盘空间可能会变得很大。 因此，建议不要将持久聊天数据库与后端数据库并并。 
  
下图显示了启用了合规性的单个持久聊天服务器拓扑的所有组件 (可选) 。
  
**单服务器拓扑**

![持久聊天服务器 - 单服务器拓扑。](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition具有多台持久聊天服务器的服务器

通过Enterprise Edition，您可以部署多服务器拓扑，以提升容量和可靠性。 多服务器拓扑与单服务器拓扑相同，但多台服务器承载持久聊天服务器，并且可以扩展得更高。 多服务器拓扑可以包含多达四台运行持久聊天服务器 (高可用性和灾难恢复配置的活动计算机，最多允许八台，但只有四台处于活动状态，其余四台处于待机状态) 。 每台服务器可支持 20，000 个并发用户，总共 80，000 个并发用户连接到具有 4 台服务器的持久聊天服务器池。 运行持久聊天服务器的多台计算机应驻留在与客户端和合规性服务Skype for Business Server Active Directory 域服务域中。
  
下图显示了多服务器拓扑的所有组件，该拓扑具有多台运行持久聊天服务器的计算机、可选的合规性服务和单独的合规性数据库。
  
**多服务器拓扑**

![持久聊天服务器 - 多服务器拓扑。](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多服务器拓扑提供了服务器池功能。 在服务器池中，持久聊天服务通信和共享数据。 例如，最初发布至一个持久聊天服务的聊天历史记录可从系统内的任何持久聊天服务获得。 任何持久聊天服务都可以访问通过一个持久聊天服务上载的文件。 用户可以连接到不同的持久聊天服务器前端服务器，并且可以相互通信。 TCP 8011 的默认端口将服务器连接到服务器池，持久聊天服务使用该端口在自身之间进行通信或用于管理目的。
  
例如，在一个四台服务器的持久聊天服务器部署中（其中 80，000 个用户可以同时登录到持久聊天中）中，负载以每台服务器 20，000 个用户的速度均匀分布。 如果一台服务器不可用，则连接到该服务器的用户将失去对持久聊天服务器的访问权限。 断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。 
  

