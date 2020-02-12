---
title: Skype for Business 服务器中的后端服务器高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 了解 Skype for Business 服务器支持的后端服务器高可用性选项，包括 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例、数据库镜像和 SQL 故障转移群集。
ms.openlocfilehash: 4c814e525b3a1d0900e7162255ec4d7e86d79605
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888611"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Skype for Business 服务器中的后端服务器高可用性
 
了解 Skype for Business 服务器支持的后端服务器高可用性选项，包括 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例、数据库镜像和 SQL 故障转移群集。
  
为提高后端服务器的高可用性，你有四个选项：
  
- 数据库镜像
    
- AlwaysOn 可用性组
    
- AlwaysOn 故障转移群集实例（FCI）
    
- SQL 故障转移群集
    
可以选择使用上述任何一个解决方案，但建议保持组织的业务连续性。 否则，让单个数据库服务器停机可能导致重要的 Skype for business 服务器数据丢失。 
  
你可以仅使用拓扑生成器设置数据库镜像。 对于 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例或 SQL 故障转移群集，你可以使用 SQL Server 创建高可用性解决方案，然后你可以使用拓扑生成器将其与前端池相关联。
  
如果你在与另一个前端池（用于灾难恢复）配对的前端池上使用后端服务器高可用性，则应在两个池中使用相同的后端高可用性解决方案。 
  
## <a name="database-mirroring"></a>数据库镜像

Skype for Business 服务器支持与以下数据库软件进行镜像：
  
- SQL Server 2019 （企业版和标准版）

- SQL Server 2017 （企业版和标准版）

- SQL Server 2016 （企业版和标准版）

- SQL Server 2014 （企业版和标准版）
    
- SQL Server 2012 SP2 和 CU2 （企业版和标准版）
    

> [!NOTE]
> 在 Skype for Business Server 2015 中可以使用 SQL 镜像，但 Skype for Business Server 2019 不再支持该功能。 "AlwaysOn 可用性组"、"AlwaysOn 故障转移群集实例" （FCI）和 "SQL 故障转移群集" 方法是 Skype for Business Server 2019 的唯一受支持的选项。
    
Skype for business Server 中的后端服务器高可用性不支持异步数据库镜像。 在本文档的后续部分中，除非另有说明，否则数据库镜像即表示同步数据库镜像。 
  
当你在前端池中部署数据库镜像时，池中的所有 Skype for business 服务器数据库都将被镜像，包括中央管理存储（如果位于此池中）以及响应组应用数据库和呼叫寄存应用程序数据库（如果这些应用程序在池中运行）。 
  
通过使用数据库镜像，您无需对服务器使用共享存储。每台服务器将其数据库副本保留在本地存储上。 
  
您可选择使用或不使用见证服务器部署数据库镜像。我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。否则，管理员必须手动调用故障转移。请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。
  
如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>适用于计划后端服务器镜像的准则

通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：
  
- 主服务器的 SQL Server 版本必须支持 SQL 镜像。
    
- 主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。 
    
- 主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。
    
有关见证角色支持哪些 SQL 版本的 SQL 最佳做法，请参阅 MSDN 库中的["数据库镜像见证"](https://go.microsoft.com/fwlink/p/?LinkId=247345) 。
  
配置服务器镜像之前，必须先正确设置 SQL 数据库权限。 有关详细信息，请参阅为[数据库镜像或 AlwaysOn 可用性组（SQL Server）设置登录帐户](https://go.microsoft.com/fwlink/p/?LinkId=268454)。
  
对于 SQL 镜像，数据库恢复模式始终设置为“**完全**”，这意味着你必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。建议你确定你的 Lync 部署工作负载所需的事务日志增长程度，以便进行适当的规划。下列文章提供了有关 SQL 备份和日志管理的其他信息：
  
> [!IMPORTANT]
> 仅当主映像、镜像和见证（如果需要）服务器都属于同一域时，才支持使用拓扑生成器或 cmdlet 来设置和删除 SQL 镜像。 如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。 

> [!NOTE]
> 在 Skype for Business Server 2015 中可以使用 SQL 镜像，但 Skype for Business Server 2019 不再支持该功能。 对于 Skype for Business Server 2019，首选 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法。
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>通过数据库镜像实施自动后端服务器故障转移的恢复时间

对于通过数据库镜像实施自动后端故障转移，恢复时间目标 (RTO) 的设计目标为 5 分钟。由于使用了同步的数据库镜像，我们在后端服务器失败期间无需考虑数据丢失（除了在服务器间移动数据期间前端服务器和后端服务器同时宕机的罕见情况）。恢复点目标 (RPO) 的设计目标为 5 分钟。
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>使用数据库镜像的后端服务器失败期间的用户体验

失败期间的用户体验取决于失败的性质和拓扑。
  
如果您使用数据库镜像并且配置了见证服务器，则当主体失败时，后端服务器故障转移将自动快速地发生。活动用户应该不太会注意到正在进行的会话出现中断。
  
如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。 在这段时间内，活动用户可能会受到影响。 他们将继续大约 30 分钟的正常会话。 如果主服务器仍未还原，或者管理员未故障转移到备份，则用户将切换到复原模式，这意味着他们无法执行需要在 Lync Server 上永久更改的任务（如添加联系人）。
  
如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 可用性组和 AlwaysOn 故障转移群集实例

Skype for business 服务器仅支持将 AlwaysOn 可用性组用作主动/被动组，而不支持主动/主动组。 
  
若要使用 AlwaysOn 可用性组或 AlwaysOn 故障转移群集实例，请首先使用 SQL Server 设置和配置高可用性解决方案。 然后，你可以使用拓扑生成器将其与前端池相关联。

Skype for Business 服务器通过以下数据库软件支持 AlwaysOn：

- SQL Server 2019 企业版

- SQL Server 2019 标准版有限制，请参阅下面的注意

- SQL Server 2017 企业版

- SQL Server 2017 标准版有限制，请参阅下面的注意

- SQL Server 2016 企业版

- SQL Server 2016 标准版有限制，请参阅下面的注意

- SQL Server 2014 企业版
    
- SQL Server 2012 SP2 和 CU2 企业版

> [!NOTE]
> SQL Server 2019、2017和2016是 Skype for Business Server 2019 支持的唯一版本。

> [!NOTE]
> SQL 2016、2017和2019标准版本中**不**支持 Alwayson 可用性组，但你可以始终使用故障转移群集实例。 若要了解详细信息，请参阅[SQL Server 2016 的版本和支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)。
  
> [!IMPORTANT]
> 多个 AlwaysOn 可用性组实例的实例名称必须相同。 
  
有关部署 AlwaysOn 可用性组的步骤，请参阅[在 Skype for Business 服务器的后端服务器上部署 AlwaysOn 可用性组](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。
  
## <a name="sql-server-failover-clustering"></a>SQL Server 故障转移群集

Skype for Business 服务器支持具有以下数据库软件的 SQL Server 故障转移群集：
  
- SQL Server 2019 （企业版和标准版）

- SQL Server 2017 （企业版和标准版）

- SQL Server 2016 （企业版和标准版）

- SQL Server 2014 （企业版和标准版）
    
- SQL Server 2012 SP2 和 CU2 （企业版和标准版）

若要使用 SQL 故障转移群集，应先先设置和配置 SQL Server 群集，然后再部署你的前端池。 有关 SQL Server 2012 中故障转移群集的最佳做法和设置说明， [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)请参阅。

> [!NOTE]
> SQL Server 2019、2017和 SQL Server 2016 是 Skype for Business Server 2019 支持的唯一版本。
    
若要使用 SQL 故障转移群集，应先先设置和配置 SQL Server 群集，然后再部署你的前端池。 有关 SQL Server 2014 和2016中故障转移群集的最佳做法和设置说明， [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)请参阅。 有关 SQL Server 2008 中的故障转移群集[https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)，请参阅。
  
安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。
  
