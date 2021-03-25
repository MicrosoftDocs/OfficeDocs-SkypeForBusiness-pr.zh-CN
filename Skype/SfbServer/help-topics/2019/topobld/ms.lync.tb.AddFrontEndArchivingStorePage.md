---
title: 添加前端存档存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 (（可以是默认实例）或指定指定) 的命名实例的 SQL Server 实例之外，还可以选择以前定义的用于存档的 SQL Server 数据库，或者通过指定 SQL Server 数据库所在的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库。
ms.openlocfilehash: ae9c90cedc7be4e60689978b28eecce2031a4991
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122663"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="cd3df-104">添加前端存档存储</span><span class="sxs-lookup"><span data-stu-id="cd3df-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="cd3df-105">存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="cd3df-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="cd3df-106">除了要用于新的 SQL Server 数据库 (（可以是默认实例）或指定指定) 的命名实例的 SQL Server 实例之外，还可以选择以前定义的用于存档的 SQL Server 数据库，或者通过指定 SQL Server 数据库所在的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="cd3df-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="cd3df-107">如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。</span><span class="sxs-lookup"><span data-stu-id="cd3df-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="cd3df-108">您还可以稍后创建数据库，该数据库包含在安装过程中。</span><span class="sxs-lookup"><span data-stu-id="cd3df-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="cd3df-109">若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是要安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="cd3df-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="cd3df-110">如果您不是 sysadmin SQL Server的成员，则必须请求将您添加到该组，直到部署数据库文件。</span><span class="sxs-lookup"><span data-stu-id="cd3df-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="cd3df-111">如果您无法成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。</span><span class="sxs-lookup"><span data-stu-id="cd3df-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="cd3df-112">有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="cd3df-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>