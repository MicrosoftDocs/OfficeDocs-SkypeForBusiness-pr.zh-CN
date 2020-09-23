---
title: 添加存档 SQL Server 存储
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
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 存档服务器需要一个受支持的 SQL Server 数据库软件的64位版本来存储存档数据。 通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，以及要用于新 SQL Server 数据库的 SQL Server 实例，可以选择以前定义的 SQL Server 数据库，以便将其用于存档或定义新的 SQL server 数据库 (该数据库可以是您指定的默认实例或命名实例的) 。
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217433"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="4fe6f-104">添加存档 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="4fe6f-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="4fe6f-105">存档服务器需要一个受支持的 SQL Server 数据库软件的64位版本来存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="4fe6f-106">通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，以及要用于新 SQL Server 数据库的 SQL Server 实例，可以选择以前定义的 SQL Server 数据库，以便将其用于存档或定义新的 SQL server 数据库 (该数据库可以是您指定的默认实例或命名实例的) 。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="4fe6f-p103">如果用于发布拓扑的帐户具有相应的用户权限，则您可以在发布拓扑时创建存档数据库 (LcsLog)。也可以稍后在安装过程中或其他操作过程中创建数据库。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="4fe6f-109">若要在基于 SQL Server 的服务器上安装和部署数据库以进行存档，您必须是要在其中安装数据库文件的基于 SQL server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="4fe6f-110">如果您不是 SQL Server sysadmin 组的成员，则必须请求将添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="4fe6f-111">如果不能成为 sysadmin 组的成员，则应为 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="4fe6f-112">有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4fe6f-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


