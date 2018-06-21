---
title: 添加监控服务器 SQL Server 存储
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 监控服务器需要支持的 64 位版本的 SQL Server 数据库软件存储监视数据。 您可以选择先前定义的 SQL Server 数据库，用于监控，或通过指定在其的 SQL Server 数据库将位于，除了 SQL 实例的服务器的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 的服务器。
ms.openlocfilehash: 362f4be3d778d0c5607f6c0ee1233d85d6b9149e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19969769"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="a1d06-104">添加监控服务器 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="a1d06-104">Add Monitoring Server SQL Server Store</span></span>
 
<span data-ttu-id="a1d06-105">监控服务器需要支持的 64 位版本的 SQL Server 数据库软件存储监视数据。</span><span class="sxs-lookup"><span data-stu-id="a1d06-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="a1d06-106">您可以选择先前定义的 SQL Server 数据库，用于监控，或通过指定在其的 SQL Server 数据库将位于，除了 SQL 实例的服务器的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 的服务器。</span><span class="sxs-lookup"><span data-stu-id="a1d06-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
<span data-ttu-id="a1d06-107">有关 SQL Server 的详细信息支持，请参阅可支持性文档中的[数据库软件和群集支持](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a1d06-107">For details about SQL Server support, see [Database Software and Clustering Support](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="a1d06-108">详细信息监视数据库，包括并置的监控数据库，请参阅[支持的服务器位置](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)可支持性文档中的规划文档和[SQL Server 数据的[Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)中和日志文件放置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)部署文档中。</span><span class="sxs-lookup"><span data-stu-id="a1d06-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1d06-109">如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建的监控数据库时发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a1d06-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="a1d06-110">您还可以创建数据库更高版本，包括安装过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1d06-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="a1d06-111">> 到安装和部署监控的基于 SQL Server 的服务器上的数据库，您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="a1d06-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="a1d06-112">如果您不是 SQL Server sysadmin 组的成员，您必须请求添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="a1d06-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="a1d06-113">如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。</span><span class="sxs-lookup"><span data-stu-id="a1d06-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="a1d06-114">有关用户权限和完成这些过程所需的权限的详细信息，请参阅部署文档中的[SQL Server 的部署权限](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a1d06-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

