---
title: 添加存档服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 存档服务器需要支持的 64 位版本的 SQL Server 数据库软件存储存档数据。 您可以选择先前定义的 SQL Server 数据库，用于存档或通过指定在其将驻留的 SQL Server 数据库，server 和 SQL Server 实例的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库的您想要用于新的 SQL Server 数据库 （这可以是默认实例或您指定的命名的实例）。
ms.openlocfilehash: 54a51ad26be95a4657e4e04d84fd0246a58849ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886633"
---
# <a name="add-archiving-server-sql-server-store"></a>添加存档服务器 SQL Server 存储

存档服务器需要支持的 64 位版本的 SQL Server 数据库软件存储存档数据。 您可以选择先前定义的 SQL Server 数据库，用于存档或通过指定在其将驻留的 SQL Server 数据库，server 和 SQL Server 实例的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库的您想要用于新的 SQL Server 数据库 （这可以是默认实例或您指定的命名的实例）。

> [!NOTE]
> 如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建存档数据库 (LcsLog)，当您发布您的拓扑。 您还可以更高版本，安装过程的一部分创建数据库或其他方式。

> [!NOTE]
> 若要安装和部署存档的基于 SQL Server 的服务器上的数据库，您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 SQL Server sysadmins 组的成员，您必须请求添加到组中，直到部署数据库文件。 如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。 有关用户权限和完成这些过程所需的权限的详细信息，请参阅部署文档中的[SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


