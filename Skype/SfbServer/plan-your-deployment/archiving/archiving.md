---
title: 在 Skype for Business 服务器中规划存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: '摘要: 阅读本主题, 了解如何在 Skype for Business Server 中规划存档。'
ms.openlocfilehash: 9d24457d8345aa6b496489b68347a98c069abc69
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417872"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划存档
 
**摘要:** 阅读本主题, 了解如何在 Skype for Business Server 中规划存档。
  
公司和其他组织需要服从数量不断增多的行业规定和政府法规，这些规定和法规要求保留特定类型的通信。 如果您的组织具有此类要求, 则可以使用 Skype for Business Server 中的存档来存档即时消息 (IM) 和会议 (会议) 通信, 以帮助支持某些符合性要求。
  
## <a name="archiving-components"></a>存档组件

Skype for business 服务器使用以下存档组件:
  
- **存档代理**。 将在每个 Enterprise Edition 前端池和 Standard Edition 服务器上自动安装和激活存档代理（也称为“统一数据收集代理”）。 尽管会自动激活存档代理，但实际上并不捕获任何消息，除非启用存档并正确配置存档。 默认将禁用存档功能。
    
- **存档数据存储**。 Skype for business Server 的数据存储可以实现为 Skype for business Server SQL Server 数据库, 或者, 如果你有 Exchange 部署, 并且与 Exchange 存储集成。 
    
存档还需要文件存储，但是存档使用与前端服务器或 Standard Edition 服务器相同的文件存储。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>确定组织的存档要求

若要实现存档, 你需要通过确定以下内容来确定如何满足组织的存档要求:
  
- **要使用哪种存储选项**。 您可以通过以下两种方式之一或将两者相结合来实施存储：
    
  - **Exchange 存储。** 如果您有 Exchange 部署, 则可以集成 Skype for business Server 和 Exchange 存档, 以便您的 Skype for Business 服务器和 Exchange 存档数据将一起存储在 Exchange 中。 如果启用 "Microsoft Exchange 集成" 选项, 则托管在 Exchange 服务器上的用户邮箱将 Exchange 存储用于存档的数据, 但仅当邮箱已放在原地保留时。 默认情况下, 不启用 Microsoft Exchange 集成。
    
  - **Skype for business 服务器存储。** 如果您的用户不是 Exchange 托管的用户或没有邮箱置于原地保留状态的用户, 或者如果您不希望对部署中的任何用户或所有用户使用 Microsoft Exchange 集成, 则可以使用 S 部署 Skype for Business Server 存档数据库QL 服务器。
    
- **何时部署存档**。 你可以将存档部署为初始 Skype for Business Server 部署的一部分, 也可以将其添加到现有部署。 若要使用 Skype for business 服务器存档存储 (SQL Server 数据库), 请使用拓扑生成器将数据库添加到拓扑中, 然后再次发布拓扑。 如果你的所有用户都托管在 Exchange 上, 并且其邮箱放置在原地保留, 则不必更新你的拓扑, 但仅需要启用 Microsoft Exchange 集成才能将存档的数据存储在 Exchange 中。 
    
- **组织中的哪些站点和用户需要存档**。 你可以为整个组织配置存档设置, 也可以为特定网站、池、用户和用户组配置存档设置。
    
- **应存档哪些内容**。无论是在全局级别还是为其中每个级别的特定站点和用户指定存档，您都要指定是否启用以下类型的内容： 
    
  - 对等即时消息
    
  - 多方即时消息的会议
    
  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）
    
  - 会议期间共享的白板和投票
    
- **不能存档哪些内容**。 不能存档以下类型的内容： 
    
  - 对等文件传输
    
  - 对等即时消息和会议的音频/视频
    
  - 对等即时消息和会议的桌面和应用程序共享
    
    Skype for business 服务器也不会存档持久聊天对话。 若要存档持久聊天对话, 您必须启用和配置合规性服务, 该服务是可以使用持久聊天服务器部署的组件。 有关详细信息, 请参阅[在 Skype for Business server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

    > [!NOTE] 
    > Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 
    
- **存档材料应保留多长时间**。 存档数据库不是为了长期保留, 而 Skype for Business 服务器不提供用于存档数据的电子发现 (搜索) 解决方案, 因此需要将数据移动到其他存储。 Skype for Business 服务器提供了一种会话导出工具, 可用于导出已存档的数据, 并可创建已存档数据的可搜索脚本。 
    
     对于全局策略以及你创建的每个网站和用户策略, 你可以指定何时清除存档和导出的数据。 有关清除数据的详细信息, 请参阅[管理 Skype For Business 服务器中的存档数据清除](../../manage/archiving/purging-of-archived-data.md)。 有关使用会话导出工具的详细信息, 请参阅[在 Skype For Business 服务器中导出存档的数据](../../manage/archiving/export-archived-data.md)。
    
- **存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。
    
    > [!NOTE]
    > 仅适用于 Skype for business 策略, 控制内部或外部通信的存档。 对于 Exchange 集成的存档, 内部和外部通信均为 "已存档" 或 "未存档"。 
  
- **是否实施关键模式**。 如果存档是你的组织的要求, 则配置关键模式将阻止在可能阻止存档的 Skype for business 服务器故障事件中的 IM 和会议会话。 例如： 
    
  - Skype for Business 服务器存储服务有问题。 在此情况下，为启用存档的用户阻止 IM。
    
  - 文件共享不可用或存储服务出现问题。在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>选择存档部署和配置选项

部署每台前端服务器时将自动在该服务器上安装存档，但存档在您配置之前不会启用。 配置存档的方式由存档的部署方式决定。 您可以通过以下其中一种方式来部署存档：
  
- 使用 Microsoft Exchange 存储
    
- 使用 Skype for Business 服务器存储
    
> [!NOTE]
> 如果你实现 Skype for business 服务器存档数据库并启用 Microsoft Exchange 集成, Exchange 策略将覆盖 Skype for business Server 存档策略, 但仅适用于托管在 Exchange 上并已将其邮箱置于的用户就地保留。 Skype for Business 存档取决于 Microsoft Exchange 就地保留策略。 
  
如果你为一个前端池或标准版服务器部署存档, 你应该为部署中的所有其他前端池和标准版服务器启用它。 如果承载该对话或会议的池上没有启用存档，则可能无法存档所有会议数据。 存档对于 IM 消息仍然有效，但可能无法存档会议内容和事件。
  
> [!NOTE]
> 若要在维护组织的安全标准的同时启用管理任务的委派, Skype for business 服务器使用基于角色的访问控制 (RBAC)。 利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。 若要配置 Skype for Business 存档策略和配置, 用户必须分配给 CsArchivingAdministrator 角色 (除非直接在部署存档的服务器上执行配置, 而不是从其他计算机远程执行的配置)). 有关存档部署所需的用户权限、权限和角色的列表, 请参阅为[Skype for Business 服务器部署存档](../../deploy/deploy-archiving/deploy-archiving.md)。 
  
> [!NOTE]
> 如果你使用 Microsoft Exchange 集成, 则 Exchange 策略的配置需要相应的管理员权限。 有关详细信息, 请参阅 Exchange 文档。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储

 如果选择 "Microsoft Exchange 集成", 则使用 Exchange 策略和配置来控制 Skype for Business 服务器的存档。 你可以在全局级别、网站级别和池级别配置 Microsoft Exchange 集成选项。 如果你的部署包含多个林, 则必须在 Skype for Business Server 和 Exchange 之间同步设置。 您需要确定：
  
- 是否存档 IM、会议或二者
    
- 是否实现在 Skype for business 服务器出现故障时阻止 IM 和会议会话的关键模式 
    
- 选择 "Microsoft Exchange 集成" 选项以使用 Exchange 存储存档数据
    
有关如何配置 Exchange 就地保留策略和设置以支持存档的信息, 请参阅 Exchange 产品文档。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server 存储

如果您选择 "Skype for business 服务器存储", 则使用 Skype for Business 服务器存档策略和配置来控制启用和实施存档的方式。 Skype for business 服务器存储使用 SQL Server 数据库, 因此你需要将相应的 SQL Server 数据库添加到你的拓扑中, 然后配置你的存档策略。 
  
### <a name="add-storage-databases-to-your-topology"></a>向拓扑添加存储数据库

将 SQL Server 存储数据库添加到拓扑中时, 可以选择将存档数据库 collocate 以下任何一种:
  
- 监控数据库
    
- 企业版前端池的后端数据库
    
> [!NOTE]
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。 
  
如果您 collocate 使用监视数据库、后端数据库或这两个数据库中的存档数据库, 则可以为任何或所有数据库使用单个 SQL 实例, 也可以为每个数据库使用单独的 SQL 实例, 如下所示限制: 每个 SQL 实例只能包含一个后端数据库、单个监视数据库和一个存档数据库。
  
有关所有服务器角色和数据库的 collocation 的详细信息, 请参阅[Skype for Business 服务器的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。 有关将拓扑更新为包含存储数据库的详细信息, 请参阅[在 Skype For Business 服务器中创建和发布新拓扑](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>确定存档选项和用户策略

您需要确定：
  
- 是否启用或禁用内部和外部通信存档
    
- 是否存档 IM、会议或二者
    
- 是否实现在 Skype for business 服务器出现故障时阻止 IM 和会议会话的关键模式 
    
- 是否为特定用户和组启用策略
    
Skype for business 服务器存档选项可以按以下级别指定。 
  
- **全局级别选项**。 这是默认存档配置，适用于您的整个部署。 它是在部署 Skype for Business 服务器时创建的, 并且默认情况下, 将禁用内部和外部通信的存档。 您无法删除此选项。 如果您选择删除选项，那么全局选项将重置为默认设置。
    
- **站点级别选项**。您可以通过为一个或多个特定站点创建和配置站点级别存档选项，来对该站点启用或禁用存档。您可以删除任何您所创建的站点级别存档选项。站点级别存档选项会覆盖全局选项，但仅针对选项中指定的站点。 
    
    例如，如果在全局配置中对内部和外部通信启用存档，并创建了一个为外部通信禁用存档的站点配置，则将为该站点仅存档内部通信。另外，如果您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点配置，那么仅会为该站点存档会议，而不会为组织的其他站点存档会议。
    
- **池级别选项**。您可以通过为单个池创建和配置池级别配置来为一个或多个特定池指定存档设置。池级别存档配置仅在您创建它后才会存在。您可以修改或删除任何池级别存档配置。池级别存档配置会覆盖全局配置和您可能已创建的任何站点存档配置。 
    
    例如，假设您在全局配置中仅为 IM 启用存档，并创建了一个同时为 IM 和会议启用存档的站点级别配置，然后创建了一个仅为 IM 启用存档的池级别配置。 将为该站点的所有用户存档 IM 和会议通信，但是不包括那些驻留在池级别配置中指定的池中的用户。 对于您组织中的所有其他用户，仅针对 IM 启用存档。
    
- **用户存档策略**。您可以通过为一个或多个指定用户和用户组创建、配置和应用用户级别存档策略，来为这些特定用户和用户组启用或禁用存档。您可以删除任何您所创建的用户级别存档策略，并且可以更改应用存档策略的用户和用户组。用户级别存档策略会覆盖全局策略和任何站点策略，但仅针对应用策略的用户和用户组。 
    
    例如，如果在全局配置中对内部和外部通信禁用存档，并创建了一个对内部和外部通信启用存档的站点级别策略，然后创建了一个对外部通信禁用存档的用户级别策略。 那么将为所有站点用户存档外部和内部通信，但是不包括那些应用了用户级别策略的用户，将仅为这些用户存档内部通信。
    
有关如何在部署存档时设置初始存档配置的详细信息, 请参阅[部署 Skype for Business 服务器存档](../../deploy/deploy-archiving/deploy-archiving.md)。 有关在部署后管理存档的详细信息, 请参阅[在 Skype For Business 服务器中管理存档](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>存档配置工具

 您可以通过使用 Skype for Business 服务器控制面板控制大部分存档选项。 但是, 只有使用 Skype for Business Server 命令行管理器, 才可使用某些选项。 这些选项包括存档重复消息和导出存档数据。 有关使用 Skype for Business 服务器控制面板和 Skype for Business Server Management Shell 管理存档策略的详细信息, 请参阅[管理 Skype For Business 服务器中的存档](../../manage/archiving/archiving.md)。
  
## <a name="access-archived-data"></a>访问存档数据

存档数据的访问取决于数据的存储位置： 
  
- **Microsoft Exchange 存储**。 如果你选择 "Exchange 集成" 选项, 则 Skype for Business 服务器将为托管在 Exchange 上的所有用户在 Exchange 存储中为其存档内容, 并将其邮箱放在原地保留中。 已存档的数据存储在用户邮箱 "可恢复的项目" 文件夹中, 该文件夹通常对用户不可见, 并且只能由具有 Exchange**发现管理**角色的用户搜索。 如果部署了, Exchange 将启用联合搜索和发现, 以及 SharePoint。 有关存储在 Exchange 中的数据的存储、保留和发现的更多详细信息, 请参阅 Exchange 和 SharePoint 文档。
    
- **Skype For Business 服务器归档存储**。 如果您设置了 Skype for business 服务器存档数据库, Skype for business 服务器将把内容存档到 Skype for Business 服务器存档数据库中, 而不是托管于 Exchange 的任何用户, 并且未将其邮箱放在原地保留中。 This data is not searchable, but it can be exported to formats that are searchable using other tools. 有关导出存储在存档数据库中的数据的详细信息, 请参阅[在 Skype For Business 服务器中导出存档的数据](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>有关详细信息

有关存档的详细信息，请参阅下列主题：
  
- [为 Skype for Business Server 部署存档](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [管理 Skype for Business 服务器中的存档](../../manage/archiving/archiving.md)
    
有关 Skype for business 服务器和 Exchange 如何协同工作的更多详细信息, 请参阅[计划集成 skype For business 和 exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  

