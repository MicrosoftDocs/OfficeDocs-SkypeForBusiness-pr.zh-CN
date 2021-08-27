---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 在删除Microsoft SQL Server依赖于这些数据库和实例的服务器之后，或者将服务器重新配置为使用另一个数据库之后，可以删除这些数据库和实例。 停用当前数据库时，您需要执行本主题中的过程SQL Server或重新配置当前服务器，使其使数据库过时或不可用。
ms.openlocfilehash: dafd1589bc4d1624a71998813fe785841cbfb713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582026"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>删除后端服务器上的 SQL Server 实例和数据库

在删除Microsoft SQL Server依赖于这些数据库和实例的服务器之后，或者将服务器重新配置为使用另一个数据库之后，可以删除这些数据库和实例。 停用当前数据库时，您需要执行本主题中的过程SQL Server或重新配置当前服务器，使其使数据库过时或不可用。
  
若要删除存档服务器或监控服务器的数据库或实例，必须先删除服务器角色。 同样，若要删除前端池的实例或数据库，必须先删除或重新配置从属服务器角色。 在并置的数据库或单独的服务器实例之间，这些过程没有差别。 这些过程不受数据库并置的影响。
  
## <a name="in-this-section"></a>本节内容

- [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [删除监控服务器的 SQL Server 数据库](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [删除存档服务器的 SQL Server 数据库](remove-the-sql-server-database-for-an-archiving-server.md)
    

