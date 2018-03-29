---
title: 在 Skype for Business Server 2015 中更改存档数据库选项
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要： 了解如何更改 Skype 业务服务器 2015年的存档数据库选项。
ms.openlocfilehash: 5bb7ee9329cc3fa7a0795115f9a0d11768ab7aa4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="change-archiving-database-options-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中更改存档数据库选项

**摘要：**了解如何更改 Skype 业务服务器 2015年的存档数据库选项。
  
如果您部署存档的存档存储任何用户使用 SQL Server 存储，您可以更改以下数据库存储：
  
- 使用不同的 SQL Server 数据库的存档存储。 这包括主存档数据库和 SQL Server 镜像您使用任何数据库。
    
- 切换到 Microsoft Exchange 集成存储存档数据和 Exchange 服务器上的文件。 如果您想要对您的部署中的所有用户使用 Microsoft Exchange 存储您的所有用户都驻留在 Exchange 服务器上，您应该从您的拓扑结构中删除 SQL Server 存储数据库。 
    
若要使这些更改的任何一个，必须运行拓扑生成器、 进行更改，然后再次发布拓扑结构。 除非您的业务用户没有驻留在 Exchange 服务器有 Skype 不指定**存档的 SQL Server 存储**或**启用 SQL Server 存储镜像**信息。
  
## <a name="change-archiving-database-options"></a>更改存档数据库选项

1. 运行 Skype 业务服务器的计算机上或在其上 Skype 的安装业务服务器管理工具，使用登录的帐户是本地用户组 （或具有相当的用户权限的帐户） 的成员。
    
    > [!NOTE]
    > 您可以通过使用本地用户组的成员帐户定义拓扑，但若要发布一个拓扑结构，需要将组件添加到拓扑结构中，则必须使用的帐户是**域管理员**组和**RTCUniversalSer 的成员verAdmins**组中，并且使用 Skype 业务服务器文件存储的 （也就是说，以便拓扑生成器可以配置所需的任意访问控制文件共享具有完全控制权限 （即读取、 写入和修改）列表 (Dacl) 或具有同等权限的帐户。
  
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
    
    - 若要指定新的 SQL Server 存储，单击**新建**，然后在**定义新建 SQL Server 存储**对话框中，执行下列：
    
      - 在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 存储的服务器的 FQDN。
    
      - 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
      - 如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。
    
  - 若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“**启用 SQL Server 存储镜像**”，然后执行下列操作：
    
    - 要用于现有的 SQL Server 存储镜像中**存档的 SQL Server 存储镜像**下拉列表框中，单击想要使用镜像的 SQL Server 存储的名称。
    
    - 若要指定新的 SQL Server 存储镜像，单击**新建**，然后在**定义新建 SQL Server 存储**对话框中，执行以下任一项：
    
      a. 在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 存储 SQL Server 的 FQDN。
    
      b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
    
      c. 如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。
    
  - 如果您启用 SQL Server 镜像，并且想要添加或更改镜像见证 （的第三个独立 SQL Server 实例可以检测到主 SQL Server 服务器实例和镜像实例的运行状况） SQL Server，选择**使用 SQL Server 镜像见证到启用自动故障切换**复选框，然后再执行下列操作之一：
    
      a. 在**SQL Server FQDN**，指定您要在其创建镜像见证新的 SQL Server 的服务器的 FQDN。
    
      b. 单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。
    
      c. 如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。
    
  - 若要切换到 Microsoft Exchange 集成存储存档数据和 Exchange 服务器 （如果您的部署中的所有用户都驻留在 Exchange 服务器） 上的文件，删除存档数据库的所有信息。
    
    > [!IMPORTANT]
    > 如果您有任何 Skype 业务用户没有驻留在 Exchange 服务器上，则不要删除 SQL Server 存储信息。 
  
8. 若要保存配置，请单击“**确定**”。
    
    > [!IMPORTANT]
    > 发布新的拓扑拓扑生成器中所做的更改会生效。 有关详细信息，请参阅[添加到现有的业务服务器 2015 Skype 在部署的存档数据库](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>使用 Windows PowerShell 更改存档数据库的位置

在大多数情况下，您无需更改存档数据库的位置，在您安装存档服务器时将指定该位置。 但是，如果出现硬件故障或其他问题，您可以使用 **Set-CsArchivingServer** cmdlet 将存档服务器指向新的数据库。
  
下面的示例更改为 ArchivingServer:atl 的存档数据库的位置-cs-001.contoso.com 存档服务器。 在此示例中，新数据库位于 ArchivingDatabase:atl-sql-001.contoso.com中：
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


