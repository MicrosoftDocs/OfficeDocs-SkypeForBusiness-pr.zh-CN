---
title: Lync Server 2013：向拓扑添加持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中向拓扑添加持久聊天服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-06_

你必须将 Lync Server 2013 和拓扑中的持久聊天服务器支持合并到你的拓扑中, 然后才能配置你的部署以支持永久聊天服务器。 本主题中的信息介绍了如何使用拓扑生成器将持久聊天服务器支持添加到现有拓扑。

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>将持久聊天服务器添加到拓扑

若要在不使用灾难恢复配置的情况下安装单个持久聊天服务器池, 请执行以下步骤。 有关为高可用性和灾难恢复配置延长的持久聊天服务器池, 请参阅在部署文档中[为 Lync server 2013 中的高可用性和灾难恢复配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

若要部署多个持久聊天服务器池, 请为每个池重复相同的过程。

1.  在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上, 使用作为本地用户组成员的帐户 (或具有等效用户权限的帐户) 登录。
    
    <div>
    

    > [!NOTE]  
    > 你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要发布安装 Lync Server 2013 服务器所需的拓扑, 你必须使用<STRONG>域管理员</STRONG>组和 RTCUniversalS 的成员帐户。 <STRONG>erverAdmins</STRONG>组, 并且具有对永久聊天服务器文件存储中使用的文件存储的完全控制权限 (即读取、写入和修改), 以便拓扑生成器可以配置所需的 dacl, 或帐户具有等效权利。

    
    </div>

2.  启动拓扑生成器。

3.  在控制台树中, 导航到 "**持久聊天池**" 节点并展开它以选择持久聊天服务器池, 或者右键单击该节点, 然后选择 "**新建持久聊天池**"。 You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.
    
    您可选择“**多计算机池**”或“**单计算机池**”。 如果计划在持久聊天服务器池中安装多台持久聊天服务器前端服务器, 请选择前者。 现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。 如果您选择多台计算机池, 请输入组成池的单个持久聊天服务器前端服务器的名称。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果在 Lync Server 2013&nbsp;标准版服务器上安装持久聊天服务器角色, FQDN 需要与标准版服务器的 fqdn 相匹配。

    
    </div>

4.  为持久聊天服务器池定义一个简单的**显示名称**。 显示名称可由自定义客户端使用, 尤其是当存在多个持久聊天服务器池时, 可以使用它们来区分房间。

5.  定义持久聊天服务器用于与 Lync Server 前端服务器通信的端口。 默认端口为 5041。

6.  如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。 如果选择此项, 持久聊天服务器合规性服务将与持久聊天服务器前端服务器安装在同一台计算机上。 系统将提示你选择 SQL Server 后端服务器, 以便在以后持续聊天服务器合规性。

7.  为持久聊天服务器池分配网站相关性。 选中 "**将此池用作网站\<的 SiteName\>默认值**" 复选框, 或**将此池用作所有网站的默认值**将此持久聊天服务器池指定为当前网站或所有网站的默认池。 当 Lync 2013 客户端用于创建和管理会议室时, 聊天室创建和管理体验将使用与用户的网站关联的默认池, 以便它可以将会议室创建和管理操作路由到该池。 这仅适用于已部署多个持久聊天服务器池的情况, 并且希望使用持久聊天服务器的聊天室创建和管理功能。
    
    <div>
    

    > [!IMPORTANT]  
    > 可以使用持久聊天服务器软件开发工具包 (SDK) 自定义聊天室创建和管理功能。<BR>有关如何为灾难恢复配置 SQL Server 备份数据库的详细信息, 请参阅在部署文档中将<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">持久聊天服务器配置为适用于 Lync server 2013 的高可用性和灾难恢复</A>。

    
    </div>

8.  通过执行下列操作之一, 定义**持久聊天服务器后端的 SQL 应用商店 (存储聊天室内容)** :
    
      - 若要使用现有 SQL Server 数据库, 请在下拉列表中单击要使用的 SQL Server 数据库的名称。
    
      - 若要指定新的 SQL Server 数据库, 请单击 "**新建**", 然后在 "**定义新的 SQL 存储**" 中, 执行下列操作:
    
    <!-- end list -->
    
      - 在**SQL SERVER FQDN**中, 指定要在其上创建新的 sql server 数据库的 sql SERVER 的 FQDN。
    
      - 选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。

9.  如果已启用合规性, 请定义 SQL Server 合规性数据库。
    
    <div>
    

    > [!IMPORTANT]  
    > 有关如何将 SQL Server 镜像配置为持久聊天服务器数据库和持久聊天服务器合规性数据库的高可用性的详细信息, 请参阅<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">在 Lync 中配置持久聊天服务器以实现高可用性和灾难恢复</A>部署文档中的服务器2013。

    
    </div>

10. 定义文件存储。 文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。 在多服务器持久聊天服务器拓扑的情况下, 这必须是通用命名约定 (UNC) 路径;对于单服务器持久聊天服务器拓扑, 它可以是本地文件路径。
    
    若要使用现有文件存储，请执行下列步骤：
    
      - 在 "**文件服务器 FQDN**" 中, 指定要在其中创建新文件存储的文件存储的 FQDN。
    
      - 在“**文件共享**”中，指定要使用的文件存储。
    
    <div>
    

    > [!IMPORTANT]  
    > 你可以在创建文件存储之前在拓扑生成器中定义文件存储, 但你必须在发布拓扑之前在定义的位置创建文件存储。

    
    </div>

11. 选择要用作此持久聊天服务器池的下一跃点的前端服务器池。 这是可以将持久聊天服务器请求路由到此池的前端服务器池。

12. 若要保存配置，请单击“**完成**”。 持久聊天服务器池显示在拓扑生成器中, 附带你的特定池设置。
    
    若要立即发布您的持久聊天服务器的更新拓扑, 请参阅部署文档中的[Lync Server 2013 中的 "发布更新的拓扑](lync-server-2013-publish-the-updated-topology.md)"。
    
    <div>
    

    > [!NOTE]  
    > 拓扑生成器已打开, 你可以继续在<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中发布已更新拓扑</A>的步骤3以开始发布更新的拓扑。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

