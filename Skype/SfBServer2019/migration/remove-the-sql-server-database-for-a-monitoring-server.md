---
title: 删除监控服务器的 SQL Server 数据库
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除监控服务器后，您可以删除承载服务器数据的 SQL Server 数据库。 使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。
ms.openlocfilehash: 85999f1bbb3fc443edcab9d1f1354f26187c6a75
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373355"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>删除监控服务器的 SQL Server 数据库

删除监控服务器后，您可以删除承载服务器数据的 SQL Server 数据库。 使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>若要删除使用拓扑生成器的 SQL Server 数据库

1. 在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。
    
2. 在拓扑生成器中，导航到**共享组件**，然后选择**SQL Server 存储**，右键单击 SQL Server 实例关联的已删除或重新配置监控服务器，然后单击**删除**。
    
3. 发布拓扑，并检查复制状态。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>若要从 SQL Server 中删除数据库文件

1. 若要删除基于 SQL Server 的服务器上的数据库，您必须在其中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmins 组的成员。
    
2. 打开 Skype 业务 Server 命令行管理程序。
    
3. 在命令行中键入：
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_\<FQDN\>_ 是数据库服务器的完全限定的域名 (FQDN) 和_\<实例\>_ 是可选的命名的数据库实例。 
    
4. 当**卸载 CsDataBase** cmdlet 提示您确认操作时，读取信息，并按 Y （或 Enter） 以继续，或按 N，然后按 Enter，如果您想要停止 cmdlet （如果有错误）。 
    

