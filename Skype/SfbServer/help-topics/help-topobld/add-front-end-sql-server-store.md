---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: 部署 Standard Edition server 自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，所有选项都预先都填充，并且您无法更改为默认配置。
ms.openlocfilehash: b85c98f81be4dc53a9a7b5d0bfea708fd267135b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894386"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="813a2-104">添加前端 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="813a2-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="813a2-105">部署 Standard Edition server 自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="813a2-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="813a2-106">因此，所有选项都预先都填充，并且您无法更改为默认配置。</span><span class="sxs-lookup"><span data-stu-id="813a2-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="813a2-107">Enterprise Edition 服务器部署中的前端池的后端数据库需要的 SQL Server 数据库软件的支持的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="813a2-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="813a2-108">您可以选择先前定义的 SQL Server 数据库，用于后端数据库，或通过指定在其上驻留，SQL Server 数据库的服务器和 SQL S 实例的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 的服务器。</span><span class="sxs-lookup"><span data-stu-id="813a2-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="813a2-109">您还可以选择启用镜像 SQL Server 存储，并指定镜像见证的自动故障转移。</span><span class="sxs-lookup"><span data-stu-id="813a2-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="813a2-110">有关 SQL Server 的详细信息支持，请参阅可支持性文档中的[数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="813a2-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="813a2-111">有关为后端数据库的 SQL Server 设置的详细信息，请参阅部署文档中的[Lync Server 2010 配置 SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="813a2-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="813a2-112">如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建后端数据库 （实时通信 (RTC)） 发布您的拓扑时。</span><span class="sxs-lookup"><span data-stu-id="813a2-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="813a2-113">您还可以创建数据库更高版本，包括安装过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="813a2-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="813a2-114">若要安装和部署 Enterprise Edition 部署中的基于 SQL Server 的服务器上的数据库，您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="813a2-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="813a2-115">如果您不是 SQL Server sysadmins 组的成员，您必须请求添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="813a2-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="813a2-116">如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。</span><span class="sxs-lookup"><span data-stu-id="813a2-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="813a2-117">有关用户权限和完成这些过程所需的权限的详细信息，请参阅[SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="813a2-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


