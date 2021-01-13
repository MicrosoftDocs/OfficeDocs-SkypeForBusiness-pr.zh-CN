---
title: 规划持久聊天服务器拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825502"
---
# <a name="plan-persistent-chat-server-topology"></a>规划持久聊天服务器拓扑
 
**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。
  
持久聊天服务器支持单服务器和多服务器配置。 可以在 Skype for Business Server 2015 Enterprise Edition 或 Standard Edition Server 上安装持久聊天服务器。 

> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
  
## <a name="persistent-chat-server-components"></a>持久聊天服务器组件

持久聊天服务器由以下组件组成：
  
- 运行持久聊天服务器并提供以下服务的一台或多台计算机：
    
  - 持久聊天服务
    
  - 合规性服务，在启用合规性时打开
    
- 如果使用镜像 (一台或多台服务器) 则运行 SQL Server 后端数据库以承载存储聊天室内容、聊天室和类别的持久聊天内容数据库。
    
    > [!NOTE]
    > 后端数据库存储聊天历史记录数据，包括有关已创建的类别和持久聊天室的信息。 
  
- 如果启用了合规性，则一台或多台服务器 (一台或多台服务器（如果使用镜像) 则运行 SQL Server 后端数据库以承载持久聊天合规性数据库，其中存储了合规性事件和用于合规性的聊天内容。
    
有关持久聊天服务器的硬件和软件要求的详细信息，请参阅 [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 的服务器要求以及 Skype for Business Server [2015](hardware-and-software-requirements.md)中持久聊天服务器的硬件和软件要求。 
  
## <a name="persistent-chat-server-topologies"></a>持久聊天服务器拓扑

可以在单服务器或多服务器池中以及单池或多池拓扑中部署持久聊天服务器。 持久聊天服务器支持以下拓扑：
  
-  Standard Edition Server，其持久聊天服务器并位于前端服务器上
    
-  在单独的服务器上具有持久聊天服务器的 Standard Edition Server
    
-  在单独的服务器上具有单个持久聊天服务器的 Enterprise Edition Server
    
-  在单独的服务器上具有多个持久聊天服务器的 Enterprise Edition Server
    
尽管您可以在 Standard Edition Server 上部署持久聊天服务器，但请注意性能和规模将受到影响，并且高可用性不是一个选项。 因此，建议主要出于概念证明和评估目的在 Standard Edition Server 上部署持久聊天。 
  
Skype for Business Server 2015 支持各种并置方案，这样一来，如果您拥有小型组织)  (，您可以在一台服务器上运行多个组件，从而灵活节省硬件成本;如果组织规模较大，且需要可伸缩性和性能)  (则在不同服务器上运行各个组件。 在决定是否并集组件之前，应考虑可伸缩性因素。 Skype for Business Server 2015 Enterprise Edition 和 Standard Edition Server 的并置方案有所不同。 
  
以下各节更详细地介绍了拓扑，包括并置方案和后端数据库服务器的选项。 有关所有服务器角色和数据库并置的详细信息，请参阅[Topology Basics for Skype for Business Server 2015。](../../plan-your-deployment/topology-basics/topology-basics.md)
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server，其持久聊天服务器并位于前端服务器上

使用 Standard Edition，可以在前端服务器上并排持久聊天。 这是最简单和最基本的配置。 必须确保现有前端服务器在物理资源方面具有足够的容量：CPU、内存、磁盘空间等。
  
此外，如果在本地 SQL Server Express 后端服务器上启用了) ，您可以将持久聊天服务器后端服务器和持久聊天合规性数据库并 (。 还可以选择将单独的应用程序SQL Server专用实例。 
  
> [!IMPORTANT]
> 如果第一台持久聊天服务器与 Standard Edition 前端服务器并排，则不能向持久聊天服务器池添加其他服务器。 建议您将第一台服务器安装为独立实例，以便以后可以添加更多服务器（如果需要）。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>在单独的服务器上安装了持久聊天服务器的 Standard Edition Server

使用 Standard Edition，可以安装持久聊天服务器作为独立实例，并稍后根据需要添加更多服务器。 
  
如果在本地 (Express 后端服务器上启用了) ，您可以将持久聊天服务器后端服务器和持久SQL Server合规性数据库并SQL Server。 还可以选择将单独的应用程序SQL Server专用实例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server 与单个持久聊天服务器

使用 Enterprise Edition，必须在单独的计算机上安装持久聊天服务器。 也就是说，您无法在 Enterprise Edition 前端服务器上并排持久聊天服务器。 此部署需要运行持久聊天服务器和合规性服务（如果启用 (）的) 。
  
但是，可以将持久SQL Server数据库并放在 Enterprise Edition 前端池的后端数据库上。
  
> [!NOTE]
> 如果您计划将 AlwaysOn 可用性SQL用于 HA DR，请注意，持久聊天服务器数据库不支持此组。 
  
如果将持久聊天数据库与后端数据库并并，您可以对任意或所有数据库使用 SQL Server 的单个实例，也可以将单独的 SQL Server 实例用于每个数据库。
  
> [!IMPORTANT]
> 承载持久聊天数据库的服务器可以承载其他数据库。 但是，当您考虑将持久聊天数据库与其他数据库并并时，请注意，如果您存储多个用户的消息，则持久聊天数据库所需的磁盘空间可能会变得很大。 因此，建议不要将持久聊天数据库与后端数据库并并。 
  
下图显示了启用了合规性的单个持久聊天服务器拓扑的所有组件 (可选) 。
  
**单服务器拓扑**

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>具有多台持久聊天服务器的 Enterprise Edition Server

使用 Enterprise Edition，可以部署多服务器拓扑，以提升容量和可靠性。 多服务器拓扑与单服务器拓扑相同，但多个服务器承载持久聊天服务器，并且可以扩展得更高。 多服务器拓扑可以包含多达四台运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许使用八台，但只有四台处于活动状态，其余四台处于备用状态) 。 每台服务器可支持 20，000 个并发用户，总共支持 80，000 个并发用户连接到具有 4 台服务器的持久聊天服务器池。 运行持久聊天服务器的多台计算机应驻留在与 Skype for Business Server 和合规性服务相同的 Active Directory 域服务域中。
  
下图显示了多服务器拓扑的所有组件，该拓扑具有多台运行持久聊天服务器的计算机、可选的合规性服务和单独的合规性数据库。
  
**多服务器拓扑**

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多服务器拓扑提供了服务器池功能。 在服务器池中，持久聊天服务通信和共享数据。 例如，最初张贴到一个持久聊天服务的聊天历史记录可从系统的任何持久聊天服务获得。 任何持久聊天服务都可以访问通过一个持久聊天服务上载的文件。 用户可以连接到不同的持久聊天服务器前端服务器，并可以相互通信。 TCP 8011 的默认端口将服务器连接到服务器池，持久聊天服务将其用于相互通信或用于管理目的。
  
例如，在一个四台服务器的持久聊天服务器部署中（其中 80，000 个用户可以同时登录持久聊天）中，负载平均分布为每台服务器 20，000 个用户。 如果一台服务器不可用，连接到该服务器的用户将失去对持久聊天服务器的访问权限。 断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。 
  

