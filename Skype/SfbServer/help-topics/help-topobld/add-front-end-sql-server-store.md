---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition server 部署将自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，所有选项均已预填充，并且您无法更改默认配置。
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216493"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="48500-104">添加前端 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="48500-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="48500-105">Standard Edition server 部署将自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="48500-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="48500-106">因此，所有选项均已预填充，并且您无法更改默认配置。</span><span class="sxs-lookup"><span data-stu-id="48500-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="48500-107">Enterprise Edition server 部署的前端池需要针对后端数据库的 SQL Server 数据库软件支持的64位版本。</span><span class="sxs-lookup"><span data-stu-id="48500-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="48500-108">您可以选择以前定义的用于后端数据库的 SQL Server 数据库，或定义新的 SQL Server 数据库，具体方法是：指定要在其上驻留 SQL Server 数据库的服务器 (FQDN) 的完全限定域名，以及要用于新 SQL Server 数据库的 SQL Server 实例 (可以是默认实例，也可以是指定的命名实例) 。</span><span class="sxs-lookup"><span data-stu-id="48500-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="48500-109">您还可以选择启用 SQL Server 存储上的镜像，并指定用于自动故障转移的镜像见证。</span><span class="sxs-lookup"><span data-stu-id="48500-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="48500-110">有关 SQL Server 支持的详细信息，请参阅可支持性文档中的 [数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="48500-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="48500-111">有关设置 SQL Server 作为后端数据库的详细信息，请参阅部署文档中的[为 Lync Server 2010 配置 SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48500-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="48500-112">如果用于发布拓扑的帐户具有相应的用户权限和权限，则可以在发布拓扑时创建后端数据库 (实时通信 (RTC) # A3。</span><span class="sxs-lookup"><span data-stu-id="48500-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="48500-113">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="48500-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="48500-114">若要在部署企业版的基于 SQL Server 的服务器上安装和部署数据库，您必须是要在其中安装数据库文件的基于 SQL server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="48500-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="48500-115">如果您不是 SQL Server sysadmin 组的成员，则必须请求将添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="48500-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="48500-116">如果不能成为 sysadmin 组的成员，则应为 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="48500-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="48500-117">有关完成这些步骤所需的用户权限和权限的详细信息，请参阅 [SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="48500-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


