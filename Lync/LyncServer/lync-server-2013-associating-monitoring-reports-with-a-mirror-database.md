---
title: 'Lync Server 2013: 将监视报告与镜像数据库相关联'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="f9956-102">将监视报告与 Lync Server 2013 中的镜像数据库相关联</span><span class="sxs-lookup"><span data-stu-id="f9956-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9956-103">_**主题上次修改时间:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f9956-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f9956-104">如果您为监控数据库配置了镜像，该镜像数据库将在发生故障转移时接任主数据库。</span><span class="sxs-lookup"><span data-stu-id="f9956-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="f9956-105">但是, 如果你使用 Lync Server Monitoring Reports, 并且发生故障转移, 你可能会发现你的监视报告未连接到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="f9956-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="f9956-106">这是因为在安装监控报告时，您仅指定了主数据库的位置，未指定镜像数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="f9956-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="f9956-p102">要使监控报告自动故障转移到镜像数据库，您必须将镜像数据库作为“故障转移合作伙伴”添加到监控报告使用的两个数据库（一个数据库用于存放呼叫详细信息记录数据，另一个用于存放用户体验质量 (QoE) 数据）。（注意，此步骤应在安装监控报告后执行。）您可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移伙伴信息。为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="f9956-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="f9956-p103">使用 Internet Explorer 打开“**SQL Server Reporting Services**”主页。Reporting Services 主页 URL 包括：</span><span class="sxs-lookup"><span data-stu-id="f9956-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="f9956-112">**http:** 前缀。</span><span class="sxs-lookup"><span data-stu-id="f9956-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="f9956-113">用于安装 Reporting Services 的计算机的完全限定域名 (FQDN)。（例如 **atl-sql-001.litwareinc.com**）。</span><span class="sxs-lookup"><span data-stu-id="f9956-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="f9956-114">字符串 **/Reports\_**。</span><span class="sxs-lookup"><span data-stu-id="f9956-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="f9956-115">用于安装监控报告的数据库实例的名称（例如 **archinst**）。</span><span class="sxs-lookup"><span data-stu-id="f9956-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="f9956-116">例如，如果 SQL Server Reporting Services 安装在 atl-sql-001.litwareinc.com 上的计算机上，监控报告使用数据库实例 archinst，则主页 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9956-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="f9956-117">访问报表服务主页后, 单击 " **LyncServerReports**", 然后单击 "**报表\_内容**"。</span><span class="sxs-lookup"><span data-stu-id="f9956-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="f9956-118">将转到 Lync Server Monitoring Reports 的 "**报告\_内容**" 页面。</span><span class="sxs-lookup"><span data-stu-id="f9956-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="f9956-119">在 "**报表\_内容**" 页面上, 单击 " **CDRDB** " 数据源。</span><span class="sxs-lookup"><span data-stu-id="f9956-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="f9956-p105">在“**CDRDB**”页上，在“**属性**”选项卡上查找标为“**连接字符串**”的文本框。当前连接字符串类似如下形式：</span><span class="sxs-lookup"><span data-stu-id="f9956-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="f9956-122">**数据源 = (local)\\archinst; 初始目录 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="f9956-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="f9956-p106">编辑连接字符串以包括服务器名称和镜像数据库的数据库实例。例如，如果服务器名为 atl-mirror-001，镜像数据库采用 archinst 实例，则您需要使用以下语法进行添加以指定镜像数据库：</span><span class="sxs-lookup"><span data-stu-id="f9956-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="f9956-125">**故障转移合作伙伴 = atl-镜像-\\001 archinst**</span><span class="sxs-lookup"><span data-stu-id="f9956-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="f9956-126">您编辑的连接字符串类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="f9956-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="f9956-127">**数据源 = (本地)\\archinst;故障转移合作伙伴 = atl-镜像-\\001 archinst; 初始目录 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="f9956-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="f9956-128">更新连接字符串后，单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="f9956-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="f9956-129">在 " **CDRDB** " 页面上, 单击 "**报告\_内容**" 链接。</span><span class="sxs-lookup"><span data-stu-id="f9956-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="f9956-130">单击“**QMSDB**”数据源，然后编辑 QoE 数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f9956-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="f9956-131">例如：</span><span class="sxs-lookup"><span data-stu-id="f9956-131">For example:</span></span>
    
    <span data-ttu-id="f9956-132">**数据源 = (本地)\\archinst;故障转移合作伙伴 = atl-镜像-\\001 archinst; 初始目录 = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="f9956-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="f9956-133">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="f9956-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f9956-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9956-134">See Also</span></span>


[<span data-ttu-id="f9956-135">安装 Lync Server 2013 监视报告</span><span class="sxs-lookup"><span data-stu-id="f9956-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="f9956-136">在 Lync Server 2013 中使用监视报告</span><span class="sxs-lookup"><span data-stu-id="f9956-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

