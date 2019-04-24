---
title: 规划升级到 Skype for Business Server 2015
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 摘要： 了解升级到 Skype 规划业务服务器 2015年时应考虑。 下载免费试用版 Skype 业务服务器 2015 从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 711b675c902824e6aab31ed64266a946a135b7fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213472"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>规划升级到 Skype for Business Server 2015
 
摘要： 了解升级到 Skype 规划业务服务器 2015年时应考虑。 下载免费试用版 Skype 业务服务器 2015 从 Microsoft 评估中心，网址为： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
作为升级到 Skype 的业务服务器 2015年您计划的一部分，使用本主题来了解 Skype 的推荐升级路径的业务服务器 2015年如何就地升级的工作原理、 支持的共存方案是什么，和升级过程如下所示。

> [!NOTE]
> 就地升级中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 Coexistance 都支持并排，详细信息，请参阅[迁移到业务服务器 2019年的 Skype](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>为业务服务器 2015年的 Skype 的推荐升级路径

 若要为业务服务器 2015年从 Lync Server 2013、 Lync Server 2010 或 Office Communications Server 2007 R2 升级到 Skype，使用以下升级途径：
  
> [!CAUTION]
> 就地升级可将会议目录从 Lync Server 2013 自动移至 Skype for Business Server 2015。但是，如果您计划手动移动会议目录，就务必使用 Skype for Business Server 2015 命令行管理程序。如果您尝试使用 Lync Server 2013 命令行管理程序将会议目录从 Lync Server 2013 移至 Skype for Business Server 2015，则可能出现数据丢失。一般来讲，无论您何时使用任意容量的 Skype for Business Server 2015，都应使用 Skype for Business Server 2015 工具集。  
  
|**版本**|**建议**|
|:-----|:-----|
|Lync Server 2013  <br/> | 若要升级，用于 Skype 业务 Server 拓扑生成器和上每个服务器与池关联的就地升级的新功能。 有关详细步骤，请参阅[规划 Lync Server 2013 的业务服务器 2015 Skype 以从升级](upgrade.md#BKMK_PlanUpgradeFromLync2013)和[升级到业务服务器 2015年的 Skype](../deploy/upgrade-to-skype-for-business-server.md) 。 <br/> |
|Lync Server 2010 + Lync Server 2013（双模式）  <br/> |首先，升级到 Lync Server 2013 并升级到 Skype 的业务服务器 2015年使用就地升级的新功能。 但是，如果您的拓扑是主要 Lync Server 2010，则您还可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for Business Server 2015。 在此情况下，您将不能使用就地升级，而是使用 Lync Server 2010 与 Skype for Business Server 2015 直接共存。 不支持三项并存，但支持两项共存。  <br/> |
|Lync Server 2010  <br/> |打开新的 Skype for Business Server 2015 池，然后将用户迁移到此新池中。 随后即可停用旧的 Lync Server 2010 池。 从 Lync Server 2010 升级到 Skype for Business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。 请参阅[Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。  <br/> |
|Office Communications Server 2007 R2  <br/> | 选择两个选项之一： <br/>  设置新的 Skype 业务服务器 2015年环境。 <br/>  或者，如果您的硬件和软件满足业务服务器 2015 Skype 的要求，升级到 Lync Server 2013 并升级到 Skype 的业务服务器 2015年使用就地升级的新功能。 有关详细信息，请参阅[业务服务器 2015年的 Skype 的服务器要求](requirements-for-your-environment/server-requirements.md)和[Migration from Office Communications Server 2007 R2 至 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)。  <br/> |
   
> [!NOTE]
> SQL Server 2014 业务服务器 2015 Skype 中支持，但不是支持在 Lync Server 2013 中。 如果您想要从 SQL Server 2012 升级到 SQL Server 2014 然后池必须首先升级到 Skype 的业务服务器 2015 使用就地升级方法，如本文档中所述。 然后可以升级从 SQL Server 2014 到 SQL Server 2012，请参阅[升级到 SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)。 若要了解有关数据库要求的详细信息，请参阅[业务服务器 2015年的 Skype 的服务器要求](requirements-for-your-environment/server-requirements.md)。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>规划从 Lync Server 2013 升级到 Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以使用就地升级的新功能的业务服务器 2015年的升级到 Skype 的 Lync Server 2013 系统。 在就地升级提供一键式解决方案，备份证书、 卸载服务器组件、 升级本地数据库和安装业务服务器 2015年角色 Skype。 在就地升级搜寻要保留现有的硬件和服务器上的投资，从而减少了部署业务服务器 2015 Skype 的总成本。
  
> [!NOTE]
> 就地升级可以升级到 Skype 业务服务器时使用相同的硬件。 但是，重用同样的硬件不会转换为同样的性能容量。 不应期望 Lync Server 2013 和 Skype 的业务服务器 2015年相同的性能的负载。 
  
> [!NOTE]
> 在就地升级不支持高可用性或灾难恢复的 Skype 业务服务器。 
  
在就地升级涉及使 Lync Server 2013 池脱机和升级到业务服务器 2015年池 Skype。 
  
### <a name="create-an-in-place-upgrade-plan"></a>创建就地升级计划

制定一份包含以下元素的计划：
  
1. 了解当前拓扑。
    
    > [!NOTE]
    > 确保运行就地升级之前卸载 Lync Server 2013 的 LRS 管理工具。 Lync Server 2013 LRS 管理工具不能与 Skype 的业务服务器 2015年共存。 运行就地升级之后安装新的 LRS 管理工具，请参阅[Microsoft Lync 会议室系统管理 Web 门户网站的业务服务器 2015 Skype](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. 升级主池。
    
3. 是要升级存档和监控数据库还是新建相应的数据库。
    
4. 您将使用的就地升级方法：脱机或移动用户。在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。 
    
5. 面向受影响用户的交流计划。
    
6. 防止升级失败的备用计划。
    
在升级过程中，主池中的任何用户都无法使用服务，直至升级完成为止。 如果您有可以使用的辅助池，您可以在升级之前将其迁移到辅助池，避免影响用户。 升级后，将用户移到主池。
  
### <a name="in-place-upgrade-methods"></a>就地升级方法

有两种就地升级方案： 
  
- 移动用户方法，无需用户停机。 
    
- 脱机方法，需要停机。
    
我们推荐在维护时段内安排脱机方法升级，并通知用户注意停机时间。
  
> [!NOTE]
> 升级 Lync Server 2013 上的成对池时，需要将两个池都升级到 Skype for Business Server 2015。请确保在升级第一个池后，马上升级第二个池。如果一个池运行 Lync Server 2013，而第二个池运行 Skype for Business Server 2015，则灾难恢复选项将减到最少。例如，如果一个池运行 2013，第二个运行 2015，那么当灾难来临时，数据可能丢失，因为当成对池版本不同时，灾难模式不支持池故障转移。 
  
#### <a name="in-place-upgrade-offline-method"></a>就地升级脱机方法

如果您不想在两个用户池间移动用户，请使用此方法。 升级期间，用户将不能用于 Lync 或 Skype 业务服务。 
  
下图概述了此流程。
  
![Lync 2013 到 Skype 用户脱机](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 如果采用成对的池，不要在升级之前取消配对。 
  
在开始升级服务器池之前，必须完成整个池的升级。 Skype 业务服务器不支持具有仅升级的池的一部分。 
  
#### <a name="move-users-method-no-user-downtime"></a>移动用户方法（用户无需停机）
<a name="bkmk_MoveUsersMethod"> </a>

要使用这种方法，您要首先将用户移动到另一个池，然后开始升级。 升级期间，用户可以使用 Lync 服务。 它们移动到升级后的池后，他们可以 for Business 使用 Skype。 下图展示了此过程的概况。
  
> [!IMPORTANT]
> 在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。 PSTN 电话拨入式会议仍会将 ConferenceID 解析到正在升级的池，而不是配对的池。 因此，如果您仍希望在升级期间访问池中安排的 PSTN 会议，则需要移动会议目录。 
  
![泳道图，显示在升级池之前将用户迁移到另一个池，然后在升级完毕后再迁回原池。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>为硬件升级移动用户
<a name="bkmk_MoveUsersMethod"> </a>

 如果您的硬件不满足[业务服务器 2015年的 Skype 的服务器要求](requirements-for-your-environment/server-requirements.md)，设置新 Skype 业务服务器 2015年环境，并那里移动用户。 下图概述了从 Lync Server 2010 升级的流程。 
  
![泳道图，显示将 Lync Server 主前端池中的用户迁移到 Skype for Business Server 2015，并且停用 Lync Server 池。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>就地升级过程

 为业务服务器 2015 使用以下步骤从 Lync Server 2013 升级到 Skype:
  
1. 在升级之前备份所有数据库。
    
2. 确保要升级的所有服务都处于运行状态。
    
3. 使用拓扑生成器升级并发布拓扑文件。
    
4. 停止所有前端服务器上的全部服务。
    
5. 安装新 Skype 业务服务器所需的必备组件。
    
6. 在每台前端服务器上，开始就地升级。
    
7. 升级完成后，重启所有服务。
    
   - 对于前端池，使用命令 Start-CsPool 重启服务。
    
   - 对于非前端服务器，使用 Start-CSWindowsService。
    
> [!NOTE]
>  如果不想升级现有存档和监控数据库，请在升级拓扑之前移除依赖关系。 如果想创建新的存档和监控数据库，在升级过程中，可以创建新的 SQL 存储，并将其与池关联。 您可以找到有关如何执行此操作在主题中，[升级到业务服务器 2015年的 Skype](../deploy/upgrade-to-skype-for-business-server.md)的步骤。 > 就地升级不支持高可用性或灾难恢复的 Skype 业务服务器。 若要避免中断用户的服务，请 xds 副本处于最大可用空间的磁盘驱动器上的本地共享文件夹在升级过程中使用 upgrade.>[移动用户方法 （没有用户停机时间）](upgrade.md#bkmk_MoveUsersMethod) 。 如果该磁盘以后被删除，则您可以遇到服务未启动等问题。
  
### <a name="upgrade-order"></a>升级顺序

从内部拓扑升级至外部。 所有池首先都升级，然后边缘服务器和最后中央管理存储 (CMS) 池。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 身份验证考虑事项

如果为 Web 服务使用了 Kerberos 身份验证，则必须在就地升级完成后重新分配 Kerberos 帐户并重置密码。 若要了解如何执行此操作，请参阅[设置 Kerberos 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=530342)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>支持与 Lync Server 2013 和 Lync Server 2010 共存
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

你可以在与 Lync Server 2013 或 Lync Server 2010 相同的拓扑中运行 Skype for Business Server 2015，但是不能将三者同时置于同一个拓扑中。
  
如果 Lync Server 2010 和 Lync Server 2013 同时存在，建议将整个拓扑升级到 Lync Server 2013，然后再使用就地升级来升级到 Skype for Business Server 2015。 有关详细信息，请参阅[Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。
  
如果你的拓扑主要是 Lync Server 2010，请在将拓扑升级到 Skype for Business Server 2015 之前，将 Lync Server 2013 组件回退到 Lync Server 2010。在这种情况下，你将丧失就地升级的优势，并且具有 Lync Server 2010 与 Skype for Business Server 2015 同时存在的拓扑。
  
下图显示了使用 Lync Server 2013 和 Lync Server 2010 的业务服务器 2015 Skype 的共存支持。
  
![显示 Skype for Business Server 2015 与 Lync Server 2013 或 Lync Server 2010 共存支持的图表。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>现有 Survivable Branch Appliance 和服务器的升级流程
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype 的业务服务器 2015年不支持就地升级的 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS)。
  
但是，我们支持 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。 
  
规划采用关联分支就地升级 Lync Server 2013 前端 (FE) 池时，可以将现有用户留在 Lync Server 2013 SBA/SBS 上。 在升级过程中，SBA/SBS 用户将进入恢复模式，并在升级完成后返回正常功能。 恢复能力模式期间用户体验的详细信息，请参阅[Lync Server 2013 中的分支站点恢复能力功能](https://technet.microsoft.com/library/gg398715.aspx)。
  
将 Lync Server 2010 拓扑迁移到 Skype for Business Server 2015 时，与迁移到 Lync Server 2013 类似，必须将 SBA/SBS 重新添加到拓扑。 有关所需的步骤，请阅读[到 Lync Server 2013 前端池的连接 Survivable Branch Appliance](https://technet.microsoft.com/library/jj688026.aspx)。
  
为 Lync Server 2010 和 Lync Server 2013 的共存拓扑，对齐首先给与 Lync Server 2013 和 Lync Server 2010 共存支持一节中所做的建议。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[升级到 Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
