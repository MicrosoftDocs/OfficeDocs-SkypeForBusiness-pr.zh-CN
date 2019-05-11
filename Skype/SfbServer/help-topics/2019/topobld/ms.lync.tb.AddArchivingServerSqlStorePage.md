---
title: 添加存档服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: 存档服务器需要支持的 64 位版本的 SQL Server 数据库软件存储存档数据。 您可以选择先前定义的 SQL Server 数据库，用于存档或通过指定在其将驻留的 SQL Server 数据库，server 和 SQL Server 实例的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库的您想要用于新的 SQL Server 数据库 （这可以是默认实例或您指定的命名的实例）。
ms.openlocfilehash: 340282aabee67e758741e26dc1c586c44c13210d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889218"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="9b609-104">添加存档服务器 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="9b609-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="9b609-105">存档服务器需要支持的 64 位版本的 SQL Server 数据库软件存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="9b609-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="9b609-106">您可以选择先前定义的 SQL Server 数据库，用于存档或通过指定在其将驻留的 SQL Server 数据库，server 和 SQL Server 实例的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库的您想要用于新的 SQL Server 数据库 （这可以是默认实例或您指定的命名的实例）。</span><span class="sxs-lookup"><span data-stu-id="9b609-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="9b609-107">如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建存档数据库 (LcsLog)，当您发布您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b609-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="9b609-108">您还可以更高版本，安装过程的一部分创建数据库或其他方式。</span><span class="sxs-lookup"><span data-stu-id="9b609-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="9b609-109">若要安装和部署存档的基于 SQL Server 的服务器上的数据库，您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="9b609-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="9b609-110">如果您不是 SQL Server sysadmins 组的成员，您必须请求添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="9b609-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="9b609-111">如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。</span><span class="sxs-lookup"><span data-stu-id="9b609-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="9b609-112">有关用户权限和完成这些过程所需的权限的详细信息，请参阅部署文档中的[SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9b609-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


