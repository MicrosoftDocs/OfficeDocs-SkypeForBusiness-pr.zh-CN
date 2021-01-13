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
description: 监控服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储监控数据。 除了要用于新 SQL Server SQL Server 数据库 (（可以是默认实例）或指定指定) 实例的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，
ms.openlocfilehash: 53e8a95b179c3e15f52b694710248b5155ef8d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828692"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="7d821-104">添加监控服务器 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="7d821-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="7d821-105">监控服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储监控数据。</span><span class="sxs-lookup"><span data-stu-id="7d821-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="7d821-106">除了要用于新 SQL Server SQL Server 数据库 (（可以是默认实例）或指定指定) 实例的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，</span><span class="sxs-lookup"><span data-stu-id="7d821-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="7d821-107">有关支持SQL Server，请参阅可支持性文档中的数据库 [软件和群集](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 支持。</span><span class="sxs-lookup"><span data-stu-id="7d821-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="7d821-108">有关监控数据库的详细信息，包括监控数据库并置，请参阅可支持性文档中的 Supported [Server Location、](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)规划[](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)文档中的"规划监控"和部署文档中的[SQL Server Data and Log File Placement。](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d821-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="7d821-109">如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。</span><span class="sxs-lookup"><span data-stu-id="7d821-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="7d821-110">还可以稍后创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="7d821-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="7d821-111">>若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是要安装数据库文件的基于 SQL Server 服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="7d821-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7d821-112">如果您不是 sysadmin SQL Server的成员，则必须请求添加到组，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="7d821-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7d821-113">如果您不能成为 sysadmins 组的成员，您应该向您的 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="7d821-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7d821-114">有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中SQL Server部署权限。 [](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d821-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


