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
ms.openlocfilehash: 0f7473bac98ede76763a3f5bda8aee3484c3c03f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222129"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="09b2c-104">规划升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09b2c-104">Plan to upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09b2c-105">摘要: 了解在计划升级到 Skype for Business 服务器2015时应考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="09b2c-105">Summary: Learn about the things you should consider when you plan an upgrade to Skype for Business Server 2015.</span></span> <span data-ttu-id="09b2c-106">从 Microsoft 评估中心的以下位置下载 Skype for business Server 2015 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):。</span><span class="sxs-lookup"><span data-stu-id="09b2c-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="09b2c-107">作为计划升级到 Skype for Business Server 2015 的一部分, 请使用本主题了解推荐的 Skype for business Server 2015 升级路径、就地升级的工作方式、受支持的共存方案以及升级过程如下所示。</span><span class="sxs-lookup"><span data-stu-id="09b2c-107">As part of your plan to upgrade to Skype for Business Server 2015, use this topic to understand the recommended upgrade paths to Skype for Business Server 2015, how the In-Place Upgrade works, what the supported coexistence scenarios are, and what the upgrade process looks like.</span></span>

> [!NOTE]
> <span data-ttu-id="09b2c-108">Skype for business Server 2015 中提供了就地升级, 但 Skype for business Server 2019 不再支持就地升级。</span><span class="sxs-lookup"><span data-stu-id="09b2c-108">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="09b2c-109">支持 "并排 coexistance", 有关详细信息, 请参阅[迁移到 Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="09b2c-109">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a><span data-ttu-id="09b2c-110">Skype for business Server 2015 的推荐升级路径</span><span class="sxs-lookup"><span data-stu-id="09b2c-110">Recommended upgrade paths to Skype for Business Server 2015</span></span>

 <span data-ttu-id="09b2c-111">若要从 Lync Server 2013、Lync Server 2010 或 Office 通信服务器 2007 R2 升级到 Skype for Business Server 2015, 请使用以下升级路径:</span><span class="sxs-lookup"><span data-stu-id="09b2c-111">To upgrade from Lync Server 2013, Lync Server 2010, or Office Communications Server 2007 R2 to Skype for Business Server 2015, use the following upgrade paths:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="09b2c-p104">就地升级可将会议目录从 Lync Server 2013 自动移至 Skype for Business Server 2015。但是，如果您计划手动移动会议目录，就务必使用 Skype for Business Server 2015 命令行管理程序。如果您尝试使用 Lync Server 2013 命令行管理程序将会议目录从 Lync Server 2013 移至 Skype for Business Server 2015，则可能出现数据丢失。一般来讲，无论您何时使用任意容量的 Skype for Business Server 2015，都应使用 Skype for Business Server 2015 工具集。</span><span class="sxs-lookup"><span data-stu-id="09b2c-p104">In-Place Upgrade automatically moves conference directories from Lync Server 2013 to Skype for Business Server 2015. However, if you plan to manually move conference directories it is very important to use the Skype for Business Server 2015 Management Shell. If you try to use the Lync Server 2013 Management Shell to move conference directories from Lync Server 2013 to Skype for Business Server 2015 then data loss can occur. In general, whenever you are working with Skype for Business Server 2015 in any capacity you should use the Skype for Business Server 2015 tool set.</span></span>  
  
|<span data-ttu-id="09b2c-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="09b2c-116">**Version**</span></span>|<span data-ttu-id="09b2c-117">**建议**</span><span class="sxs-lookup"><span data-stu-id="09b2c-117">**Recommendations**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09b2c-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b2c-118">Lync Server 2013</span></span>  <br/> | <span data-ttu-id="09b2c-119">若要升级, 请使用 Skype for Business Server 拓扑生成器以及与池关联的每个服务器上新的就地升级功能。</span><span class="sxs-lookup"><span data-stu-id="09b2c-119">To upgrade, use the Skype for Business Server Topology Builder and the new In-Place Upgrade feature on each of the servers associated with the pool.</span></span> <span data-ttu-id="09b2c-120">请参阅[计划从 Lync Server 2013 升级到 skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)并[升级到 Skype for business server 2015](../deploy/upgrade-to-skype-for-business-server.md) , 了解详细步骤。</span><span class="sxs-lookup"><span data-stu-id="09b2c-120">see [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps.</span></span> <br/> |
|<span data-ttu-id="09b2c-121">Lync Server 2010 + Lync Server 2013（双模式）</span><span class="sxs-lookup"><span data-stu-id="09b2c-121">Lync Server 2010 + Lync Server 2013 (dual-mode)</span></span>  <br/> |<span data-ttu-id="09b2c-122">首先, 升级到 Lync Server 2013, 然后使用新的就地升级功能升级到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="09b2c-122">First, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="09b2c-123">但是，如果您的拓扑是主要 Lync Server 2010，则您还可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="09b2c-123">However, if your topology is primary Lync Server 2010 you can also roll back the Lync Server 2013 components to Lync Server 2010 and then upgrade directly to Skype for Business Server 2015.</span></span> <span data-ttu-id="09b2c-124">在此情况下，您将不能使用就地升级，而是使用 Lync Server 2010 与 Skype for Business Server 2015 直接共存。</span><span class="sxs-lookup"><span data-stu-id="09b2c-124">In this case you would not be able to take advantage of In-Place Upgrade and would use straight co-existence between Lync Server 2010 and Skype for Business Server 2015.</span></span> <span data-ttu-id="09b2c-125">不支持三项并存，但支持两项共存。</span><span class="sxs-lookup"><span data-stu-id="09b2c-125">Tri-existence is not supported but co-existence is supported.</span></span>  <br/> |
|<span data-ttu-id="09b2c-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="09b2c-126">Lync Server 2010</span></span>  <br/> |<span data-ttu-id="09b2c-127">打开新的 Skype for Business Server 2015 池，然后将用户迁移到此新池中。</span><span class="sxs-lookup"><span data-stu-id="09b2c-127">Bring up a new Skype for Business Server 2015 pool and then migrate users to this new pool.</span></span> <span data-ttu-id="09b2c-128">随后即可停用旧的 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-128">You can then decommission the old Lync Server 2010 pool.</span></span> <span data-ttu-id="09b2c-129">从 Lync Server 2010 升级到 Skype for Business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="09b2c-129">Upgrading from Lync Server 2010 to Skype for Business Server 2015 is similar to upgrading from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="09b2c-130">请参阅[从 Lync server 2010 迁移到 Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-130">See [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).</span></span>  <br/> |
|<span data-ttu-id="09b2c-131">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="09b2c-131">Office Communications Server 2007 R2</span></span>  <br/> | <span data-ttu-id="09b2c-132">选择两个选项之一：</span><span class="sxs-lookup"><span data-stu-id="09b2c-132">Pick one of two options:</span></span> <br/>  <span data-ttu-id="09b2c-133">设置新的 Skype for Business Server 2015 环境。</span><span class="sxs-lookup"><span data-stu-id="09b2c-133">Set up a new Skype for Business Server 2015 environment.</span></span> <br/>  <span data-ttu-id="09b2c-134">或者, 如果你的硬件和软件满足 Skype for business Server 2015 的要求, 请升级到 Lync Server 2013, 然后使用新的就地升级功能升级到 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="09b2c-134">Or if your hardware and software meet the requirements for Skype for Business Server 2015, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="09b2c-135">有关详细信息, 请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)和[从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-135">For more information, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="09b2c-136">SQL Server 2014 在 Skype for Business Server 2015 中受支持, 但在 Lync Server 2013 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="09b2c-136">SQL Server 2014 is supported in Skype for Business Server 2015 but is not supported in Lync Server 2013.</span></span> <span data-ttu-id="09b2c-137">如果要从 SQL Server 2012 升级到 SQL Server 2014, 则必须首先使用本文档中介绍的就地升级方法升级到 Skype for Business 服务器2015。</span><span class="sxs-lookup"><span data-stu-id="09b2c-137">If you want to upgrade from SQL Server 2012 to SQL Server 2014 then the pool must first be upgraded to Skype for Business Server 2015 using the In-Place Upgrade method as described in this document.</span></span> <span data-ttu-id="09b2c-138">然后, 你可以从 SQL Server 2012 升级到 SQL Server 2014, 请参阅[升级到 Sql server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-138">You can then upgrade from SQL Server 2012 to SQL Server 2014, see [Upgrade to SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx).</span></span> <span data-ttu-id="09b2c-139">若要了解有关数据库要求的详细信息, 请参阅[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-139">To learn more about database requirements, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md).</span></span> 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a><span data-ttu-id="09b2c-140">规划从 Lync Server 2013 升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09b2c-140">Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015</span></span>
<span data-ttu-id="09b2c-141"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="09b2c-141"></span></span>

<span data-ttu-id="09b2c-142">你可以使用新的就地升级功能将 Lync Server 2013 系统升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="09b2c-142">You can upgrade Lync Server 2013 systems to Skype for Business Server 2015 using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="09b2c-143">就地升级提供了一次单击的解决方案, 可备份证书、卸载服务器组件、升级本地数据库, 以及安装 Skype for Business Server 2015 角色。</span><span class="sxs-lookup"><span data-stu-id="09b2c-143">In-place upgrade provides a one-click solution that backs up certificates, uninstalls server components, upgrades local databases, and installs the Skype for Business Server 2015 roles.</span></span> <span data-ttu-id="09b2c-144">就地升级旨在保留现有硬件和服务器投资, 降低部署 Skype for Business Server 2015 的总成本。</span><span class="sxs-lookup"><span data-stu-id="09b2c-144">In-place upgrade seeks to preserve existing hardware and server investments, reducing the overall cost to deploy Skype for Business Server 2015.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09b2c-145">就地升级允许你在升级到 Skype for Business 服务器时使用相同的硬件。</span><span class="sxs-lookup"><span data-stu-id="09b2c-145">In-Place Upgrade allows you to use the same hardware when upgrading to Skype for Business Server.</span></span> <span data-ttu-id="09b2c-146">但是，重用同样的硬件不会转换为同样的性能容量。</span><span class="sxs-lookup"><span data-stu-id="09b2c-146">However, reusing the same hardware does not translate into the same performance capacity.</span></span> <span data-ttu-id="09b2c-147">不应指望 Lync Server 2013 和 Skype for business Server 2015 的性能负载是相同的。</span><span class="sxs-lookup"><span data-stu-id="09b2c-147">You should not expect the performance loads for Lync Server 2013 and Skype for Business Server 2015 to be identical.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="09b2c-148">就地升级不支持 Skype for business 服务器的高可用性或灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="09b2c-148">In-Place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> 
  
<span data-ttu-id="09b2c-149">就地升级涉及将 Lync Server 2013 池脱机并将其升级到 Skype for business Server 2015 池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-149">In-place upgrade involves taking the Lync Server 2013 pool offline and upgrading it to a Skype for Business Server 2015 pool.</span></span> 
  
### <a name="create-an-in-place-upgrade-plan"></a><span data-ttu-id="09b2c-150">创建就地升级计划</span><span class="sxs-lookup"><span data-stu-id="09b2c-150">Create an In-Place Upgrade plan</span></span>

<span data-ttu-id="09b2c-151">制定一份包含以下元素的计划：</span><span class="sxs-lookup"><span data-stu-id="09b2c-151">Make a plan that includes:</span></span>
  
1. <span data-ttu-id="09b2c-152">对当前拓扑的理解。</span><span class="sxs-lookup"><span data-stu-id="09b2c-152">An understanding of your current topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09b2c-153">请确保卸载 Lync Server 2013 的 LRS 管理工具, 然后再运行就地升级。</span><span class="sxs-lookup"><span data-stu-id="09b2c-153">Be sure to uninstall LRS Admin tool for Lync Server 2013 before running In-Place Upgrade.</span></span> <span data-ttu-id="09b2c-154">Lync Server 2013 的 LRS 管理工具无法与 Skype for Business Server 2015 共存。</span><span class="sxs-lookup"><span data-stu-id="09b2c-154">The LRS Admin Tool for Lync Server 2013 cannot coexist with Skype for Business Server 2015.</span></span> <span data-ttu-id="09b2c-155">运行就地升级后, 安装新的 LRS 管理工具。</span><span class="sxs-lookup"><span data-stu-id="09b2c-155">After running In-Place Upgrade install the new LRS Admin tool.</span></span> <span data-ttu-id="09b2c-156">有关详细信息, 请参阅[Microsoft Lync 会议室系统管理 Web 门户 For Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) 。</span><span class="sxs-lookup"><span data-stu-id="09b2c-156">See [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) for more details.</span></span>
  
2. <span data-ttu-id="09b2c-157">升级的主池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-157">The primary pool for the upgrade.</span></span>
    
3. <span data-ttu-id="09b2c-158">是要升级存档和监控数据库还是新建相应的数据库。</span><span class="sxs-lookup"><span data-stu-id="09b2c-158">Whether you'll upgrade the Archiving and Monitoring databases or create new ones.</span></span>
    
4. <span data-ttu-id="09b2c-p113">您将使用的就地升级方法：脱机或移动用户。在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。</span><span class="sxs-lookup"><span data-stu-id="09b2c-p113">The In-Place Upgrade method you'll use: Offline or Move Users. As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> 
    
5. <span data-ttu-id="09b2c-161">面向受影响用户的交流计划。</span><span class="sxs-lookup"><span data-stu-id="09b2c-161">A communication plan for impacted users.</span></span>
    
6. <span data-ttu-id="09b2c-162">防止升级失败的备用计划。</span><span class="sxs-lookup"><span data-stu-id="09b2c-162">A backup plan in case the upgrades fails.</span></span>
    
<span data-ttu-id="09b2c-163">在升级过程中，主池中的任何用户都无法使用服务，直至升级完成为止。</span><span class="sxs-lookup"><span data-stu-id="09b2c-163">Any users that are in the primary pool while it's being upgraded won't be able to use the services until the upgrade is complete.</span></span> <span data-ttu-id="09b2c-164">如果您有可以使用的辅助池，您可以在升级之前将其迁移到辅助池，避免影响用户。</span><span class="sxs-lookup"><span data-stu-id="09b2c-164">If you have a working secondary pool, you can avoid impacting users by moving them to the secondary pool before the upgrade.</span></span> <span data-ttu-id="09b2c-165">升级后, 将用户移回主池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-165">After the upgrade, move the users back to the primary pool.</span></span>
  
### <a name="in-place-upgrade-methods"></a><span data-ttu-id="09b2c-166">就地升级方法</span><span class="sxs-lookup"><span data-stu-id="09b2c-166">In-place upgrade methods</span></span>

<span data-ttu-id="09b2c-167">有两种就地升级方案：</span><span class="sxs-lookup"><span data-stu-id="09b2c-167">There are two scenarios for In-Place Upgrade:</span></span> 
  
- <span data-ttu-id="09b2c-168">移动用户方法，无需用户停机。</span><span class="sxs-lookup"><span data-stu-id="09b2c-168">The Move User method, which requires no downtime for users.</span></span> 
    
- <span data-ttu-id="09b2c-169">脱机方法，需要停机。</span><span class="sxs-lookup"><span data-stu-id="09b2c-169">The Offline method, which requires downtime.</span></span>
    
<span data-ttu-id="09b2c-170">我们推荐在维护时段内安排脱机方法升级，并通知用户注意停机时间。</span><span class="sxs-lookup"><span data-stu-id="09b2c-170">We recommend that an Offline method upgrade be scheduled during a maintenance window and users are notified of the downtime.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09b2c-p115">升级 Lync Server 2013 上的成对池时，需要将两个池都升级到 Skype for Business Server 2015。请确保在升级第一个池后，马上升级第二个池。如果一个池运行 Lync Server 2013，而第二个池运行 Skype for Business Server 2015，则灾难恢复选项将减到最少。例如，如果一个池运行 2013，第二个运行 2015，那么当灾难来临时，数据可能丢失，因为当成对池版本不同时，灾难模式不支持池故障转移。</span><span class="sxs-lookup"><span data-stu-id="09b2c-p115">When upgrading a paired pool on Lync Server 2013 and you want to upgrade both pools to Skype for Business Server 2015. Make sure to upgrade the second pool immediately after upgrading the first pool. When one pool is running Lync Server 2013 and the second pool is running Skype for Business Server 2015 then disaster recovery options are minimized. For example, if one pool is running 2013 and the second is 2015 and there is a disaster then you could experience data loss because pool failover is not supported in disaster mode when paired pools are not the same version.</span></span> 
  
#### <a name="in-place-upgrade-offline-method"></a><span data-ttu-id="09b2c-175">就地升级脱机方法</span><span class="sxs-lookup"><span data-stu-id="09b2c-175">In-place upgrade Offline method</span></span>

<span data-ttu-id="09b2c-176">如果您不想在两个用户池间移动用户，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="09b2c-176">Use this method if you don't want to move users between user pools.</span></span> <span data-ttu-id="09b2c-177">在升级期间, 用户将无法使用 Lync 或 Skype for business 服务。</span><span class="sxs-lookup"><span data-stu-id="09b2c-177">During the upgrade, users will not be able to use Lync or Skype for Business services.</span></span> 
  
<span data-ttu-id="09b2c-178">下图概述了此流程。</span><span class="sxs-lookup"><span data-stu-id="09b2c-178">The following diagram shows an overview of this process.</span></span>
  
![Lync 2013 到 Skype 用户脱机](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> <span data-ttu-id="09b2c-180">如果采用成对的池，不要在升级之前取消配对。</span><span class="sxs-lookup"><span data-stu-id="09b2c-180">If you have paired pools, do not unpair them before the upgrade.</span></span> 
  
<span data-ttu-id="09b2c-181">在开始升级服务器池之前，必须完成整个池的升级。</span><span class="sxs-lookup"><span data-stu-id="09b2c-181">Once you start to upgrade a server pool, you must complete the upgrade of the entire pool.</span></span> <span data-ttu-id="09b2c-182">Skype for Business 服务器不支持仅更新部分池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-182">Skype for Business Server doesn't support having only a portion of the pool upgraded.</span></span> 
  
#### <a name="move-users-method-no-user-downtime"></a><span data-ttu-id="09b2c-183">移动用户方法（用户无需停机）</span><span class="sxs-lookup"><span data-stu-id="09b2c-183">Move Users method (no user downtime)</span></span>
<span data-ttu-id="09b2c-184"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="09b2c-184"></span></span>

<span data-ttu-id="09b2c-185">要使用这种方法，您要首先将用户移动到另一个池，然后开始升级。</span><span class="sxs-lookup"><span data-stu-id="09b2c-185">To use this method, you move users to another pool before you start the upgrade.</span></span> <span data-ttu-id="09b2c-186">在升级期间, 用户可以使用 Lync 服务。</span><span class="sxs-lookup"><span data-stu-id="09b2c-186">During the upgrade, users can use Lync services.</span></span> <span data-ttu-id="09b2c-187">在将其移动到已升级的库后, 他们可以使用 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="09b2c-187">After they're moved to the upgraded pool, they can use Skype for Business.</span></span> <span data-ttu-id="09b2c-188">下图展示了此过程的概况。</span><span class="sxs-lookup"><span data-stu-id="09b2c-188">The following diagram shows an overview of this process.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="09b2c-189">在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。</span><span class="sxs-lookup"><span data-stu-id="09b2c-189">As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> <span data-ttu-id="09b2c-190">PSTN 电话拨入式会议仍会将 ConferenceID 解析到正在升级的池，而不是配对的池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-190">PSTN dial-in conferencing will still resolve ConferenceID to the pool being upgraded, instead of the paired pool.</span></span> <span data-ttu-id="09b2c-191">因此，如果您仍希望在升级期间访问池中安排的 PSTN 会议，则需要移动会议目录。</span><span class="sxs-lookup"><span data-stu-id="09b2c-191">So you need to move Conference Directories, if you still want PSTN conferences scheduled in the pool to be accessible during upgrade.</span></span> 
  
![泳道图，显示在升级池之前将用户迁移到另一个池，然后在升级完毕后再迁回原池。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a><span data-ttu-id="09b2c-193">为硬件升级移动用户</span><span class="sxs-lookup"><span data-stu-id="09b2c-193">Move users for hardware upgrade</span></span>
<span data-ttu-id="09b2c-194"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="09b2c-194"></span></span>

 <span data-ttu-id="09b2c-195">如果你的硬件不满足[Skype for Business server 2015 的服务器要求](requirements-for-your-environment/server-requirements.md), 请设置新的 skype For business server 2015 环境, 并将用户移动到此处。</span><span class="sxs-lookup"><span data-stu-id="09b2c-195">If your hardware doesn't meet the [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md), set up a new Skype for Business Server 2015 environment, and move users there.</span></span> <span data-ttu-id="09b2c-196">下图概述了从 Lync Server 2010 升级的流程。</span><span class="sxs-lookup"><span data-stu-id="09b2c-196">The following diagram shows an overview of this process for upgrade from Lync Server 2010.</span></span> 
  
![泳道图，显示将 Lync Server 主前端池中的用户迁移到 Skype for Business Server 2015，并且停用 Lync Server 池。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a><span data-ttu-id="09b2c-198">就地升级过程</span><span class="sxs-lookup"><span data-stu-id="09b2c-198">In-place upgrade process</span></span>

 <span data-ttu-id="09b2c-199">使用以下步骤从 Lync Server 2013 升级到 Skype for business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="09b2c-199">Upgrade from Lync Server 2013 to Skype for Business Server 2015 using the following steps:</span></span>
  
1. <span data-ttu-id="09b2c-200">在升级之前备份所有数据库。</span><span class="sxs-lookup"><span data-stu-id="09b2c-200">Back up all databases before the upgrade.</span></span>
    
2. <span data-ttu-id="09b2c-201">确保要升级的所有服务都处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="09b2c-201">Make sure all services that are to be upgraded are in a running state.</span></span>
    
3. <span data-ttu-id="09b2c-202">使用拓扑生成器升级并发布拓扑文件。</span><span class="sxs-lookup"><span data-stu-id="09b2c-202">Upgrade and publish the topology file using the topology builder.</span></span>
    
4. <span data-ttu-id="09b2c-203">停止所有前端服务器上的全部服务。</span><span class="sxs-lookup"><span data-stu-id="09b2c-203">Stop all services on all Front End servers.</span></span>
    
5. <span data-ttu-id="09b2c-204">安装 Skype for business 服务器所需的新的先决条件。</span><span class="sxs-lookup"><span data-stu-id="09b2c-204">Install new prerequisites required for Skype for Business Server.</span></span>
    
6. <span data-ttu-id="09b2c-205">在每台前端服务器上，开始就地升级。</span><span class="sxs-lookup"><span data-stu-id="09b2c-205">On each Front End server, start the In-Place Upgrade.</span></span>
    
7. <span data-ttu-id="09b2c-206">升级完成后，重启所有服务。</span><span class="sxs-lookup"><span data-stu-id="09b2c-206">When the upgrade is complete, restart all services.</span></span>
    
   - <span data-ttu-id="09b2c-207">对于前端池，使用命令 Start-CsPool 重启服务。</span><span class="sxs-lookup"><span data-stu-id="09b2c-207">For the Front End pool, restart services using the command Start-CsPool.</span></span>
    
   - <span data-ttu-id="09b2c-208">对于非前端服务器，使用 Start-CSWindowsService。</span><span class="sxs-lookup"><span data-stu-id="09b2c-208">For non-Front End servers, use Start-CSWindowsService.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="09b2c-209">如果不想升级现有存档和监控数据库，请在升级拓扑之前移除依赖关系。</span><span class="sxs-lookup"><span data-stu-id="09b2c-209">If you don't want to upgrade your existing Archiving and Monitoring databases, remove the dependency before you upgrade the topology.</span></span> <span data-ttu-id="09b2c-210">如果想创建新的存档和监控数据库，在升级过程中，可以创建新的 SQL 存储，并将其与池关联。</span><span class="sxs-lookup"><span data-stu-id="09b2c-210">If you want to create new Archiving and Monitoring databases, during the upgrade, you can create a new SQL store and associate it with the pool.</span></span> <span data-ttu-id="09b2c-211">你可以在主题 "[升级到 Skype for Business 服务器 2015](../deploy/upgrade-to-skype-for-business-server.md)" 中找到有关如何执行此操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="09b2c-211">You can find the steps on how to do this in the topic,[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md).</span></span> <span data-ttu-id="09b2c-212">> 就地升级不支持 Skype for business 服务器的高可用性或灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="09b2c-212">>  In-place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> <span data-ttu-id="09b2c-213">为避免中断用户的服务, 请使用 "[移动用户" 方法 (无用户停机)](upgrade.md#bkmk_MoveUsersMethod)进行升级。升级过程中的 > 在升级过程中, xds 将放置在具有最大可用空间的磁盘驱动器上的本地共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="09b2c-213">To avoid interrupting users' services, use the [Move Users method (no user downtime)](upgrade.md#bkmk_MoveUsersMethod) to upgrade.>  During the upgrade process the xds-replica is placed in the local shared folder on the disk drive with the most free space.</span></span> <span data-ttu-id="09b2c-214">如果该磁盘以后被删除，则您可以遇到服务未启动等问题。</span><span class="sxs-lookup"><span data-stu-id="09b2c-214">If that disk is later removed then you can run into issues such as services not starting.</span></span>
  
### <a name="upgrade-order"></a><span data-ttu-id="09b2c-215">升级顺序</span><span class="sxs-lookup"><span data-stu-id="09b2c-215">Upgrade order</span></span>

<span data-ttu-id="09b2c-216">将拓扑从内部升级到外部。</span><span class="sxs-lookup"><span data-stu-id="09b2c-216">Upgrade the topology from the inside to the outside.</span></span> <span data-ttu-id="09b2c-217">首先升级所有池, 然后升级边缘服务器, 最后升级到中央管理存储 (CMS) 池。</span><span class="sxs-lookup"><span data-stu-id="09b2c-217">Upgrade all your pools first, then the edge servers, and finally the Central Management Store (CMS) pool.</span></span> 
  
### <a name="kerberos-authentication-considerations"></a><span data-ttu-id="09b2c-218">Kerberos 身份验证考虑事项</span><span class="sxs-lookup"><span data-stu-id="09b2c-218">Kerberos authentication considerations</span></span>

<span data-ttu-id="09b2c-219">如果为 Web 服务使用了 Kerberos 身份验证，则必须在就地升级完成后重新分配 Kerberos 帐户并重置密码。</span><span class="sxs-lookup"><span data-stu-id="09b2c-219">If you use Kerberos authentication for Web Services, you must reassign Kerberos accounts and reset the password after the In-Place Upgrade is complete.</span></span> <span data-ttu-id="09b2c-220">若要了解如何执行此操作, 请参阅[设置 Kerberos 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=530342)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-220">To learn how to do this, see [Setting up Kerberos authentication](https://go.microsoft.com/fwlink/p/?LinkId=530342).</span></span>
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a><span data-ttu-id="09b2c-221">支持 Lync Server 2013 和 Lync Server 2010 共存</span><span class="sxs-lookup"><span data-stu-id="09b2c-221">Support for coexistence with Lync Server 2013 and Lync Server 2010</span></span>
<span data-ttu-id="09b2c-222"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="09b2c-222"></span></span>

<span data-ttu-id="09b2c-223">你可以在与 Lync Server 2013 或 Lync Server 2010 相同的拓扑中运行 Skype for Business Server 2015，但是不能将三者同时置于同一个拓扑中。</span><span class="sxs-lookup"><span data-stu-id="09b2c-223">You can run Skype for Business Server 2015 in the same topology as Lync Server 2013 or Lync Server 2010, but you can't have all three in the same topology.</span></span>
  
<span data-ttu-id="09b2c-224">如果 Lync Server 2010 和 Lync Server 2013 同时存在，建议将整个拓扑升级到 Lync Server 2013，然后再使用就地升级来升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="09b2c-224">If you have a co-existence between Lync Server 2010 and Lync Server 2013, it is recommended to upgrade the entire topology to Lync Server 2013, and then upgrade to Skype for Business Server 2015 using the In-Place Upgrade.</span></span> <span data-ttu-id="09b2c-225">有关详细信息, 请参阅[从 Lync server 2010 迁移到 Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-225">For more information, see [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).</span></span>
  
<span data-ttu-id="09b2c-p125">如果你的拓扑主要是 Lync Server 2010，请在将拓扑升级到 Skype for Business Server 2015 之前，将 Lync Server 2013 组件回退到 Lync Server 2010。在这种情况下，你将丧失就地升级的优势，并且具有 Lync Server 2010 与 Skype for Business Server 2015 同时存在的拓扑。</span><span class="sxs-lookup"><span data-stu-id="09b2c-p125">If your topology is primarily Lync Server 2010, roll back the Lync Server 2013 components to Lync Server 2010 before upgrading the topology to Skype for Business Server 2015. In this case, you lose the benefit of the In-Place Upgrade and have a co-existence topology between Lync Server 2010 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="09b2c-228">下图显示了 Skype for Business 服务器2015与 Lync Server 2013 和 Lync Server 2010 的共存支持。</span><span class="sxs-lookup"><span data-stu-id="09b2c-228">The following diagram shows the coexistence support of Skype for Business Server 2015 with Lync Server 2013 and Lync Server 2010.</span></span>
  
![显示 Skype for Business Server 2015 与 Lync Server 2013 或 Lync Server 2010 共存支持的图表。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a><span data-ttu-id="09b2c-230">现有 Survivable Branch Appliance 和服务器的升级流程</span><span class="sxs-lookup"><span data-stu-id="09b2c-230">Upgrade process with existing Survivable Branch Appliance and Server</span></span>
<span data-ttu-id="09b2c-231"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="09b2c-231"></span></span>

<span data-ttu-id="09b2c-232">Skype for Business Server 2015 不支持 Survivable 分支装置 (SBA) 或 Survivable 分支服务器 (SBS) 的就地升级。</span><span class="sxs-lookup"><span data-stu-id="09b2c-232">Skype for Business Server 2015 doesn't support an In-Place Upgrade of a Survivable Branch Appliance (SBA) or a Survivable Branch Server (SBS).</span></span>
  
<span data-ttu-id="09b2c-233">但是，我们支持 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。</span><span class="sxs-lookup"><span data-stu-id="09b2c-233">However, we do support coexistence of Skype for Business Server datacenters with Lync Server 2010 or Lync Server 2013 SBA/SBS.</span></span> 
  
<span data-ttu-id="09b2c-234">规划采用关联分支就地升级 Lync Server 2013 前端 (FE) 池时，可以将现有用户留在 Lync Server 2013 SBA/SBS 上。</span><span class="sxs-lookup"><span data-stu-id="09b2c-234">When planning for an In-Place Upgrade of a Lync Server 2013 Front End (FE) pool with an associated branch, you can leave the existing users on the Lync Server 2013 SBA/SBS.</span></span> <span data-ttu-id="09b2c-235">在升级过程中，SBA/SBS 用户将进入恢复模式，并在升级完成后返回正常功能。</span><span class="sxs-lookup"><span data-stu-id="09b2c-235">During the upgrade, the SBA/SBS users will go in resiliency mode and will return to normal functionality after the upgrade has completed.</span></span> <span data-ttu-id="09b2c-236">有关用户在复原模式期间的体验的详细信息, 请参阅[Lync Server 2013 中的分支站点复原功能](https://technet.microsoft.com/library/gg398715.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-236">For more information about the users' experience during the resiliency mode, please see [Branch-site resiliency features in Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).</span></span>
  
<span data-ttu-id="09b2c-237">将 Lync Server 2010 拓扑迁移到 Skype for Business Server 2015 时，与迁移到 Lync Server 2013 类似，必须将 SBA/SBS 重新添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="09b2c-237">When migrating a Lync Server 2010 topology to Skype for Business Server 2015, the SBA/SBS must re-added to the topology, similar to the migration to Lync Server 2013.</span></span> <span data-ttu-id="09b2c-238">有关所需步骤, 请阅读[将 Survivable 分支装置连接到 Lync Server 2013 前端池](https://technet.microsoft.com/library/jj688026.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09b2c-238">For the required steps, please read [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](https://technet.microsoft.com/library/jj688026.aspx).</span></span>
  
<span data-ttu-id="09b2c-239">对于 Lync Server 2010 和 Lync Server 2013 的共存拓扑, 请首先与 "对 Lync Server 2013 和 Lync Server 2010 共存的支持" 部分中的建议进行对齐。</span><span class="sxs-lookup"><span data-stu-id="09b2c-239">For co-existence topologies of Lync Server 2010 and Lync Server 2013, align first to the recommendations made in the section 'Support for coexistence with Lync Server 2013 and Lync Server 2010'.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09b2c-240">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09b2c-240">See also</span></span>
<span data-ttu-id="09b2c-241"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="09b2c-241"></span></span>

[<span data-ttu-id="09b2c-242">升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09b2c-242">Upgrade to Skype for Business Server 2015</span></span>](../deploy/upgrade-to-skype-for-business-server.md)
  
[<span data-ttu-id="09b2c-243">Environmental requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09b2c-243">Environmental requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/environmental-requirements.md)
  
[<span data-ttu-id="09b2c-244">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="09b2c-244">Server requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/server-requirements.md)
