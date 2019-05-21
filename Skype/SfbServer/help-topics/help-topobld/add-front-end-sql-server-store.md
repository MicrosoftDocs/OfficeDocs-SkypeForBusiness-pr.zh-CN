---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: 标准版服务器部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此, 所有选项均已预填充, 并且不能对默认配置进行更改。
ms.openlocfilehash: 73e1e9351c5d5b6d9b9f596e2b839037b9081e29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275372"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="9ab7b-104">添加前端 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="9ab7b-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="9ab7b-105">标准版服务器部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="9ab7b-106">因此, 所有选项均已预填充, 并且不能对默认配置进行更改。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="9ab7b-107">企业版服务器部署的前端池需要后端数据库的 SQL Server 数据库软件支持的64位版本。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="9ab7b-108">你可以选择要用于后端数据库的以前定义的 SQL Server 数据库, 或者通过指定 SQL Server 数据库所在服务器的完全限定的域名 (FQDN), 以及 SQL S 的实例来定义新的 SQL Server 数据库。要用于新 SQL Server 数据库的 erver (可以是默认实例或你指定的命名实例)。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="9ab7b-109">你还可以选择在 SQL Server 存储上启用镜像, 并为自动故障转移指定镜像见证。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="9ab7b-110">有关 SQL Server 支持的详细信息, 请参阅支持文档中的[数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="9ab7b-111">有关为后端数据库设置 SQL Server 的详细信息, 请参阅部署文档中的 "[为 Lync server 2010 配置 Sql server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) "。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="9ab7b-112">如果用于发布拓扑的帐户具有相应的用户权限和权限, 则可以在发布拓扑时创建后端数据库 (实时通信 (RTC))。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="9ab7b-113">你还可以稍后创建数据库, 包括安装过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="9ab7b-114">若要在基于 SQL Server 的企业版部署服务器上安装和部署数据库, 您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="9ab7b-115">如果您不是 SQL Server sysadmin 组的成员, 则必须请求将其添加到组中, 直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="9ab7b-116">如果你不能成为 sysadmin 组的成员, 你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="9ab7b-117">有关完成这些步骤所需的用户权限和权限的详细信息, 请参阅[SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9ab7b-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


