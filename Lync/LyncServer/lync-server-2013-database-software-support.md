---
title: Lync Server 2013 数据库软件支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013 中的数据库软件支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-12-01_

Lync Server 2013 支持下列数据库管理系统:

  - **前端池的后端数据库、存档数据库、监控数据库、持久聊天数据库和持久聊天合规性数据库**
    
      - Microsoft SQL Server 2008 R2 Enterprise 数据库软件（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Standard（64 位版本）。 此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2012 Enterprise（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2012 Standard（64 位版本）。此外，建议运行最新的 Service Pack。

  - **标准版服务器数据库和前端服务器数据库**
    
      - Microsoft SQL Server 2012 Express（64 位版本）。 此外，建议运行最新的 Service Pack。
        
        我们支持在前端服务器和标准版服务器上修补和升级 Microsoft SQL Server。 但是, 当您在前端服务器上进行任何类型的升级或修补程序时, 必须考虑仲裁要求。 有关详细信息，请参阅[Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)和 [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64 位版) 由 Lync Server 2013 在每个标准版服务器和每台前端服务器服务器上自动安装。

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 不支持32位版本的 SQL Server。 必须使用 64 位版本。</P>
> <LI>
> <P>SQL Server Web edition 和 SQL Server 工作组版不受支持。 不能将它们与 Lync Server 2013 一起使用。</P>
> <LI>
> <P>Lync Server 2013 支持本机数据库镜像。</P>
> <LI>
> <P>若要使用监视服务器角色, 应安装 SQL Server Reporting Services。</P></LI></UL>



</div>

在前端池中, 后端数据库可以是单个 SQL Server 计算机。

<div>


> [!IMPORTANT]  
> 如果你将 Lync Server 数据库与其他数据库 collocate, 我们强烈建议评估可能影响可用性和性能的所有因素, 并确保如果一个节点出现故障, 则其余节点可以处理该负载。 若要验证故障转移功能，建议您测试所有故障转移方案。



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>使用 SQL 镜像和 SQL 群集

Lync Server 2013 支持对每个 Lync Server 数据库使用 SQL 镜像或 SQL 群集。 你可以在 Lync Server 2013 中轻松设置拓扑生成器工具的 SQL 镜像。 对于 SQL 故障转移群集，您必须使用 SQL Server 进行设置。

Lync Server 2013 支持针对所有部署 (包括全新部署和从早期版本的 Lync Server 升级的组织) 的 SQL 镜像和 SQL 群集拓扑。

SQL 群集支持适用于主动/被动配置。出于性能原因，被动节点不应被任何其他 SQL 实例共享。

包括以下支持：

  - 针对以下各项的双节点故障转移群集：
    
      - Microsoft SQL Server 2012 Standard（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Standard（64 位版本）。此外，建议运行最新的 Service Pack。

  - 针对以下各项的最多十六节点的故障转移群集：
    
      - Microsoft SQL Server 2012 Enterprise（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Enterprise 数据库软件（64 位版本）。此外，建议运行最新的 Service Pack。

有关 SQL 镜像的详细信息, 请参阅[Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。 有关如何部署 SQL 群集的详细信息, 请参阅[配置 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。

有关 SQL Server 2012 中故障转移群集的详细信息和最佳做法, <http://technet.microsoft.com/en-us/library/hh231721.aspx>请参阅。 有关 SQL Server 2008 中的故障转移群集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>, 请参阅。

</div>

</div>

<span> </span>

</div>

</div>

</div>

