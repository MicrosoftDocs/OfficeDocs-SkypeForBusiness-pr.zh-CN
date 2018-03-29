---
title: 将监视报告与 Skype 在镜像数据库相关联的业务服务器 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要： 了解如何监视报告相关联的业务服务器 2015 Skype 使用镜像数据库。
ms.openlocfilehash: 246f16fd54133e2a6cf1e26a8126d0ec546bd686
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server-2015"></a><span data-ttu-id="16232-103">将监视报告与 Skype 在镜像数据库相关联的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="16232-103">Associate Monitoring Reports with a mirror database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="16232-104">**摘要：**了解如何监视报告相关联的业务服务器 2015 Skype 使用镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="16232-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server 2015.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="16232-105">监控报告与镜像数据库</span><span class="sxs-lookup"><span data-stu-id="16232-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="16232-106">如果您为监控数据库配置了镜像，该镜像数据库将在发生故障转移时接任主数据库。</span><span class="sxs-lookup"><span data-stu-id="16232-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="16232-107">但是，如果您使用 Skype 业务服务器监视报告并且发生故障转移，您可能发现您监视报告都无法连接到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="16232-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="16232-108">这是因为在安装监控报告时，您仅指定了主数据库的位置，未指定镜像数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="16232-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="16232-p102">要使监控报告自动故障转移到镜像数据库，您必须将镜像数据库作为“故障转移合作伙伴”添加到监控报告使用的两个数据库（一个数据库用于存放呼叫详细信息记录数据，另一个用于存放用户体验质量 (QoE) 数据）。（注意，此步骤应在安装监控报告后执行。）您可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移伙伴信息。为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="16232-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="16232-p103">使用 Internet Explorer 打开“**SQL Server Reporting Services**”主页。Reporting Services 主页 URL 包括：</span><span class="sxs-lookup"><span data-stu-id="16232-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="16232-114">**http:** 前缀。</span><span class="sxs-lookup"><span data-stu-id="16232-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="16232-115">用于安装 Reporting Services 的计算机的完全限定域名 (FQDN)。（例如 **atl-sql-001.litwareinc.com**）。</span><span class="sxs-lookup"><span data-stu-id="16232-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="16232-116">字符字符串 **/Reports_**。</span><span class="sxs-lookup"><span data-stu-id="16232-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="16232-117">用于安装监控报告的数据库实例的名称（例如 **archinst**）。</span><span class="sxs-lookup"><span data-stu-id="16232-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="16232-118">例如，如果 SQL Server Reporting Services 安装在 atl-sql-001.litwareinc.com 上的计算机上，监控报告使用数据库实例 archinst，则主页 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="16232-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="16232-119">访问 Reporting Services 主页后，单击“**ServerReports**”，然后单击“**Reports_Content**”。</span><span class="sxs-lookup"><span data-stu-id="16232-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="16232-120">这样，就会到**Reports_Content**页的 Skype 的业务服务器监视报告。</span><span class="sxs-lookup"><span data-stu-id="16232-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="16232-121">在“**Reports_Content**”页上，单击“**CDRDB**”数据源。</span><span class="sxs-lookup"><span data-stu-id="16232-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="16232-p105">在“**CDRDB**”页上，在“**属性**”选项卡上查找标为“**连接字符串**”的文本框。当前连接字符串类似如下形式：</span><span class="sxs-lookup"><span data-stu-id="16232-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="16232-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="16232-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="16232-p106">编辑连接字符串以包括服务器名称和镜像数据库的数据库实例。例如，如果服务器名为 atl-mirror-001，镜像数据库采用 archinst 实例，则您需要使用以下语法进行添加以指定镜像数据库：</span><span class="sxs-lookup"><span data-stu-id="16232-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="16232-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="16232-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="16232-128">您编辑的连接字符串类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="16232-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="16232-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="16232-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="16232-130">更新连接字符串后，单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="16232-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="16232-p107">在“**CDRDB**”页上，单击“**Reports_Content**”链接。单击“**QMSDB**”数据源，然后编辑 QoE 数据库的连接字符串。例如：</span><span class="sxs-lookup"><span data-stu-id="16232-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="16232-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="16232-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="16232-135">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="16232-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="16232-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16232-136">See also</span></span>

#### 

[<span data-ttu-id="16232-137">安装业务服务器 2015年监控在 Skype 的报告</span><span class="sxs-lookup"><span data-stu-id="16232-137">Install Monitoring Reports in Skype for Business Server 2015</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="16232-138">使用业务服务器 2015年监控在 Skype 的报告</span><span class="sxs-lookup"><span data-stu-id="16232-138">Using Monitoring Reports in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)

