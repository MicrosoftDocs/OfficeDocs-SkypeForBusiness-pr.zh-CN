---
title: 添加监控服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 监控服务器需要受支持的 64 位版本SQL Server数据库软件来存储监控数据。 除了要用于新的 SQL Server 数据库 (（可以是默认实例）或指定指定) 实例的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，从而选择要用于监视的以前定义的 SQL Server 数据库，或者定义新的 SQL Server 数据库。
ms.openlocfilehash: 5c1ef4c7b2474a094492aa7905c044a5da145ff5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119721"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="2c17d-104">添加监控服务器 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="2c17d-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="2c17d-105">监控服务器需要受支持的 64 位版本SQL Server数据库软件来存储监控数据。</span><span class="sxs-lookup"><span data-stu-id="2c17d-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="2c17d-106">除了要用于新的 SQL Server 数据库 (（可以是默认实例）或指定指定) 实例的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，从而选择要用于监视的以前定义的 SQL Server 数据库，或者定义新的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="2c17d-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="2c17d-107">有关支持SQL Server的详细信息，请参阅可支持性文档中 [的数据库软件和群集](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 支持。</span><span class="sxs-lookup"><span data-stu-id="2c17d-107">For details about SQL Server support, see [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) in the Supportability documentation.</span></span> <span data-ttu-id="2c17d-108">有关监控数据库（包括监控数据库并置）的详细信息，请参阅可支持性文档中的S supported [Server Location、](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)规划文档中的 Planning[for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)和部署文档中的 SQL Server Data and Log [File Placement。](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)</span><span class="sxs-lookup"><span data-stu-id="2c17d-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation,[Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="2c17d-109">如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。</span><span class="sxs-lookup"><span data-stu-id="2c17d-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="2c17d-110">还可以稍后创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="2c17d-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="2c17d-111">> 若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="2c17d-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="2c17d-112">如果您不是 sysadmin SQL Server的成员，则必须请求添加到组，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="2c17d-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="2c17d-113">如果您无法成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="2c17d-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="2c17d-114">有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的 Deployment [Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) for SQL Server。</span><span class="sxs-lookup"><span data-stu-id="2c17d-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>