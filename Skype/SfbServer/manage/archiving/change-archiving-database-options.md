---
title: 在 Skype for Business 服务器中更改存档数据库选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：了解如何更改 Skype for business 服务器的存档数据库选项。
ms.openlocfilehash: 3e7ae30e012464b6d1f72e323dd60ad397e7430d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992759"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>在 Skype for Business 服务器中更改存档数据库选项

**摘要：** 了解如何更改 Skype for business 服务器的存档数据库选项。
  
如果使用 SQL Server 存储部署存档以便为任何用户存档存储，则可以更改以下数据库存储：
  
- 将不同的 SQL Server 数据库用于存档存储。 这包括用于 SQL Server 镜像的主存档数据库和任何数据库。
    
- 切换到 Microsoft Exchange 集成以存储 Exchange 服务器上的存档数据和文件。 如果你的所有用户都托管在 Exchange 服务器上，并且你希望为部署中的所有用户使用 Microsoft Exchange 存储，则应从拓扑中删除 SQL Server 应用商店数据库。 
    
若要执行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。 不要指定**存档 Sql server 存储**或**启用 sql server 应用商店镜像**信息，除非您有未托管在 Exchange 服务器上的 Skype for business 用户。
  
## <a name="change-archiving-database-options"></a>更改存档数据库选项

1. 在运行 Skype for Business 服务器或安装了 Skype for business 服务器管理工具的计算机上，使用属于本地 Users 组的成员的帐户（或具有等效用户权限的帐户）登录。
    
    > [!NOTE]
    > 你可以通过使用属于本地用户组的成员的帐户定义拓扑，但要发布拓扑（这是将组件添加到拓扑所必需的）你必须使用属于**域管理员**组和**RTCUniversalServerAdmins**组成员的帐户，并且具有对 Skype for business Server 文件存储所使用的文件共享的完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（Dacl）或具有等效权限的帐户。
  
2. 启动拓扑生成器。
    
3. 在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。
    
4. 在“**操作**”菜单上，单击“**编辑属性**”。 
    
5. 在“**编辑属性**”对话框中，单击“**常规**”。
    
6. 向下滚动到“**存档**”。
    
7. 在“**存档**”中，执行下列操作：
    
   - 若要切换到其他现有 SQL Server 存储，请在“**存档 SQL Server 存储**”下的下拉列表框中，执行下列操作：
    
   - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
    
   - 若要指定新的 SQL Server 存储，请单击“**新建**”，然后在“**定义新的 SQL Server 存储**”对话框中，执行下列操作：
    
     - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
    
     - 若要指定新的 SQL Server 应用商店，请单击 "**新建**"，然后在 "**定义新的 SQL server 存储**" 对话框中，执行下列操作：
    
       - 在**SQL SERVER FQDN**中，指定要在其上创建新的 SQL Server 应用商店的服务器的 FQDN。
    
       - 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
       - 如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。
    
   - 若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“**启用 SQL Server 存储镜像**”，然后执行下列操作：
    
     - 若要使用现有的 SQL Server 应用商店进行镜像，请在 "**存档 Sql server 存储镜像**" 下拉列表框中，单击要用于镜像的 SQL server 应用商店的名称。
    
     - 若要为镜像指定新的 SQL Server 存储，请单击 "**新建**"，然后在 "**定义新的 SQL server 存储**" 对话框中，执行下列操作之一：
    
       a. 在**SQL SERVER FQDN**中，指定要在其上创建新的 sql server 应用商店的 sql SERVER 的 FQDN。
    
       b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
       c. 如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。
    
   - 如果启用 SQL Server 镜像并希望添加或更改 SQL Server 镜像见证（第三个单独的 SQL Server 实例，它可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框，然后执行下列操作之一：
    
      a. 在**SQL SERVER FQDN**中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。
    
      b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。
    
      c. 如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。
    
   - 若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 服务器上（如果部署中的所有用户都托管在 Exchange 服务器上），请删除存档数据库的所有信息。
    
     > [!IMPORTANT]
     > 如果您有未驻留在 Exchange 服务器上的任何 Skype for Business 用户，请不要删除 SQL Server 存储信息。 
  
8. 若要保存配置，请单击“**确定**”。
    
    > [!IMPORTANT]
    > 在发布新拓扑之前，在拓扑生成器中所做的更改不会生效。 有关详细信息，请参阅[将存档数据库添加到 Skype for Business 服务器中的现有部署](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>使用 Windows PowerShell 更改存档数据库的位置

在大多数情况下，您无需更改存档数据库的位置，在您安装存档服务器时将指定该位置。 但是，如果出现硬件故障或其他问题，您可以使用 **Set-CsArchivingServer** cmdlet 将存档服务器指向新的数据库。
  
以下示例更改了 ArchivingServer：001.contoso.com 存档服务器的存档数据库的位置。 在此示例中，新数据库位于 ArchivingDatabase:atl-sql-001.contoso.com中：
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


