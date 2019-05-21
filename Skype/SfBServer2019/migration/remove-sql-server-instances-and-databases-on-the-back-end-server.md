---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除依赖于这些数据库的服务器或在将服务器重新配置为使用另一个数据库之后, 将删除该 Microsoft SQL Server 数据库和实例。 当你注销当前 SQL Server 或重新配置当前服务器时, 你需要执行本主题中的过程, 使其呈现数据库过时或不可用。
ms.openlocfilehash: 2d0902293c675143609dd720cd33734edd538d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301116"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>删除后端服务器上的 SQL Server 实例和数据库

删除依赖于这些数据库的服务器或在将服务器重新配置为使用另一个数据库之后, 将删除该 Microsoft SQL Server 数据库和实例。 当你注销当前 SQL Server 或重新配置当前服务器时, 你需要执行本主题中的过程, 使其呈现数据库过时或不可用。
  
若要删除存档服务器或监视服务器的数据库或实例, 必须首先删除服务器角色。 同样, 若要删除前端池的实例或数据库, 必须首先删除或重新配置从属服务器角色。 这些过程不区分 collocated 数据库或服务器的单独实例。 数据库的 collocation 不会影响这些过程。
  
## <a name="in-this-section"></a>本节内容

- [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [删除监控服务器的 SQL Server 数据库](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [删除存档服务器的 SQL Server 数据库](remove-the-sql-server-database-for-an-archiving-server.md)
    

