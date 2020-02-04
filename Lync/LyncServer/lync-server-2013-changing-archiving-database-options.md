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
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>在 Lync Server 2013 中更改存档数据库选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

如果使用 SQL Server 存储部署存档以便为任何用户存档存储，则可以更改以下数据库存储：

  - 将不同的 SQL Server 数据库用于存档存储。 这包括用于 SQL Server 镜像的主存档数据库和任何数据库。

  - 切换到 Microsoft Exchange 集成以在 Exchange 2013 服务器上存储存档数据和文件。 如果你的所有用户都托管在 Exchange 2013 服务器上，并且你希望为部署中的所有用户使用 Microsoft Exchange 存储，则应从拓扑中删除 SQL Server 应用商店数据库。

若要执行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。 可以使用拓扑生成器执行此操作。 不要指定**存档 Sql server 存储**或**启用 sql server 存储镜像**信息，除非您没有在 Exchange 2013 服务器上托管的 Lync 用户。

<div>

## <a name="to-change-your-archiving-database-option"></a>更改存档数据库选项

1.  在运行 Lync Server 2013 的计算机上，或安装了 Lync Server 管理工具的计算机上，使用属于本地 Users 组的成员（或具有等效用户权限的帐户）登录。
    
    <div>
    

    > [!NOTE]  
    > 你可以通过使用属于本地用户组的成员的帐户定义拓扑，但要发布拓扑（这是将组件添加到拓扑所必需的）你必须使用属于<STRONG>域管理员</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组成员的帐户，并且具有对 Lync Server 2013 文件存储所使用的文件共享的完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（Dacl）或具有等效权限的帐户。

    
    </div>

2.  启动拓扑生成器。

3.  在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。

4.  在“**操作**”菜单上，单击“**编辑属性**”。

5.  在“**编辑属性**”对话框中，单击“**常规**”。

6.  向下滚动到“**存档**”。

7.  在“**存档**”中，执行下列操作：
    
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
            
            1.  在**SQL SERVER FQDN**中，指定要在其上创建新的 sql server 应用商店的 sql SERVER 的 FQDN。
            
            2.  单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。
            
            3.  如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。
        
          - 如果启用 SQL Server 镜像并希望添加或更改 SQL Server 镜像见证（第三个单独的 SQL Server 实例，它可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框，然后执行下列操作之一：
            
            1.  在**SQL SERVER FQDN**中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。
            
            2.  单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。
            
            3.  如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。
    
      - 若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上（如果你的部署中的所有用户都托管在 Exchange 2013 服务器上），请删除存档数据库的所有信息。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果你的任何 Lync 用户均未托管在 Exchange 2013 服务器上，请不要删除 SQL Server 存储信息。

    
    </div>

8.  若要保存配置，请单击“**确定**”。
    
    <div>
    

    > [!IMPORTANT]  
    > 在发布新拓扑之前，在拓扑生成器中所做的更改不会生效。 有关详细信息，请参阅<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">发布更新后的拓扑以在 Lync Server 2013</A>中的部署文档中添加存档数据库。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

