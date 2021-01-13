---
title: 规划 Skype for Business Server 中的存档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中规划存档。
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810142"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>规划 Skype for Business Server 中的存档
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中规划存档。
  
公司和其他组织需要服从数量不断增多的行业规定和政府法规，这些规定和法规要求保留特定类型的通信。 如果你的组织有此类要求，可以使用 Skype for Business Server 中的存档功能存档即时消息 (IM) 和会议 (会议) 通信，以帮助支持一些合规性要求。
  
## <a name="archiving-components"></a>存档组件

Skype for Business Server 使用下列存档组件：
  
- **存档代理**。 存档 (也称为统一数据收集代理) 每个 Enterprise Edition 前端池和 Standard Edition Server 上自动安装和激活。 尽管会自动激活存档代理，但实际上不会捕获任何消息，直到启用并正确配置存档。 默认情况下，存档处于禁用状态。
    
- **存档数据存储**。 Skype for Business Server 的数据存储可以实施为 Skype for Business Server SQL Server数据库，或者（如果有 Exchange 部署）与 Exchange 存储集成。 
    
存档还需要文件存储，但存档使用与前端服务器或 Standard Edition Server 相同的文件存储。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>确定组织的存档要求

若要实施存档，您需要确定如何满足组织的存档要求，方法如下：
  
- **使用哪个存储选项**。 可以通过以下两种方法之一实现存储，或者结合使用这两种方法：
    
  - **Exchange 存储。** 如果你有 Exchange 部署，可以集成 Skype for Business Server 和 Exchange 存档，以便 Skype for Business Server 和 Exchange 存档数据一起存储在 Exchange 中。 如果启用 Microsoft Exchange 集成选项，则 Exchange Server 上的用户邮箱对存档数据使用 Exchange 存储，但只有在邮箱已置于"保留"In-Place。 默认情况下，Microsoft Exchange 集成未启用。
    
  - **Skype for Business Server 存储。** 如果你的用户未位于 Exchange 上，或者尚未将其邮箱置于 In-Place 保留状态，或者如果你不希望为部署中的任意或所有用户使用 Microsoft Exchange 集成，可以使用 SQL Server 部署 Skype for Business Server 存档数据库。
    
- **何时部署存档**。 可以将存档部署为初始 Skype for Business Server 部署的一部分，也可以将其添加到现有部署中。 若要将 Skype for Business Server 存档存储 (SQL Server数据库) ，请使用拓扑生成器将数据库添加到拓扑，然后再次发布拓扑。 如果您的所有用户都位于 Exchange 上，并且其邮箱都置于 In-Place 保留状态，则无需更新拓扑，但只需启用 Microsoft Exchange 集成以在 Exchange 中存储存档数据。 
    
- **组织中哪些站点和用户需要存档**。 您可以为整个组织以及（可选）特定站点、池、用户和用户组配置存档设置。
    
- **应存档的内容**。 无论是在全局级别还是为特定网站和用户指定存档，您在每个级别都指定是否启用以下类型的内容： 
    
  - 对等即时消息
    
  - 多方即时消息的会议
    
  - 会议内容，包括上载的内容（例如讲义）以及与事件相关的内容（例如，加入、离开、上载、共享以及可见性变化）
    
  - 会议期间共享的白板和投票
    
- **哪些内容无法存档**。 无法存档以下类型的内容： 
    
  - 对等文件传输
    
  - 对等即时消息和会议的音频/视频
    
  - 对等即时消息和会议的桌面和应用程序共享
    
    Skype for Business Server 也不存档持久聊天对话。 若要存档持久聊天对话，必须启用和配置合规性服务，该服务是一个可以使用持久聊天服务器部署的组件。 有关详细信息，请参阅 [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

    > [!NOTE] 
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
    
- **存档材料应保留多久**。 存档数据库不用于长期保留，Skype for Business Server 不提供存档数据的电子发现 (搜索) 解决方案，因此需要将数据移动到其他存储。 Skype for Business Server 提供了会话导出工具，可用于导出存档数据，并创建存档数据的可搜索脚本。 
    
     对于全局策略以及您创建的每个站点和用户策略，可以指定何时清除存档和导出的数据。 有关清除数据详细信息，请参阅"管理清除 Skype for Business Server 中的存档[数据"。](../../manage/archiving/purging-of-archived-data.md) 有关使用会话导出工具的信息，请参阅 [导出 Skype for Business Server 中的存档数据](../../manage/archiving/export-archived-data.md)。
    
- **存档内部通信还是外部通信**。您可实现对内部通信（即，内部用户间的通信）、外部通信（即，至少包括内部网络之外的一个用户的通信）或二者的存档。您可为整个组织指定这些选项，也可以为特定网站和池指定它们。默认情况下，将不会启用任一选项。
    
    > [!NOTE]
    > 控制内部或外部通信的存档仅适用于 Skype for Business 策略。 对于 Exchange 集成的存档，内部和外部通信都存档或不存档。 
  
- **是否实现临界模式**。 如果您的组织需要存档，则配置关键模式将在 Skype for Business Server 出现故障时阻止 IM 和会议会话，这将阻止存档。 例如： 
    
  - Skype for Business Server 存储服务出现问题。 在这种情况下，将阻止启用存档的用户使用 IM。
    
  - 文件共享不可用或存储服务出现问题。 在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。
    
    IM 和会议都能在修复故障后自动恢复。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>选择存档部署和配置选项

部署服务器时，存档会自动安装在每台前端服务器上，但在配置存档之前不会启用存档。 配置存档方式由部署存档方式决定。 您可以通过以下方法之一部署存档：
  
- 使用 Microsoft Exchange 存储
    
- 使用 Skype for Business Server 存储
    
> [!NOTE]
> 如果同时实现 Skype for Business Server 存档数据库并启用 Microsoft Exchange 集成，Exchange 策略将覆盖 Skype for Business Server 存档策略，但仅针对那些位于 Exchange 上且其邮箱已置于"In-Place保留"的用户。 Skype for Business 存档取决于 Microsoft Exchange In-Place保留策略。 
  
如果为一个前端池或 Standard Edition Server 部署存档，应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。 如果未在承载对话或会议的池上启用存档，则可能无法存档所有会议数据。 存档仍适用于 IM 消息，但会议内容和事件可能无法存档。
  
> [!NOTE]
> 为了在维护组织的安全标准的同时允许委派管理任务，Skype for Business Server 使用基于角色的访问控制 (RBAC) 。 利用 RBAC，可以通过将用户分配至预定义的管理角色来授予管理特权。 若要配置 Skype for Business 存档策略和配置，必须将用户分配给 CsArchivingAdministrator 角色 (除非配置直接在部署存档的服务器上执行，而不是从另一台计算机远程) 。 有关存档部署所需的用户权限和角色的列表，请参阅[Deploy archiving for Skype for Business Server.](../../deploy/deploy-archiving/deploy-archiving.md) 
  
> [!NOTE]
> 如果使用 Microsoft Exchange 集成，则 Exchange 策略的配置需要相应的管理员权限。 有关详细信息，请参阅 Exchange 文档。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 存储

 如果选择 Microsoft Exchange 集成，请使用 Exchange 策略和配置来控制 Skype for Business Server 的存档。 可以在全局级别、站点级别和池级别配置 Microsoft Exchange 集成选项。 如果部署包括多个林，则必须在 Skype for Business Server 和 Exchange 之间同步设置。 你将需要确定：
  
- 存档 IM 和/或会议
    
- 是否实现关键模式，该模式在 Skype for Business Server 出现故障时阻止 IM 和会议会话 
    
- 选择 Microsoft Exchange 集成选项以使用 Exchange 存储存档数据
    
若要了解如何配置 Exchange In-Place保留策略和设置以支持存档，请参阅 Exchange 产品文档。
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server 存储

如果选择 Skype for Business Server 存储，则使用 Skype for Business Server 存档策略和配置来控制如何启用和实施存档。 Skype for Business Server 存储使用SQL Server数据库，因此你需要将相应的SQL Server数据库添加到拓扑，然后配置存档策略。 
  
### <a name="add-storage-databases-to-your-topology"></a>将存储数据库添加到拓扑

将SQL Server数据库添加到拓扑时，可以选择将存档数据库与以下任一项并并：
  
- 监控数据库
    
- 企业版前端池的后端数据库
    
> [!NOTE]
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。 
  
如果将存档数据库与监控数据库、后端数据库或这两个数据库并并，您可以对任意或所有数据库使用单个 SQL 实例，也可以针对每个数据库使用单独的 SQL 实例，但具有以下限制：每个 SQL 实例只能包含一个后端数据库、单个监控数据库和单个存档数据库。
  
有关所有服务器角色和数据库并置的详细信息，请参阅[Topology Basics for Skype for Business Server。](../../plan-your-deployment/topology-basics/topology-basics.md) 有关更新拓扑以包含存储数据库的详细信息，请参阅 Create [and publish new topology in Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)
  
### <a name="determine-archiving-options-and-user-policies"></a>确定存档选项和用户策略

你将需要确定：
  
- 是启用还是禁用内部和外部通信的存档
    
- 存档 IM 和/或会议
    
- 是否实现关键模式，该模式在 Skype for Business Server 出现故障时阻止 IM 和会议会话 
    
- 是否为特定用户和组启用策略
    
可在以下级别指定 Skype for Business Server 存档选项。 
  
- **全局级别选项**。 这是默认存档配置，适用于整个部署。 它在您部署 Skype for Business Server 时创建，并且默认情况下会禁用内部和外部通信的存档。 不能删除此选项。 如果选择删除选项，则全局选项将重置为默认设置。
    
- **网站级别选项**。 您可以通过为一个或多个特定站点创建和配置站点级别存档选项来启用或禁用存档。 您可以删除创建的任何站点级别存档选项。 站点级别存档选项会覆盖全局选项，但仅适用于该选项中指定的站点。 
    
    例如，如果在全局配置中对内部和外部通信启用存档，并创建一个禁用外部通信存档的站点配置，则只会为该网站存档内部通信。 另一个示例是，如果在全局配置中仅对 IM 启用存档，并创建一个同时为 IM 和会议启用存档的站点配置，则仅会为站点存档会议，而不是为组织的其余部分存档会议。
    
- **池级别选项**。 通过为单个池创建和配置池级别配置，您可以为一个或多个特定池指定存档设置。 池级别存档配置仅在您创建时存在。 您可以修改和删除任何池级别的存档配置。 池级别存档配置会覆盖全局配置和您可能已创建的任何站点存档配置。 
    
    例如，假定仅在全局配置中为 IM 启用存档，然后创建一个站点级别配置，其中同时为 IM 和会议启用存档，然后创建一个仅对 IM 启用存档的池级别配置。 除了在池级别配置中指定的池中所管理的用户之外，还将为站点的所有用户存档 IM 和会议通信。 对于组织中的所有其他用户，仅对 IM 启用存档。
    
- **用户存档策略**。 您可以通过为指定用户和用户组创建、配置和应用用户级别存档策略，为一个或多个特定用户和用户组启用或禁用存档。 您可以删除创建的任何用户级别存档策略，并可以更改存档策略所适用的用户和用户组。 用户级别的存档策略会覆盖全局策略和任何站点策略，但仅适用于应用了该策略的用户和用户组。 
    
    例如，假定在全局配置中禁用内部和外部通信的存档，创建一个站点级别的策略，在策略中为内部和外部通信启用存档，然后创建一个用户级别的策略，在策略中禁用外部通信的存档。 对于所有站点用户（应用用户级别策略的用户除外）的外部和内部通信，将存档通信，仅存档这些用户的内部通信。
    
有关部署存档时如何设置初始存档配置的详细信息，请参阅[Deploy archiving for Skype for Business Server。](../../deploy/deploy-archiving/deploy-archiving.md) 有关部署后管理存档的详细信息，请参阅["在 Skype for Business Server 中管理存档"。](../../manage/archiving/archiving.md) 
  
## <a name="archiving-configuration-tools"></a>存档配置工具

 使用 Skype for Business Server 控制面板控制大多数存档选项。 但是，只有使用 Skype for Business Server 命令行管理程序才能使用一些选项。 这些选项包括存档重复消息和导出存档数据。 有关使用 Skype for Business Server 控制面板和 Skype for Business Server 命令行管理程序 管理存档策略的信息，请参阅"在 Skype for Business Server 中管理存档["。](../../manage/archiving/archiving.md)
  
## <a name="access-archived-data"></a>访问存档数据

存档数据的访问取决于数据的存储位置： 
  
- **Microsoft Exchange 存储**。 如果选择 Exchange 集成选项，Skype for Business Server 将存档内容存储在 Exchange 存储中，供所有位于 Exchange 上且其邮箱置于保留状态的用户In-Place保留。 存档数据存储在用户邮箱"可恢复的项目"文件夹中，该文件夹通常对用户不可见，并且只能由具有 Exchange **发现** 管理角色的用户搜索。 Exchange 启用联合搜索和发现以及 SharePoint（如果已部署）。 有关 Exchange 中存储的数据的存储、保留和发现的详细信息，请参阅 Exchange 和 SharePoint 文档。
    
- **Skype for Business Server 存档存储**。 如果设置 Skype for Business Server 存档数据库，Skype for Business Server 将在 Skype for Business Server 存档数据库中为未位于 Exchange 上且其邮箱尚未置于"保留"状态的任何用户In-Place存档内容。 虽然此数据是不可搜索的，但可以采用可通过其他工具搜索的格式导出此数据。 有关导出存档数据库中存储的数据的详细信息，请参阅 [导出 Skype for Business Server 中的存档数据](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>详细信息

有关存档详细信息，请参阅下列主题：
  
- [为 Skype for Business Server 部署存档](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [在 Skype for Business Server 中管理存档](../../manage/archiving/archiving.md)
    
有关 Skype for Business Server 和 Exchange 如何协同工作的更多详细信息，请参阅规划 Skype [for Business](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)和 Exchange 集成。
  

