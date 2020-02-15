---
title: Lync Server 2013：将监控报告与镜像数据库相关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d1ec6b1256326cca9e74d47d27820529050721
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="27427-102">在 Lync Server 2013 中将监控报告与镜像数据库相关联</span><span class="sxs-lookup"><span data-stu-id="27427-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27427-103">_**上次修改的主题：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="27427-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="27427-104">如果为监视数据库配置了镜像，则在发生故障转移时，镜像数据库将接管主数据库。</span><span class="sxs-lookup"><span data-stu-id="27427-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="27427-105">但是，如果您使用 Lync Server 监控报告，并且发生故障转移，则您可能会发现监视报告未连接到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="27427-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="27427-106">这是因为，在安装监控报告时，仅指定主数据库的位置;您不指定镜像数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="27427-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="27427-107">若要获取监控报告以自动将故障转移到镜像数据库，您必须将镜像数据库作为 "故障转移合作伙伴" 添加到监视报告使用的两个数据库（一个数据库用于呼叫详细信息记录数据，另一个数据库的质量为体验（QoE）数据）。</span><span class="sxs-lookup"><span data-stu-id="27427-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="27427-108">（请注意，在安装了监控报告之后，应执行此步骤。）您可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移合作伙伴信息。</span><span class="sxs-lookup"><span data-stu-id="27427-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="27427-109">为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="27427-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="27427-110">使用 Internet Explorer 打开**SQL Server Reporting Services**主页。</span><span class="sxs-lookup"><span data-stu-id="27427-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="27427-111">Reporting Services 主页 URL 包括：</span><span class="sxs-lookup"><span data-stu-id="27427-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="27427-112">**Http：** 前缀。</span><span class="sxs-lookup"><span data-stu-id="27427-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="27427-113">安装了 Reporting Services 的计算机的完全限定的域名（FQDN）（例如， **atl-sql-001.litwareinc.com**）。</span><span class="sxs-lookup"><span data-stu-id="27427-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="27427-114">字符字符串 **/Reports\_**。</span><span class="sxs-lookup"><span data-stu-id="27427-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="27427-115">在其中安装监控报告的数据库实例的名称（例如， **archinst**）。</span><span class="sxs-lookup"><span data-stu-id="27427-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="27427-116">例如，如果在计算机 atl-sql-001.litwareinc.com 上安装了 SQL Server Reporting Services，并且监控报告使用的是数据库实例 archinst，则主页 URL 将如下所示：</span><span class="sxs-lookup"><span data-stu-id="27427-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="27427-117">访问 Reporting Services 主页后，单击 " **LyncServerReports**"，然后单击 "**报告\_内容**"。</span><span class="sxs-lookup"><span data-stu-id="27427-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="27427-118">这将转到 Lync Server Monitoring 报告的 "**报告\_内容**" 页。</span><span class="sxs-lookup"><span data-stu-id="27427-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="27427-119">在 "**报告\_内容**" 页上，单击 " **CDRDB** " 数据源。</span><span class="sxs-lookup"><span data-stu-id="27427-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="27427-120">在 " **CDRDB** " 页上的 "**属性**" 选项卡上，查找标有 "**连接字符串**" 的文本框。</span><span class="sxs-lookup"><span data-stu-id="27427-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="27427-121">当前连接字符串将如下所示：</span><span class="sxs-lookup"><span data-stu-id="27427-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="27427-122">**数据源 = （local）\\archinst; 初始目录 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="27427-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="27427-123">编辑连接字符串以包含镜像数据库的服务器名称和数据库实例。</span><span class="sxs-lookup"><span data-stu-id="27427-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="27427-124">例如，如果服务器名为 atl-001，镜像数据库在 archinst 实例中，则需要使用以下语法添加以指定镜像数据库：</span><span class="sxs-lookup"><span data-stu-id="27427-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="27427-125">**故障转移合作伙伴 = atl-mirror-\\001 archinst**</span><span class="sxs-lookup"><span data-stu-id="27427-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="27427-126">已编辑的连接字符串将如下所示：</span><span class="sxs-lookup"><span data-stu-id="27427-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="27427-127">**数据源 = （local）\\archinst;故障转移合作伙伴 = atl-mirror-\\001 archinst; 初始目录 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="27427-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="27427-128">更新连接字符串后，单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="27427-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="27427-129">在 " **CDRDB** " 页上，单击 "**报告\_内容**" 链接。</span><span class="sxs-lookup"><span data-stu-id="27427-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="27427-130">单击 " **QMSDB** " 数据源，然后编辑 QoE 数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="27427-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="27427-131">例如：</span><span class="sxs-lookup"><span data-stu-id="27427-131">For example:</span></span>
    
    <span data-ttu-id="27427-132">**数据源 = （local）\\archinst;故障转移合作伙伴 = atl-mirror-\\001 archinst; 初始目录 = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="27427-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="27427-133">单击“应用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="27427-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="27427-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27427-134">See Also</span></span>


[<span data-ttu-id="27427-135">安装 Lync Server 2013 监控报告</span><span class="sxs-lookup"><span data-stu-id="27427-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="27427-136">在 Lync Server 2013 中使用监控报告</span><span class="sxs-lookup"><span data-stu-id="27427-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

