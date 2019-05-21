---
title: 规划持久聊天服务器拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '摘要: 阅读本主题, 了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。'
ms.openlocfilehash: edbc0184efe19e662c9ce8933b47c32f7e6fdd1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297083"
---
# <a name="plan-persistent-chat-server-topology"></a>规划持久聊天服务器拓扑
 
**摘要:** 阅读本主题, 了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。
  
持久聊天服务器支持单服务器和多服务器配置。 你可以在 Skype for Business Server 2015 Enterprise Edition 或 Standard Edition 服务器上安装持久聊天服务器。 

> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 
  
## <a name="persistent-chat-server-components"></a>持久聊天服务器组件

持久聊天服务器由以下组件组成：
  
- 运行持久聊天服务器并提供以下服务的一个或多个计算机:
    
  - 持久聊天服务
    
  - 合规性服务，在启用合规性时打开
    
- 一个或多个服务器 (如果使用镜像, 则使用多个) 运行 SQL Server 后端数据库以托管持久聊天内容数据库, 其中存储了聊天室内容、会议室和类别。
    
    > [!NOTE]
    > 后端数据库存储聊天历史记录数据, 包括有关已创建的类别和持续聊天室的信息。 
  
- 如果启用合规性, 则一个或多个服务器 (如果使用了镜像) 运行 SQL Server 后端数据库, 以托管持久的聊天合规性数据库, 其中存储了合规性事件和用于实现合规性的聊天内容。
    
有关持久聊天服务器的硬件和软件要求的详细信息, 请参阅 skype for business server [2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[Skype for business Server 2015 中持久聊天服务器的硬件和软件要求](hardware-and-software-requirements.md)。 
  
## <a name="persistent-chat-server-topologies"></a>持久聊天服务器拓扑

你可以在单服务器或多服务器池中部署持久聊天服务器, 并通过单个池或多池拓扑进行部署。 持久聊天服务器支持下列拓扑:
  
-  Standard Edition Server 与持久聊天服务器并置在前端服务器上
    
-  单独服务器上具有持久聊天服务器的标准版服务器
    
-  企业版服务器, 在单独的服务器上使用单个持久聊天服务器
    
-  不同服务器上有多个持久聊天服务器的企业版服务器
    
虽然你可以在标准版服务器上部署持久聊天服务器, 但请注意性能和规模将受到影响, 并且不能选择高可用性。 因此, 建议在标准版服务器上部署持久聊天, 主要用于概念和评估目的。 
  
Skype for Business Server 2015 支持各种 collocation 方案, 让你可以通过在一台服务器 (如果有一个小型组织) 上运行多个组件来灵活地保存硬件成本, 或在不同服务器上运行单个组件 (如果您有一个需要可伸缩性和性能的大型组织。 在决定是否 collocate 组件之前, 应考虑可伸缩性因素。 Collocation 方案不同于 Skype for business Server 2015 Enterprise Edition 和 Standard Edition 服务器。 
  
以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。 有关所有服务器角色和数据库的 collocation 的详细信息, 请参阅[Skype for Business server 2015 的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server 与持久聊天服务器并置在前端服务器上

使用 Standard Edition，可以将持久聊天并置在前端服务器上。 这是最简单也最基本的配置。 您必须确保现有前端服务器在物理资源方面具有足够的容量: CPU、内存、磁盘空间等。
  
此外, 你可以在本地 SQL Server Express 后端服务器上 collocate 持久聊天服务器后端服务器和持久聊天合规性数据库 (如果已启用)。 还可以选择使用独立的 SQL Server 及专用实例。 
  
> [!IMPORTANT]
> 如果第一个持久聊天服务器与标准版前端服务器 collocated, 则不能将其他服务器添加到持久聊天服务器池中。 建议你将第一台服务器安装为独立实例, 以便你可以在以后添加更多服务器 (如果需要)。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition Server 与持久聊天服务器安装在不同的服务器上

使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。   
  
你可以在本地 SQL Server Express 后端服务器上 collocate 持久聊天服务器后端服务器和持久聊天合规性数据库 (如果已启用)。 还可以选择使用独立的 SQL Server 及专用实例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server 与一个持久聊天服务器

使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。 也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。 此部署需要运行持久聊天服务器和合规性服务 (如果已启用) 的单独服务器。
  
但是, 你可以为企业版前端池的后端数据库上的持久聊天服务器 collocate SQL Server 数据库。
  
> [!NOTE]
> 如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。 
  
如果你将持久聊天数据库与后端数据库 collocate, 则可以对任何或所有数据库使用一个 SQL Server 实例, 也可以为每个数据库使用单独的 SQL Server 实例。
  
> [!IMPORTANT]
> 托管持久聊天数据库的服务器可以托管其他数据库。 但是, 当你考虑将持久聊天数据库与其他数据库一起使用时, 请注意, 如果你存储的消息超过了几个用户, 则持久聊天数据库所需的磁盘空间会变得非常大。 因此, 我们不建议将持久聊天数据库与后端数据库 collocating。 
  
下图显示了一个已启用合规性的单个持久聊天服务器的拓扑的所有组件 (可选)。
  
**单服务器拓扑**

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition Server 与多个持久聊天服务器

使用企业版, 你可以部署多服务器拓扑, 以获得更大的容量和可靠性。 多服务器拓扑与单服务器拓扑相同, 不同之处在于多台服务器托管持久聊天服务器, 并且可以更高的比例。 多服务器拓扑可以包括多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许八个, 但只有四个可以激活, 并且其余四个处于待机状态)。 每台服务器可支持多达20000并行用户, 总共可支持连接到具有4台服务器的持久聊天服务器池的80000个并发用户。 运行持久聊天服务器的多台计算机应位于与 Skype for Business 服务器和合规性服务相同的 Active Directory 域服务域中。
  
下图显示多服务器拓扑的所有组件, 其中包含运行持久聊天服务器的多台计算机、可选合规性服务和单独的合规性数据库。
  
**多服务器拓扑**

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多服务器拓扑提供了服务器池功能。 在服务器池中, 持久聊天服务与数据进行通信和共享。 例如, 您可以从系统中的任何持续聊天服务获取最初发布到一个持久聊天服务的聊天历史记录。 通过一个持久聊天服务上载的文件可由任何永久聊天服务访问。 用户可以连接到不同的持久聊天服务器前端服务器, 并且可以相互进行通信。 TCP 8011 的默认端口将服务器连接到服务器池, 并由持久聊天服务用于自身通信, 或用于管理用途。
  
例如, 在四台服务器持久聊天服务器部署 (其中80000用户可以同时登录到持久聊天) 中, 每个服务器的20000用户均会平均分配负载。 如果一台服务器不可用, 连接到该服务器的用户将失去其永久聊天服务器的访问权限。 断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。 
  

