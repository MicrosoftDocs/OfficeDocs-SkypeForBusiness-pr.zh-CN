---
title: 删除前端池的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除前端池或将池重新配置为使用其他数据库后, 可以删除托管池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: d22a90401bdfa4a2897a18805e8b9c588892c5fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241561"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>删除前端池的 SQL Server 数据库

删除前端池或将池重新配置为使用其他数据库后, 可以删除托管池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1. 从 Skype for Business 服务器2019前端服务器, 打开拓扑生成器并下载现有拓扑。 
    
2. 在拓扑生成器中, 导航到 "**共享组件**", 然后导航到 " **sql server 存储**", 右键单击与删除或重新配置的前端池相关联的 SQL Server 实例, 然后单击 "**删除**"。
    
3. 发布拓扑, 然后检查复制状态。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>从 SQL server 中删除用户和应用程序数据库

1. 若要删除 SQL server 上的数据库, 您必须是要删除数据库文件的 SQL server 的 SQL Server sysadmin 组的成员。 
    
2. 打开 Skype for Business Server 命令行管理程序。
    
3. 若要删除 "池用户" 存储的数据库, 请键入:
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<FQDN\> _是数据库服务器的完全限定的域名 (fqdn), _ \<实例\> _是指定的数据库实例 (即, 如果定义了一个实例)。 
    
4. 若要删除池应用商店的数据库, 请键入:
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<fqdn\> _是数据库服务器的 fqdn, _ \<实例\> _是指定的数据库实例 (即, 如果定义了一个实例)。 
    
5. 当**CsDataBase** cmdlet 提示你确认操作时, 请阅读信息, 然后按 "Y" (或 enter) 继续操作, 或者按 N, 然后按 N, 然后按 enter 以停止 cmdlet (如果存在错误)。 
    

