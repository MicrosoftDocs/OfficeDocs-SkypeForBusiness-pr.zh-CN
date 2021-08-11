---
title: 后端服务器高可用性Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 了解 Skype for Business Server 中支持的后端服务器高可用性选项，包括 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例、数据库镜像SQL故障转移群集。
ms.openlocfilehash: 5cc325b0726afab72581f679873fe454d8302dec5a478685c24e84b430a25017
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318735"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>后端服务器高可用性Skype for Business Server
 
了解 Skype for Business Server 中支持的后端服务器高可用性选项，包括 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例、数据库镜像SQL故障转移群集。
  
若要增强后端服务器的高可用性，有四个选项：
  
- 数据库镜像
    
- AlwaysOn 可用性组
    
- AlwaysOn 故障转移群集实例 (FCI) 
    
- SQL故障转移群集
    
可以选择使用其中一个解决方案，但建议保留组织的业务连续性。 否则，如果单个数据库服务器关闭，则可能导致丢失大量Skype for Business Server数据。 
  
只能使用拓扑生成器设置数据库镜像。 对于 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例或 SQL 故障转移群集，可以使用 SQL Server 创建高可用性解决方案，然后可以使用拓扑生成器将其与前端池关联。
  
如果在与另一个前端池配对的前端池上使用后端服务器高可用性，则应该在两个池中使用相同的后端高可用性解决方案。 
  
## <a name="database-mirroring"></a>数据库镜像

Skype for Business Server以下数据库软件进行镜像：
  
- SQL Server 2019 年 10 月，Enterprise Edition和 Standard Edition

- SQL Server 2017 年，Enterprise Edition 和 Standard Edition

- SQL Server 2016 Enterprise Edition和 Standard Edition

- SQL Server 2014 Enterprise Edition和 Standard Edition
    
- SQL Server 2012 SP2 和 CU2，Enterprise Edition和 Standard Edition
    

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 中唯一支持的选项。
    
后端服务器高可用性不支持异步数据库镜像Skype for Business Server。 在本文档的其余部分中，除非另有说明，否则数据库镜像是指同步数据库镜像。 
  
在前端池中部署数据库镜像时，将镜像池中的所有 Skype for Business Server 数据库（如果中央管理存储位于该池中）以及响应组 应用数据库 和呼叫库 应用数据库（如果这些应用程序正在池中运行）。 
  
使用数据库镜像时，无需对服务器使用共享存储。 每台服务器将其数据库副本保留在本地存储上。 
  
可以选择部署带见证的数据库镜像，也可以不部署见证服务器。 我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。 否则，管理员必须手动调用故障转移。 请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。
  
如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>规划后端服务器镜像的指南

通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：
  
- 主服务器的版本必须支持SQL Server镜像SQL镜像。
    
- 主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。 
    
- 主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。
    
有关SQL角色支持哪些SQL的最佳实践，请参阅 MSDN 库中的"数据库[镜像](/sql/database-engine/database-mirroring/database-mirroring-witness)见证"。
  
配置服务器镜像之前，必须先正确设置SQL权限。 有关详细信息，请参阅"为数据库镜像或 AlwaysOn 可用性组设置登录[ (SQL Server) "。](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)
  
对于 SQL 镜像，数据库恢复模式始终设置为“完全”，这意味着您必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。建议您确定您的 Lync 部署工作负载所需的事务日志增长程度，以便进行适当的规划。下列文章提供了有关 SQL 备份和日志管理的其他信息：
  
> [!IMPORTANT]
> 仅在主服务器、镜像服务器和见证 (服务器都属于同一域时，才支持使用拓扑生成器或 cmdlet 设置和删除) SQL 镜像。 如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。 

> [!NOTE]
> SQL镜像在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中Skype for Business Server首选。
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>使用数据库镜像进行自动后端服务器故障转移的恢复时间

对于使用数据库镜像的自动后端故障转移，RTO (恢复) 目标为 5 分钟。 由于同步数据库镜像，我们预计后端服务器故障期间会丢失数据，除非在服务器之间移动数据的同时，前端服务器和后端服务器同时出现故障的极少数情况除外。 恢复点目标 (RPO) 的设计目标为 5 分钟。
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>使用数据库镜像的后端服务器故障期间用户体验

失败期间的用户体验取决于失败的性质和拓扑。
  
如果使用数据库镜像并配置了见证服务器，并且主体出现故障，后端服务器故障转移将自动快速地发生。 活动用户应该不太会注意到正在进行的会话出现中断。
  
如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。 在这段时间内，活动用户可能会受到影响。 他们将继续大约 30 分钟的正常会话。 如果主服务器仍未还原，或者管理员尚未对备份进行故障切换，则用户会切换到恢复能力模式，这意味着他们无法执行需要在 Lync Server (上进行永久性更改的任务，例如添加联系人) 。
  
如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 可用性组和 AlwaysOn 故障转移群集实例

Skype for Business Server AlwaysOn 可用性组仅支持主动/被动，而非主动/主动。 
  
若要使用 AlwaysOn 可用性组或 AlwaysOn 故障转移群集实例，首先SQL Server设置和配置高可用性解决方案。 然后，可以使用拓扑生成器将其与前端池关联。

Skype for Business Server以下数据库软件支持 AlwaysOn：

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition有限制，请参阅下面的说明

- 2017 SQL Server Enterprise Edition

- SQL Server 2017 Standard Edition有限制，请参阅下面的说明

- 2016 SQL Server Enterprise Edition

- SQL Server 2016 Standard Edition有限制，请参阅下面的说明

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 和 CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019、2017 和 2016 是唯一受 Skype for Business Server 2019 支持的版本。

> [!NOTE]
> Always On 可用性组 **在** SQL 2016、2017 和 2019 Standard Edition 中不受支持，但可以使用 Always On 故障转移群集实例。 有关详细信息[，请参阅 SQL Server 2016](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)版本和支持的功能。
  
> [!IMPORTANT]
> 多个 AlwaysOn 可用性组实例的实例名称必须相同。 
  
有关部署 AlwaysOn 可用性组的步骤，请参阅在 Skype for Business Server 中的后端服务器上部署[AlwaysOn 可用性Skype for Business Server。](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)
  
## <a name="sql-server-failover-clustering"></a>SQL Server故障转移群集

Skype for Business Server支持SQL Server数据库软件进行故障转移群集：
  
- SQL Server 2019 年 10 月，Enterprise Edition和 Standard Edition

- SQL Server 2017 年，Enterprise Edition 和 Standard Edition

- SQL Server 2016 Enterprise Edition和 Standard Edition

- SQL Server 2014 Enterprise Edition和 Standard Edition
    
- SQL Server 2012 SP2 和 CU2，Enterprise Edition和 Standard Edition

若要SQL故障转移群集，应首先设置和配置 SQL Server 群集，然后再部署前端池。 有关 2012 年 3 月故障转移群集的最佳实践SQL Server说明，请参阅 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。

> [!NOTE]
> SQL Server 2019、2017 和 SQL Server 2016 是唯一受 Skype for Business Server 2019 支持的版本。
    
若要SQL故障转移群集，应首先设置和配置 SQL Server 群集，然后再部署前端池。 有关在 2014 和 2016 SQL Server故障转移群集的最佳实践和设置说明，请参阅 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。 有关 SQL Server 2008 中的故障转移群集，请参阅 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) 。
  
安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。 安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。
