---
title: 删除前端池的 SQL Server 数据库
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 删除前端池或将池重新配置为使用其他数据库之后，可以删除承载池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753404"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>删除前端池的 SQL Server 数据库

删除前端池或将池重新配置为使用其他数据库之后，可以删除承载池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1. 在 Skype for Business Server 2019 前端服务器中，打开拓扑生成器并下载现有拓扑。 
    
2. 在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的前端池关联的 SQL Server 实例，然后单击 "**删除**"。
    
3. 发布拓扑，然后检查复制状态。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>从 SQL server 中删除用户数据库和应用程序数据库

1. 若要删除 SQL server 上的数据库，您必须是要在其中删除数据库文件的 SQL server 的 SQL Server sysadmin 组的成员。 
    
2. 打开 Skype for Business Server 命令行管理程序。
    
3. 若要删除池用户存储的数据库，请键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中， _\<FQDN\>_ 是数据库服务器的完全限定的域名（FQDN）， _\<instance\>_ 是指定的数据库实例（如果定义了一个实例）。 
    
4. 若要删除池应用程序存储的数据库，请键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中， _\<FQDN\>_ 是数据库服务器的 FQDN， _\<instance\>_ 是指定的数据库实例（如果定义了一个实例）。 
    
5. 当 CsDataBase cmdlet 提示您确认操作时，请阅读**相关**信息，然后按 "Y" （或 enter）继续，或者按 N，然后按 enter 以停止 cmdlet （如果有错误）。 
    

