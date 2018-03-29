---
title: 添加监视服务器 SQL Server 存储库
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 监视服务器要求的受支持的 64 位版本的 SQL Server 数据库软件，以存储监控数据。 可以选择以前定义的 SQL Server 数据库，以用于监视，或者通过指定的 SQL Server 数据库将驻留，除了 SQL 实例的服务器的完全合格的域名称 (FQDN) 来定义一个新的 SQL Server 数据库要使用新的 SQL Server 数据库 （它可以是默认实例或命名的实例指定） 的服务器。
ms.openlocfilehash: f52f44acd9ca57112da75fcc368d8ebaae99b081
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-monitoring-server-sql-server-store"></a>添加监视服务器 SQL Server 存储库
 
监视服务器要求的受支持的 64 位版本的 SQL Server 数据库软件，以存储监控数据。 可以选择以前定义的 SQL Server 数据库，以用于监视，或者通过指定的 SQL Server 数据库将驻留，除了 SQL 实例的服务器的完全合格的域名称 (FQDN) 来定义一个新的 SQL Server 数据库要使用新的 SQL Server 数据库 （它可以是默认实例或命名的实例指定） 的服务器。
  
有关 SQL Server 支持，请参阅中的可支持性文档[数据库软件和群集支持](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 有关监视数据库，包括监视数据库的配置详细信息请参阅 》 中可支持性文档，[为监视计划](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)中的规划文档和[SQL Server 数据[支持服务器位置](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)日志文件位置和](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)部署文档中。
  
> [!NOTE]
> 如果用来发布拓扑的帐户具有适当的用户权限和权限，您可以创建监视数据库，当发布您的拓扑结构。 您还可以创建数据库之后，包括作为安装过程的一部分。 > 安装和部署用于监视基于 SQL Server 的服务器上的数据库时，您必须是要安装的数据库文件的基于 SQL Server 的服务器的 SQL Server 系统管理员组的成员。 如果您不是 SQL Server 系统管理员组的成员，则您必须请求部署数据库文件之前要添加到组。 如果不能进行系统管理员组的成员，应将您的 SQL Server 数据库管理员提供的脚本来配置和部署数据库。 有关完成这些过程所需的权限和用户权利的详细信息，请参阅部署文档中的[SQL Server 部署权限](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。
  

