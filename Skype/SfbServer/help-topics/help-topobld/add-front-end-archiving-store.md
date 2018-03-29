---
title: 添加前端归档存储
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件，以将存储存档数据。 可以选择以前定义的 SQL Server 数据库，以用于存档，或者通过指定的 SQL Server 数据库将驻留，除了 SQL Se 的实例的服务器的完全合格的域名称 (FQDN) 来定义一个新的 SQL Server 数据库要使用新的 SQL Server 数据库 （它可以是默认实例或命名的实例指定） 的进行服务器。
ms.openlocfilehash: 528c8062b07593a4c7e4cc00f3d1d2566c05f77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="2a958-104">添加前端归档存储</span><span class="sxs-lookup"><span data-stu-id="2a958-104">Add Front End Archiving Store</span></span>
 
<span data-ttu-id="2a958-105">存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件，以将存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="2a958-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="2a958-106">可以选择以前定义的 SQL Server 数据库，以用于存档，或者通过指定的 SQL Server 数据库将驻留，除了 SQL Se 的实例的服务器的完全合格的域名称 (FQDN) 来定义一个新的 SQL Server 数据库要使用新的 SQL Server 数据库 （它可以是默认实例或命名的实例指定） 的进行服务器。</span><span class="sxs-lookup"><span data-stu-id="2a958-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a958-107">如果用来发布拓扑的帐户具有适当的用户权限和权限，您可以创建监视数据库，当发布您的拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="2a958-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="2a958-108">您稍后还可创建数据库（包括在安装过程中）。</span><span class="sxs-lookup"><span data-stu-id="2a958-108">You can also create the database later, included as part of the installation procedure.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2a958-109">要安装和部署用于监视基于 SQL Server 的服务器上的数据库时，您必须是要安装的数据库文件的基于 SQL Server 的服务器的 SQL Server 系统管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="2a958-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="2a958-110">如果您不是 SQL Server 系统管理员组的成员，您必须请求部署数据库文件之前要添加到组。</span><span class="sxs-lookup"><span data-stu-id="2a958-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="2a958-111">如果不能进行系统管理员组的成员，应将您的 SQL Server 数据库管理员提供的脚本来配置和部署数据库。</span><span class="sxs-lookup"><span data-stu-id="2a958-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="2a958-112">有关完成这些过程所需的权限和用户权限的详细信息，请参阅部署文档中的[SQL Server 部署权限](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2a958-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

