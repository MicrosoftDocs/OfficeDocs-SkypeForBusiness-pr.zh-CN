---
title: Lync Server 2013：更改存档数据库选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8961b33a7b576559115c3afaa36e07b795d69ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>在 Lync Server 2013 中更改存档数据库选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

如果使用 SQL Server 存储部署存档以存档任何用户的存储，则可以进行以下数据库存储更改：

  - 使用不同的 SQL Server 数据库存档存储。 这包括主存档数据库和用于 SQL Server 镜像的任何数据库。

  - 切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上。 如果你的所有用户都驻留在 Exchange 2013 服务器上，并且想要对部署中的所有用户使用 Microsoft Exchange 存储，则应从拓扑中删除 SQL Server 存储数据库。

若要进行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。 您可以使用拓扑生成器执行此操作。 不要指定**存档 Sql server 存储**或**启用 sql server 存储镜像**信息，除非您没有在 Exchange 2013 服务器上托管的 Lync 用户。

<div>

## <a name="to-change-your-archiving-database-option"></a>更改存档数据库选项

1.  在运行 Lync Server 2013 的计算机上，或安装了 Lync Server 管理工具的计算机上，使用属于本地 Users 组成员的帐户（或具有等效用户权限的帐户）进行登录。
    
    <div>
    

    > [!NOTE]  
    > 您可以通过使用属于本地 Users 组成员的帐户来定义拓扑，但要发布拓扑（将组件添加到拓扑，则必须）。您必须使用属于<STRONG>Domain Admins</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组成员的帐户，并且在您对 Lync Server 2013 文件存储使用的文件共享上具有完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（Dacl）或具有等效权限的帐户。

    
    </div>

2.  启动拓扑生成器。

3.  在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。

4.  在“操作”**** 菜单上，单击“编辑属性”****。

5.  在“编辑属性”**** 对话框中，单击“常规”****。

6.  向下滚动到“存档”****。

7.  在“存档”**** 中，执行下列操作：
    
      - 若要切换到其他现有 SQL Server 存储，请在“存档 SQL Server 存储”**** 下的下拉列表框中，执行下列操作：
        
          - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
        
          - 若要指定新的 SQL Server 存储，请单击“新建”****，然后在“定义新的 SQL Server 存储”**** 对话框中，执行下列操作：
            
              - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
            
              - 若要指定新的 SQL Server 存储，请单击 "**新建**"，然后在 "**定义新的 SQL server 存储**" 对话框中，执行下列操作：
                
                  - 在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 SQL Server 存储的服务器的 FQDN。
                
                  - 单击“默认实例”**** 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”****，然后指定要使用的实例。
                
                  - 如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中，指定端口号。
    
      - 若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”****，然后执行下列操作：
        
          - 若要将现有的 SQL Server 存储用于镜像，请在 "**存档 Sql server 存储镜像**" 下拉列表框中，单击要用于镜像的 SQL server 存储的名称。
        
          - 若要指定新的 SQL Server 存储进行镜像，请单击 "**新建**"，然后在 "**定义新的 sql server 存储**" 对话框中，执行下列操作之一：
            
            1.  在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 sql server 存储的 sql SERVER 的 FQDN。
            
            2.  单击“默认实例”**** 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”****，然后指定要使用的实例。
            
            3.  如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中，指定端口号。
        
          - 如果启用 SQL Server 镜像，并且想要添加或更改 SQL Server 镜像见证（第三个单独的 SQL Server 实例，可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中 "**使用 SQL Server 镜像见证启用自动故障转移**" 复选框，然后执行下列操作之一：
            
            1.  在 " **SQL SERVER FQDN**" 中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。
            
            2.  单击“默认实例”**** 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”****，然后指定要用于镜像见证的实例。
            
            3.  如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中，指定端口号。
    
      - 若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上（如果部署中的所有用户都托管在 Exchange 2013 服务器上），请删除存档数据库的所有信息。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您有任何 Lync 用户未驻留在 Exchange 2013 服务器上，请不要删除 SQL Server 存储信息。

    
    </div>

8.  若要保存配置，请单击“确定”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在拓扑生成器中所做的更改在您发布新的拓扑之前不会生效。 有关详细信息，请参阅部署文档中的<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">发布更新后的拓扑以在 Lync Server 2013 中添加存档数据库</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

