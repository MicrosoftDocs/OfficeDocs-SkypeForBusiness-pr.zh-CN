---
title: 规划升级到 Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '摘要: 了解在计划升级到 Skype for Business 服务器2015时应考虑的事项。 从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:。'
ms.openlocfilehash: 931ac609dec370d03fe50034300346b7e41c5f56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296782"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>规划升级到 Skype for Business Server 2015
 
摘要: 了解在计划升级到 Skype for Business 服务器2015时应考虑的事项。 从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):。
  
作为计划升级到 Skype for Business Server 2015 的一部分, 请使用本主题了解推荐的 Skype for business Server 2015 升级路径、就地升级的工作方式、受支持的共存方案以及升级过程如下所示。

> [!NOTE]
> Skype for business Server 2015 中提供了就地升级, 但 Skype for business Server 2019 不再支持就地升级。 支持 "并排 coexistance", 有关详细信息, 请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Skype for business Server 2015 的推荐升级路径

 若要从 Lync Server 2013、Lync Server 2010 或 Office 通信服务器 2007 R2 升级到 Skype for Business Server 2015, 请使用以下升级路径:
  
> [!CAUTION]
> 就地升级可将会议目录从 Lync Server 2013 自动移至 Skype for Business Server 2015。但是，如果您计划手动移动会议目录，就务必使用 Skype for Business Server 2015 命令行管理程序。如果您尝试使用 Lync Server 2013 命令行管理程序将会议目录从 Lync Server 2013 移至 Skype for Business Server 2015，则可能出现数据丢失。一般来讲，无论您何时使用任意容量的 Skype for Business Server 2015，都应使用 Skype for Business Server 2015 工具集。  
  
|**版本**|**建议**|
|:-----|:-----|
|Lync Server 2013  <br/> | 若要升级, 请使用 Skype for Business Server 拓扑生成器以及与池关联的每个服务器上新的就地升级功能。 请参阅[计划从 Lync Server 2013 升级到 skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)并[升级到 Skype for business server 2015](../deploy/upgrade-to-skype-for-business-server.md) , 了解详细步骤。 <br/> |
|Lync Server 2010 + Lync Server 2013（双模式）  <br/> |首先, 升级到 Lync Server 2013, 然后使用新的就地升级功能升级到 Skype for business Server 2015。 但是，如果您的拓扑是主要 Lync Server 2010，则您还可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for Business Server 2015。 在此情况下，您将不能使用就地升级，而是使用 Lync Server 2010 与 Skype for Business Server 2015 直接共存。 不支持三项并存，但支持两项共存。  <br/> |
|Lync Server 2010  <br/> |打开新的 Skype for Business Server 2015 池，然后将用户迁移到此新池中。 随后即可停用旧的 Lync Server 2010 池。 从 Lync Server 2010 升级到 Skype for Business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。 请参阅[从 Lync server 2010 迁移到 Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。  <br/> |
|Office Communications Server 2007 R2  <br/> | 选择两个选项之一： <br/>  设置新的 Skype for Business Server 2015 环境。 <br/>  或者, 如果你的硬件和软件满足 Skype for business Server 2015 的要求, 请升级到 Lync Server 2013, 然后使用新的就地升级功能升级到 Skype for business Server 2015。 有关详细信息, 请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)和[从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)。  <br/> |
   
> [!NOTE]
> SQL Server 2014 在 Skype for Business Server 2015 中受支持, 但在 Lync Server 2013 中不受支持。 如果要从 SQL Server 2012 升级到 SQL Server 2014, 则必须首先使用本文档中介绍的就地升级方法升级到 Skype for Business 服务器2015。 然后, 你可以从 SQL Server 2012 升级到 SQL Server 2014, 请参阅[升级到 Sql server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)。 若要了解有关数据库要求的详细信息, 请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>规划从 Lync Server 2013 升级到 Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

你可以使用新的就地升级功能将 Lync Server 2013 系统升级到 Skype for Business Server 2015。 就地升级提供了一次单击的解决方案, 可备份证书、卸载服务器组件、升级本地数据库, 以及安装 Skype for Business Server 2015 角色。 就地升级旨在保留现有硬件和服务器投资, 降低部署 Skype for Business Server 2015 的总成本。
  
> [!NOTE]
> 就地升级允许你在升级到 Skype for Business 服务器时使用相同的硬件。 但是，重用同样的硬件不会转换为同样的性能容量。 不应指望 Lync Server 2013 和 Skype for business Server 2015 的性能负载是相同的。 
  
> [!NOTE]
> 就地升级不支持 Skype for business 服务器的高可用性或灾难恢复。 
  
就地升级涉及将 Lync Server 2013 池脱机并将其升级到 Skype for business Server 2015 池。 
  
### <a name="create-an-in-place-upgrade-plan"></a>创建就地升级计划

制定一份包含以下元素的计划：
  
1. 对当前拓扑的理解。
    
    > [!NOTE]
    > 请确保卸载 Lync Server 2013 的 LRS 管理工具, 然后再运行就地升级。 Lync Server 2013 的 LRS 管理工具无法与 Skype for Business Server 2015 共存。 运行就地升级后, 安装新的 LRS 管理工具, 请参阅[Microsoft Lync 会议室系统管理 Web 门户 For Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. 升级的主池。
    
3. 是要升级存档和监控数据库还是新建相应的数据库。
    
4. 您将使用的就地升级方法：脱机或移动用户。在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。 
    
5. 面向受影响用户的交流计划。
    
6. 防止升级失败的备用计划。
    
在升级过程中，主池中的任何用户都无法使用服务，直至升级完成为止。 如果您有可以使用的辅助池，您可以在升级之前将其迁移到辅助池，避免影响用户。 升级后, 将用户移回主池。
  
### <a name="in-place-upgrade-methods"></a>就地升级方法

有两种就地升级方案： 
  
- 移动用户方法，无需用户停机。 
    
- 脱机方法，需要停机。
    
我们推荐在维护时段内安排脱机方法升级，并通知用户注意停机时间。
  
> [!NOTE]
> 升级 Lync Server 2013 上的成对池时，需要将两个池都升级到 Skype for Business Server 2015。请确保在升级第一个池后，马上升级第二个池。如果一个池运行 Lync Server 2013，而第二个池运行 Skype for Business Server 2015，则灾难恢复选项将减到最少。例如，如果一个池运行 2013，第二个运行 2015，那么当灾难来临时，数据可能丢失，因为当成对池版本不同时，灾难模式不支持池故障转移。 
  
#### <a name="in-place-upgrade-offline-method"></a>就地升级脱机方法

如果您不想在两个用户池间移动用户，请使用此方法。 在升级期间, 用户将无法使用 Lync 或 Skype for business 服务。 
  
下图概述了此流程。
  
![Lync 2013 到 Skype 用户脱机](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 如果采用成对的池，不要在升级之前取消配对。 
  
在开始升级服务器池之前，必须完成整个池的升级。 Skype for Business 服务器不支持仅更新部分池。 
  
#### <a name="move-users-method-no-user-downtime"></a>移动用户方法（用户无需停机）
<a name="bkmk_MoveUsersMethod"> </a>

要使用这种方法，您要首先将用户移动到另一个池，然后开始升级。 在升级期间, 用户可以使用 Lync 服务。 在将其移动到已升级的库后, 他们可以使用 Skype for Business。 下图展示了此过程的概况。
  
> [!IMPORTANT]
> 在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。 PSTN 电话拨入式会议仍会将 ConferenceID 解析到正在升级的池，而不是配对的池。 因此，如果您仍希望在升级期间访问池中安排的 PSTN 会议，则需要移动会议目录。 
  
![泳道图，显示在升级池之前将用户迁移到另一个池，然后在升级完毕后再迁回原池。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>为硬件升级移动用户
<a name="bkmk_MoveUsersMethod"> </a>

 如果你的硬件不满足[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md), 请设置新的 skype For business server 2015 环境, 并将用户移动到此处。 下图概述了从 Lync Server 2010 升级的流程。 
  
![泳道图，显示将 Lync Server 主前端池中的用户迁移到 Skype for Business Server 2015，并且停用 Lync Server 池。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>就地升级过程

 使用以下步骤从 Lync Server 2013 升级到 Skype for business Server 2015:
  
1. 在升级之前备份所有数据库。
    
2. 确保要升级的所有服务都处于运行状态。
    
3. 使用拓扑生成器升级并发布拓扑文件。
    
4. 停止所有前端服务器上的全部服务。
    
5. 安装 Skype for business 服务器所需的新的先决条件。
    
6. 在每台前端服务器上，开始就地升级。
    
7. 升级完成后，重启所有服务。
    
   - 对于前端池，使用命令 Start-CsPool 重启服务。
    
   - 对于非前端服务器，使用 Start-CSWindowsService。
    
> [!NOTE]
>  如果不想升级现有存档和监控数据库，请在升级拓扑之前移除依赖关系。 如果想创建新的存档和监控数据库，在升级过程中，可以创建新的 SQL 存储，并将其与池关联。 你可以在主题 "[升级到 Skype for Business 服务器 2015](../deploy/upgrade-to-skype-for-business-server.md)" 中找到有关如何执行此操作的步骤。 > 就地升级不支持 Skype for business Server 的高可用性或灾难恢复。 为避免中断用户的服务, 请使用 "[移动用户" 方法 (无用户停机)](upgrade.md#bkmk_MoveUsersMethod)升级过程中的 >。在升级过程中, xds-副本将放在具有最大可用空间的磁盘驱动器上的本地共享文件夹中。 如果该磁盘以后被删除，则您可以遇到服务未启动等问题。
  
### <a name="upgrade-order"></a>升级顺序

将拓扑从内部升级到外部。 首先升级所有池, 然后升级边缘服务器, 最后升级到中央管理存储 (CMS) 池。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 身份验证考虑事项

如果为 Web 服务使用了 Kerberos 身份验证，则必须在就地升级完成后重新分配 Kerberos 帐户并重置密码。 若要了解如何执行此操作, 请参阅[设置 Kerberos 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=530342)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>支持 Lync Server 2013 和 Lync Server 2010 共存
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

你可以在与 Lync Server 2013 或 Lync Server 2010 相同的拓扑中运行 Skype for Business Server 2015，但是不能将三者同时置于同一个拓扑中。
  
如果 Lync Server 2010 和 Lync Server 2013 同时存在，建议将整个拓扑升级到 Lync Server 2013，然后再使用就地升级来升级到 Skype for Business Server 2015。 有关详细信息, 请参阅[从 Lync server 2010 迁移到 Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。
  
如果你的拓扑主要是 Lync Server 2010，请在将拓扑升级到 Skype for Business Server 2015 之前，将 Lync Server 2013 组件回退到 Lync Server 2010。在这种情况下，你将丧失就地升级的优势，并且具有 Lync Server 2010 与 Skype for Business Server 2015 同时存在的拓扑。
  
下图显示了 Skype for Business 服务器2015与 Lync Server 2013 和 Lync Server 2010 的共存支持。
  
![显示 Skype for Business Server 2015 与 Lync Server 2013 或 Lync Server 2010 共存支持的图表。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>现有 Survivable Branch Appliance 和服务器的升级流程
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 不支持 Survivable 分支装置 (SBA) 或 Survivable 分支服务器 (SBS) 的就地升级。
  
但是，我们支持 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。 
  
规划采用关联分支就地升级 Lync Server 2013 前端 (FE) 池时，可以将现有用户留在 Lync Server 2013 SBA/SBS 上。 在升级过程中，SBA/SBS 用户将进入恢复模式，并在升级完成后返回正常功能。 有关用户在复原模式期间的体验的详细信息, 请参阅[Lync Server 2013 中的分支站点复原功能](https://technet.microsoft.com/library/gg398715.aspx)。
  
将 Lync Server 2010 拓扑迁移到 Skype for Business Server 2015 时，与迁移到 Lync Server 2013 类似，必须将 SBA/SBS 重新添加到拓扑。 有关所需步骤, 请阅读[将 Survivable 分支装置连接到 Lync Server 2013 前端池](https://technet.microsoft.com/library/jj688026.aspx)。
  
对于 Lync Server 2010 和 Lync Server 2013 的共存拓扑, 请首先与 "对 Lync Server 2013 和 Lync Server 2010 共存的支持" 部分中的建议进行对齐。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[升级到 Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
