---
title: 添加存档 SQL Server 存储
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: 存档服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储存档数据。 可以选择用于存档的以前定义的 SQL Server 数据库，或者通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 以及要用于新数据库的 SQL Server 实例来定义新的 SQL Server 数据库SQL Server database (，可以是默认实例或您指定的命名) 。
ms.openlocfilehash: 11ca3b8a83d565064e573ae8a080f896f846175a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775462"
---
# <a name="add-archiving-server-sql-server-store"></a>添加存档 SQL Server 存储

存档服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储存档数据。 可以选择用于存档的以前定义的 SQL Server 数据库，或者通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 以及要用于新数据库的 SQL Server 实例来定义新的 SQL Server 数据库SQL Server database (，可以是默认实例或您指定的命名) 。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则您可以在发布拓扑时创建存档数据库 (LcsLog)。也可以稍后在安装过程中或其他操作过程中创建数据库。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库进行存档，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmins SQL Server的成员，则必须请求添加到组，直到部署数据库文件。 如果您无法成为 sysadmins 组的成员，您应向 SQL Server 管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。