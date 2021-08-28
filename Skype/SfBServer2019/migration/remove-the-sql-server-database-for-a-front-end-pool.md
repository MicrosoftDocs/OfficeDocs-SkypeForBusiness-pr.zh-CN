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
ms.localizationpriority: medium
description: 在删除前端池或将池重新配置为使用不同的数据库后，可以删除托管SQL Server数据库。 使用以下过程从拓扑生成器中删除定义，然后从拓扑生成器中删除数据库和数据库服务器。
ms.openlocfilehash: 2a11057811035b0dc51810d3a6b7eb8220c7df1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580106"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>删除前端池的 SQL Server 数据库

在删除前端池或将池重新配置为使用不同的数据库后，可以删除托管SQL Server数据库。 使用以下过程从拓扑生成器中删除定义，然后从拓扑生成器中删除数据库和数据库服务器。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑SQL Server删除数据库

1. 从 Skype for Business Server 2019 前端服务器中，打开拓扑生成器并下载现有拓扑。 
    
2. 在拓扑生成器中，导航 **到**"共享组件"，SQL Server存储"，右键单击与已删除或重新配置的前端池关联的 SQL Server 实例，然后单击"删除 **"。** 
    
3. 发布拓扑，然后检查复制状态。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>从服务器中删除用户和应用程序SQL数据库

1. 若要删除 SQL 上的数据库，您必须是要删除数据库文件的 SQL 服务器的 SQL Server sysadmins 组的成员。 
    
2. 打开 Skype for Business Server 命令行管理程序。
    
3. 若要删除池用户存储的数据库，请键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中 是 (FQDN) 的完全限定域名，数据库服务器是命名数据库实例 (，也就是说，如果已定义  _\<FQDN\>_  _\<instance\>_) 。 
    
4. 若要删除池应用程序存储的数据库，请键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中 是数据库的 FQDN，数据库服务器是已命名的数据库实例 (，也就是说，如果已定义一个  _\<FQDN\>_  _\<instance\>_) 。 
    
5. 当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 Y (或 Enter) 继续，或者，如果要停止该 cmdlet (如果存在错误) ，请按 N，然后按 Enter。 
    

