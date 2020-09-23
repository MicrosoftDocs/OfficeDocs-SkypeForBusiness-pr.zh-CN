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
# <a name="add-archiving-server-sql-server-store"></a>添加存档 SQL Server 存储

存档服务器需要一个受支持的 SQL Server 数据库软件的64位版本来存储存档数据。 通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，以及要用于新 SQL Server 数据库的 SQL Server 实例，可以选择以前定义的 SQL Server 数据库，以便将其用于存档或定义新的 SQL server 数据库 (该数据库可以是您指定的默认实例或命名实例的) 。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则您可以在发布拓扑时创建存档数据库 (LcsLog)。也可以稍后在安装过程中或其他操作过程中创建数据库。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库以进行存档，您必须是要在其中安装数据库文件的基于 SQL server 的服务器的 SQL Server sysadmin 组的成员。 如果您不是 SQL Server sysadmin 组的成员，则必须请求将添加到组中，直到部署数据库文件。 如果不能成为 sysadmin 组的成员，则应为 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


