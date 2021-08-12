---
title: 删除监控服务器的 SQL Server 数据库
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
description: 删除监控服务器后，可以删除SQL Server服务器数据的数据库。 使用以下过程从拓扑生成器中删除定义，然后从拓扑生成器中删除数据库服务器。
ms.openlocfilehash: cadb24e2dcbe88e643c234dd8559d07406e5566e3e7eea0e33eec796cd98cf52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280387"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>删除监控服务器的 SQL Server 数据库

删除监控服务器后，可以删除SQL Server服务器数据的数据库。 使用以下过程从拓扑生成器中删除定义，然后从拓扑生成器中删除数据库服务器。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑SQL Server删除数据库

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 在拓扑生成器中，导航到"共享组件"，SQL Server存储"，右键单击与已删除或重新配置的监控服务器关联的 SQL Server 实例，然后单击"删除 **"。** 
    
3. 发布拓扑，然后检查复制状态。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>从 SQL Server 中删除数据库文件

1. 要删除基于 SQL Server 的服务器上的数据库，您必须是从其中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmin 组成员。
    
2. 打开"Skype for Business Server命令行管理程序"。
    
3. 在命令行中键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中 是数据库的 FQDN (完全限定) ，数据库服务器  _\<FQDN\>_  _\<instance\>_ 是可选命名的数据库实例。 
    
4. 当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 Y (或 Enter) 继续，或者，如果要在出现错误) 时停止该 cmdlet，请按 N，然后按 Enter (。 
    

