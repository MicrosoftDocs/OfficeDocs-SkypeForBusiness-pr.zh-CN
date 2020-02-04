---
title: 添加存档服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 存档服务器需要支持的 SQL Server 数据库软件的64位版本才能存储存档数据。 你可以选择要用于存档的以前定义的 SQL Server 数据库，也可以通过指定 SQL Server 数据库将驻留的服务器的完全限定的域名（FQDN）和 SQL Server 实例（该 sql Server 的 SQL Server 实例）来定义新的 sql server 数据库。你想要用于新的 SQL Server 数据库（它可以是你指定的默认实例或命名实例）。
ms.openlocfilehash: 232b363e3a43f0cd58783a829bfe672434385fa8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698667"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="dcdf5-104">添加存档服务器 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="dcdf5-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="dcdf5-105">存档服务器需要支持的 SQL Server 数据库软件的64位版本才能存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="dcdf5-106">你可以选择要用于存档的以前定义的 SQL Server 数据库，也可以通过指定 SQL Server 数据库将驻留的服务器的完全限定的域名（FQDN）和 SQL Server 实例（该 sql Server 的 SQL Server 实例）来定义新的 sql server 数据库。你想要用于新的 SQL Server 数据库（它可以是你指定的默认实例或命名实例）。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="dcdf5-107">如果用于发布拓扑的帐户具有相应的用户权利和权限，则可以在发布拓扑时创建存档数据库（LcsLog）。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="dcdf5-108">你还可以稍后创建数据库，作为安装过程的一部分或其他方式。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="dcdf5-109">若要在基于 SQL Server 的服务器上安装和部署数据库以用于存档，您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="dcdf5-110">如果您不是 SQL Server sysadmin 组的成员，则必须请求将其添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="dcdf5-111">如果你不能成为 sysadmin 组的成员，你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="dcdf5-112">有关完成这些步骤所需的用户权限和权限的详细信息，请参阅部署文档中的[SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dcdf5-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


