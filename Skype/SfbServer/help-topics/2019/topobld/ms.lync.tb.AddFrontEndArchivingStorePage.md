---
title: 添加前端存档存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 存档，需要支持的 64 位版本的 Microsoft SQL Server 数据库软件存储存档数据。 您可以选择先前定义的 SQL Server 数据库，用于存档，或通过指定在其上驻留，除了 SQL Se 实例的 SQL Server 数据库的服务器完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 进行的服务器。
ms.openlocfilehash: 83964daddb7319c99399f0a8fd4bf82cdaf62db9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906737"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="41b12-104">添加前端存档存储</span><span class="sxs-lookup"><span data-stu-id="41b12-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="41b12-105">存档，需要支持的 64 位版本的 Microsoft SQL Server 数据库软件存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="41b12-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="41b12-106">您可以选择先前定义的 SQL Server 数据库，用于存档，或通过指定在其上驻留，除了 SQL Se 实例的 SQL Server 数据库的服务器完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 进行的服务器。</span><span class="sxs-lookup"><span data-stu-id="41b12-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="41b12-107">如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建的监控数据库时发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="41b12-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="41b12-108">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="41b12-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="41b12-109">若要安装和部署监控的基于 SQL Server 的服务器上的数据库，您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="41b12-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="41b12-110">如果您不是 SQL Server sysadmin 组的成员，您必须请求之前部署数据库文件将添加到组。</span><span class="sxs-lookup"><span data-stu-id="41b12-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="41b12-111">如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。</span><span class="sxs-lookup"><span data-stu-id="41b12-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="41b12-112">有关用户权限和完成这些过程所需的权限的详细信息，请参阅部署文档中的[SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41b12-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


