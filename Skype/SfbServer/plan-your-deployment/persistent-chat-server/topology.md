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
description: 摘要： 阅读本主题，以学习业务服务器 2015年有关持久聊天服务器组件和 Skype 的拓扑。
ms.openlocfilehash: 11d12283c3ee302c8133b0a56bbea53315508aec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-persistent-chat-server-topology"></a>规划持久聊天服务器拓扑
 
**摘要：**阅读本主题，以学习业务服务器 2015年有关持久聊天服务器组件和 Skype 的拓扑。
  
持久的聊天服务器支持单服务器和多服务器配置。 业务服务器 2015年企业版或标准版服务器，您可以安装在任何一个 Skype 上持久聊天服务器。 
  
## <a name="persistent-chat-server-components"></a>持久的聊天服务器组件

持久聊天服务器由以下组件组成：
  
- 一个或多个计算机运行持续聊天服务器并提供以下服务：
    
  - 持久的聊天服务
    
  - 合规性服务，在启用合规性时打开
    
- 一个或多个服务器 （一个以上如果使用了镜像） 运行持续聊天内容数据库所在的 SQL Server 后端数据库存储聊天室内容、 房间和类别。
    
    > [!NOTE]
    > 后端数据库存储聊天历史数据，包括有关信息类别和创建持久性聊天室。 
  
- 如果启用了法规遵从性，（一个以上如果使用了镜像） 的一个或多个服务器运行 SQL Server 的后端数据库承载持久聊天法规数据库，出于法规遵从目的符合性事件和聊天的内容位置存储。
    
持久的聊天服务器的硬件和软件要求的详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[业务服务器 2015年的 Skype 的持久聊天服务器的硬件和软件要求](hardware-and-software-requirements.md)。 
  
## <a name="persistent-chat-server-topologies"></a>持久的聊天服务器拓扑

您可以部署持续聊天服务器单个服务器或多服务器池，再加上单池或多个池的拓扑结构。 持久的聊天服务器支持下列拓扑：
  
-  Standard Edition Server 与持久聊天服务器并置在前端服务器上
    
-  标准版服务器与持久聊天服务器不同的服务器上
    
-  企业版服务器与一个持久聊天服务器不同的服务器上
    
-  企业版服务器与多个持久聊天服务器不同的服务器上
    
虽然您可以部署在标准版服务器的持久性聊天服务器，请注意，会影响性能和可扩展性，高可用性不是一个选项。 因此，建议您将部署在主要的概念和评估目的的证明标准版服务器持续聊天。 
  
Skype 的业务服务器 2015年支持多种配置方案，为您提供的灵活性来节约硬件成本由多个组件运行在一个服务器上 （如果您有一个小的组织），或不同的服务器 （运行单个组件如果您有一个较大的组织所需要的可扩展性和性能）。 在决定是否布置组件之前，应考虑可伸缩性因素。 Skype 业务服务器 2015年企业版和标准版服务器的不同配置方案。 
  
以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。 所有服务器角色和数据库的配置的详细信息，请参阅[拓扑业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server 与持久聊天服务器并置在前端服务器上

使用 Standard Edition，可以将持久聊天并置在前端服务器上。 这是最简单也最基本的配置。 您必须确保现有前端服务器具有足够的容量的物理资源： CPU、 内存、 磁盘空间等等。
  
此外，您可以配置持久聊天服务器后端服务器和持久聊天的法规遵从性数据库 （如果已启用） 本地 SQL Server Express 后端服务器上。 还可以选择使用独立的 SQL Server 及专用实例。 
  
> [!IMPORTANT]
> 如果第一个持久聊天服务器搭配使用标准版前端服务器，不能到持久聊天服务器池添加其他服务器。 建议您安装第一台服务器作为独立实例，以便您可以添加更多服务器以后，如果需要。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition Server 与持久聊天服务器安装在不同的服务器上

使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。   
  
您可以配置持久聊天服务器后端服务器和持久聊天的法规遵从性数据库 （如果已启用） 本地 SQL Server Express 后端服务器上。 还可以选择使用独立的 SQL Server 及专用实例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server 与一个持久聊天服务器

使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。 也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。 此部署需要一个单独的服务器，它运行持续聊天服务器和法规遵从性服务 （如果已启用）。
  
但是，可以前端企业版池的后端数据库上为持久聊天服务器布置的 SQL Server 数据库。
  
> [!NOTE]
> 如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。 
  
如果布置的持久聊天数据库后端数据库，您可以任意或所有数据库，都使用 SQL Server 的单个实例或您可以为每个数据库都使用一个单独的 SQL Server 实例。
  
> [!IMPORTANT]
> 持续聊天数据库所在的服务器可以承载其他数据库。 但是，考虑配置持久聊天数据库与其他数据库时，会意识到，如果有存储的多个用户的邮件时，磁盘空间需要持久聊天数据库可以变得非常大。 由于这个原因，我们不建议配置的持久聊天数据库后端数据库。 
  
下图显示了一个拓扑中的所有组件单个持久聊天服务器启用的法规 （可选）。
  
**单服务器拓扑**

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition Server 与多个持久聊天服务器

使用企业版，您可以部署一个多服务器拓扑结构为更高容量和可靠性。 一个多服务器拓扑结构相同的单服务器拓扑只是多个服务器维护持久聊天服务器，并且可扩展性更高。 多服务器拓扑结构可以包含多达四个活动的计算机运行持续聊天服务器 （高可用性和灾难恢复配置将允许多达 8 个，但只有四个可以主动和剩余的四个待机状态）。 每个服务器可以支持多达 20000 个并发用户，总共为 80000 并发用户连接到 4 服务器的持久性聊天服务器池。 多台计算机运行持续聊天服务器应位于 Skype 与位于同一 Active Directory 域服务域业务服务器和法规遵从性服务。
  
下图显示所有组件的多服务器拓扑结构与多台计算机运行持续聊天服务器、 可选的法规遵从性服务和一个单独的法规遵从性数据库。
  
**多服务器拓扑结构**

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多服务器拓扑提供了服务器池功能。 池中服务器持续聊天服务进行通讯和共享数据。 例如，最初过帐到一个持久的聊天服务的聊天历史提供了任何持久聊天服务系统中。 通过一个持久聊天服务上载的文件的可由任何持久聊天服务。 用户可以连接到不同持久聊天服务器前端服务器，可以彼此通信。 默认端口的 TCP 8011 将服务器连接到服务器池，并持续聊天服务用于通信之间本身，或出于管理的目的。
  
例如，在四台服务器持续聊天服务器中部署，80000 用户可以同时登录并使用持久聊天，负载均匀分布在每个服务器的 20000 个用户。 如果一台服务器变得不可用，连接到该服务器的用户将无法持久聊天服务器的访问。 断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。 
  

