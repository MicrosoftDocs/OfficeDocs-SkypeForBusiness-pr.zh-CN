---
title: 添加前端存档存储
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 存档需要 Microsoft SQL Server 数据库软件的受支持的64位版本才能存储存档数据。 您可以选择以前定义的用于存档的 SQL Server 数据库，或者，通过指定 SQL Server 数据库所驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，以及要用于新 SQL Server 数据库的 SQL Server 实例 (它可以是默认实例，也可以是指定的指定实例，) 指定的名称。
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216713"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="01328-104">添加前端存档存储</span><span class="sxs-lookup"><span data-stu-id="01328-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="01328-105">存档需要 Microsoft SQL Server 数据库软件的受支持的64位版本才能存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="01328-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="01328-106">您可以选择以前定义的用于存档的 SQL Server 数据库，或者，通过指定 SQL Server 数据库所驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，以及要用于新 SQL Server 数据库的 SQL Server 实例 (它可以是默认实例，也可以是指定的指定实例，) 指定的名称。</span><span class="sxs-lookup"><span data-stu-id="01328-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="01328-107">如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。</span><span class="sxs-lookup"><span data-stu-id="01328-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="01328-108">您还可以在以后创建数据库，包括在安装过程中。</span><span class="sxs-lookup"><span data-stu-id="01328-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="01328-109">若要在基于 SQL Server 的服务器上安装和部署数据库以进行监视，您必须是要在其中安装数据库文件的基于 SQL server 的服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="01328-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="01328-110">如果您不是 SQL Server sysadmin 组的成员，则必须请求将您添加到组中，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="01328-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="01328-111">如果不能成为 sysadmin 组的成员，则应为 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="01328-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="01328-112">有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="01328-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


