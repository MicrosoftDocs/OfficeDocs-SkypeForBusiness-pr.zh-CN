---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition Server 部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和SQL Server数据库。 因此，所有选项都预填充，你无法对默认配置进行更改。
ms.openlocfilehash: 6861fd20c8f3e164a4d8d713dfc725bd2f949acd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118671"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="b142f-104">添加前端 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="b142f-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="b142f-105">Standard Edition Server 部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和SQL Server数据库。</span><span class="sxs-lookup"><span data-stu-id="b142f-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="b142f-106">因此，所有选项都预填充，你无法对默认配置进行更改。</span><span class="sxs-lookup"><span data-stu-id="b142f-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="b142f-107">Enterprise Edition 服务器部署的前端池需要支持的 64 位版本的 SQL Server 数据库软件用于后端数据库。</span><span class="sxs-lookup"><span data-stu-id="b142f-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="b142f-108">可以选择之前定义的 SQL Server 数据库用于后端数据库，或者通过指定 SQL Server SQL Server 数据库所在的服务器的完全限定域名 (FQDN) ，以及要用于新的 SQL Server 数据库 (（可以是默认实例）或指定) 的命名实例来定义新的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="b142f-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="b142f-109">还可以选择在数据库存储上启用SQL Server，并指定用于自动故障转移的镜像见证。</span><span class="sxs-lookup"><span data-stu-id="b142f-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="b142f-110">有关支持SQL Server的详细信息，请参阅可支持性文档中 [的数据库软件和群集](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 支持。</span><span class="sxs-lookup"><span data-stu-id="b142f-110">For details about SQL Server support, see [Database Software and Clustering Support](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) in the Supportability documentation.</span></span> <span data-ttu-id="b142f-111">有关为后端数据库SQL Server的详细信息，请参阅部署文档中的[Configure SQL Server。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span><span class="sxs-lookup"><span data-stu-id="b142f-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="b142f-112">如果用于发布拓扑的帐户具有相应的用户权限，您可以在发布拓扑时创建后端数据库 (实时通信 (RTC) ) 。</span><span class="sxs-lookup"><span data-stu-id="b142f-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="b142f-113">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="b142f-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="b142f-114">若要在基于 SQL Server 的服务器上为 Enterprise Edition 部署安装和部署数据库，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="b142f-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="b142f-115">如果您不是 sysadmins SQL Server的成员，则必须请求添加到组，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="b142f-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="b142f-116">如果您无法成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="b142f-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="b142f-117">有关完成这些过程所需的用户权限的详细信息，请参阅 [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="b142f-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).</span></span>