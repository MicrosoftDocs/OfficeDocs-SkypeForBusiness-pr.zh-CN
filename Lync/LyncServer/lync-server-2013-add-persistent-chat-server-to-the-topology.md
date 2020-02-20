---
title: Lync Server 2013：将持久聊天服务器添加到拓扑中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b857c63b08906ada2cee2611960717f97e7a3cc1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中向拓扑添加持久聊天服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

您必须将 Lync Server 2013 与拓扑中的持久聊天服务器支持结合在一起，然后才能将部署配置为支持持久聊天服务器。 本主题中的信息介绍如何使用拓扑生成器将持久聊天服务器支持添加到现有拓扑中。

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>将持久聊天服务器添加到拓扑中

执行以下步骤以在不进行灾难恢复配置的情况下安装单个持久聊天服务器池。 有关为高可用性和灾难恢复配置延伸的持久聊天服务器池，请参阅部署文档中的在[Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

若要部署多个持久聊天服务器池，请为每个池重复相同的过程。

1.  在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上，使用属于本地 Users 组成员的帐户（或具有等效用户权限的帐户）登录。
    
    <div>
    

    > [!NOTE]  
    > 您可以通过使用属于本地用户组成员的帐户来定义拓扑，但要发布安装 Lync Server 2013 服务器所需的拓扑，您必须使用属于<STRONG>Domain Admins</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组成员的帐户，并且对要用于持久聊天服务器文件存储的文件存储具有完全控制权限（即读取、写入和修改）（即，以便拓扑生成器可以配置所需的 dacl）。，或具有等效权限的帐户。

    
    </div>

2.  启动拓扑生成器。

3.  在控制台树中，导航到 "**持久聊天池**" 节点并展开它以选择持久聊天服务器池，或者右键单击该节点，然后选择 "**新建持久聊天池**"。 您必须定义该池的完全限定的域名 (FQDN)，并指示该池是单服务器池部署还是多服务器池部署。
    
    您可选择“多计算机池”**** 或“单计算机池”****。 如果计划在持久聊天服务器池中安装多台持久聊天服务器前端服务器，请选择前者。 现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。 如果选择 "多计算机池"，请输入构成池的单个持久聊天服务器前端服务器的名称。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果在 Lync Server 2013&nbsp;Standard edition server 上安装持久聊天服务器角色，则 fqdn 需要与 Standard edition SERVER 的 fqdn 匹配。

    
    </div>

4.  为持久聊天服务器池定义一个简单的**显示名称**。 自定义客户端可以使用显示名称，尤其是在有多个持久聊天服务器池时，要区分房间。

5.  定义持久聊天服务器用于与 Lync Server 前端服务器进行通信的端口。 默认端口为 5041。

6.  如果您的组织需要合规性支持，请选中“启用合规性”**** 复选框。 如果选择此项，持久聊天服务器合规性服务将安装在与持久聊天服务器前端服务器相同的计算机上。 随后系统会提示你选择一个 SQL Server 后端服务器来实现持久聊天服务器兼容性。

7.  为持久聊天服务器池分配网站相关性。 选中 "**将此池用作网站\<SiteName\>的默认值**" 复选框，或**将此池用作所有网站的默认值**，以将此持久聊天服务器池指定为当前网站或所有网站的默认池。 在使用 Lync 2013 客户端创建和管理会议室时，会使用与用户网站相关联的默认池来创建和管理体验，以便它可以将会议室创建和管理操作路由到该池。 这仅适用于部署了多个持久聊天服务器池的情况，并且想要使用持久聊天服务器的会议室创建和管理功能。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以使用持久聊天服务器软件开发工具包（SDK）自定义会议室创建和管理功能。<BR>有关如何为灾难恢复配置 SQL Server 备份数据库的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复</A>。

    
    </div>

8.  通过执行以下操作之一，定义**持久聊天服务器后端的 SQL 存储（其中存储了聊天室内容）** ：
    
      - 若要使用现有的 SQL Server 数据库，请在下拉列表中单击要使用的 SQL Server 数据库的名称。
    
      - 若要指定新的 SQL Server 数据库，请单击 "**新建**"，并在 "**定义新的 sql 存储**" 中执行以下操作：
    
    <!-- end list -->
    
      - 在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 sql server 数据库的 sql SERVER 的 FQDN。
    
      - 选择“默认实例”**** 以使用默认实例，或指定其他实例，选择“命名实例”****，然后指定要使用的实例。

9.  如果启用了合规性，则定义 SQL Server 合规性数据库。
    
    <div>
    

    > [!IMPORTANT]  
    > 有关如何为持久聊天服务器数据库和持久聊天服务器合规性数据库的高可用性配置 SQL Server 镜像的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复</A>。

    
    </div>

10. 定义文件存储。 文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。 在多服务器持久聊天服务器拓扑的情况下，这必须是通用命名约定（UNC）路径;对于单服务器持久聊天服务器拓扑，它可以是本地文件路径。
    
    若要使用现有文件存储，请执行下列步骤：
    
      - 在“文件服务器 FQDN”**** 中，指定要在其上创建新的文件存储的文件存储的 FQDN。
    
      - 在“文件共享”**** 中，指定要使用的文件存储。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以在拓扑生成器中定义文件存储，然后再创建文件存储，但您必须在发布拓扑之前定义的定义位置中创建文件存储。

    
    </div>

11. 选择要用作此持久聊天服务器池的下一个跃点的前端服务器池。 这是能够将持久聊天服务器请求路由到此池的前端服务器池。

12. 若要保存配置，请单击“完成”****。 持久聊天服务器池在拓扑生成器中显示，附带您的特定池设置。
    
    若要立即发布已永久聊天服务器的更新的拓扑，请参阅部署文档中的在[Lync Server 2013 中发布更新后的拓扑](lync-server-2013-publish-the-updated-topology.md)。
    
    <div>
    

    > [!NOTE]  
    > 已打开拓扑生成器，您可以继续在<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中发布更新后的拓扑</A>中的步骤3，以开始发布更新的拓扑。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

