---
title: 在 Skype for Business Server 2015 中规划存档
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 摘要： 阅读本主题，以了解如何为存档在 Skype 业务服务器 2015年计划。
ms.openlocfilehash: 53895a404c2502a0d54553fda979add6031b09f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-archiving-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划存档
 
**摘要：**阅读本主题，以了解如何为存档在 Skype 业务服务器 2015年计划。
  
公司和其他组织需要服从数量不断增多的行业规定和政府法规，这些规定和法规要求保留特定类型的通信。 如果您的组织都有这种要求，可以使用存档业务服务器 2015年的 Skype 的存档即时消息 (IM) 和会议 （会议） 的通信来帮助支持法规遵从性要求的一部分。
  
## <a name="archiving-components"></a>存档组件

Skype 业务服务器使用存档的下列组件：
  
- **存档代理**。 将在每个 Enterprise Edition 前端池和 Standard Edition 服务器上自动安装和激活存档代理（也称为“统一数据收集代理”）。 尽管会自动激活存档代理，但实际上并不捕获任何消息，除非启用存档并正确配置存档。 默认将禁用存档功能。
    
- **存档数据存储**。 业务服务器 2015年的 Skype 的数据存储可以作为 Skype 实现对于业务服务器的 SQL Server 数据库，或者，如果您的 Exchange 部署集成与 Exchange 存储。 
    
存档还需要文件存储，但是存档使用与前端服务器或 Standard Edition 服务器相同的文件存储。
  
针对归档的硬件和软件要求的列表，请参阅[存档业务服务器 2015年的 Skype 在硬件和软件要求](hardware-and-software-requirements.md)。
  
## <a name="determine-your-organizations-requirements-for-archiving"></a>确定组织的存档要求

若要实现存档，您需要决定如何满足您的组织要求存档通过确定以下：
  
- **要使用哪种存储选项**。 您可以通过以下两种方式之一或将两者相结合来实施存储：
    
  - **Exchange 存储。** 如果您的 Exchange 部署，您可以将 Skype 集成业务服务器和 Exchange 归档以便您 Skype 业务服务器和 Exchange 存档数据都存储在一起在 Exchange。 如果您启用 Microsoft Exchange 集成选项，用户邮箱驻留 Exchange 存储已存档数据，但仅当邮箱已放上适当地存放在 Exchange Server 使用。 默认情况下，不启用 Microsoft Exchange 集成。
    
  - **Skype 的业务服务器的存储。** 如果有谁没有驻留在 Exchange 或谁没有放在原位保存，其邮箱的用户，或不想为您的部署中的任何或所有用户使用 Microsoft Exchange 集成，您可以使用业务服务器存档数据库的部署 Skype SQL 服务器。
    
- **何时部署存档**。 可以部署归档您初始 Skype 业务服务器部署的一部分，也可以将其添加到现有部署。 若要使用 Skype 业务服务器存档存储 （SQL Server 数据库），您使用拓扑生成器来将数据库添加到您的拓扑结构，然后再次发布拓扑。 如果您的所有用户都驻留在 Exchange 上并适当地存放在放有自己的邮箱，您不需要更新您的拓扑结构，但只需启用 Microsoft Exchange 在 Exchange 存储已存档的数据的集成。 
    
- **组织中的哪些站点和用户需要存档**。 您的整个组织，而且也为特定的站点、 池、 用户和用户组，您可以配置存档设置。
    
- **应存档哪些内容**。无论是在全局级别还是为其中每个级别的特定站点和用户指定存档，您都要指定是否启用以下类型的内容： 
    
  - 对等即时消息
    
  - 多方即时消息的会议
    
  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）
    
  - 会议期间共享的白板和投票
    
- **不能存档哪些内容**。 不能存档以下类型的内容： 
    
  - 对等文件传输
    
  - 对等即时消息和会议的音频/视频
    
  - 对等即时消息和会议的桌面和应用程序共享
    
    Skype 业务服务器也不会存档持久聊天对话。 持久聊天会话存档，您必须启用并配置的法规遵从性服务，这是可以持久的聊天服务器部署的组件。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。
    
- **存档材料应保留多长时间**。 存档数据库不适合长期保留，和 Skype 业务服务器不提供电子邮件发现 （搜索） 解决方案的已存档数据，因此数据需要移动到其他存储。 Skype 业务服务器提供可用于导出存档的数据，并创建可搜索的归档数据记录会话导出工具。 
    
     对于全球的政策，以及您创建的每个网站和用户的策略，您可以指定何时清除存档和导出数据。 有关清除数据的详细信息，请参阅[管理中业务服务器 2015年的 Skype 的已存档数据的清除](../../manage/archiving/purging-of-archived-data.md)。 有关使用该会话详细信息导出工具，请参阅[导出存档的数据业务服务器 2015年的 Skype](../../manage/archiving/export-archived-data.md)。
    
- **存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。
    
    > [!NOTE]
    > 控制内部或外部通信存档功能仅适用于 Skype 业务策略。 对于交换集成存档，内部和外部通信归档或不存档。 
  
- **是否实施关键模式**。 如果存档是为您的组织的要求，配置关键模式将阻止在业务服务器故障，将导致无法存档的 Skype 的 IM 和会议会话。 例如： 
    
  - 为业务服务器存储服务 Skype 有问题。 在此情况下，为启用存档的用户阻止 IM。
    
  - 文件共享不可用或存储服务出现问题。在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>选择存档部署和配置选项

部署每台前端服务器时将自动在该服务器上安装存档，但存档在您配置之前不会启用。 配置存档的方式由存档的部署方式决定。 您可以通过以下其中一种方式来部署存档：
  
- 使用 Microsoft Exchange 存储
    
- 使用 Skype 业务服务器的存储
    
> [!NOTE]
> 如果实施这两种 Skype 业务服务器存档数据库并启用 Microsoft Exchange 集成，交换策略替代 Skype 业务服务器归档策略，但只能用于驻留在 Exchange 和拥有自己的邮箱的用户放就地封存。 企业存档的 Skype 取决于 Microsoft Exchange 就地保存策略。 
  
如果您部署一个前端池或标准版服务器存档，则应部署中其他所有的前端池和标准版服务器启用它。 如果承载该对话或会议的池上没有启用存档，则可能无法存档所有会议数据。 存档对于 IM 消息仍然有效，但可能无法存档会议内容和事件。
  
> [!NOTE]
> 若要启用委派管理任务的同时维护您组织的安全标准，Skype 业务服务器使用基于角色的访问控制 (RBAC)。 利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。 要配置 Skype 业务归档策略和配置，用户必须分配到 CsArchivingAdministrator 角色 (除非配置完成存档部署的位置，而不是远程服务器上直接从另一台计算机). 列表中的用户权限，权限和角色所需的归档部署，请参阅[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)。 
  
> [!NOTE]
> 如果您使用 Microsoft Exchange 集成，交换策略的配置要求相应的管理员权利和权限。 有关详细信息，请参阅 Exchange 文档。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储

 如果您选择 Microsoft Exchange 集成，使用交换策略及配置来控制业务服务器的存档 Skype。 您可以在全局级别、 站点级别和池级配置 Microsoft Exchange 集成选项。 如果您的部署中包含多个目录林，必须同步业务服务器的 Skype 和交换之间的设置。 您需要确定：
  
- 是否存档 IM、会议或二者
    
- 是否实现关键模式下，会阻止 IM 和会议会话在 Skype 业务服务器失败 
    
- 选择要用于存储存档数据的交换 Microsoft Exchange 集成选项
    
有关如何配置 Exchange 就地保存策略和设置以支持存档的信息，请参阅 Exchange 产品文档。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server 存储

如果您选择 Skype 业务服务器存储，使用 Skype 业务服务器归档策略和配置来控制如何存档启用和实现。 Skype 业务服务器存储使用 SQL Server 数据库中，因此您将需要将相应的 SQL Server 数据库添加到您的拓扑结构，然后配置您的存档策略。 
  
### <a name="add-storage-databases-to-your-topology"></a>向拓扑添加存储数据库

时将 SQL Server 存储数据库添加到您的拓扑结构，您可以选择配置存档数据库具有下列任一：
  
- 监控数据库
    
- 企业版前端池的后端数据库
    
> [!NOTE]
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。 
  
如果布置与监视数据库、 后端数据库，或两个数据库存档数据库时，您可以使用单个的 SQL 实例的任何一个或所有数据库，或者可以使用一个单独的 SQL 实例的每个数据库中，使用以下限制： 每个 SQL 实例只能包含单个后端数据库、 一个监视数据库和一个存档数据库。
  
所有服务器角色和数据库的配置的详细信息，请参阅[拓扑业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。 更新您的拓扑结构，包括存储数据库的详细信息，请参阅[创建并发布新的拓扑结构在 Skype 业务服务器 2015年](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>确定存档选项和用户策略

您需要确定：
  
- 是否启用或禁用内部和外部通信存档
    
- 是否存档 IM、会议或二者
    
- 是否实现关键模式下，会阻止 IM 和会议会话在 Skype 业务服务器失败 
    
- 是否为特定用户和组启用策略
    
Skype 业务服务器归档选项可以指定在以下层面。 
  
- **全局级别选项**。 这是默认存档配置，适用于您的整个部署。 它创建业务服务器部署 Skype 时，默认情况下，禁用的内部和外部通信存档。 您无法删除此选项。 如果您选择删除选项，那么全局选项将重置为默认设置。
    
- **站点级别选项**。您可以通过为一个或多个特定站点创建和配置站点级别存档选项，来对该站点启用或禁用存档。您可以删除任何您所创建的站点级别存档选项。站点级别存档选项会覆盖全局选项，但仅针对选项中指定的站点。 
    
    例如，如果在全局配置中对内部和外部通信启用存档，并创建了一个为外部通信禁用存档的站点配置，则将为该站点仅存档内部通信。另外，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点配置，那么仅会为该站点存档会议，而不会为组织的其他站点存档会议。
    
- **池级别选项**。您可以通过为单个池创建和配置池级别配置来为一个或多个特定池指定存档设置。池级别存档配置仅在您创建它后才会存在。您可以修改或删除任何池级别存档配置。池级别存档配置会覆盖全局配置和您可能已创建的任何站点存档配置。 
    
    例如，假设您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点级别配置，然后创建了一个仅为 IM 启用存档的池级别配置。 将为该站点的所有用户存档 IM 和会议通信，但是不包括那些驻留在池级别配置中指定的池中的用户。 对于您组织中的所有其他用户，仅针对 IM 启用存档。
    
- **用户存档策略**。您可以通过为一个或多个指定用户和用户组创建、配置和应用用户级别存档策略，来为这些特定用户和用户组启用或禁用存档。您可以删除任何您所创建的用户级别存档策略，并且可以更改应用存档策略的用户和用户组。用户级别存档策略会覆盖全局策略和任何站点策略，但仅针对应用策略的用户和用户组。 
    
    例如，如果在全局配置中对内部和外部通信禁用存档，并创建了一个对内部和外部通信启用存档的站点级别策略，然后创建了一个对外部通信禁用存档的用户级别策略。 那么将为所有站点用户存档外部和内部通信，但是不包括那些应用了用户级别策略的用户，将仅为这些用户存档内部通信。
    
有关如何部署归档时设置初始的存档配置的详细信息，请参阅[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)。 有关存档在部署后管理的详细信息，请参阅[管理存档业务服务器 2015年的 Skype](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>存档配置工具

 您可以通过 Skype 业务服务器控件面板控制大多数存档选项。 但是，有几个选项仅通过 Skype 业务服务器管理程序。 这些选项包括存档重复消息和导出存档数据。 有关使用 Skype 业务服务器的控制面板和 Skype 的业务服务器管理外壳程序来管理存档策略的详细信息，请参阅[管理业务服务器 2015年的 Skype 在存档](../../manage/archiving/archiving.md)。
  
## <a name="access-archived-data"></a>访问存档数据

存档数据的访问取决于数据的存储位置： 
  
- **Microsoft Exchange 存储**。 如果您选择的交换集成选项，Skype 业务服务器的所有用户谁驻留在 Exchange，并曾放在原位保存其邮箱的 Exchange 存储中中放归档的内容。 存档的数据存储在用户的邮箱恢复项文件夹，通常看不到用户，且具有 Exchange**发现管理**角色的用户可以只搜索。 交换可使联合的搜索和发现，以及 SharePoint，如果它部署。 有关存储、 保留和存储在 Exchange 数据的查询的详细信息，请参阅 Exchange 和 SharePoint 文档。
    
- **Skype 业务服务器存档存储**。 如果您设置了 Skype 业务服务器存档数据库，不存档内容业务服务器存档数据库的任何用户的 Skype 业务服务器存款的 Skype 驻留在 Exchange 中，并没有放在原位保存其邮箱。 虽然此数据是不可搜索的，但可以采用可通过其他工具搜索的格式导出此数据。 导出存档数据库中存储的数据的详细信息，请参阅[导出存档的数据业务服务器 2015年的 Skype](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>有关详细信息

有关存档的详细信息，请参阅下列主题：
  
- [部署存档为 Skype 业务服务器 2015](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [管理存档在 Skype 业务服务器 2015](../../manage/archiving/archiving.md)
    
有关更多详细介绍 Skype 业务服务器和 Exchange 一起使用，请参阅[计划集成 Skype 业务和交换](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  

