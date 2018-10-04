---
title: 删除前端池的 SQL Server 数据库
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除前端池或重新配置要使用不同的数据库的池后，您可以删除承载池数据的 SQL Server 数据库。 使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。
ms.openlocfilehash: 35c9429fc16aef886945f8b0adcd5894ce40b834
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373124"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>删除前端池的 SQL Server 数据库

删除前端池或重新配置要使用不同的数据库的池后，您可以删除承载池数据的 SQL Server 数据库。 使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>若要删除使用拓扑生成器的 SQL Server 数据库

1. 从业务 Server 2019 前端服务器的 Skype，打开拓扑生成器并下载现有拓扑。 
    
2. 在拓扑生成器中，导航到**共享组件**，然后选择**SQL Server 存储**，右键单击与已删除的或重新配置前端池关联的 SQL Server 实例，然后单击**删除**。
    
3. 发布拓扑，，然后检查复制状态。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>若要从 SQL server 中删除用户和应用程序数据库

1. 若要删除 SQL server 上的数据库，您必须在其中删除数据库文件的 SQL server 的 SQL Server sysadmins 组的成员。 
    
2. 打开 Skype 业务 Server 命令行管理程序。
    
3. 若要删除池用户存储的数据库，请键入：
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_\<FQDN\>_ 是数据库服务器的完全限定的域名 (FQDN) 和_\<实例\>_ 是命名的数据库实例 （如果已定义）。 
    
4. 若要删除池应用程序存储的数据库，请键入：
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_\<FQDN\>_ 是数据库服务器的 FQDN 和_\<实例\>_ 是命名的数据库实例 （如果已定义）。 
    
5. 当**卸载 CsDataBase** cmdlet 提示您确认操作时，读取信息，并按 Y （或 Enter） 以继续，或按 N，然后按 Enter，如果您想要停止 cmdlet （如果有错误）。 
    

