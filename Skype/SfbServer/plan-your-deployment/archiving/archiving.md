---
title: 规划存档中 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 摘要： 阅读本主题可了解如何规划适用于业务 Server archiving Skype 中。
ms.openlocfilehash: 164a3207153986e788a7db47b86014063e37e0e5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236114"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>规划存档中 Skype 业务服务器
 
**摘要：** 阅读本主题可了解如何规划适用于业务 Server archiving Skype 中。
  
公司和其他组织需要服从数量不断增多的行业规定和政府法规，这些规定和法规要求保留特定类型的通信。 如果您的组织具有此类要求，可以使用存档 Skype 业务服务器进行存档即时消息 (IM) 和会议通信，以帮助支持某些合规性要求。
  
## <a name="archiving-components"></a>存档组件

Skype 业务服务器使用以下存档组件：
  
- **存档代理**。 将在每个 Enterprise Edition 前端池和 Standard Edition 服务器上自动安装和激活存档代理（也称为“统一数据收集代理”）。 尽管会自动激活存档代理，但实际上并不捕获任何消息，除非启用存档并正确配置存档。 默认将禁用存档功能。
    
- **存档数据存储**。 Skype 业务服务器的数据存储可以作为 Skype 实现业务 Server SQL Server 数据库，或者，如果 Exchange 部署，与 Exchange 存储的集成。 
    
存档还需要文件存储，但是存档使用与前端服务器或 Standard Edition 服务器相同的文件存储。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>确定组织的存档要求

若要实现存档，您需要决定如何满足组织的存档通过确定以下要求：
  
- **要使用哪种存储选项**。 您可以通过以下两种方式之一或将两者相结合来实施存储：
    
  - **Exchange 存储。** 如果您具有 Exchange 部署，您可以 Business Server 和 Exchange 存档集成 Skype，以便在 Exchange 一起存储您 Skype Business Server 和 Exchange 存档数据。 如果您启用 Microsoft Exchange 集成选项，用户邮箱驻留 Exchange 存储的存档数据，但仅当邮箱已被置于就地保留在 Exchange 服务器使用。 默认情况下不启用 Microsoft Exchange 集成。
    
  - **业务服务器存储的 Skype。** 如果有的用户未驻留在 Exchange 或没有其邮箱置于就地保留，或如果您不想要用于部署中的任何或所有用户的 Microsoft Exchange 集成，您可以使用的业务 Server 存档数据库部署 Skype SQL 服务器。
    
- **何时部署存档**。 可以部署存档对于业务服务器部署，您初始 Skype 的一部分，也可以将其添加到现有部署。 若要使用 Skype 业务服务器存档存储 （SQL Server 数据库），您使用拓扑生成器将数据库添加到拓扑中，然后再次发布该拓扑。 如果您的所有用户都驻留在 Exchange 上并具有其邮箱置于就地保留，您无需更新您的拓扑，但只需启用 Microsoft Exchange 集成，以在 Exchange 存储存档的数据。 
    
- **组织中的哪些站点和用户需要存档**。 为整个组织和 （可选） 为特定站点、 池、 用户和用户组，您可以配置存档设置。
    
- **应存档哪些内容**。无论是在全局级别还是为其中每个级别的特定站点和用户指定存档，您都要指定是否启用以下类型的内容： 
    
  - 对等即时消息
    
  - 多方即时消息的会议
    
  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）
    
  - 会议期间共享的白板和投票
    
- **不能存档哪些内容**。 不能存档以下类型的内容： 
    
  - 对等文件传输
    
  - 对等即时消息和会议的音频/视频
    
  - 对等即时消息和会议的桌面和应用程序共享
    
    Skype 业务服务器也不会存档持久聊天的对话。 若要将持久聊天会话的存档，必须启用并配置合规性服务，它是一个可与持久聊天服务器部署的组件。 有关详细信息，请参阅[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

    > [!NOTE] 
    > 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
    
- **存档材料应保留多长时间**。 存档数据库不是以进行长期保留和 Skype 业务服务器不提供电子发现 （搜索） 解决方案的存档数据，因此需要移动到其他存储的数据。 Skype 业务服务器还提供一个会话导出工具可用来导出存档的数据，以及其创建的存档数据的可搜索脚本。 
    
     对于全局策略，以及您创建的每个站点和用户策略，您可以指定何时清除存档和导出数据。 有关清除数据的详细信息，请参阅[管理 Skype 业务服务器中的存档数据的清除](../../manage/archiving/purging-of-archived-data.md)。 有关使用该会话的详细信息导出工具，请参阅[导出 Skype 业务服务器中的存档的数据](../../manage/archiving/export-archived-data.md)。
    
- **存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。
    
    > [!NOTE]
    > 控制内部或外部通信的存档功能仅适用于业务策略的 Skype。 Exchange 集成存档，内部和外部通信存档，或者不存档。 
  
- **是否实施关键模式**。 如果存档是组织的要求，配置临界模式将阻止发生业务服务器故障会阻止存档的 Skype 的 IM 和会议会话。 例如： 
    
  - 为业务服务器存储服务 Skype 有问题。 在此情况下，为启用存档的用户阻止 IM。
    
  - 文件共享不可用或存储服务出现问题。在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>选择存档部署和配置选项

部署每台前端服务器时将自动在该服务器上安装存档，但存档在您配置之前不会启用。 配置存档的方式由存档的部署方式决定。 您可以通过以下其中一种方式来部署存档：
  
- 使用 Microsoft Exchange 存储
    
- 使用 Skype Business Server 存储
    
> [!NOTE]
> 如果您实现两个 Skype 业务 Server 存档数据库，并启用 Microsoft Exchange 集成，Exchange 策略业务服务器存档策略，会覆盖 Skype，而只为驻留在 Exchange 和过其邮箱的用户置于就地保留。 Skype 业务存档取决于在 Microsoft Exchange 就地保留策略。 
  
如果您部署存档一个前端池或 Standard Edition Server，则应在部署中的所有其他前端池和 Standard Edition 服务器启用它。 如果承载该对话或会议的池上没有启用存档，则可能无法存档所有会议数据。 存档对于 IM 消息仍然有效，但可能无法存档会议内容和事件。
  
> [!NOTE]
> 若要启用委派管理任务的同时维护组织的安全标准，Skype 业务服务器，请使用基于角色的访问控制 (RBAC)。 利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。 若要配置业务存档策略和配置 Skype，用户必须分配给 CsArchivingAdministrator 角色 (除非直接在存档部署的位置，而不是远程服务器上完成配置从另一台计算机). 有关用户权限的列表，权限和角色所需的存档部署，请参阅[部署存档 Skype 业务服务器](../../deploy/deploy-archiving/deploy-archiving.md)。 
  
> [!NOTE]
> 如果您使用 Microsoft Exchange 集成，Exchange 策略的配置需要相应的管理员权限。 有关详细信息，请参阅 Exchange 文档。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储

 如果您选择 Microsoft Exchange 集成，使用 Exchange 策略和配置来控制适用于业务 Server archiving Skype。 您可以在全局级别、 站点级别和池级别配置的 Microsoft Exchange 集成选项。 如果您的部署包括多个林，您必须同步 Skype 业务 server 和 Exchange 之间的设置。 您需要确定：
  
- 是否存档 IM、会议或二者
    
- 是否要实现关键模式下，阻止 IM 和会议会话时 Skype 业务服务器失败 
    
- 所选内容的 Exchange 用于存储存档数据的 Microsoft Exchange 集成选项
    
有关如何配置 Exchange 就地保留策略和设置以支持存档的信息，请参阅 Exchange 产品文档。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server 存储

如果您选择 Skype 业务服务器存储的您使用 Skype Business Server 存档策略和配置来控制如何存档启用并实现。 业务服务器存储的 Skype 使用 SQL Server 数据库，因此您需要将相应的 SQL Server 数据库添加到拓扑中，然后配置存档策略。 
  
### <a name="add-storage-databases-to-your-topology"></a>向拓扑添加存储数据库

时将 SQL Server 存储数据库添加到您的拓扑，您可以选择将使用以下任一存档数据库并置：
  
- 监控数据库
    
- 企业版前端池的后端数据库
    
> [!NOTE]
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。 
  
如果将存档数据库与监控数据库、 后端数据库，或两个数据库并置，您可以使用单一的 SQL 实例的任意或全部数据库，也可以为每个数据库，替换为以下使用一个单独的 SQL 实例限制： 仅限单个后端数据库、 一个监控数据库和一个存档数据库可以包含每个 SQL 实例。
  
有关所有服务器角色和数据库并置的详细信息，请参阅[拓扑的 Skype 业务服务器的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。 有关更新您的拓扑，以包括存储数据库的详细信息，请参阅[创建和发布新拓扑中 Skype 业务服务器](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>确定存档选项和用户策略

您需要确定：
  
- 是否启用或禁用内部和外部通信存档
    
- 是否存档 IM、会议或二者
    
- 是否要实现关键模式下，阻止 IM 和会议会话时 Skype 业务服务器失败 
    
- 是否为特定用户和组启用策略
    
可以在以下级别指定 Skype 业务 Server 存档选项。 
  
- **全局级别选项**。 这是默认存档配置，适用于您的整个部署。 为业务 Server 部署 Skype 时创建及其，默认情况下禁用内部和外部通信的存档。 您无法删除此选项。 如果您选择删除选项，那么全局选项将重置为默认设置。
    
- **站点级别选项**。您可以通过为一个或多个特定站点创建和配置站点级别存档选项，来对该站点启用或禁用存档。您可以删除任何您所创建的站点级别存档选项。站点级别存档选项会覆盖全局选项，但仅针对选项中指定的站点。 
    
    例如，如果在全局配置中对内部和外部通信启用存档，并创建了一个为外部通信禁用存档的站点配置，则将为该站点仅存档内部通信。另外，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点配置，那么仅会为该站点存档会议，而不会为组织的其他站点存档会议。
    
- **池级别选项**。您可以通过为单个池创建和配置池级别配置来为一个或多个特定池指定存档设置。池级别存档配置仅在您创建它后才会存在。您可以修改或删除任何池级别存档配置。池级别存档配置会覆盖全局配置和您可能已创建的任何站点存档配置。 
    
    例如，假设您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点级别配置，然后创建了一个仅为 IM 启用存档的池级别配置。 将为该站点的所有用户存档 IM 和会议通信，但是不包括那些驻留在池级别配置中指定的池中的用户。 对于您组织中的所有其他用户，仅针对 IM 启用存档。
    
- **用户存档策略**。您可以通过为一个或多个指定用户和用户组创建、配置和应用用户级别存档策略，来为这些特定用户和用户组启用或禁用存档。您可以删除任何您所创建的用户级别存档策略，并且可以更改应用存档策略的用户和用户组。用户级别存档策略会覆盖全局策略和任何站点策略，但仅针对应用策略的用户和用户组。 
    
    例如，如果在全局配置中对内部和外部通信禁用存档，并创建了一个对内部和外部通信启用存档的站点级别策略，然后创建了一个对外部通信禁用存档的用户级别策略。 那么将为所有站点用户存档外部和内部通信，但是不包括那些应用了用户级别策略的用户，将仅为这些用户存档内部通信。
    
有关如何部署存档时设置初始存档配置的详细信息，请参阅[部署存档 Skype 业务服务器](../../deploy/deploy-archiving/deploy-archiving.md)。 有关管理存档部署后的详细信息，请参阅[管理业务服务器 Skype 的存档](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>存档配置工具

 使用适用于业务 Server Control Panel Skype 控制大多数的存档选项。 但是，有几个选项可只使用 Skype for Business Server Management Shell。 这些选项包括存档重复消息和导出存档数据。 有关使用 Skype 业务 Server Control Panel 和 Skype 的业务 Server Management Shell 管理存档策略的详细信息，请参阅[管理业务服务器 Skype 的存档](../../manage/archiving/archiving.md)。
  
## <a name="access-archived-data"></a>访问存档数据

存档数据的访问取决于数据的存储位置： 
  
- **Microsoft Exchange 存储**。 如果您选择 Exchange 集成选项，Skype 业务服务器内存中的所有用户驻留在 Exchange，且谁具有必须置于就地保留其邮箱的 Exchange 存储放存档的内容。 存档的数据存储在用户邮箱可恢复的项目文件夹，其中给用户，通常不可见，才可由具有 Exchange**发现管理**角色的用户搜索。 如果它将部署，Exchange 启用联合的搜索和发现，以及 SharePoint、。 有关存储、 保留和发现在 Exchange 存储的数据的详细信息，请参阅 Exchange 和 SharePoint 文档。
    
- **Skype 业务服务器存档存储**。 如果您设置了 Skype 业务 Server 存档数据库，业务服务器存款不存档中的任何用户业务 Server 存档数据库的 Skype 的内容的 Skype 驻留在 Exchange 和谁不过其邮箱置于就地保留。 This data is not searchable, but it can be exported to formats that are searchable using other tools. 有关导出存档数据库中存储数据的详细信息，请参阅[导出 Skype 业务服务器中的存档的数据](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>有关详细信息

有关存档的详细信息，请参阅下列主题：
  
- [部署存档的 Skype 业务服务器](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [管理存档中 Skype 业务服务器](../../manage/archiving/archiving.md)
    
有关操作的详细信息 Skype 的业务服务器和 Exchange 一起使用，请参阅[计划集成业务和 Exchange Skype](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  

