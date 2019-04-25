---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您删除的 Microsoft SQL Server 数据库和实例后删除的服务器运行的是相关的用户、 或之后重新配置为使用另一个数据库的服务器。 您需要执行本主题中的步骤，停用当前的 SQL Server 或重新配置当前服务器的方式，它将呈现数据库已过时或不可用时。
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231502"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>删除后端服务器上的 SQL Server 实例和数据库

您删除的 Microsoft SQL Server 数据库和实例后删除的服务器运行的是相关的用户、 或之后重新配置为使用另一个数据库的服务器。 您需要执行本主题中的步骤，停用当前的 SQL Server 或重新配置当前服务器的方式，它将呈现数据库已过时或不可用时。
  
若要删除的存档服务器或监控服务器数据库或实例，必须首先删除服务器角色。 同样，若要删除的实例或前端池数据库，必须首先删除或重新配置相关的服务器角色。 这些过程的服务器都并置的数据库或单独实例之间没有区别。 过程不受数据库并置。
  
## <a name="in-this-section"></a>本节内容

- [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [删除监控服务器的 SQL Server 数据库](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [删除存档服务器的 SQL Server 数据库](remove-the-sql-server-database-for-an-archiving-server.md)
    

