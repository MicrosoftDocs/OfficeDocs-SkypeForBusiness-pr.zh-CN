---
title: Lync Server 2013：将存档数据库添加到 Lync Server 2013 拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d6f4ff4b3881f9dfbd4707d2956aa738b9a375
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>将存档数据库添加到 Lync Server 2013 拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。 本主题中的信息介绍如何使用拓扑生成器将存档添加到现有拓扑中。

<div>


> [!NOTE]  
> 如果要使用 Microsoft Exchange 集成在 Exchange 2013 服务器上为您的部署中的所有用户存储存档数据和文件，请不要指定<STRONG>存档 Sql server 存储</STRONG>或<STRONG>使用 sql server 存储镜像</STRONG>信息。



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>向拓扑中添加存档数据库支持

1.  在运行 Lync Server 2013 的计算机上，或安装了 Lync Server 管理工具的计算机上，使用属于本地 Users 组成员的帐户（或具有等效用户权限的帐户）进行登录。
    
    <div>
    

    > [!NOTE]  
    > 您可以通过使用属于本地用户组成员的帐户来定义拓扑，但要发布拓扑（将服务器添加到拓扑，则必须）。您必须使用属于<STRONG>Domain Admins</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组成员的帐户，并且在您对 Lync server 2013 文件存储使用的文件共享上具有完全控制权限（即读取、写入和修改）（即，以便拓扑生成器可以配置所需的随机访问控制列表（dacl），或具有等效权限的帐户。

    
    </div>

2.  启动拓扑生成器。

3.  在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。

4.  在“操作”**** 菜单上，单击“编辑属性”****。

5.  在“编辑属性”**** 对话框中，单击“常规”****。

6.  向下滚动到“存档”****。

7.  选中“存档”**** 复选框。

8.  在 "**存档 SQL Server 存储" 下，** 执行下列操作之一：
    
      - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。 如果你的所有用户都驻留在 Microsoft Exchange Server 2013 或更高版本上，则可以存档 Exchange 中所有用户的 Lync 通信。 在这种情况下，不需要配置 SQL Server 存档存储。
    
      - 若要指定新的 SQL Server 存储，请单击 "**新建**"，然后在 "**定义新的 SQL server 存储**" 对话框中，执行下列操作：
        
          - 在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 SQL Server 存储的服务器的 FQDN。
        
          - 单击“默认实例”**** 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”****，然后指定要使用的实例。
        
          - 如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中，指定端口号。

9.  如果要使用 SQL Server 存储镜像，请选择 "**启用 Sql Server 存储镜像**"，然后执行以下操作：
    
      - 若要将现有的 SQL Server 存储用于镜像，请在 "**存档 Sql server 存储镜像**" 下拉列表框中，单击要用于镜像的 SQL server 存储的名称。
    
      - 若要指定新的 SQL Server 存储进行镜像，请单击 "**新建**"，然后在 "**定义新的 sql server 存储**" 对话框中，执行下列操作之一：
        
        1.  在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 sql server 存储的 sql SERVER 的 FQDN。
        
        2.  单击“默认实例”**** 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”****，然后指定要使用的实例。
        
        3.  如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中，指定端口号。
    
      - 如果启用 SQL Server 镜像，并希望包含 SQL Server 镜像见证（第三个单独的 SQL Server 实例，可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中 "**使用 SQL Server 镜像见证启用自动故障转移**" 复选框，然后执行下列操作之一：
        
        1.  在 " **SQL SERVER FQDN**" 中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。
        
        2.  单击“默认实例”**** 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”****，然后指定要用于镜像见证的实例。
        
        3.  如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中，指定端口号。

10. 若要保存配置，请单击“确定”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

