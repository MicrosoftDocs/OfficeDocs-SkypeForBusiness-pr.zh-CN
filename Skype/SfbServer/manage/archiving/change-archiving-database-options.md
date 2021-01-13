---
title: 更改 Skype for Business Server 中的存档数据库选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：了解如何更改 Skype for Business Server 的存档数据库选项。
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817692"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>更改 Skype for Business Server 中的存档数据库选项

**摘要：** 了解如何更改 Skype for Business Server 的存档数据库选项。
  
如果使用存档存储SQL Server任何用户的存档存储部署存档，您可以进行以下数据库存储更改：
  
- 使用不同的数据库SQL Server存档存储。 这包括主存档数据库和用于镜像SQL Server数据库。
    
- 切换到 Microsoft Exchange 集成以在 Exchange 服务器上存储存档数据和文件。 如果您的所有用户都位于 Exchange 服务器上，并且您希望对部署中的所有用户使用 Microsoft Exchange 存储，则应该从拓扑中删除 SQL Server 存储数据库。 
    
若要进行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。 不要指定存档 **SQL Server或** 启用SQL Server存储 **镜像** 信息，除非你的 Skype for Business 用户未位于 Exchange 服务器上。
  
## <a name="change-archiving-database-options"></a>更改存档数据库选项

1. 在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上，使用本地用户组 (或具有同等用户权限的帐户登录) 。
    
    > [!NOTE]
    > 可以使用作为本地 Users 组的成员的帐户定义拓扑，但若要发布拓扑（向拓扑中添加组件是必需的）必须使用 Domain **Admins** 组和 **RTCUniversalServerAdmins** 组的成员帐户， 并且具有对要用于 Skype for Business Server 文件存储 (的文件共享的完全控制权限 (即读取、写入和修改) ，以便拓扑生成器可以配置所需的任意访问控制列表 (DACLS) 或具有同等权限的帐户。
  
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。
    
4. 在“操作”菜单上，单击“编辑属性”。 
    
5. 在“编辑属性”对话框中，单击“常规”。
    
6. 向下滚动到“存档”。
    
7. 在“存档”中，执行下列操作：
    
   - 若要切换到其他现有 SQL Server 存储，请在“存档 SQL Server 存储”下的下拉列表框中，执行下列操作：
    
   - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
    
   - 若要指定新的 SQL Server 存储，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作：
    
     - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
    
     - 若要指定新的SQL Server，请单击"新建 **"，然后在**"定义新的 SQL Server 应用商店"对话框中，执行以下操作： 
    
       - 在 **SQL Server FQDN** 中，指定要创建新数据库存储的服务器的 FQDN SQL Server FQDN。
    
       - 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
    
       - 如果指定的 SQL Server 实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在镜像端口号中指定端口号。 
    
   - 若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”，然后执行下列操作：
    
     - 若要将现有 SQL Server 存储用于镜像，请在"存档 **SQL Server** 存储镜像"下拉列表框中，单击要用于镜像的 SQL Server 存储的名称。
    
     - 若要指定新的SQL Server存储进行镜像，请单击"新建"，然后在"定义新的 SQL Server **应用商店**"对话框中，执行下列操作之一：
    
       a. 在 **SQL Server FQDN** 中，指定要SQL Server新存储的 SQL Server 的 FQDN。
    
       b. 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
    
       c. 如果指定的 SQL Server 实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在镜像端口号中指定端口号。 
    
   - 如果启用 SQL Server 镜像，并且想要添加或更改 SQL Server 镜像见证 (第三个可检测主 SQL Server 服务器和镜像实例) 运行状况的单独 SQL Server 实例，请选中"使用 **SQL Server** 镜像见证启用自动故障转移"复选框，然后执行下列操作之一：
    
      a. 在 **SQL Server FQDN** 中，指定要创建新的镜像见证SQL Server服务器的 FQDN。
    
      b. 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要用于镜像见证的实例。
    
      c. 如果指定的 SQL Server 实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在镜像端口号中指定端口号。 
    
   - 若要切换到 Microsoft Exchange 集成以在 Exchange 服务器上存储存档数据和文件 (如果部署中的所有用户都位于 Exchange 服务器上) ，请删除存档数据库的所有信息。
    
     > [!IMPORTANT]
     > 如果有未在 Exchange 服务器上存储的任何 Skype for Business 用户，请不要删除SQL Server存储信息。 
  
8. 若要保存配置，请单击“确定”。
    
    > [!IMPORTANT]
    > 在发布新拓扑之前，在拓扑生成器中所做的更改不会生效。 有关详细信息，请参阅在 Skype for Business Server 中 [向现有部署添加存档数据库](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>使用"存档"选项更改存档数据库Windows PowerShell

在大多数情况下，不需要更改存档数据库的位置，该位置是在安装存档服务器时指定的。 但是，如果发生硬件故障或其他问题，您可以使用 **Set-CsArchivingServer** cmdlet 将存档服务器指向新数据库。
  
以下示例更改 ArchivingServer：atl-cs-001.contoso.com存档服务器的存档数据库的位置。 本示例中，新数据库位于 ArchivingDatabase：atl-sql-001.contoso.com：
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


