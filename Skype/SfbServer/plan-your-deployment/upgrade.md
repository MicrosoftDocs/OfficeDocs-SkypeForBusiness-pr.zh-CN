---
title: 规划升级到 Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 8cbde89eb7be8fd48e3c8faf7b0e00bac26f073d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910874"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="b68eb-104">规划升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b68eb-104">Plan to upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b68eb-105">摘要： 了解升级到 Skype 规划业务服务器 2015年时应考虑。</span><span class="sxs-lookup"><span data-stu-id="b68eb-105">Summary: Learn about the things you should consider when you plan an upgrade to Skype for Business Server 2015.</span></span> <span data-ttu-id="b68eb-106">下载免费试用版 Skype 业务服务器 2015 从 Microsoft 评估中心，网址为： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b68eb-107">作为升级到 Skype 的业务服务器 2015年您计划的一部分，使用本主题来了解 Skype 的推荐升级路径的业务服务器 2015年如何就地升级的工作原理、 支持的共存方案是什么，和升级过程如下所示。</span><span class="sxs-lookup"><span data-stu-id="b68eb-107">As part of your plan to upgrade to Skype for Business Server 2015, use this topic to understand the recommended upgrade paths to Skype for Business Server 2015, how the In-Place Upgrade works, what the supported coexistence scenarios are, and what the upgrade process looks like.</span></span>

> [!NOTE]
> <span data-ttu-id="b68eb-108">就地升级中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="b68eb-108">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b68eb-109">Coexistance 都支持并排，详细信息，请参阅[迁移到业务服务器 2019年的 Skype](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="b68eb-109">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a><span data-ttu-id="b68eb-110">为业务服务器 2015年的 Skype 的推荐升级路径</span><span class="sxs-lookup"><span data-stu-id="b68eb-110">Recommended upgrade paths to Skype for Business Server 2015</span></span>

 <span data-ttu-id="b68eb-111">若要为业务服务器 2015年从 Lync Server 2013、 Lync Server 2010 或 Office Communications Server 2007 R2 升级到 Skype，使用以下升级途径：</span><span class="sxs-lookup"><span data-stu-id="b68eb-111">To upgrade from Lync Server 2013, Lync Server 2010, or Office Communications Server 2007 R2 to Skype for Business Server 2015, use the following upgrade paths:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b68eb-p104">就地升级可将会议目录从 Lync Server 2013 自动移至 Skype for Business Server 2015。但是，如果您计划手动移动会议目录，就务必使用 Skype for Business Server 2015 命令行管理程序。如果您尝试使用 Lync Server 2013 命令行管理程序将会议目录从 Lync Server 2013 移至 Skype for Business Server 2015，则可能出现数据丢失。一般来讲，无论您何时使用任意容量的 Skype for Business Server 2015，都应使用 Skype for Business Server 2015 工具集。</span><span class="sxs-lookup"><span data-stu-id="b68eb-p104">In-Place Upgrade automatically moves conference directories from Lync Server 2013 to Skype for Business Server 2015. However, if you plan to manually move conference directories it is very important to use the Skype for Business Server 2015 Management Shell. If you try to use the Lync Server 2013 Management Shell to move conference directories from Lync Server 2013 to Skype for Business Server 2015 then data loss can occur. In general, whenever you are working with Skype for Business Server 2015 in any capacity you should use the Skype for Business Server 2015 tool set.</span></span>  
  
|<span data-ttu-id="b68eb-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="b68eb-116">**Version**</span></span>|<span data-ttu-id="b68eb-117">**建议**</span><span class="sxs-lookup"><span data-stu-id="b68eb-117">**Recommendations**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b68eb-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b68eb-118">Lync Server 2013</span></span>  <br/> | <span data-ttu-id="b68eb-119">若要升级，用于 Skype 业务 Server 拓扑生成器和上每个服务器与池关联的就地升级的新功能。</span><span class="sxs-lookup"><span data-stu-id="b68eb-119">To upgrade, use the Skype for Business Server Topology Builder and the new In-Place Upgrade feature on each of the servers associated with the pool.</span></span> <span data-ttu-id="b68eb-120">有关详细步骤，请参阅[规划 Lync Server 2013 的业务服务器 2015 Skype 以从升级](upgrade.md#BKMK_PlanUpgradeFromLync2013)和[升级到业务服务器 2015年的 Skype](../deploy/upgrade-to-skype-for-business-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="b68eb-120">see [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps.</span></span> <br/> |
|<span data-ttu-id="b68eb-121">Lync Server 2010 + Lync Server 2013（双模式）</span><span class="sxs-lookup"><span data-stu-id="b68eb-121">Lync Server 2010 + Lync Server 2013 (dual-mode)</span></span>  <br/> |<span data-ttu-id="b68eb-122">首先，升级到 Lync Server 2013 并升级到 Skype 的业务服务器 2015年使用就地升级的新功能。</span><span class="sxs-lookup"><span data-stu-id="b68eb-122">First, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="b68eb-123">但是，如果您的拓扑是主要 Lync Server 2010，则您还可以将 Lync Server 2013 组件回滚到 Lync Server 2010，然后直接升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b68eb-123">However, if your topology is primary Lync Server 2010 you can also roll back the Lync Server 2013 components to Lync Server 2010 and then upgrade directly to Skype for Business Server 2015.</span></span> <span data-ttu-id="b68eb-124">在此情况下，您将不能使用就地升级，而是使用 Lync Server 2010 与 Skype for Business Server 2015 直接共存。</span><span class="sxs-lookup"><span data-stu-id="b68eb-124">In this case you would not be able to take advantage of In-Place Upgrade and would use straight co-existence between Lync Server 2010 and Skype for Business Server 2015.</span></span> <span data-ttu-id="b68eb-125">不支持三项并存，但支持两项共存。</span><span class="sxs-lookup"><span data-stu-id="b68eb-125">Tri-existence is not supported but co-existence is supported.</span></span>  <br/> |
|<span data-ttu-id="b68eb-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b68eb-126">Lync Server 2010</span></span>  <br/> |<span data-ttu-id="b68eb-127">打开新的 Skype for Business Server 2015 池，然后将用户迁移到此新池中。</span><span class="sxs-lookup"><span data-stu-id="b68eb-127">Bring up a new Skype for Business Server 2015 pool and then migrate users to this new pool.</span></span> <span data-ttu-id="b68eb-128">随后即可停用旧的 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="b68eb-128">You can then decommission the old Lync Server 2010 pool.</span></span> <span data-ttu-id="b68eb-129">从 Lync Server 2010 升级到 Skype for Business Server 2015 类似于从 Lync Server 2010 升级到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b68eb-129">Upgrading from Lync Server 2010 to Skype for Business Server 2015 is similar to upgrading from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="b68eb-130">请参阅[Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-130">See [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).</span></span>  <br/> |
|<span data-ttu-id="b68eb-131">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b68eb-131">Office Communications Server 2007 R2</span></span>  <br/> | <span data-ttu-id="b68eb-132">选择两个选项之一：</span><span class="sxs-lookup"><span data-stu-id="b68eb-132">Pick one of two options:</span></span> <br/>  <span data-ttu-id="b68eb-133">设置新的 Skype 业务服务器 2015年环境。</span><span class="sxs-lookup"><span data-stu-id="b68eb-133">Set up a new Skype for Business Server 2015 environment.</span></span> <br/>  <span data-ttu-id="b68eb-134">或者，如果您的硬件和软件满足业务服务器 2015 Skype 的要求，升级到 Lync Server 2013 并升级到 Skype 的业务服务器 2015年使用就地升级的新功能。</span><span class="sxs-lookup"><span data-stu-id="b68eb-134">Or if your hardware and software meet the requirements for Skype for Business Server 2015, upgrade to Lync Server 2013, and then upgrade to Skype for Business Server 2015 by using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="b68eb-135">有关详细信息，请参阅[业务服务器 2015年的 Skype 的服务器要求](requirements-for-your-environment/server-requirements.md)和[Migration from Office Communications Server 2007 R2 至 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-135">For more information, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b68eb-136">SQL Server 2014 业务服务器 2015 Skype 中支持，但不是支持在 Lync Server 2013 中。</span><span class="sxs-lookup"><span data-stu-id="b68eb-136">SQL Server 2014 is supported in Skype for Business Server 2015 but is not supported in Lync Server 2013.</span></span> <span data-ttu-id="b68eb-137">如果您想要从 SQL Server 2012 升级到 SQL Server 2014 然后池必须首先升级到 Skype 的业务服务器 2015 使用就地升级方法，如本文档中所述。</span><span class="sxs-lookup"><span data-stu-id="b68eb-137">If you want to upgrade from SQL Server 2012 to SQL Server 2014 then the pool must first be upgraded to Skype for Business Server 2015 using the In-Place Upgrade method as described in this document.</span></span> <span data-ttu-id="b68eb-138">然后可以升级从 SQL Server 2014 到 SQL Server 2012，请参阅[升级到 SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-138">You can then upgrade from SQL Server 2012 to SQL Server 2014, see [Upgrade to SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx).</span></span> <span data-ttu-id="b68eb-139">若要了解有关数据库要求的详细信息，请参阅[业务服务器 2015年的 Skype 的服务器要求](requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-139">To learn more about database requirements, see [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md).</span></span> 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a><span data-ttu-id="b68eb-140">规划从 Lync Server 2013 升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b68eb-140">Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015</span></span>
<span data-ttu-id="b68eb-141"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="b68eb-141"></span></span>

<span data-ttu-id="b68eb-142">您可以使用就地升级的新功能的业务服务器 2015年的升级到 Skype 的 Lync Server 2013 系统。</span><span class="sxs-lookup"><span data-stu-id="b68eb-142">You can upgrade Lync Server 2013 systems to Skype for Business Server 2015 using the new In-Place Upgrade feature.</span></span> <span data-ttu-id="b68eb-143">在就地升级提供一键式解决方案，备份证书、 卸载服务器组件、 升级本地数据库和安装业务服务器 2015年角色 Skype。</span><span class="sxs-lookup"><span data-stu-id="b68eb-143">In-place upgrade provides a one-click solution that backs up certificates, uninstalls server components, upgrades local databases, and installs the Skype for Business Server 2015 roles.</span></span> <span data-ttu-id="b68eb-144">在就地升级搜寻要保留现有的硬件和服务器上的投资，从而减少了部署业务服务器 2015 Skype 的总成本。</span><span class="sxs-lookup"><span data-stu-id="b68eb-144">In-place upgrade seeks to preserve existing hardware and server investments, reducing the overall cost to deploy Skype for Business Server 2015.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b68eb-145">就地升级可以升级到 Skype 业务服务器时使用相同的硬件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-145">In-Place Upgrade allows you to use the same hardware when upgrading to Skype for Business Server.</span></span> <span data-ttu-id="b68eb-146">但是，重用同样的硬件不会转换为同样的性能容量。</span><span class="sxs-lookup"><span data-stu-id="b68eb-146">However, reusing the same hardware does not translate into the same performance capacity.</span></span> <span data-ttu-id="b68eb-147">不应期望 Lync Server 2013 和 Skype 的业务服务器 2015年相同的性能的负载。</span><span class="sxs-lookup"><span data-stu-id="b68eb-147">You should not expect the performance loads for Lync Server 2013 and Skype for Business Server 2015 to be identical.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b68eb-148">在就地升级不支持高可用性或灾难恢复的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="b68eb-148">In-Place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> 
  
<span data-ttu-id="b68eb-149">在就地升级涉及使 Lync Server 2013 池脱机和升级到业务服务器 2015年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="b68eb-149">In-place upgrade involves taking the Lync Server 2013 pool offline and upgrading it to a Skype for Business Server 2015 pool.</span></span> 
  
### <a name="create-an-in-place-upgrade-plan"></a><span data-ttu-id="b68eb-150">创建就地升级计划</span><span class="sxs-lookup"><span data-stu-id="b68eb-150">Create an In-Place Upgrade plan</span></span>

<span data-ttu-id="b68eb-151">制定一份包含以下元素的计划：</span><span class="sxs-lookup"><span data-stu-id="b68eb-151">Make a plan that includes:</span></span>
  
1. <span data-ttu-id="b68eb-152">了解当前拓扑。</span><span class="sxs-lookup"><span data-stu-id="b68eb-152">An understanding of your current topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b68eb-153">确保运行就地升级之前卸载 Lync Server 2013 的 LRS 管理工具。</span><span class="sxs-lookup"><span data-stu-id="b68eb-153">Be sure to uninstall LRS Admin tool for Lync Server 2013 before running In-Place Upgrade.</span></span> <span data-ttu-id="b68eb-154">Lync Server 2013 LRS 管理工具不能与 Skype 的业务服务器 2015年共存。</span><span class="sxs-lookup"><span data-stu-id="b68eb-154">The LRS Admin Tool for Lync Server 2013 cannot coexist with Skype for Business Server 2015.</span></span> <span data-ttu-id="b68eb-155">运行就地升级之后安装新的 LRS 管理工具，请参阅[Microsoft Lync 会议室系统管理 Web 门户网站的业务服务器 2015 Skype](https://go.microsoft.com/fwlink/?LinkID=544807)</span><span class="sxs-lookup"><span data-stu-id="b68eb-155">After running In-Place Upgrade install the new LRS Admin tool, see [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015 ](https://go.microsoft.com/fwlink/?LinkID=544807)</span></span>
  
2. <span data-ttu-id="b68eb-156">升级主池。</span><span class="sxs-lookup"><span data-stu-id="b68eb-156">The primary pool for the upgrade.</span></span>
    
3. <span data-ttu-id="b68eb-157">是要升级存档和监控数据库还是新建相应的数据库。</span><span class="sxs-lookup"><span data-stu-id="b68eb-157">Whether you'll upgrade the Archiving and Monitoring databases or create new ones.</span></span>
    
4. <span data-ttu-id="b68eb-p113">您将使用的就地升级方法：脱机或移动用户。在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。</span><span class="sxs-lookup"><span data-stu-id="b68eb-p113">The In-Place Upgrade method you'll use: Offline or Move Users. As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> 
    
5. <span data-ttu-id="b68eb-160">面向受影响用户的交流计划。</span><span class="sxs-lookup"><span data-stu-id="b68eb-160">A communication plan for impacted users.</span></span>
    
6. <span data-ttu-id="b68eb-161">防止升级失败的备用计划。</span><span class="sxs-lookup"><span data-stu-id="b68eb-161">A backup plan in case the upgrades fails.</span></span>
    
<span data-ttu-id="b68eb-162">在升级过程中，主池中的任何用户都无法使用服务，直至升级完成为止。</span><span class="sxs-lookup"><span data-stu-id="b68eb-162">Any users that are in the primary pool while it's being upgraded won't be able to use the services until the upgrade is complete.</span></span> <span data-ttu-id="b68eb-163">如果您有可以使用的辅助池，您可以在升级之前将其迁移到辅助池，避免影响用户。</span><span class="sxs-lookup"><span data-stu-id="b68eb-163">If you have a working secondary pool, you can avoid impacting users by moving them to the secondary pool before the upgrade.</span></span> <span data-ttu-id="b68eb-164">升级后，将用户移到主池。</span><span class="sxs-lookup"><span data-stu-id="b68eb-164">After the upgrade, move the users back to the primary pool.</span></span>
  
### <a name="in-place-upgrade-methods"></a><span data-ttu-id="b68eb-165">就地升级方法</span><span class="sxs-lookup"><span data-stu-id="b68eb-165">In-place upgrade methods</span></span>

<span data-ttu-id="b68eb-166">有两种就地升级方案：</span><span class="sxs-lookup"><span data-stu-id="b68eb-166">There are two scenarios for In-Place Upgrade:</span></span> 
  
- <span data-ttu-id="b68eb-167">移动用户方法，无需用户停机。</span><span class="sxs-lookup"><span data-stu-id="b68eb-167">The Move User method, which requires no downtime for users.</span></span> 
    
- <span data-ttu-id="b68eb-168">脱机方法，需要停机。</span><span class="sxs-lookup"><span data-stu-id="b68eb-168">The Offline method, which requires downtime.</span></span>
    
<span data-ttu-id="b68eb-169">我们推荐在维护时段内安排脱机方法升级，并通知用户注意停机时间。</span><span class="sxs-lookup"><span data-stu-id="b68eb-169">We recommend that an Offline method upgrade be scheduled during a maintenance window and users are notified of the downtime.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b68eb-p115">升级 Lync Server 2013 上的成对池时，需要将两个池都升级到 Skype for Business Server 2015。请确保在升级第一个池后，马上升级第二个池。如果一个池运行 Lync Server 2013，而第二个池运行 Skype for Business Server 2015，则灾难恢复选项将减到最少。例如，如果一个池运行 2013，第二个运行 2015，那么当灾难来临时，数据可能丢失，因为当成对池版本不同时，灾难模式不支持池故障转移。</span><span class="sxs-lookup"><span data-stu-id="b68eb-p115">When upgrading a paired pool on Lync Server 2013 and you want to upgrade both pools to Skype for Business Server 2015. Make sure to upgrade the second pool immediately after upgrading the first pool. When one pool is running Lync Server 2013 and the second pool is running Skype for Business Server 2015 then disaster recovery options are minimized. For example, if one pool is running 2013 and the second is 2015 and there is a disaster then you could experience data loss because pool failover is not supported in disaster mode when paired pools are not the same version.</span></span> 
  
#### <a name="in-place-upgrade-offline-method"></a><span data-ttu-id="b68eb-174">就地升级脱机方法</span><span class="sxs-lookup"><span data-stu-id="b68eb-174">In-place upgrade Offline method</span></span>

<span data-ttu-id="b68eb-175">如果您不想在两个用户池间移动用户，请使用此方法。</span><span class="sxs-lookup"><span data-stu-id="b68eb-175">Use this method if you don't want to move users between user pools.</span></span> <span data-ttu-id="b68eb-176">升级期间，用户将不能用于 Lync 或 Skype 业务服务。</span><span class="sxs-lookup"><span data-stu-id="b68eb-176">During the upgrade, users will not be able to use Lync or Skype for Business services.</span></span> 
  
<span data-ttu-id="b68eb-177">下图概述了此流程。</span><span class="sxs-lookup"><span data-stu-id="b68eb-177">The following diagram shows an overview of this process.</span></span>
  
![Lync 2013 到 Skype 用户脱机](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> <span data-ttu-id="b68eb-179">如果采用成对的池，不要在升级之前取消配对。</span><span class="sxs-lookup"><span data-stu-id="b68eb-179">If you have paired pools, do not unpair them before the upgrade.</span></span> 
  
<span data-ttu-id="b68eb-180">在开始升级服务器池之前，必须完成整个池的升级。</span><span class="sxs-lookup"><span data-stu-id="b68eb-180">Once you start to upgrade a server pool, you must complete the upgrade of the entire pool.</span></span> <span data-ttu-id="b68eb-181">Skype 业务服务器不支持具有仅升级的池的一部分。</span><span class="sxs-lookup"><span data-stu-id="b68eb-181">Skype for Business Server doesn't support having only a portion of the pool upgraded.</span></span> 
  
#### <a name="move-users-method-no-user-downtime"></a><span data-ttu-id="b68eb-182">移动用户方法（用户无需停机）</span><span class="sxs-lookup"><span data-stu-id="b68eb-182">Move Users method (no user downtime)</span></span>
<span data-ttu-id="b68eb-183"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="b68eb-183"></span></span>

<span data-ttu-id="b68eb-184">要使用这种方法，您要首先将用户移动到另一个池，然后开始升级。</span><span class="sxs-lookup"><span data-stu-id="b68eb-184">To use this method, you move users to another pool before you start the upgrade.</span></span> <span data-ttu-id="b68eb-185">升级期间，用户可以使用 Lync 服务。</span><span class="sxs-lookup"><span data-stu-id="b68eb-185">During the upgrade, users can use Lync services.</span></span> <span data-ttu-id="b68eb-186">它们移动到升级后的池后，他们可以 for Business 使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="b68eb-186">After they're moved to the upgraded pool, they can use Skype for Business.</span></span> <span data-ttu-id="b68eb-187">下图展示了此过程的概况。</span><span class="sxs-lookup"><span data-stu-id="b68eb-187">The following diagram shows an overview of this process.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b68eb-188">在“移动用户”过程中，您还需要迁移与主池关联的全局会议目录。</span><span class="sxs-lookup"><span data-stu-id="b68eb-188">As part of Move Users you also will need to migrate the global conference directories associated with the primary pool.</span></span> <span data-ttu-id="b68eb-189">PSTN 电话拨入式会议仍会将 ConferenceID 解析到正在升级的池，而不是配对的池。</span><span class="sxs-lookup"><span data-stu-id="b68eb-189">PSTN dial-in conferencing will still resolve ConferenceID to the pool being upgraded, instead of the paired pool.</span></span> <span data-ttu-id="b68eb-190">因此，如果您仍希望在升级期间访问池中安排的 PSTN 会议，则需要移动会议目录。</span><span class="sxs-lookup"><span data-stu-id="b68eb-190">So you need to move Conference Directories, if you still want PSTN conferences scheduled in the pool to be accessible during upgrade.</span></span> 
  
![泳道图，显示在升级池之前将用户迁移到另一个池，然后在升级完毕后再迁回原池。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a><span data-ttu-id="b68eb-192">为硬件升级移动用户</span><span class="sxs-lookup"><span data-stu-id="b68eb-192">Move users for hardware upgrade</span></span>
<span data-ttu-id="b68eb-193"><a name="bkmk_MoveUsersMethod"> </a></span><span class="sxs-lookup"><span data-stu-id="b68eb-193"></span></span>

 <span data-ttu-id="b68eb-194">如果您的硬件不满足[业务服务器 2015年的 Skype 的服务器要求](requirements-for-your-environment/server-requirements.md)，设置新 Skype 业务服务器 2015年环境，并那里移动用户。</span><span class="sxs-lookup"><span data-stu-id="b68eb-194">If your hardware doesn't meet the [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md), set up a new Skype for Business Server 2015 environment, and move users there.</span></span> <span data-ttu-id="b68eb-195">下图概述了从 Lync Server 2010 升级的流程。</span><span class="sxs-lookup"><span data-stu-id="b68eb-195">The following diagram shows an overview of this process for upgrade from Lync Server 2010.</span></span> 
  
![泳道图，显示将 Lync Server 主前端池中的用户迁移到 Skype for Business Server 2015，并且停用 Lync Server 池。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a><span data-ttu-id="b68eb-197">就地升级过程</span><span class="sxs-lookup"><span data-stu-id="b68eb-197">In-place upgrade process</span></span>

 <span data-ttu-id="b68eb-198">为业务服务器 2015 使用以下步骤从 Lync Server 2013 升级到 Skype:</span><span class="sxs-lookup"><span data-stu-id="b68eb-198">Upgrade from Lync Server 2013 to Skype for Business Server 2015 using the following steps:</span></span>
  
1. <span data-ttu-id="b68eb-199">在升级之前备份所有数据库。</span><span class="sxs-lookup"><span data-stu-id="b68eb-199">Back up all databases before the upgrade.</span></span>
    
2. <span data-ttu-id="b68eb-200">确保要升级的所有服务都处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="b68eb-200">Make sure all services that are to be upgraded are in a running state.</span></span>
    
3. <span data-ttu-id="b68eb-201">使用拓扑生成器升级并发布拓扑文件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-201">Upgrade and publish the topology file using the topology builder.</span></span>
    
4. <span data-ttu-id="b68eb-202">停止所有前端服务器上的全部服务。</span><span class="sxs-lookup"><span data-stu-id="b68eb-202">Stop all services on all Front End servers.</span></span>
    
5. <span data-ttu-id="b68eb-203">安装新 Skype 业务服务器所需的必备组件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-203">Install new prerequisites required for Skype for Business Server.</span></span>
    
6. <span data-ttu-id="b68eb-204">在每台前端服务器上，开始就地升级。</span><span class="sxs-lookup"><span data-stu-id="b68eb-204">On each Front End server, start the In-Place Upgrade.</span></span>
    
7. <span data-ttu-id="b68eb-205">升级完成后，重启所有服务。</span><span class="sxs-lookup"><span data-stu-id="b68eb-205">When the upgrade is complete, restart all services.</span></span>
    
   - <span data-ttu-id="b68eb-206">对于前端池，使用命令 Start-CsPool 重启服务。</span><span class="sxs-lookup"><span data-stu-id="b68eb-206">For the Front End pool, restart services using the command Start-CsPool.</span></span>
    
   - <span data-ttu-id="b68eb-207">对于非前端服务器，使用 Start-CSWindowsService。</span><span class="sxs-lookup"><span data-stu-id="b68eb-207">For non-Front End servers, use Start-CSWindowsService.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b68eb-208">如果不想升级现有存档和监控数据库，请在升级拓扑之前移除依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b68eb-208">If you don't want to upgrade your existing Archiving and Monitoring databases, remove the dependency before you upgrade the topology.</span></span> <span data-ttu-id="b68eb-209">如果想创建新的存档和监控数据库，在升级过程中，可以创建新的 SQL 存储，并将其与池关联。</span><span class="sxs-lookup"><span data-stu-id="b68eb-209">If you want to create new Archiving and Monitoring databases, during the upgrade, you can create a new SQL store and associate it with the pool.</span></span> <span data-ttu-id="b68eb-210">您可以找到有关如何执行此操作在主题中，[升级到业务服务器 2015年的 Skype](../deploy/upgrade-to-skype-for-business-server.md)的步骤。</span><span class="sxs-lookup"><span data-stu-id="b68eb-210">You can find the steps on how to do this in the topic,[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md).</span></span> <span data-ttu-id="b68eb-211">> 就地升级不支持高可用性或灾难恢复的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="b68eb-211">>  In-place upgrade does not support high availability or disaster recovery for Skype for Business Server.</span></span> <span data-ttu-id="b68eb-212">若要避免中断用户的服务，请 xds 副本处于最大可用空间的磁盘驱动器上的本地共享文件夹在升级过程中使用 upgrade.>[移动用户方法 （没有用户停机时间）](upgrade.md#bkmk_MoveUsersMethod) 。</span><span class="sxs-lookup"><span data-stu-id="b68eb-212">To avoid interrupting users' services, use the [Move Users method (no user downtime)](upgrade.md#bkmk_MoveUsersMethod) to upgrade.>  During the upgrade process the xds-replica is placed in the local shared folder on the disk drive with the most free space.</span></span> <span data-ttu-id="b68eb-213">如果该磁盘以后被删除，则您可以遇到服务未启动等问题。</span><span class="sxs-lookup"><span data-stu-id="b68eb-213">If that disk is later removed then you can run into issues such as services not starting.</span></span>
  
### <a name="upgrade-order"></a><span data-ttu-id="b68eb-214">升级顺序</span><span class="sxs-lookup"><span data-stu-id="b68eb-214">Upgrade order</span></span>

<span data-ttu-id="b68eb-215">从内部拓扑升级至外部。</span><span class="sxs-lookup"><span data-stu-id="b68eb-215">Upgrade the topology from the inside to the outside.</span></span> <span data-ttu-id="b68eb-216">所有池首先都升级，然后边缘服务器和最后中央管理存储 (CMS) 池。</span><span class="sxs-lookup"><span data-stu-id="b68eb-216">Upgrade all your pools first, then the edge servers, and finally the Central Management Store (CMS) pool.</span></span> 
  
### <a name="kerberos-authentication-considerations"></a><span data-ttu-id="b68eb-217">Kerberos 身份验证考虑事项</span><span class="sxs-lookup"><span data-stu-id="b68eb-217">Kerberos authentication considerations</span></span>

<span data-ttu-id="b68eb-218">如果为 Web 服务使用了 Kerberos 身份验证，则必须在就地升级完成后重新分配 Kerberos 帐户并重置密码。</span><span class="sxs-lookup"><span data-stu-id="b68eb-218">If you use Kerberos authentication for Web Services, you must reassign Kerberos accounts and reset the password after the In-Place Upgrade is complete.</span></span> <span data-ttu-id="b68eb-219">若要了解如何执行此操作，请参阅[设置 Kerberos 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=530342)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-219">To learn how to do this, see [Setting up Kerberos authentication](https://go.microsoft.com/fwlink/p/?LinkId=530342).</span></span>
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a><span data-ttu-id="b68eb-220">支持与 Lync Server 2013 和 Lync Server 2010 共存</span><span class="sxs-lookup"><span data-stu-id="b68eb-220">Support for coexistence with Lync Server 2013 and Lync Server 2010</span></span>
<span data-ttu-id="b68eb-221"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="b68eb-221"></span></span>

<span data-ttu-id="b68eb-222">你可以在与 Lync Server 2013 或 Lync Server 2010 相同的拓扑中运行 Skype for Business Server 2015，但是不能将三者同时置于同一个拓扑中。</span><span class="sxs-lookup"><span data-stu-id="b68eb-222">You can run Skype for Business Server 2015 in the same topology as Lync Server 2013 or Lync Server 2010, but you can't have all three in the same topology.</span></span>
  
<span data-ttu-id="b68eb-223">如果 Lync Server 2010 和 Lync Server 2013 同时存在，建议将整个拓扑升级到 Lync Server 2013，然后再使用就地升级来升级到 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b68eb-223">If you have a co-existence between Lync Server 2010 and Lync Server 2013, it is recommended to upgrade the entire topology to Lync Server 2013, and then upgrade to Skype for Business Server 2015 using the In-Place Upgrade.</span></span> <span data-ttu-id="b68eb-224">有关详细信息，请参阅[Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-224">For more information, see [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).</span></span>
  
<span data-ttu-id="b68eb-p125">如果你的拓扑主要是 Lync Server 2010，请在将拓扑升级到 Skype for Business Server 2015 之前，将 Lync Server 2013 组件回退到 Lync Server 2010。在这种情况下，你将丧失就地升级的优势，并且具有 Lync Server 2010 与 Skype for Business Server 2015 同时存在的拓扑。</span><span class="sxs-lookup"><span data-stu-id="b68eb-p125">If your topology is primarily Lync Server 2010, roll back the Lync Server 2013 components to Lync Server 2010 before upgrading the topology to Skype for Business Server 2015. In this case, you lose the benefit of the In-Place Upgrade and have a co-existence topology between Lync Server 2010 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b68eb-227">下图显示了使用 Lync Server 2013 和 Lync Server 2010 的业务服务器 2015 Skype 的共存支持。</span><span class="sxs-lookup"><span data-stu-id="b68eb-227">The following diagram shows the coexistence support of Skype for Business Server 2015 with Lync Server 2013 and Lync Server 2010.</span></span>
  
![显示 Skype for Business Server 2015 与 Lync Server 2013 或 Lync Server 2010 共存支持的图表。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a><span data-ttu-id="b68eb-229">现有 Survivable Branch Appliance 和服务器的升级流程</span><span class="sxs-lookup"><span data-stu-id="b68eb-229">Upgrade process with existing Survivable Branch Appliance and Server</span></span>
<span data-ttu-id="b68eb-230"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="b68eb-230"></span></span>

<span data-ttu-id="b68eb-231">Skype 的业务服务器 2015年不支持就地升级的 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-231">Skype for Business Server 2015 doesn't support an In-Place Upgrade of a Survivable Branch Appliance (SBA) or a Survivable Branch Server (SBS).</span></span>
  
<span data-ttu-id="b68eb-232">但是，我们支持 Skype for Business Server 数据中心与 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。</span><span class="sxs-lookup"><span data-stu-id="b68eb-232">However, we do support coexistence of Skype for Business Server datacenters with Lync Server 2010 or Lync Server 2013 SBA/SBS.</span></span> 
  
<span data-ttu-id="b68eb-233">规划采用关联分支就地升级 Lync Server 2013 前端 (FE) 池时，可以将现有用户留在 Lync Server 2013 SBA/SBS 上。</span><span class="sxs-lookup"><span data-stu-id="b68eb-233">When planning for an In-Place Upgrade of a Lync Server 2013 Front End (FE) pool with an associated branch, you can leave the existing users on the Lync Server 2013 SBA/SBS.</span></span> <span data-ttu-id="b68eb-234">在升级过程中，SBA/SBS 用户将进入恢复模式，并在升级完成后返回正常功能。</span><span class="sxs-lookup"><span data-stu-id="b68eb-234">During the upgrade, the SBA/SBS users will go in resiliency mode and will return to normal functionality after the upgrade has completed.</span></span> <span data-ttu-id="b68eb-235">恢复能力模式期间用户体验的详细信息，请参阅[Lync Server 2013 中的分支站点恢复能力功能](https://technet.microsoft.com/library/gg398715.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-235">For more information about the users' experience during the resiliency mode, please see [Branch-site resiliency features in Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).</span></span>
  
<span data-ttu-id="b68eb-236">将 Lync Server 2010 拓扑迁移到 Skype for Business Server 2015 时，与迁移到 Lync Server 2013 类似，必须将 SBA/SBS 重新添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="b68eb-236">When migrating a Lync Server 2010 topology to Skype for Business Server 2015, the SBA/SBS must re-added to the topology, similar to the migration to Lync Server 2013.</span></span> <span data-ttu-id="b68eb-237">有关所需的步骤，请阅读[到 Lync Server 2013 前端池的连接 Survivable Branch Appliance](https://technet.microsoft.com/library/jj688026.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b68eb-237">For the required steps, please read [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](https://technet.microsoft.com/library/jj688026.aspx).</span></span>
  
<span data-ttu-id="b68eb-238">为 Lync Server 2010 和 Lync Server 2013 的共存拓扑，对齐首先给与 Lync Server 2013 和 Lync Server 2010 共存支持一节中所做的建议。</span><span class="sxs-lookup"><span data-stu-id="b68eb-238">For co-existence topologies of Lync Server 2010 and Lync Server 2013, align first to the recommendations made in the section 'Support for coexistence with Lync Server 2013 and Lync Server 2010'.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b68eb-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b68eb-239">See also</span></span>
<span data-ttu-id="b68eb-240"><a name="BKMK_PlanUpgradeFromLync2013"> </a></span><span class="sxs-lookup"><span data-stu-id="b68eb-240"></span></span>

[<span data-ttu-id="b68eb-241">升级到 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b68eb-241">Upgrade to Skype for Business Server 2015</span></span>](../deploy/upgrade-to-skype-for-business-server.md)
  
[<span data-ttu-id="b68eb-242">Environmental requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b68eb-242">Environmental requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/environmental-requirements.md)
  
[<span data-ttu-id="b68eb-243">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b68eb-243">Server requirements for Skype for Business Server 2015</span></span>](requirements-for-your-environment/server-requirements.md)
