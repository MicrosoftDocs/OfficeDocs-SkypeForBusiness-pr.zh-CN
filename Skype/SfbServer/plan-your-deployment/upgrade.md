---
title: 计划升级到 2015 Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 摘要：了解在计划升级到 2015 Skype for Business Server时应考虑的事项。
ms.openlocfilehash: 0b31234bbb0cbc5c2475b241b810430f7595f411
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860593"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>计划升级到 2015 Skype for Business Server
 
摘要：了解在计划升级到 2015 Skype for Business Server时应考虑的事项。
  
作为升级到 Skype for Business Server 2015 计划的一部分，请使用本主题了解建议的 2015 Skype for Business Server升级路径、In-Place升级的工作原理、支持的共存方案以及升级过程的外观。

> [!NOTE]
> 就地升级在 2015 Skype for Business Server提供，但在 2019 Skype for Business Server不再受支持。 支持并行共存，有关详细信息，请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>2015 Skype for Business Server建议的升级路径

 若要从 Lync Server 2013、Lync Server 2010 或 Office Communications Server 2007 R2 升级到 2015 Skype for Business Server，请使用以下升级路径：
  
> [!CAUTION]
> In-Place升级会自动将会议目录从 Lync Server 2013 移动到 2015 Skype for Business Server。 但是，如果计划手动移动会议目录，请务必使用 Skype for Business Server 2015 Management Shell。 如果尝试使用 Lync Server 2013 Management Shell 将会议目录从 Lync Server 2013 移动到 2015 Skype for Business Server，则可能会发生数据丢失。 通常，只要以任何容量使用 Skype for Business Server 2015，就应使用 Skype for Business Server 2015 工具集。  
  
|**版本**|**建议**|
|:-----|:-----|
|Lync Server 2013  <br/> | 若要升级，请在与池关联的每个服务器上使用Skype for Business Server拓扑生成器和新的In-Place升级功能。 有关详细步骤，请参阅[计划从 Lync Server 2013 升级到 Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)，[并升级到 Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)。 <br/> |
|Lync Server 2010 + Lync Server 2013 (双模式)   <br/> |首先，升级到 Lync Server 2013，然后使用新的 In-Place 升级功能升级到 Skype for Business Server 2015。 但是，如果拓扑是 Lync Server 2010 的主数据库，也可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for Business Server 2015。 在这种情况下，你将无法利用In-Place升级，并且会在 Lync Server 2010 和 2015 Skype for Business Server之间使用直接共存。 不支持三合一，但支持共存。  <br/> |
|Lync Server 2010  <br/> |启动新的 Skype for Business Server 2015 池，然后将用户迁移到此新池。 然后，可以解除旧 Lync Server 2010 池的授权。 从 Lync Server 2010 升级到 Skype for Business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。 请参阅 [从 Lync Server 2010 迁移到 Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。  <br/> |
|Office Communications Server 2007 R2  <br/> | 选择两个选项之一： <br/>  设置新的 Skype for Business Server 2015 环境。 <br/>  或者，如果硬件和软件满足 Skype for Business Server 2015 的要求，请升级到 Lync Server 2013，然后使用新的 In-Place 升级功能升级到 Skype for Business Server 2015。 有关详细信息，请参阅 [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) 和[从 Office Communications Server 2007 R2 迁移到 Lync Server 2013 的服务器](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013)要求。  <br/> |
   
> [!NOTE]
> SQL Server 2014 在 2015 Skype for Business Server受支持，但在 Lync Server 2013 中不受支持。 如果要从 SQL Server 2012 升级到 2014 SQL Server，则必须首先使用In-Place升级方法将池升级到 2015 Skype for Business Server，如本文档中所述。 然后，可以从 SQL Server 2012 升级到 2014 SQL Server，请参阅[升级到 2014 SQL Server](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014)。 若要详细了解数据库要求，请参阅 [Skype for Business Server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>计划从 Lync Server 2013 升级到 2015 Skype for Business Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

可以使用新的In-Place升级功能将 Lync Server 2013 系统升级到 2015 Skype for Business Server。 就地升级提供一键式解决方案，用于备份证书、卸载服务器组件、升级本地数据库以及安装 Skype for Business Server 2015 角色。 就地升级旨在保留现有硬件和服务器投资，从而降低 2015 Skype for Business Server部署的总成本。
  
> [!NOTE]
> In-Place升级允许在升级到Skype for Business Server时使用相同的硬件。 但是，重复使用相同的硬件不会转换为相同的性能容量。 不应期望 Lync Server 2013 和 Skype for Business Server 2015 的性能负载相同。 
  
> [!NOTE]
> In-Place升级不支持Skype for Business Server的高可用性或灾难恢复。 
  
就地升级涉及将 Lync Server 2013 池脱机并将其升级到 Skype for Business Server 2015 池。 
  
### <a name="create-an-in-place-upgrade-plan"></a>创建In-Place升级计划

制定包含以下内容的计划：
  
1. 了解当前拓扑。
    
    > [!NOTE]
    > 在运行 In-Place 升级之前，请务必卸载 Lync Server 2013 的 LRS 管理员 工具。 适用于 Lync Server 2013 的 LRS 管理员 工具不能与 2015 Skype for Business Server共存。 运行In-Place升级后安装新的 LRS 管理员工具。 有关更多详细信息，请参阅 [Microsoft Lync 会议室系统管理 Web 门户Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)。
  
2. 升级的主池。
    
3. 是升级存档和监视数据库还是创建新数据库。
    
4. 将使用的In-Place升级方法：脱机或移动用户。 作为移动用户的一部分，还需要迁移与主池关联的全局会议目录。 
    
5. 受影响用户的通信计划。
    
6. 如果升级失败，请执行备份计划。
    
升级时位于主池中的任何用户在升级完成之前将无法使用这些服务。 如果有一个有效的辅助池，则可以在升级前将用户移到辅助池来避免影响用户。 升级后，将用户移回主池。
  
### <a name="in-place-upgrade-methods"></a>就地升级方法

In-Place升级有两种方案： 
  
- Move User 方法，无需用户停机。 
    
- 脱机方法，需要停机时间。
    
建议在维护时段内计划脱机方法升级，并通知用户停机时间。
  
> [!NOTE]
> 在 Lync Server 2013 上升级配对池时，要将两个池升级到 2015 Skype for Business Server。 升级第一个池后，请务必立即升级第二个池。 当一个池运行 Lync Server 2013，第二个池在 2015 Skype for Business Server运行时，灾难恢复选项将最小化。 例如，如果一个池正在运行 2013，第二个池是 2015，并且发生灾难，则可能会出现数据丢失，因为当配对池不是同一版本时，在灾难模式下不支持池故障转移。 
  
#### <a name="in-place-upgrade-offline-method"></a>就地升级脱机方法

如果不想在用户池之间移动用户，请使用此方法。 在升级期间，用户将无法使用 Lync 或 Skype for Business 服务。 
  
下图显示了此过程的概述。
  
![Lync 2013 以脱机Skype用户。](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 如果已配对池，请不要在升级前取消对它们。 
  
开始升级服务器池后，必须完成整个池的升级。 Skype for Business Server不支持仅升级池的一部分。 
  
#### <a name="move-users-method-no-user-downtime"></a>移动用户方法 (没有用户停机时间) 
<a name="bkmk_MoveUsersMethod"> </a>

若要使用此方法，请在开始升级之前将用户移动到另一个池。 在升级期间，用户可以使用 Lync 服务。 移动到升级后的池后，可以使用Skype for Business。 下图显示了此过程的概述。
  
> [!IMPORTANT]
> 作为移动用户的一部分，还需要迁移与主池关联的全局会议目录。 PSTN 电话拨入式会议仍会将 ConferenceID 解析为正在升级的池，而不是配对池。 因此，如果仍希望在升级期间可以访问池中安排的 PSTN 会议，则需要移动会议目录。 
  
![游泳图显示在升级池之前将用户移动到另一个池，并在升级后移回池。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>移动用户进行硬件升级
<a name="bkmk_MoveUsersMethod"> </a>

 如果硬件不符合 [Skype for Business Server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)，请设置新的 Skype for Business Server 2015 环境，并将用户移动到该环境。 下图概述了从 Lync Server 2010 升级的过程。 
  
![泳道图显示 Lync Server 主前端池中的用户被移动到 2015 Skype for Business Server，Lync Server 池已停用。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>就地升级过程

 使用以下步骤从 Lync Server 2013 升级到 Skype for Business Server 2015：
  
1. 在升级之前备份所有数据库。
    
2. 确保要升级的所有服务都处于运行状态。
    
3. 使用拓扑生成器升级和发布拓扑文件。
    
4. 停止所有前端服务器上的所有服务。
    
5. 安装Skype for Business Server所需的新先决条件。
    
6. 在每个前端服务器上，启动In-Place升级。
    
7. 升级完成后，重启所有服务。
    
   - 对于前端池，请使用命令 "开始"菜单-CsPool 重启服务。
    
   - 对于非前端服务器，请使用 "开始"菜单-CSWindowsService。
    
> [!NOTE]
>  如果不想升级现有的存档和监视数据库，请在升级拓扑之前删除依赖项。 如果要创建新的存档和监视数据库，在升级期间，可以创建新的SQL存储并将其与池关联。 可以在主题“[升级到 2015 Skype for Business Server](../deploy/upgrade-to-skype-for-business-server.md)”中找到有关如何执行此操作的步骤。 >就地升级不支持Skype for Business Server的高可用性或灾难恢复。 若要避免中断用户的服务， [请使用 Move Users 方法 (没有用户停机时间) ](upgrade.md#bkmk_MoveUsersMethod) 升级。>在升级过程中，xds-replica 将放置在磁盘驱动器上具有最大可用空间的本地共享文件夹中。 如果稍后删除该磁盘，则可能会遇到服务未启动等问题。
  
### <a name="upgrade-order"></a>升级顺序

将拓扑从内部升级到外部。 首先升级所有池，然后升级边缘服务器，最后升级中央管理Microsoft Store (CMS) 池。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 身份验证注意事项

如果对 Web 服务使用 Kerberos 身份验证，则必须在完成In-Place升级后重新分配 Kerberos 帐户并重置密码。 若要了解如何执行此操作，请参阅 [“设置 Kerberos 身份验证](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication)”。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>支持与 Lync Server 2013 和 Lync Server 2010 共存
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

可以在 Lync Server 2013 或 Lync Server 2010 所在的同一拓扑中运行 Skype for Business Server 2015，但不能将这三个拓扑都包含在同一拓扑中。
  
如果在 Lync Server 2010 和 Lync Server 2013 之间共存，建议将整个拓扑升级到 Lync Server 2013，然后使用 In-Place 升级升级到 Skype for Business Server 2015。 有关详细信息，请参阅 [从 Lync Server 2010 迁移到 Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。
  
如果拓扑主要是 Lync Server 2010，请将 Lync Server 2013 组件回滚到 Lync Server 2010，然后将拓扑升级到 2015 Skype for Business Server。 在这种情况下，你将失去In-Place升级的好处，并在 Lync Server 2010 和 2015 Skype for Business Server之间共存拓扑。
  
下图显示了 Skype for Business Server 2015 与 Lync Server 2013 和 Lync Server 2010 的共存支持。
  
![显示 Lync Server 2013 或 Lync Server 2010 Skype for Business Server 2015 的共存支持关系图。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>使用现有 Survivable Branch 设备和服务器的升级过程
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 不支持In-Place升级 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS) 。
  
但是，我们确实支持将 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。 
  
在计划使用关联分支In-Place升级 Lync Server 2013 前端 (FE) 池时，可以将现有用户保留在 Lync Server 2013 SBA/SBS 上。 升级期间，SBA/SBS 用户将进入复原模式，并在升级完成后返回到正常功能。 有关用户在复原模式下的体验的详细信息，请参阅 [Lync Server 2013 中的分支站点复原功能](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features)。
  
将 Lync Server 2010 拓扑迁移到 2015 Skype for Business Server时，必须将 SBA/SBS 添加到拓扑，类似于迁移到 Lync Server 2013。 有关所需步骤，请阅读 [将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool)。
  
对于 Lync Server 2010 和 Lync Server 2013 的共存拓扑，请先遵循“支持与 Lync Server 2013 和 Lync Server 2010 共存”部分中的建议。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[升级到 2015 Skype for Business Server](../deploy/upgrade-to-skype-for-business-server.md)
  
[2015 Skype for Business Server的环境要求](requirements-for-your-environment/environmental-requirements.md)
  
[Skype for Business Server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)
