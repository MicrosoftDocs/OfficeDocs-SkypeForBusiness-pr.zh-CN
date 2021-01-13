---
title: 将监控报告与 Skype for Business Server 中的镜像数据库关联
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要：了解如何将监控报告与 Skype for Business Server 使用的镜像数据库关联。
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802162"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="235eb-103">将监控报告与 Skype for Business Server 中的镜像数据库关联</span><span class="sxs-lookup"><span data-stu-id="235eb-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="235eb-104">**摘要：** 了解如何将监控报告与 Skype for Business Server 使用的镜像数据库关联。</span><span class="sxs-lookup"><span data-stu-id="235eb-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="235eb-105">使用镜像数据库监视报告</span><span class="sxs-lookup"><span data-stu-id="235eb-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="235eb-106">如果为监控数据库配置镜像，该镜像数据库将在发生故障转移时接管为主数据库。</span><span class="sxs-lookup"><span data-stu-id="235eb-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="235eb-107">但是，如果使用 Skype for Business Server 监控报告并发生故障转移，您可能会发现监控报告未连接到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="235eb-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="235eb-108">这是因为，在安装监控报告时，仅指定主数据库的位置;不指定镜像数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="235eb-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="235eb-109">若要使监控报告自动故障转移到镜像数据库，必须将镜像数据库作为"故障转移合作伙伴"添加到监控报告使用的两个数据库中 (一个数据库用于呼叫详细信息记录数据，另一个数据库用于用户体验质量 (QoE) 数据) 。</span><span class="sxs-lookup"><span data-stu-id="235eb-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="235eb-110"> (请注意，应在安装监控报告后执行此步骤。) 可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移合作伙伴信息。</span><span class="sxs-lookup"><span data-stu-id="235eb-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="235eb-111">为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="235eb-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="235eb-112">使用Internet Explorer打开 **SQL Server Reporting Services** 主页。</span><span class="sxs-lookup"><span data-stu-id="235eb-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="235eb-113">Reporting Services 主页 URL 包括：</span><span class="sxs-lookup"><span data-stu-id="235eb-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="235eb-114">**http：** 前缀。</span><span class="sxs-lookup"><span data-stu-id="235eb-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="235eb-115">例如， (安装 Reporting Services) 的计算机的完全限定域名 (FQDN **atl-sql-001.litwareinc.com) 。**</span><span class="sxs-lookup"><span data-stu-id="235eb-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="235eb-116">字符字符串 **/Reports_。**</span><span class="sxs-lookup"><span data-stu-id="235eb-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="235eb-117">安装了监控报告的数据库实例的名称 (例如 **，archinst) 。**</span><span class="sxs-lookup"><span data-stu-id="235eb-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="235eb-118">例如，如果SQL Server Reporting Services 安装在计算机上atl-sql-001.litwareinc.com监控报告使用数据库实例 archinst，则主页 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="235eb-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="235eb-119">访问 Reporting Services 主页后，单击 **ServerReports，\*\*\*\*然后单击Reports_Content。**</span><span class="sxs-lookup"><span data-stu-id="235eb-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="235eb-120">这将将你介绍 skype for **Business Reports_Content** 报告的信息页面。</span><span class="sxs-lookup"><span data-stu-id="235eb-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="235eb-121">在 **Reports_Content** 页上，单击 **CDRDB** 数据源。</span><span class="sxs-lookup"><span data-stu-id="235eb-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="235eb-122">在 **CDRDB 页上** 的"属性 **"选项卡上** ，查找标记为"连接" **字符串的文本框**。</span><span class="sxs-lookup"><span data-stu-id="235eb-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="235eb-123">当前连接字符串将类似于：</span><span class="sxs-lookup"><span data-stu-id="235eb-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="235eb-124">Data source= (local) \archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="235eb-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="235eb-125">编辑连接字符串以包含镜像数据库的服务器名称和数据库实例。</span><span class="sxs-lookup"><span data-stu-id="235eb-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="235eb-126">例如，如果服务器名为 atl-mirror-001，并且镜像数据库位于 archinst 实例中，则需要添加它以使用此语法指定镜像数据库：</span><span class="sxs-lookup"><span data-stu-id="235eb-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="235eb-127">故障转移 Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="235eb-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="235eb-128">编辑的连接字符串如下所示：</span><span class="sxs-lookup"><span data-stu-id="235eb-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="235eb-129">Data source= (local) \archinst;故障转移 Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="235eb-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="235eb-130">更新连接字符串后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="235eb-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="235eb-131">在 **CDRDB 页上** ，单击 **Reports_Content链接** 。</span><span class="sxs-lookup"><span data-stu-id="235eb-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="235eb-132">单击 **QMSDB** 数据源，然后编辑 QoE 数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="235eb-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="235eb-133">例如：</span><span class="sxs-lookup"><span data-stu-id="235eb-133">For example:</span></span>
    
    <span data-ttu-id="235eb-134">Data source= (local) \archinst;故障转移 Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="235eb-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="235eb-135">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="235eb-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="235eb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="235eb-136">See also</span></span>

[<span data-ttu-id="235eb-137">在 Skype for Business Server 中安装监控报告</span><span class="sxs-lookup"><span data-stu-id="235eb-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="235eb-138">在 Skype for Business Server 中使用监控报告</span><span class="sxs-lookup"><span data-stu-id="235eb-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
