---
title: Lync Server 2013：发布拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-01_

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑, 您应作为 RTCUniversalServerAdmins 和域管理员组成员的用户登录。 也可以委派正确的管理员权利和权限。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。 对于其他配置更改, 仅需要 RTCUniversalServerAdmins 组中的成员身份。

在拓扑生成器中定义拓扑后, 必须将拓扑发布到中央管理存储。 中央管理存储为定义、设置、维护、管理、描述和操作 Lync Server 2013 部署所需的数据提供可靠的 schematized 存储。 它还会验证数据, 以帮助确保配置一致性。 对此配置数据的所有更改都在中央管理存储上进行，这可以消除“不同步”问题。 数据的只读副本将复制到拓扑中的所有服务器, 包括边缘服务器。

<div>


> [!NOTE]  
> SQL Server 至少需要 20 GB 的可用磁盘空间, 才能成功发布初始拓扑并创建中央管理服务器。



</div>

<div>


> [!NOTE]  
> 仅适用于企业版: 为了发布拓扑, 基于 SQL Server 的后端服务器必须处于联机状态, 并且存在防火墙例外。 有关指定防火墙例外的详细信息, 请参阅<A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">了解适用于 Lync server 2013 的 SQL Server 的防火墙要求</A>。 有关配置 SQL Server 的详细信息, 请参阅<A href="lync-server-2013-configure-sql-server-for-lync-server.md">配置 Lync server 2013 的 SQL Server</A>。



</div>

<div>

## <a name="to-publish-a-topology"></a>发布拓扑

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  选择以从本地文件中打开拓扑。 如果您在定义拓扑的计算机上, 该位置将位于您在前面的步骤中保存它的位置。 通常, 这将是配置了拓扑的用户的 "文档" 文件夹。

3.  右键单击 " **Lync Server 2013** " 节点, 然后单击 "**发布拓扑**"。

4.  在“**发布拓扑**”页上，单击“**下一步**”。

5.  在 "**创建数据库**" 页面上, 选择要发布的数据库。
    
    <div>
    

    > [!NOTE]  
    > 如果你没有创建数据库的相应权限，可以清除这些数据库旁边的复选框，稍后可以由具有相应权限的用户创建数据库。 有关详细信息, 请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。

    
    </div>

6.  也可以单击“**高级**”。 高级 SQL Server 数据文件放置选项使你可以在以下选项之间进行选择:
    
      - **自动确定数据库文件位置**-此选项通过将日志和数据文件分发到最佳位置, 基于基于 SQL server 的服务器上的磁盘配置确定最佳操作性能。
    
      - **使用 SQL Server 实例默认值** - 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“**确定**”，然后单击“**下一步**”。

7.  在 "**选择中央管理服务器**" 页面上, 选择 "前端池"。

8.  也可以单击“**高级**”。 高级 SQL Server 数据文件放置选项使你可以选择以下选项:
    
      - **自动确定数据库文件位置**-此选项通过将日志和数据文件分发到最佳位置, 基于基于 SQL server 的服务器上的磁盘配置确定最佳操作性能。
    
      - **使用 SQL Server 实例默认值** - 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“**确定**”。

9.  单击“**下一步**”完成发布过程。

10. 发布过程完成后, 单击 "**完成**"。
    
    成功发布拓扑后, 你可以开始在拓扑中运行 Lync Server 2013 的每台服务器上安装中央管理存储的本地副本。 我们建议您从第一个前端池开始。

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

