---
title: 计划升级到 Skype for business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 摘要：了解在计划升级到 Skype for business Server 2015 时应考虑的事项。 从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030636"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>计划升级到 Skype for business Server 2015
 
摘要：了解在计划升级到 Skype for business Server 2015 时应考虑的事项。 从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)：。
  
作为将升级到 Skype for business Server 2015 的计划的一部分，请使用本主题来了解推荐的 Skype for business Server 2015 升级路径、就地升级的工作方式、受支持的共存方案以及升级过程如下所示。

> [!NOTE]
> Skype for Business Server 2015 中提供了就地升级，但 Skype for Business Server 2019 不再支持就地升级。 支持并行共存，有关详细信息，请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Skype for business Server 2015 的推荐升级路径

 若要从 Lync Server 2013、Lync Server 2010 或 Office 通信服务器 2007 R2 升级到 Skype for business Server 2015，请使用以下升级路径：
  
> [!CAUTION]
> 就地升级会自动将会议目录从 Lync Server 2013 移动到 Skype for business Server 2015。 但是，如果您计划手动移动会议目录，请务必使用 Skype for Business Server 2015 命令行管理程序。 如果您尝试使用 Lync Server 2013 命令行管理程序将会议目录从 Lync Server 2013 移动到 Skype for Business Server 2015，则可能会发生数据丢失。 通常情况下，无论您何时在任何容量中使用 Skype for Business Server 2015，都应使用 Skype for Business Server 2015 工具集。  
  
|**版本**|**推荐**|
|:-----|:-----|
|Lync Server 2013  <br/> | 若要进行升级，请在与池关联的每台服务器上使用 Skype for Business Server 拓扑生成器和新的就地升级功能。 有关详细步骤，请参阅[Plan to upgrade From Lync server 2013 To skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)和[upgrade to Skype for business server 2015](../deploy/upgrade-to-skype-for-business-server.md) 。 <br/> |
|Lync Server 2010 + Lync Server 2013 （双模式）  <br/> |首先，升级到 Lync Server 2013，然后使用新的就地升级功能升级到 Skype for Business Server 2015。 但是，如果拓扑是主 Lync Server 2010，您还可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for business Server 2015。 在这种情况下，你将无法利用就地升级，并且将在 Lync Server 2010 和 Skype for Business Server 2015 之间使用直接共存性共存。 不支持并存在三个存在，但支持共存。  <br/> |
|Lync Server 2010  <br/> |打开新的 Skype for Business Server 2015 池，然后将用户迁移到此新池。 然后，您可以停用旧的 Lync Server 2010 池。 从 Lync Server 2010 升级到 Skype for business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。 请参阅[从 Lync server 2010 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。  <br/> |
|Office Communications Server 2007 R2  <br/> | 选择以下两个选项之一： <br/>  设置新的 Skype for Business Server 2015 环境。 <br/>  或者，如果您的硬件和软件符合 Skype for business Server 2015 的要求，请升级到 Lync Server 2013，然后使用新的就地升级功能升级到 Skype for Business Server 2015。 有关详细信息，请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)和[从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)。  <br/> |
   
> [!NOTE]
> Skype for Business Server 2015 支持 SQL Server 2014，但在 Lync Server 2013 中不受支持。 如果要从 SQL Server 2012 升级到 SQL Server 2014，则必须首先使用本文档中所述的就地升级方法将池升级到 Skype for Business Server 2015。 然后，可以从 SQL Server 2012 升级到 SQL Server 2014，请参阅[upgrade TO SQL server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx)。 若要了解有关数据库要求的详细信息，请参阅[Skype For Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>计划从 Lync Server 2013 升级到 Skype for business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以使用新的就地升级功能将 Lync Server 2013 系统升级到 Skype for business Server 2015。 就地升级提供了一次单击解决方案来备份证书、卸载服务器组件、升级本地数据库以及安装 Skype for Business Server 2015 角色。 就地升级旨在保留现有的硬件和服务器投资，降低部署 Skype for Business Server 2015 的总成本。
  
> [!NOTE]
> 就地升级允许您在升级到 Skype for Business Server 时使用相同的硬件。 但是，重复使用相同的硬件并不会转化为相同的性能容量。 您不应期望 Lync Server 2013 和 Skype for business Server 2015 的性能负载相同。 
  
> [!NOTE]
> 就地升级不支持 Skype for business Server 的高可用性或灾难恢复。 
  
就地升级涉及将 Lync Server 2013 池脱机并将其升级到 Skype for Business Server 2015 池。 
  
### <a name="create-an-in-place-upgrade-plan"></a>创建就地升级计划

制定包括以下内容的计划：
  
1. 了解你当前的拓扑。
    
    > [!NOTE]
    > 在运行就地升级之前，请务必卸载 Lync Server 2013 的 LRS 管理工具。 Lync Server 2013 的 LRS 管理工具不能与 Skype for Business Server 2015 共存。 运行就地升级后，安装新的 LRS 管理工具。 有关详细信息，请参阅适用于[Skype for Business Server 2015 的 Microsoft Lync 会议室系统管理 Web 门户](https://go.microsoft.com/fwlink/?LinkID=544807)。
  
2. 升级的主池。
    
3. 是否要升级存档和监控数据库或创建新数据库。
    
4. 将使用的就地升级方法： "脱机" 或 "移动用户"。 作为移动用户的一部分，您还需要迁移与主池关联的全局会议目录。 
    
5. 受影响的用户的通信计划。
    
6. 在升级失败的情况下的备份计划。
    
升级主池中的任何用户都不能使用这些服务，直到升级完成。 如果具有工作的辅助池，则可以在升级之前将其移动到辅助池，从而避免影响用户。 升级后，将用户移回主池。
  
### <a name="in-place-upgrade-methods"></a>就地升级方法

有两种就地升级方案： 
  
- 移动用户方法，无需用户停机。 
    
- 脱机方法，这需要停机时间。
    
建议在维护窗口期间安排脱机方法升级，并通知用户停机时间。
  
> [!NOTE]
> 在 Lync Server 2013 上升级配对池时，若要将这两个池升级到 Skype for Business Server 2015。 请确保在升级第一个池后立即升级第二个池。 当一个池运行 Lync Server 2013，而第二个池运行 Skype for Business Server 2015 时，将最大限度地减少灾难恢复选项。 例如，如果一个池运行的是2013，第二个是2015，并且发生了灾难，则可能会遇到数据丢失，因为在成对池不是相同版本时，灾难模式不支持池故障转移。 
  
#### <a name="in-place-upgrade-offline-method"></a>就地升级脱机方法

如果您不想在用户池之间移动用户，请使用此方法。 在升级过程中，用户将不能使用 Lync 或 Skype for Business 服务。 
  
下图显示了此过程的概述。
  
![Lync 2013 到 Skype 用户脱机](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 如果您具有配对的池，请不要在升级前 unpair 它们。 
  
在开始升级服务器池之后，必须完成整个池的升级。 Skype for Business Server 不支持仅将一部分升级到池。 
  
#### <a name="move-users-method-no-user-downtime"></a>移动 Users 方法（无用户停机）
<a name="bkmk_MoveUsersMethod"> </a>

若要使用此方法，请在开始升级之前，将用户移动到另一个池。 在升级期间，用户可以使用 Lync 服务。 在将其移动到已升级的池之后，可以使用 Skype for Business。 下图显示了此过程的概述。
  
> [!IMPORTANT]
> 作为移动用户的一部分，您还需要迁移与主池关联的全局会议目录。 PSTN 电话拨入式会议仍会将 ConferenceID 解析为要升级的池，而不是配对的池。 因此，如果您仍希望在升级过程中可访问池中安排的 PSTN 会议，则需要移动会议目录。 
  
![显示在升级池之前将用户移动到另一个池并将其移回池的泳道图。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>移动用户以进行硬件升级
<a name="bkmk_MoveUsersMethod"> </a>

 如果您的硬件不符合[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)，请设置新的 Skype For business server 2015 环境，并将用户移动到此处。 下图显示了从 Lync Server 2010 升级的这一过程的概述。 
  
![泳道图，显示移动到 Skype for business Server 2015 的 Lync Server 主前端池中的用户和取消阻止的 Lync Server 池的用户。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>就地升级过程

 使用以下步骤从 Lync Server 2013 升级到 Skype for business Server 2015：
  
1. 在升级之前备份所有数据库。
    
2. 请确保要升级的所有服务处于运行状态。
    
3. 使用拓扑生成器升级和发布拓扑文件。
    
4. 停止所有前端服务器上的所有服务。
    
5. 安装 Skype for business Server 所需的新必备组件。
    
6. 在每个前端服务器上，启动就地升级。
    
7. 升级完成后，重新启动所有服务。
    
   - 对于前端池，使用命令 Start-cspool 重新启动服务。
    
   - 对于非前端服务器，请使用 Start-cswindowsservice。
    
> [!NOTE]
>  如果您不想升级现有的存档和监控数据库，请在升级拓扑之前删除依赖项。 如果要创建新的存档和监控数据库，则在升级过程中，可以创建新的 SQL 存储并将其与池相关联。 若要了解如何执行此操作的步骤，请参阅[升级到 Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)主题。 > 就地升级不支持 Skype for business Server 的高可用性或灾难恢复。 若要避免中断用户的服务，请使用[Move users 方法（无用户停机时间）](upgrade.md#bkmk_MoveUsersMethod)进行升级。在升级过程中 >，xds 将放置在具有最大可用空间的磁盘驱动器上的本地共享文件夹中。 如果稍后删除该磁盘，则可以遇到诸如服务未启动等问题。
  
### <a name="upgrade-order"></a>升级顺序

将拓扑从内部升级到外部。 先升级所有池，然后升级边缘服务器，最后升级到中央管理存储（CMS）池。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 身份验证注意事项

如果对 Web 服务使用 Kerberos 身份验证，则必须在就地升级完成后重新分配 Kerberos 帐户并重置密码。 若要了解如何执行此操作，请参阅[设置 Kerberos 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=530342)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>支持 Lync Server 2013 和 Lync Server 2010 共存
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以在与 Lync Server 2013 或 Lync Server 2010 相同的拓扑中运行 Skype for Business Server 2015，但不能将所有三个在同一个拓扑中。
  
如果您在 Lync Server 2010 和 Lync Server 2013 之间存在共存，建议将整个拓扑升级到 Lync Server 2013，然后使用就地升级升级到 Skype for Business Server 2015。 有关详细信息，请参阅[从 Lync server 2010 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。
  
如果拓扑主要是 Lync Server 2010，请先将 Lync Server 2013 组件回滚到 Lync Server 2010，然后再将拓扑升级到 Skype for Business Server 2015。 在这种情况下，您将失去就地升级的优势，并在 Lync Server 2010 和 Skype for business Server 2015 之间存在共存拓扑。
  
下图显示了 Skype for business Server 2015 with Lync Server 2013 和 Lync Server 2010 的共存支持。
  
![显示共存支持的 Skype for business Server 2015 与 Lync Server 2013 或 Lync Server 2010 的关系图。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>现有 Survivable 分支设备和服务器的升级过程
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 不支持 Survivable 分支装置（SBA）或 Survivable 分支服务器（SBS）的就地升级。
  
但是，我们支持将 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。 
  
当规划具有关联分支的 Lync Server 2013 前端（FE）池的就地升级时，您可以将现有用户保留在 Lync Server 2013 SBA/SBS 上。 在升级过程中，SBA/SBS 用户将进入恢复模式，并将在升级完成后返回到正常功能。 有关在恢复模式期间用户体验的详细信息，请参阅[Lync Server 2013 中的分支站点恢复功能](https://technet.microsoft.com/library/gg398715.aspx)。
  
将 Lync Server 2010 拓扑迁移到 Skype for business Server 2015 时，必须将 SBA/SBS 重新添加到拓扑中，类似于迁移到 Lync Server 2013。 有关所需步骤，请阅读[连接 Survivable 分支设备到 Lync Server 2013 前端池](https://technet.microsoft.com/library/jj688026.aspx)。
  
对于 Lync Server 2010 和 Lync Server 2013 的共存拓扑，请先与 "支持 Lync Server 2013 和 Lync Server 2010 共存" 一节中的建议进行校准。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[升级到 Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Skype for business Server 2015 的环境要求](requirements-for-your-environment/environmental-requirements.md)
  
[Skype for business Server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)
