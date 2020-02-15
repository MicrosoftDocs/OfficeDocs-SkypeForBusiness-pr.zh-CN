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
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="9fb19-104">计划升级到 Skype for business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fb19-104">Plan to upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9fb19-105">摘要：了解在计划升级到 Skype for business Server 2015 时应考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="9fb19-105">Summary: Learn about the things you should consider when you plan an upgrade to Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-106">从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)：。</span><span class="sxs-lookup"><span data-stu-id="9fb19-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="9fb19-107">作为将升级到 Skype for business Server 2015 的计划的一部分，请使用本主题来了解推荐的 Skype for business Server 2015 升级路径、就地升级的工作方式、受支持的共存方案以及升级过程如下所示。</span><span class="sxs-lookup"><span data-stu-id="9fb19-107">As part of your plan to upgrade to Skype for Business Server 2015, use this topic to understand the recommended upgrade paths to Skype for Business Server 2015, how the In-Place Upgrade works, what the supported coexistence scenarios are, and what the upgrade process looks like.</span></span>

> [!NOTE]
> <span data-ttu-id="9fb19-108">Skype for Business Server 2015 中提供了就地升级，但 Skype for Business Server 2019 不再支持就地升级。</span><span class="sxs-lookup"><span data-stu-id="9fb19-108">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9fb19-109">支持并行共存，有关详细信息，请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="9fb19-109">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a><span data-ttu-id="9fb19-110">Skype for business Server 2015 的推荐升级路径</span><span class="sxs-lookup"><span data-stu-id="9fb19-110">Recommended upgrade paths to Skype for Business Server 2015</span></span>

 <span data-ttu-id="9fb19-111">若要从 Lync Server 2013、Lync Server 2010 或 Office 通信服务器 2007 R2 升级到 Skype for business Server 2015，请使用以下升级路径：</span><span class="sxs-lookup"><span data-stu-id="9fb19-111">To upgrade from Lync Server 2013, Lync Server 2010, or Office Communications Server 2007 R2 to Skype for Business Server 2015, use the following upgrade paths:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9fb19-112">就地升级会自动将会议目录从 Lync Server 2013 移动到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-112">In-Place Upgrade automatically moves conference directories from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-113">但是，如果您计划手动移动会议目录，请务必使用 Skype for Business Server 2015 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="9fb19-113">However, if you plan to manually move conference directories it is very important to use the Skype for Business Server 2015 Management Shell.</span></span> <span data-ttu-id="9fb19-114">如果您尝试使用 Lync Server 2013 命令行管理程序将会议目录从 Lync Server 2013 移动到 Skype for Business Server 2015，则可能会发生数据丢失。</span><span class="sxs-lookup"><span data-stu-id="9fb19-114">If you try to use the Lync Server 2013 Management Shell to move conference directories from Lync Server 2013 to Skype for Business Server 2015 then data loss can occur.</span></span> <span data-ttu-id="9fb19-115">通常情况下，无论您何时在任何容量中使用 Skype for Business Server 2015，都应使用 Skype for Business Server 2015 工具集。</span><span class="sxs-lookup"><span data-stu-id="9fb19-115">In general, whenever you are working with Skype for Business Server 2015 in any capacity you should use the Skype for Business Server 2015 tool set.</span></span>  
  
|<span data-ttu-id="9fb19-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="9fb19-116">**Version**</span></span>|<span data-ttu-id="9fb19-117">**推荐**</span><span class="sxs-lookup"><span data-stu-id="9fb19-117">**Recommendations**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9fb19-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fb19-118">Lync Server 2013</span></span>  <br/> | <span data-ttu-id="9fb19-119">若要进行升级，请在与池关联的每台服务器上使用 Skype for Business Server 拓扑生成器和新的就地升级功能。</span><span class="sxs-lookup"><span data-stu-id="9fb19-119">To upgrade, use the Skype for Business Server Topology Builder and the new In-Place Upgrade feature on each of the servers associated with the pool.</span></span> <span data-ttu-id="9fb19-120">有关详细步骤，请参阅[Plan to upgrade From Lync server 2013 To skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)和[upgrade to Skype for business server 2015](../deploy/upgrade-to-skype-for-business-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="9fb19-120">see [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps.</span></span> <br/> |
|<span data-ttu-id="9fb19-121">Lync Server 2010 + Lync Server 2013 （双模式）</span><span class="sxs-lookup"><span data-stu-id="9fb19-121">Lync Server 2010 + Lync Server 2013 (dual-mode)</span></span>  <br/> |<span data-ttu-id="9fb19-122">首先，升级到 Lync Server 2013，然后使用新的就地升级功能升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-122">First, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="9fb19-123">但是，如果拓扑是主 Lync Server 2010，您还可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-123">However, if your topology is primary Lync Server 2010 you can also roll back the Lync Server 2013 components to Lync Server 2010 and then upgrade directly to Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-124">在这种情况下，你将无法利用就地升级，并且将在 Lync Server 2010 和 Skype for Business Server 2015 之间使用直接共存性共存。</span><span class="sxs-lookup"><span data-stu-id="9fb19-124">In this case you would not be able to take advantage of In-Place Upgrade and would use straight co-existence between Lync Server 2010 and Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-125">不支持并存在三个存在，但支持共存。</span><span class="sxs-lookup"><span data-stu-id="9fb19-125">Tri-existence is not supported but co-existence is supported.</span></span>  <br/> |
|<span data-ttu-id="9fb19-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9fb19-126">Lync Server 2010</span></span>  <br/> |<span data-ttu-id="9fb19-127">打开新的 Skype for Business Server 2015 池，然后将用户迁移到此新池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-127">Bring up a new Skype for Business Server 2015 pool and then migrate users to this new pool.</span></span> <span data-ttu-id="9fb19-128">然后，您可以停用旧的 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-128">You can then decommission the old Lync Server 2010 pool.</span></span> <span data-ttu-id="9fb19-129">从 Lync Server 2010 升级到 Skype for business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9fb19-129">Upgrading from Lync Server 2010 to Skype for Business Server 2015 is similar to upgrading from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="9fb19-130">请参阅[从 Lync server 2010 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-130">See [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).</span></span>  <br/> |
|<span data-ttu-id="9fb19-131">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9fb19-131">Office Communications Server 2007 R2</span></span>  <br/> | <span data-ttu-id="9fb19-132">选择以下两个选项之一：</span><span class="sxs-lookup"><span data-stu-id="9fb19-132">Pick one of two options:</span></span> <br/>  <span data-ttu-id="9fb19-133">设置新的 Skype for Business Server 2015 环境。</span><span class="sxs-lookup"><span data-stu-id="9fb19-133">Set up a new Skype for Business Server 2015 environment.</span></span> <br/>  <span data-ttu-id="9fb19-134">或者，如果您的硬件和软件符合 Skype for business Server 2015 的要求，请升级到 Lync Server 2013，然后使用新的就地升级功能升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-134">Or if your hardware and software meet the requirements for Skype for Business Server 2015, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="9fb19-135">有关详细信息，请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)和[从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-135">For more information, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9fb19-136">Skype for Business Server 2015 支持 SQL Server 2014，但在 Lync Server 2013 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="9fb19-136">SQL Server 2014 is supported in Skype for Business Server 2015 but is not supported in Lync Server 2013.</span></span> <span data-ttu-id="9fb19-137">如果要从 SQL Server 2012 升级到 SQL Server 2014，则必须首先使用本文档中所述的就地升级方法将池升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-137">If you want to upgrade from SQL Server 2012 to SQL Server 2014 then the pool must first be upgraded to Skype for Business Server 2015 using the In-Place Upgrade method as described in this document.</span></span> <span data-ttu-id="9fb19-138">然后，可以从 SQL Server 2012 升级到 SQL Server 2014，请参阅[upgrade TO SQL server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-138">You can then upgrade from SQL Server 2012 to SQL Server 2014, see [Upgrade to SQL Server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx).</span></span> <span data-ttu-id="9fb19-139">若要了解有关数据库要求的详细信息，请参阅[Skype For Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-139">To learn more about database requirements, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md).</span></span> 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a><span data-ttu-id="9fb19-140">计划从 Lync Server 2013 升级到 Skype for business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fb19-140">Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015</span></span>
<span data-ttu-id="9fb19-141"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="9fb19-141"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

<span data-ttu-id="9fb19-142">您可以使用新的就地升级功能将 Lync Server 2013 系统升级到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-142">You can upgrade Lync Server 2013 systems to Skype for Business Server 2015 using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="9fb19-143">就地升级提供了一次单击解决方案来备份证书、卸载服务器组件、升级本地数据库以及安装 Skype for Business Server 2015 角色。</span><span class="sxs-lookup"><span data-stu-id="9fb19-143">In-place upgrade provides a one-click solution that backs up certificates, uninstalls server components, upgrades local databases, and installs the Skype for Business Server 2015 roles.</span></span> <span data-ttu-id="9fb19-144">就地升级旨在保留现有的硬件和服务器投资，降低部署 Skype for Business Server 2015 的总成本。</span><span class="sxs-lookup"><span data-stu-id="9fb19-144">In-place upgrade seeks to preserve existing hardware and server investments, reducing the overall cost to deploy Skype for Business Server 2015.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fb19-145">就地升级允许您在升级到 Skype for Business Server 时使用相同的硬件。</span><span class="sxs-lookup"><span data-stu-id="9fb19-145">In-Place Upgrade allows you to use the same hardware when upgrading to Skype for Business Server.</span></span> <span data-ttu-id="9fb19-146">但是，重复使用相同的硬件并不会转化为相同的性能容量。</span><span class="sxs-lookup"><span data-stu-id="9fb19-146">However, reusing the same hardware does not translate into the same performance capacity.</span></span> <span data-ttu-id="9fb19-147">您不应期望 Lync Server 2013 和 Skype for business Server 2015 的性能负载相同。</span><span class="sxs-lookup"><span data-stu-id="9fb19-147">You should not expect the performance loads for Lync Server 2013 and Skype for Business Server 2015 to be identical.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9fb19-148">就地升级不支持 Skype for business Server 的高可用性或灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="9fb19-148">In-Place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> 
  
<span data-ttu-id="9fb19-149">就地升级涉及将 Lync Server 2013 池脱机并将其升级到 Skype for Business Server 2015 池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-149">In-place upgrade involves taking the Lync Server 2013 pool offline and upgrading it to a Skype for Business Server 2015 pool.</span></span> 
  
### <a name="create-an-in-place-upgrade-plan"></a><span data-ttu-id="9fb19-150">创建就地升级计划</span><span class="sxs-lookup"><span data-stu-id="9fb19-150">Create an In-Place Upgrade plan</span></span>

<span data-ttu-id="9fb19-151">制定包括以下内容的计划：</span><span class="sxs-lookup"><span data-stu-id="9fb19-151">Make a plan that includes:</span></span>
  
1. <span data-ttu-id="9fb19-152">了解你当前的拓扑。</span><span class="sxs-lookup"><span data-stu-id="9fb19-152">An understanding of your current topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9fb19-153">在运行就地升级之前，请务必卸载 Lync Server 2013 的 LRS 管理工具。</span><span class="sxs-lookup"><span data-stu-id="9fb19-153">Be sure to uninstall LRS Admin tool for Lync Server 2013 before running In-Place Upgrade.</span></span> <span data-ttu-id="9fb19-154">Lync Server 2013 的 LRS 管理工具不能与 Skype for Business Server 2015 共存。</span><span class="sxs-lookup"><span data-stu-id="9fb19-154">The LRS Admin Tool for Lync Server 2013 cannot coexist with Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-155">运行就地升级后，安装新的 LRS 管理工具。</span><span class="sxs-lookup"><span data-stu-id="9fb19-155">After running In-Place Upgrade install the new LRS Admin tool.</span></span> <span data-ttu-id="9fb19-156">有关详细信息，请参阅适用于[Skype for Business Server 2015 的 Microsoft Lync 会议室系统管理 Web 门户](https://go.microsoft.com/fwlink/?LinkID=544807)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-156">See [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) for more details.</span></span>
  
2. <span data-ttu-id="9fb19-157">升级的主池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-157">The primary pool for the upgrade.</span></span>
    
3. <span data-ttu-id="9fb19-158">是否要升级存档和监控数据库或创建新数据库。</span><span class="sxs-lookup"><span data-stu-id="9fb19-158">Whether you'll upgrade the Archiving and Monitoring databases or create new ones.</span></span>
    
4. <span data-ttu-id="9fb19-159">将使用的就地升级方法： "脱机" 或 "移动用户"。</span><span class="sxs-lookup"><span data-stu-id="9fb19-159">The In-Place Upgrade method you'll use: Offline or Move Users.</span></span> <span data-ttu-id="9fb19-160">作为移动用户的一部分，您还需要迁移与主池关联的全局会议目录。</span><span class="sxs-lookup"><span data-stu-id="9fb19-160">As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> 
    
5. <span data-ttu-id="9fb19-161">受影响的用户的通信计划。</span><span class="sxs-lookup"><span data-stu-id="9fb19-161">A communication plan for impacted users.</span></span>
    
6. <span data-ttu-id="9fb19-162">在升级失败的情况下的备份计划。</span><span class="sxs-lookup"><span data-stu-id="9fb19-162">A backup plan in case the upgrades fails.</span></span>
    
<span data-ttu-id="9fb19-163">升级主池中的任何用户都不能使用这些服务，直到升级完成。</span><span class="sxs-lookup"><span data-stu-id="9fb19-163">Any users that are in the primary pool while it's being upgraded won't be able to use the services until the upgrade is complete.</span></span> <span data-ttu-id="9fb19-164">如果具有工作的辅助池，则可以在升级之前将其移动到辅助池，从而避免影响用户。</span><span class="sxs-lookup"><span data-stu-id="9fb19-164">If you have a working secondary pool, you can avoid impacting users by moving them to the secondary pool before the upgrade.</span></span> <span data-ttu-id="9fb19-165">升级后，将用户移回主池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-165">After the upgrade, move the users back to the primary pool.</span></span>
  
### <a name="in-place-upgrade-methods"></a><span data-ttu-id="9fb19-166">就地升级方法</span><span class="sxs-lookup"><span data-stu-id="9fb19-166">In-place upgrade methods</span></span>

<span data-ttu-id="9fb19-167">有两种就地升级方案：</span><span class="sxs-lookup"><span data-stu-id="9fb19-167">There are two scenarios for In-Place Upgrade:</span></span> 
  
- <span data-ttu-id="9fb19-168">移动用户方法，无需用户停机。</span><span class="sxs-lookup"><span data-stu-id="9fb19-168">The Move User method, which requires no downtime for users.</span></span> 
    
- <span data-ttu-id="9fb19-169">脱机方法，这需要停机时间。</span><span class="sxs-lookup"><span data-stu-id="9fb19-169">The Offline method, which requires downtime.</span></span>
    
<span data-ttu-id="9fb19-170">建议在维护窗口期间安排脱机方法升级，并通知用户停机时间。</span><span class="sxs-lookup"><span data-stu-id="9fb19-170">We recommend that an Offline method upgrade be scheduled during a maintenance window and users are notified of the downtime.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fb19-171">在 Lync Server 2013 上升级配对池时，若要将这两个池升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-171">When upgrading a paired pool on Lync Server 2013 and you want to upgrade both pools to Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-172">请确保在升级第一个池后立即升级第二个池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-172">Make sure to upgrade the second pool immediately after upgrading the first pool.</span></span> <span data-ttu-id="9fb19-173">当一个池运行 Lync Server 2013，而第二个池运行 Skype for Business Server 2015 时，将最大限度地减少灾难恢复选项。</span><span class="sxs-lookup"><span data-stu-id="9fb19-173">When one pool is running Lync Server 2013 and the second pool is running Skype for Business Server 2015 then disaster recovery options are minimized.</span></span> <span data-ttu-id="9fb19-174">例如，如果一个池运行的是2013，第二个是2015，并且发生了灾难，则可能会遇到数据丢失，因为在成对池不是相同版本时，灾难模式不支持池故障转移。</span><span class="sxs-lookup"><span data-stu-id="9fb19-174">For example, if one pool is running 2013 and the second is 2015 and there is a disaster then you could experience data loss because pool failover is not supported in disaster mode when paired pools are not the same version.</span></span> 
  
#### <a name="in-place-upgrade-offline-method"></a><span data-ttu-id="9fb19-175">就地升级脱机方法</span><span class="sxs-lookup"><span data-stu-id="9fb19-175">In-place upgrade Offline method</span></span>

<span data-ttu-id="9fb19-176">如果您不想在用户池之间移动用户，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="9fb19-176">Use this method if you don't want to move users between user pools.</span></span> <span data-ttu-id="9fb19-177">在升级过程中，用户将不能使用 Lync 或 Skype for Business 服务。</span><span class="sxs-lookup"><span data-stu-id="9fb19-177">During the upgrade, users will not be able to use Lync or Skype for Business services.</span></span> 
  
<span data-ttu-id="9fb19-178">下图显示了此过程的概述。</span><span class="sxs-lookup"><span data-stu-id="9fb19-178">The following diagram shows an overview of this process.</span></span>
  
![Lync 2013 到 Skype 用户脱机](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> <span data-ttu-id="9fb19-180">如果您具有配对的池，请不要在升级前 unpair 它们。</span><span class="sxs-lookup"><span data-stu-id="9fb19-180">If you have paired pools, do not unpair them before the upgrade.</span></span> 
  
<span data-ttu-id="9fb19-181">在开始升级服务器池之后，必须完成整个池的升级。</span><span class="sxs-lookup"><span data-stu-id="9fb19-181">Once you start to upgrade a server pool, you must complete the upgrade of the entire pool.</span></span> <span data-ttu-id="9fb19-182">Skype for Business Server 不支持仅将一部分升级到池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-182">Skype for Business Server doesn't support having only a portion of the pool upgraded.</span></span> 
  
#### <a name="move-users-method-no-user-downtime"></a><span data-ttu-id="9fb19-183">移动 Users 方法（无用户停机）</span><span class="sxs-lookup"><span data-stu-id="9fb19-183">Move Users method (no user downtime)</span></span>
<span data-ttu-id="9fb19-184"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="9fb19-184"><a name="bkmk_MoveUsersMethod"> </a></span></span>

<span data-ttu-id="9fb19-185">若要使用此方法，请在开始升级之前，将用户移动到另一个池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-185">To use this method, you move users to another pool before you start the upgrade.</span></span> <span data-ttu-id="9fb19-186">在升级期间，用户可以使用 Lync 服务。</span><span class="sxs-lookup"><span data-stu-id="9fb19-186">During the upgrade, users can use Lync services.</span></span> <span data-ttu-id="9fb19-187">在将其移动到已升级的池之后，可以使用 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="9fb19-187">After they're moved to the upgraded pool, they can use Skype for Business.</span></span> <span data-ttu-id="9fb19-188">下图显示了此过程的概述。</span><span class="sxs-lookup"><span data-stu-id="9fb19-188">The following diagram shows an overview of this process.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9fb19-189">作为移动用户的一部分，您还需要迁移与主池关联的全局会议目录。</span><span class="sxs-lookup"><span data-stu-id="9fb19-189">As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> <span data-ttu-id="9fb19-190">PSTN 电话拨入式会议仍会将 ConferenceID 解析为要升级的池，而不是配对的池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-190">PSTN dial-in conferencing will still resolve ConferenceID to the pool being upgraded, instead of the paired pool.</span></span> <span data-ttu-id="9fb19-191">因此，如果您仍希望在升级过程中可访问池中安排的 PSTN 会议，则需要移动会议目录。</span><span class="sxs-lookup"><span data-stu-id="9fb19-191">So you need to move Conference Directories, if you still want PSTN conferences scheduled in the pool to be accessible during upgrade.</span></span> 
  
![显示在升级池之前将用户移动到另一个池并将其移回池的泳道图。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a><span data-ttu-id="9fb19-193">移动用户以进行硬件升级</span><span class="sxs-lookup"><span data-stu-id="9fb19-193">Move users for hardware upgrade</span></span>
<span data-ttu-id="9fb19-194"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="9fb19-194"><a name="bkmk_MoveUsersMethod"> </a></span></span>

 <span data-ttu-id="9fb19-195">如果您的硬件不符合[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)，请设置新的 Skype For business server 2015 环境，并将用户移动到此处。</span><span class="sxs-lookup"><span data-stu-id="9fb19-195">If your hardware doesn't meet the [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md), set up a new Skype for Business Server 2015 environment, and move users there.</span></span> <span data-ttu-id="9fb19-196">下图显示了从 Lync Server 2010 升级的这一过程的概述。</span><span class="sxs-lookup"><span data-stu-id="9fb19-196">The following diagram shows an overview of this process for upgrade from Lync Server 2010.</span></span> 
  
![泳道图，显示移动到 Skype for business Server 2015 的 Lync Server 主前端池中的用户和取消阻止的 Lync Server 池的用户。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a><span data-ttu-id="9fb19-198">就地升级过程</span><span class="sxs-lookup"><span data-stu-id="9fb19-198">In-place upgrade process</span></span>

 <span data-ttu-id="9fb19-199">使用以下步骤从 Lync Server 2013 升级到 Skype for business Server 2015：</span><span class="sxs-lookup"><span data-stu-id="9fb19-199">Upgrade from Lync Server 2013 to Skype for Business Server 2015 using the following steps:</span></span>
  
1. <span data-ttu-id="9fb19-200">在升级之前备份所有数据库。</span><span class="sxs-lookup"><span data-stu-id="9fb19-200">Back up all databases before the upgrade.</span></span>
    
2. <span data-ttu-id="9fb19-201">请确保要升级的所有服务处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="9fb19-201">Make sure all services that are to be upgraded are in a running state.</span></span>
    
3. <span data-ttu-id="9fb19-202">使用拓扑生成器升级和发布拓扑文件。</span><span class="sxs-lookup"><span data-stu-id="9fb19-202">Upgrade and publish the topology file using the topology builder.</span></span>
    
4. <span data-ttu-id="9fb19-203">停止所有前端服务器上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="9fb19-203">Stop all services on all Front End servers.</span></span>
    
5. <span data-ttu-id="9fb19-204">安装 Skype for business Server 所需的新必备组件。</span><span class="sxs-lookup"><span data-stu-id="9fb19-204">Install new prerequisites required for Skype for Business Server.</span></span>
    
6. <span data-ttu-id="9fb19-205">在每个前端服务器上，启动就地升级。</span><span class="sxs-lookup"><span data-stu-id="9fb19-205">On each Front End server, start the In-Place Upgrade.</span></span>
    
7. <span data-ttu-id="9fb19-206">升级完成后，重新启动所有服务。</span><span class="sxs-lookup"><span data-stu-id="9fb19-206">When the upgrade is complete, restart all services.</span></span>
    
   - <span data-ttu-id="9fb19-207">对于前端池，使用命令 Start-cspool 重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="9fb19-207">For the Front End pool, restart services using the command Start-CsPool.</span></span>
    
   - <span data-ttu-id="9fb19-208">对于非前端服务器，请使用 Start-cswindowsservice。</span><span class="sxs-lookup"><span data-stu-id="9fb19-208">For non-Front End servers, use Start-CSWindowsService.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="9fb19-209">如果您不想升级现有的存档和监控数据库，请在升级拓扑之前删除依赖项。</span><span class="sxs-lookup"><span data-stu-id="9fb19-209">If you don't want to upgrade your existing Archiving and Monitoring databases, remove the dependency before you upgrade the topology.</span></span> <span data-ttu-id="9fb19-210">如果要创建新的存档和监控数据库，则在升级过程中，可以创建新的 SQL 存储并将其与池相关联。</span><span class="sxs-lookup"><span data-stu-id="9fb19-210">If you want to create new Archiving and Monitoring databases, during the upgrade, you can create a new SQL store and associate it with the pool.</span></span> <span data-ttu-id="9fb19-211">若要了解如何执行此操作的步骤，请参阅[升级到 Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)主题。</span><span class="sxs-lookup"><span data-stu-id="9fb19-211">You can find the steps on how to do this in the topic,[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md).</span></span> <span data-ttu-id="9fb19-212">> 就地升级不支持 Skype for business Server 的高可用性或灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="9fb19-212">>  In-place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> <span data-ttu-id="9fb19-213">若要避免中断用户的服务，请使用[Move users 方法（无用户停机时间）](upgrade.md#bkmk_MoveUsersMethod)进行升级。在升级过程中 >，xds 将放置在具有最大可用空间的磁盘驱动器上的本地共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9fb19-213">To avoid interrupting users' services, use the [Move Users method (no user downtime)](upgrade.md#bkmk_MoveUsersMethod) to upgrade.>  During the upgrade process the xds-replica is placed in the local shared folder on the disk drive with the most free space.</span></span> <span data-ttu-id="9fb19-214">如果稍后删除该磁盘，则可以遇到诸如服务未启动等问题。</span><span class="sxs-lookup"><span data-stu-id="9fb19-214">If that disk is later removed then you can run into issues such as services not starting.</span></span>
  
### <a name="upgrade-order"></a><span data-ttu-id="9fb19-215">升级顺序</span><span class="sxs-lookup"><span data-stu-id="9fb19-215">Upgrade order</span></span>

<span data-ttu-id="9fb19-216">将拓扑从内部升级到外部。</span><span class="sxs-lookup"><span data-stu-id="9fb19-216">Upgrade the topology from the inside to the outside.</span></span> <span data-ttu-id="9fb19-217">先升级所有池，然后升级边缘服务器，最后升级到中央管理存储（CMS）池。</span><span class="sxs-lookup"><span data-stu-id="9fb19-217">Upgrade all your pools first, then the edge servers, and finally the Central Management Store (CMS) pool.</span></span> 
  
### <a name="kerberos-authentication-considerations"></a><span data-ttu-id="9fb19-218">Kerberos 身份验证注意事项</span><span class="sxs-lookup"><span data-stu-id="9fb19-218">Kerberos authentication considerations</span></span>

<span data-ttu-id="9fb19-219">如果对 Web 服务使用 Kerberos 身份验证，则必须在就地升级完成后重新分配 Kerberos 帐户并重置密码。</span><span class="sxs-lookup"><span data-stu-id="9fb19-219">If you use Kerberos authentication for Web Services, you must reassign Kerberos accounts and reset the password after the In-Place Upgrade is complete.</span></span> <span data-ttu-id="9fb19-220">若要了解如何执行此操作，请参阅[设置 Kerberos 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=530342)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-220">To learn how to do this, see [Setting up Kerberos authentication](https://go.microsoft.com/fwlink/p/?LinkId=530342).</span></span>
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a><span data-ttu-id="9fb19-221">支持 Lync Server 2013 和 Lync Server 2010 共存</span><span class="sxs-lookup"><span data-stu-id="9fb19-221">Support for coexistence with Lync Server 2013 and Lync Server 2010</span></span>
<span data-ttu-id="9fb19-222"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="9fb19-222"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

<span data-ttu-id="9fb19-223">您可以在与 Lync Server 2013 或 Lync Server 2010 相同的拓扑中运行 Skype for Business Server 2015，但不能将所有三个在同一个拓扑中。</span><span class="sxs-lookup"><span data-stu-id="9fb19-223">You can run Skype for Business Server 2015 in the same topology as Lync Server 2013 or Lync Server 2010, but you can't have all three in the same topology.</span></span>
  
<span data-ttu-id="9fb19-224">如果您在 Lync Server 2010 和 Lync Server 2013 之间存在共存，建议将整个拓扑升级到 Lync Server 2013，然后使用就地升级升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-224">If you have a co-existence between Lync Server 2010 and Lync Server 2013, it is recommended to upgrade the entire topology to Lync Server 2013, and then upgrade to Skype for Business Server 2015 using the In-Place Upgrade.</span></span> <span data-ttu-id="9fb19-225">有关详细信息，请参阅[从 Lync server 2010 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-225">For more information, see [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).</span></span>
  
<span data-ttu-id="9fb19-226">如果拓扑主要是 Lync Server 2010，请先将 Lync Server 2013 组件回滚到 Lync Server 2010，然后再将拓扑升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9fb19-226">If your topology is primarily Lync Server 2010, roll back the Lync Server 2013 components to Lync Server 2010 before upgrading the topology to Skype for Business Server 2015.</span></span> <span data-ttu-id="9fb19-227">在这种情况下，您将失去就地升级的优势，并在 Lync Server 2010 和 Skype for business Server 2015 之间存在共存拓扑。</span><span class="sxs-lookup"><span data-stu-id="9fb19-227">In this case, you lose the benefit of the In-Place Upgrade and have a co-existence topology between Lync Server 2010 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9fb19-228">下图显示了 Skype for business Server 2015 with Lync Server 2013 和 Lync Server 2010 的共存支持。</span><span class="sxs-lookup"><span data-stu-id="9fb19-228">The following diagram shows the coexistence support of Skype for Business Server 2015 with Lync Server 2013 and Lync Server 2010.</span></span>
  
![显示共存支持的 Skype for business Server 2015 与 Lync Server 2013 或 Lync Server 2010 的关系图。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a><span data-ttu-id="9fb19-230">现有 Survivable 分支设备和服务器的升级过程</span><span class="sxs-lookup"><span data-stu-id="9fb19-230">Upgrade process with existing Survivable Branch Appliance and Server</span></span>
<span data-ttu-id="9fb19-231"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="9fb19-231"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

<span data-ttu-id="9fb19-232">Skype for Business Server 2015 不支持 Survivable 分支装置（SBA）或 Survivable 分支服务器（SBS）的就地升级。</span><span class="sxs-lookup"><span data-stu-id="9fb19-232">Skype for Business Server 2015 doesn't support an In-Place Upgrade of a Survivable Branch Appliance (SBA) or a Survivable Branch Server (SBS).</span></span>
  
<span data-ttu-id="9fb19-233">但是，我们支持将 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。</span><span class="sxs-lookup"><span data-stu-id="9fb19-233">However, we do support coexistence of Skype for Business Server datacenters with Lync Server 2010 or Lync Server 2013 SBA/SBS.</span></span> 
  
<span data-ttu-id="9fb19-234">当规划具有关联分支的 Lync Server 2013 前端（FE）池的就地升级时，您可以将现有用户保留在 Lync Server 2013 SBA/SBS 上。</span><span class="sxs-lookup"><span data-stu-id="9fb19-234">When planning for an In-Place Upgrade of a Lync Server 2013 Front End (FE) pool with an associated branch, you can leave the existing users on the Lync Server 2013 SBA/SBS.</span></span> <span data-ttu-id="9fb19-235">在升级过程中，SBA/SBS 用户将进入恢复模式，并将在升级完成后返回到正常功能。</span><span class="sxs-lookup"><span data-stu-id="9fb19-235">During the upgrade, the SBA/SBS users will go in resiliency mode and will return to normal functionality after the upgrade has completed.</span></span> <span data-ttu-id="9fb19-236">有关在恢复模式期间用户体验的详细信息，请参阅[Lync Server 2013 中的分支站点恢复功能](https://technet.microsoft.com/library/gg398715.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-236">For more information about the users' experience during the resiliency mode, please see [Branch-site resiliency features in Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).</span></span>
  
<span data-ttu-id="9fb19-237">将 Lync Server 2010 拓扑迁移到 Skype for business Server 2015 时，必须将 SBA/SBS 重新添加到拓扑中，类似于迁移到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9fb19-237">When migrating a Lync Server 2010 topology to Skype for Business Server 2015, the SBA/SBS must re-added to the topology, similar to the migration to Lync Server 2013.</span></span> <span data-ttu-id="9fb19-238">有关所需步骤，请阅读[连接 Survivable 分支设备到 Lync Server 2013 前端池](https://technet.microsoft.com/library/jj688026.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9fb19-238">For the required steps, please read [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](https://technet.microsoft.com/library/jj688026.aspx).</span></span>
  
<span data-ttu-id="9fb19-239">对于 Lync Server 2010 和 Lync Server 2013 的共存拓扑，请先与 "支持 Lync Server 2013 和 Lync Server 2010 共存" 一节中的建议进行校准。</span><span class="sxs-lookup"><span data-stu-id="9fb19-239">For co-existence topologies of Lync Server 2010 and Lync Server 2013, align first to the recommendations made in the section 'Support for coexistence with Lync Server 2013 and Lync Server 2010'.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fb19-240">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fb19-240">See also</span></span>
<span data-ttu-id="9fb19-241"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="9fb19-241"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span></span>

[<span data-ttu-id="9fb19-242">升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9fb19-242">Upgrade to Skype for Business Server 2015</span></span>](../deploy/upgrade-to-skype-for-business-server.md)
  
[<span data-ttu-id="9fb19-243">Skype for business Server 2015 的环境要求</span><span class="sxs-lookup"><span data-stu-id="9fb19-243">Environmental requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/environmental-requirements.md)
  
[<span data-ttu-id="9fb19-244">Skype for business Server 2015 的服务器要求</span><span class="sxs-lookup"><span data-stu-id="9fb19-244">Server requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/server-requirements.md)
