---
title: 添加存档服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 存档服务器需要支持的 SQL Server 数据库软件的64位版本才能存储存档数据。 你可以选择要用于存档的以前定义的 SQL Server 数据库, 也可以通过指定 SQL Server 数据库将驻留的服务器的完全限定的域名 (FQDN) 和 SQL Server 实例 (该 sql Server 的 SQL Server 实例) 来定义新的 sql server 数据库。你想要用于新的 SQL Server 数据库 (它可以是你指定的默认实例或命名实例)。
ms.openlocfilehash: cda788a83b67b94f4064ca2f967878b88527b0c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304938"
---
# <a name="add-archiving-server-sql-server-store"></a>添加存档服务器 SQL Server 存储

存档服务器需要支持的 SQL Server 数据库软件的64位版本才能存储存档数据。 你可以选择要用于存档的以前定义的 SQL Server 数据库, 也可以通过指定 SQL Server 数据库将驻留的服务器的完全限定的域名 (FQDN) 和 SQL Server 实例 (该 sql Server 的 SQL Server 实例) 来定义新的 sql server 数据库。你想要用于新的 SQL Server 数据库 (它可以是你指定的默认实例或命名实例)。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权利和权限, 则可以在发布拓扑时创建存档数据库 (LcsLog)。 你还可以稍后创建数据库, 作为安装过程的一部分或其他方式。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库以用于存档, 您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。 如果您不是 SQL Server sysadmin 组的成员, 则必须请求将其添加到组中, 直到部署数据库文件。 如果你不能成为 sysadmin 组的成员, 你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些步骤所需的用户权限和权限的详细信息, 请参阅部署文档中的[SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


