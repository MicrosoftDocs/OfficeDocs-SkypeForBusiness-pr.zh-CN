---
title: 规划持久聊天服务器拓扑
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要： 阅读此主题以了解有关持久聊天服务器组件和拓扑中 Skype 的业务服务器 2015年。
ms.openlocfilehash: 9f771cddb8d3176840e8df1a34339f33e8ccac5f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968252"
---
# <a name="plan-persistent-chat-server-topology"></a>规划持久聊天服务器拓扑
 
**摘要：** 阅读此主题以了解有关持久聊天服务器组件和拓扑中 Skype 的业务服务器 2015年。
  
Persistent Chat Server 支持单服务器和多服务器的配置。 业务 Server 2015 Enterprise Edition 或 Standard Edition Server，可以在任一 Skype 上安装持久聊天服务器。 

> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
  
## <a name="persistent-chat-server-components"></a>持久聊天服务器组件

持久聊天服务器由以下组件组成：
  
- 一个或多个计算机运行持久聊天服务器并提供以下服务：
    
  - 持久聊天服务
    
  - 合规性服务，在启用合规性时打开
    
- 一个或多个服务器 （多个如果使用镜像类型） 运行承载持久聊天的内容数据库的 SQL Server 后端数据库存储聊天室内容、 聊天室和类别。
    
    > [!NOTE]
    > 后端数据库用于存储聊天历史记录数据，包括有关类别和创建的持久聊天聊天室的信息。 
  
- 如果启用合规性，则 （多个如果使用镜像类型） 的一个或多个服务器运行 SQL Server 后端数据库用于承载持久聊天合规性数据库中，出于合规性目的的合规性事件和聊天其中内容存储。
    
有关持久聊天服务器的硬件和软件要求的详细信息，请参阅[for Persistent Chat Server 中的业务服务器 2015 Skype 的硬件和软件要求](hardware-and-software-requirements.md)和[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  
## <a name="persistent-chat-server-topologies"></a>持久聊天服务器拓扑

您可以部署持久聊天服务器在单服务器还是多服务器池，并使用单池或多池拓扑。 持久聊天服务器支持以下拓扑：
  
-  Standard Edition Server 与持久聊天服务器并置在前端服务器上
    
-  Standard Edition Server 与一台服务器上的持久聊天服务器
    
-  与一个持久聊天服务器一台服务器上的 Enterprise Edition Server
    
-  使用多个持久聊天服务器不同的服务器上的 Enterprise Edition Server
    
尽管可以部署 Standard Edition Server 上的持久聊天服务器，请注意会影响性能和范围，并不高可用性，一个选项。 因此，建议您部署持久聊天主要用于证明概念和评估目的 Standard Edition Server 上。 
  
Skype 的业务服务器 2015年支持各种并置方案，从而灵活地通过在一台服务器 （如果您有一个小型组织） 上运行多个组件节省硬件成本，或在不同的服务器 （运行各个组件如果您有较大组织的需要可伸缩性和性能）。 决定是否将并置组件之前，应考虑可伸缩性因素。 并置方案不同的 Skype 业务 Server 2015 Enterprise Edition 和 Standard Edition 服务器。 
  
以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。 有关所有服务器角色和数据库并置的详细信息，请参阅[拓扑的业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server 与持久聊天服务器并置在前端服务器上

使用 Standard Edition，可以将持久聊天并置在前端服务器上。 这是最简单也最基本的配置。 您必须确保现有前端服务器具有足够的容量会严重影响物理资源： CPU、 内存、 磁盘空间，等等。
  
此外，您可以并置的持久聊天服务器后端服务器和持久聊天合规性数据库 （如果已启用） 的本地 SQL Server Express 后端服务器上。 还可以选择使用独立的 SQL Server 及专用实例。 
  
> [!IMPORTANT]
> 如果第一台持久聊天服务器与 Standard Edition 前端服务器并置，则不能向持久聊天服务器池添加其他服务器。 建议您安装第一台服务器作为独立实例，以便您可以添加更多服务器更高版本，如果需要。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition Server 与持久聊天服务器安装在不同的服务器上

使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。   
  
您可以并置的持久聊天服务器后端服务器和持久聊天合规性数据库 （如果已启用） 的本地 SQL Server Express 后端服务器上。 还可以选择使用独立的 SQL Server 及专用实例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server 与一个持久聊天服务器

使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。 也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。 这种部署需要单独的服务器在运行 Persistent Chat Server 和合规性服务 （如果已启用）。
  
您可以但是，将并置的 SQL Server 数据库对于 Persistent Chat Server 上的 Enterprise Edition 前端池的后端数据库。
  
> [!NOTE]
> 如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。 
  
如果您将并置的持久聊天数据库后端数据库，您可以使用 SQL Server 的单个实例的任意或全部数据库，或您可以为每个数据库使用单独的 SQL Server 实例。
  
> [!IMPORTANT]
> 承载持久聊天数据库的服务器可以承载其他数据库。 但是，当您考虑持久聊天数据库与其他数据库并置时，注意，如果存储较多的用户的消息的磁盘空间需要由持久聊天数据库可以变得非常大。 因此，我们不建议的持久聊天数据库后端数据库并置。 
  
下图显示拓扑的所有组件的单个持久聊天服务器与启用合规性 （可选）。
  
**单服务器拓扑**

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition Server 与多个持久聊天服务器

与 Enterprise Edition，您可以部署更大容量和可靠性的多服务器拓扑。 多服务器拓扑是单服务器拓扑相同只不过多台服务器承载持久聊天服务器，并可以扩展更高版本。 多服务器拓扑可以包括多达四台运行持久聊天服务器的活动计算机 （高可用性和灾难恢复配置将允许最多八个，但仅四可以是活动和四处于备用状态的剩余）。 每台服务器可以支持多达 20,000 个并发用户，用于连接到 4 台服务器的持久聊天服务器池的 80,000 并发用户总数。 运行持久聊天服务器的多台计算机应位于同一 Active Directory 域服务域 Skype 业务服务器和合规性服务。
  
下图显示了所有组件的多服务器拓扑与运行持久聊天服务器、 可选的合规性服务和单独合规性数据库的多台计算机。
  
**多服务器拓扑**

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多服务器拓扑提供了服务器池功能。 在服务器池中，持久聊天服务进行通信和共享数据。 例如，最初发布到一个持久聊天服务的聊天历史记录系统中是可从任何持久聊天服务。 通过一个持久聊天服务上载的文件可以访问由任何持久聊天服务。 用户可以连接到不同持久聊天服务器的前端服务器，并且可以相互通信。 端口的 TCP 8011 的默认将服务器连接至服务器池，并由持久聊天服务进行通信，或用于管理用途。
  
例如，在四台服务器持久聊天服务器部署中，其中 80,000 用户可以同时登录到持久聊天，负载均匀分布在每台服务器的 20,000 名用户。 如果一台服务器变得不可用，连接到该服务器的用户将失去对持久聊天服务器的访问。 断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。 
  

