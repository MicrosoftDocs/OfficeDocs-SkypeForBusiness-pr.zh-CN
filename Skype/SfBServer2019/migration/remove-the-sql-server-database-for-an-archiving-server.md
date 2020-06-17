---
title: 删除存档服务器的 SQL Server 数据库
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
description: 删除存档服务器后，可以删除托管池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753304"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>删除存档服务器的 SQL Server 数据库

删除存档服务器后，可以删除托管池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的存档服务器关联的 SQL Server 实例，然后单击 "**删除**"。
    
3. 发布拓扑，然后检查复制状态。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>从 SQL Server 中删除数据库文件

1. 若要删除 SQL Server 上的数据库，您必须是要从中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。
 
    
2. 打开 Skype for Business Server 命令行管理程序。
    
3. 在命令行中键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中， _\<FQDN\>_ 是数据库服务器的完全限定的域名（FQDN）， _\<instance\>_ 是指定的数据库实例（如果定义了一个实例）。 
    
4. 当 CsDataBase cmdlet 提示您确认操作时，请阅读**相关**信息，然后按 "Y" （或 enter）继续，或者按 N，然后按 enter 以停止 cmdlet （如果有错误）。 
    

