---
title: Lync Server 2013：发布拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46212fc9910885ed1d6d833ef0f4b30c3a49b7c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-01_

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 还有可能委派相应的管理员权限。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。 对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。

在拓扑生成器中定义拓扑之后，必须将拓扑发布到中央管理存储。 中央管理存储为定义、设置、维护、管理、描述和运行 Lync Server 2013 部署所需的数据提供了一个强健的架构化存储。 它还会验证数据，以帮助确保配置的一致性。 对此配置数据所做的所有更改都将发生在中央管理存储中，从而消除了 "不同步" 问题。 数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器。

<div>


> [!NOTE]  
> SQL Server 至少需要 20 GB 的可用磁盘空间，才能成功发布初始拓扑并创建中央管理服务器。



</div>

<div>


> [!NOTE]  
> 仅限 Enterprise Edition：为了发布该拓扑，基于 SQL Server 的后端服务器必须处于联机状态，并且可以通过启用的防火墙例外规则访问。 有关指定防火墙例外的详细信息，请参阅<A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">了解使用 Lync server 2013 的 SQL Server 的防火墙要求</A>。 有关配置 SQL Server 的详细信息，请参阅<A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE SQL server For Lync Server 2013</A>。



</div>

<div>

## <a name="to-publish-a-topology"></a>发布拓扑

1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  选择从本地文件打开拓扑。如果位于定义拓扑的计算机上，则将位于前面步骤中所保存的位置。通常，这是配置该拓扑的用户的“文档”文件夹。

3.  右键单击 " **Lync Server 2013** " 节点，然后单击 "**发布拓扑**"。

4.  在“发布拓扑”**** 页上，单击“下一步”****。

5.  在“创建数据库”**** 页上，选择要发布的数据库。
    
    <div>
    

    > [!NOTE]  
    > 如果您没有创建数据库的相应权限，可以清除这些数据库旁边的复选框，稍后可以由具有相应权限的用户创建数据库。 有关详细信息，请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。

    
    </div>

6.  也可以单击“高级”****。 通过 "高级 SQL Server 数据文件放置" 选项，您可以在以下选项之间进行选择：
    
      - **自动确定数据库文件位置** – 此选项将通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器上的磁盘配置确定最佳运行性能。
    
      - **使用 SQL Server 实例默认值** – 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”****，然后单击“下一步”****。

7.  在 "**选择中央管理服务器**" 页上，选择一个前端池。

8.  也可以单击“高级”****。 利用 "高级 SQL Server 数据文件放置" 选项，您可以在以下选项之间进行选择：
    
      - **自动确定数据库文件位置** – 此选项将通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器上的磁盘配置确定最佳运行性能。
    
      - **使用 SQL Server 实例默认值** – 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”****。

9.  单击“下一步”**** 完成发布过程。

10. 发布过程完成后，单击“完成”****。
    
    成功发布拓扑后，您可以开始在拓扑中运行 Lync Server 2013 的每台服务器上安装中央管理存储的本地副本。 我们建议您从第一个前端池开始。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

