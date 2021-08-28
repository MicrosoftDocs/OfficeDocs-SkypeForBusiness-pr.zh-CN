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
ms.localizationpriority: medium
description: 删除存档服务器后，可以删除SQL Server池数据的数据库。 使用以下过程从拓扑生成器中删除定义，然后从拓扑生成器中删除数据库服务器。
ms.openlocfilehash: 9305109e38c265b919d9ec22fa626d27efb19225
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621914"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>删除存档服务器的 SQL Server 数据库

删除存档服务器后，可以删除SQL Server池数据的数据库。 使用以下过程从拓扑生成器中删除定义，然后从拓扑生成器中删除数据库服务器。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑SQL Server删除数据库

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 在拓扑生成器中，导航到"共享组件"，SQL Server存储"，右键单击与已删除或重新配置的存档服务器关联的 SQL Server 实例，然后单击"删除 **"。** 
    
3. 发布拓扑，然后检查复制状态。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>从 SQL Server 中删除数据库文件

1. 若要删除 SQL Server 上的数据库，您必须是要从中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。
 
    
2. 打开"Skype for Business Server命令行管理程序"。
    
3. 在命令行中键入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中 是 (FQDN) 的完全限定域名，数据库服务器是命名数据库实例 (，也就是说，如果已定义  _\<FQDN\>_  _\<instance\>_) 。 
    
4. 当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 Y (或 Enter) 继续，或者，如果要停止该 cmdlet (如果存在错误) ，请按 N，然后按 Enter。 
    

