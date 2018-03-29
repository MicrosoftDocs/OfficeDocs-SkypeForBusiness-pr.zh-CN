---
title: 存档服务器 SQL Server 存储库中添加
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 存档服务器要求的受支持的 64 位版本的 SQL Server 数据库软件，以存储存档数据。 您可以选择以前定义的 SQL Server 数据库，以用于存档或定义一个新的 SQL Server 数据库将驻留的 SQL Server 数据库，服务器和 SQL Server 的实例指定一个完全限定的域名称 (FQDN)，您想要使用新的 SQL Server 数据库 （这可以是默认实例或命名的实例指定）。
ms.openlocfilehash: 2c63b6bf71c156bc62e07add023f3049af399095
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-server-sql-server-store"></a>存档服务器 SQL Server 存储库中添加
 
存档服务器要求的受支持的 64 位版本的 SQL Server 数据库软件，以存储存档数据。 您可以选择以前定义的 SQL Server 数据库，以用于存档或定义一个新的 SQL Server 数据库将驻留的 SQL Server 数据库，服务器和 SQL Server 的实例指定一个完全限定的域名称 (FQDN)，您想要使用新的 SQL Server 数据库 （这可以是默认实例或命名的实例指定）。
  
> [!NOTE]
> 如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建存档数据库 (LcsLog)，当发布您的拓扑结构。 您还可以创建数据库之后，作为安装过程的一部分或其他方式。 
  
> [!NOTE]
> 要安装和部署存档的基于 SQL Server 的服务器上的数据库时，您必须是要安装的数据库文件的基于 SQL Server 的服务器的 SQL Server 系统管理员组的成员。 如果您不是 SQL Server 系统管理员组的成员，则您必须请求部署数据库文件之前要添加到组。 如果不能进行系统管理员组的成员，应将您的 SQL Server 数据库管理员提供的脚本来配置和部署数据库。 有关完成这些过程所需的权限和用户权限的详细信息，请参阅部署文档中的[SQL Server 部署权限](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。
  

