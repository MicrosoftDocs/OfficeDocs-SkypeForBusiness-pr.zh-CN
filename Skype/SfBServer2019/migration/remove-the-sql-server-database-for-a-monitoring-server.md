---
title: 删除监控服务器的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除监视服务器后, 您可以删除托管服务器数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: 2f4a6feb78adb9daa15cb8d59c2041740e45a19d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301081"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>删除监控服务器的 SQL Server 数据库

删除监视服务器后, 您可以删除托管服务器数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1. 在 Skype for Business 服务器2019前端服务器上, 打开拓扑生成器。
    
2. 在拓扑生成器中, 导航到 "**共享组件**", 然后导航到 " **sql server 存储**", 右键单击与删除或重新配置的监视服务器相关联的 SQL server 实例, 然后单击 "**删除**"。
    
3. 发布拓扑, 然后检查复制状态。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>从 SQL Server 中删除数据库文件

1. 若要删除基于 SQL Server 的服务器上的数据库, 您必须是要从中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmin 组的成员。
    
2. 打开 Skype for Business 服务器命令行管理程序。
    
3. 在命令行中键入：
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<FQDN\> _是数据库服务器的完全限定的域名 (fqdn), _ \<实例\> _是可选的命名数据库实例。 
    
4. 当**CsDataBase** cmdlet 提示你确认操作时, 请阅读信息, 然后按 "Y" (或 enter) 继续操作, 或者按 N, 然后按 N, 然后按 enter 以停止 cmdlet (如果存在错误)。 
    

