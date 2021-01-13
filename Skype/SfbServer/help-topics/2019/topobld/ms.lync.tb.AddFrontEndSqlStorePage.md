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
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811622"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="fee04-104">添加前端 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="fee04-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="fee04-105">Standard Edition Server 部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和SQL Server数据库。</span><span class="sxs-lookup"><span data-stu-id="fee04-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="fee04-106">因此，所有选项都预填充，你无法对默认配置进行更改。</span><span class="sxs-lookup"><span data-stu-id="fee04-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="fee04-107">Enterprise Edition Server 部署的前端池要求后端数据库支持 64 SQL Server版本的数据库软件。</span><span class="sxs-lookup"><span data-stu-id="fee04-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="fee04-108">可以选择以前定义的 SQL Server 数据库以用于后端数据库，或者通过指定要驻留 SQL Server 数据库的服务器的完全限定域名 (FQDN) 和要用于新的 SQL Server SQL Server 数据库 (（可以是默认实例）或指定) 的命名实例来定义新的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="fee04-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="fee04-109">还可以选择在数据库存储上启用镜像SQL Server，并指定用于自动故障转移的镜像见证。</span><span class="sxs-lookup"><span data-stu-id="fee04-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="fee04-110">有关支持SQL Server，请参阅可支持性文档中的数据库 [软件和群集](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 支持。</span><span class="sxs-lookup"><span data-stu-id="fee04-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="fee04-111">有关为后端数据库SQL Server的详细信息，请参阅部署文档中SQL Server配置数据库。 [](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="fee04-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="fee04-112">如果用于发布拓扑的帐户具有相应的用户权限，您可以在发布拓扑时创建后端数据库 (实时通信 (RTC) ) 。</span><span class="sxs-lookup"><span data-stu-id="fee04-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="fee04-113">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="fee04-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="fee04-114">若要在基于 SQL Server 的服务器上安装和部署数据库以用于 Enterprise Edition 部署，您必须是要安装数据库文件的基于 SQL Server 服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="fee04-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="fee04-115">如果您不是 sysadmins SQL Server的成员，则必须请求添加到该组，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="fee04-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="fee04-116">如果您不能成为 sysadmins 组的成员，您应该向您的 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="fee04-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="fee04-117">有关完成这些过程所需的用户权限的详细信息，请参阅部署权限[SQL Server。](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)</span><span class="sxs-lookup"><span data-stu-id="fee04-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


