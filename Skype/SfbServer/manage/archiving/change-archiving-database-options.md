---
title: 更改存档数据库中的Skype for Business Server
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
description: 摘要：了解如何更改存档数据库的存档Skype for Business Server。
ms.openlocfilehash: 74404b84be52a5a4b296029a61bd1060ebbc5f82a8aa1b3cdeb974cbfece6c44
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346468"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>更改存档数据库中的Skype for Business Server

**摘要：** 了解如何更改存档数据库的存档Skype for Business Server。
  
如果使用存档存储为SQL Server部署存档，您可以进行以下数据库存储更改：
  
- 使用不同的数据库SQL Server存档存储。 这包括主存档数据库和用于镜像SQL Server数据库。
    
- 切换到 Microsoft Exchange集成，以将存档数据和文件存储在Exchange服务器上。 如果您的所有用户都位于 Exchange 服务器上，并且您希望对部署中的所有用户使用 Microsoft Exchange 存储，您应从拓扑中删除 SQL Server 存储数据库。 
    
若要进行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。 不要指定存档 **SQL Server存储** 或启用SQL Server存储 **镜像** 信息，除非您有 Skype for Business 用户未Exchange服务器。
  
## <a name="change-archiving-database-options"></a>更改存档数据库选项

1. 在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上，使用作为本地 Users 组 (成员的帐户或具有同等用户权限) 的帐户登录。
    
    > [!NOTE]
    > 您可以使用作为本地 Users 组的成员的帐户来定义拓扑，但要发布拓扑（向拓扑中添加组件需要此拓扑， 您必须使用作为 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组的成员的帐户，并且该帐户具有对 (的完全控制权限，即，读取、写入和修改用于 Skype for Business Server 文件存储 (的文件共享上的) ，以便拓扑生成器可以配置所需的任意访问控制列表 (DACLs) 或具有同等权限的帐户。
  
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
    
     - 若要指定新的SQL Server，请单击"新建"，然后在"定义新的 SQL Server **应用商店"对话框中**，执行以下操作：
    
       - 在 **SQL Server FQDN** 中，指定要创建新的数据库存储SQL Server FQDN。
    
       - 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
    
       - 如果指定的SQL Server实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在"镜像端口号"中指定端口号。 
    
   - 若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”，然后执行下列操作：
    
     - 若要将现有 SQL Server 存储用于镜像，请在"存档 **SQL Server** 存储镜像"下拉列表框中，单击要用于镜像的 SQL Server 存储的名称。
    
     - 若要指定新的SQL Server存储进行镜像，请单击"新建"，然后在"定义新的 SQL Server **存储**"对话框中，执行下列操作之一：
    
       a. 在 **SQL Server FQDN"** 中，指定要SQL Server存储的 FQDN。SQL Server FQDN。
    
       b. 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
    
       c. 如果指定的SQL Server实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在"镜像端口号"中指定端口号。 
    
   - 如果启用 SQL Server 镜像，并且想要添加或更改 SQL Server 镜像见证 (第三个单独的 SQL Server 实例，可以检测主 SQL Server 服务器和镜像实例) 的运行状况，请选中"使用 **SQL Server** 镜像见证启用自动故障转移"复选框，然后执行下列操作之一：
    
      a. 在 **SQL Server FQDN** 中，指定要创建新的镜像见证服务器SQL Server FQDN。
    
      b. 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要用于镜像见证的实例。
    
      c. 如果指定的SQL Server实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在"镜像端口号"中指定端口号。 
    
   - 若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 服务器上 (如果部署中的所有用户都位于 Exchange 服务器) 中，请删除存档数据库的所有信息。
    
     > [!IMPORTANT]
     > 如果有未Skype for Business服务器上的任何Exchange，请不要删除SQL Server存储信息。 
  
8. 若要保存配置，请单击“确定”。
    
    > [!IMPORTANT]
    > 在发布新拓扑之前，在拓扑生成器中所做的更改不会生效。 有关详细信息，请参阅 Add [archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>使用"存档"选项更改存档数据库Windows PowerShell

在大多数情况下，不需要更改存档数据库的位置，该位置是在安装存档服务器时指定的。 但是，如果发生硬件故障或其他问题，您可以使用 **Set-CsArchivingServer** cmdlet 将存档服务器指向新数据库。
  
以下示例更改 ArchivingServer：atl-cs-001.contoso.com 存档服务器的存档数据库的位置。 本示例中，新数据库位于 ArchivingDatabase：atl-sql-001.contoso.com：
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


