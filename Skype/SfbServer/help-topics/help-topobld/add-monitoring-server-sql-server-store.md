---
title: 添加监控服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 监视服务器需要 SQL Server 数据库软件的受支持的64位版本才能存储监视数据。 您可以选择一个以前定义的用于监视的 SQL Server 数据库，或者，通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，以及要用于新 SQL Server 数据库的 SQL Server 实例 (该数据库可以是默认实例，也可以是指定的命名实例) 。
ms.openlocfilehash: adeb5385b385345163d7dc99b0a652837ab8bca4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217893"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="4ce01-104">添加监控服务器 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="4ce01-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="4ce01-105">监视服务器需要 SQL Server 数据库软件的受支持的64位版本才能存储监视数据。</span><span class="sxs-lookup"><span data-stu-id="4ce01-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="4ce01-106">您可以选择一个以前定义的用于监视的 SQL Server 数据库，或者，通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，以及要用于新 SQL Server 数据库的 SQL Server 实例 (该数据库可以是默认实例，也可以是指定的命名实例) 。</span><span class="sxs-lookup"><span data-stu-id="4ce01-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="4ce01-107">有关 SQL Server 支持的详细信息，请参阅可支持性文档中的 [数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="4ce01-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="4ce01-108">有关监控数据库的详细信息（包括监控数据库的并置），请参阅可支持性文档中的 [支持的服务器位置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) 、规划在规划文档中[进行监视](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) 以及部署文档中的 [日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="4ce01-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce01-109">如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。</span><span class="sxs-lookup"><span data-stu-id="4ce01-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="4ce01-110">还可以稍后创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="4ce01-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="4ce01-111">> 若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是要在其中安装数据库文件的基于 SQL server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="4ce01-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="4ce01-112">如果您不是 SQL Server sysadmin 组的成员，则必须请求将添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="4ce01-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="4ce01-113">如果不能成为 sysadmin 组的成员，则应为 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="4ce01-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="4ce01-114">有关完成这些步骤所需的用户权限和权限的详细信息，请参阅部署文档中 [的 SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="4ce01-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


