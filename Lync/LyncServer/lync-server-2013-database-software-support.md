---
title: Lync Server 2013 数据库软件支持
description: Lync Server 2013 数据库软件支持。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c5d7b44e5febc4123dbcdf7072b98fcfd004609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558148"
---
# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013 中的数据库软件支持

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-01_

Lync Server 2013 支持以下数据库管理系统：

  - **前端池的后端数据库、存档数据库、监控数据库、持久聊天数据库和持久聊天合规性数据库**
    
      - Microsoft SQL Server 2008 R2 企业版数据库软件 (64) 位版本。 建议另外运行最新的 service pack。
    
      - Microsoft SQL Server 2008 R2 Standard (64-位版本) 。 建议另外运行最新的 service pack。
    
      - Microsoft SQL Server 2012 Enterprise (64-位版本) 。 建议另外运行最新的 service pack。
    
      - Microsoft SQL Server 2012 Standard (64-位版本) 。 建议另外运行最新的 service pack。

  - **Standard Edition server 数据库和前端服务器数据库**
    
      - Microsoft SQL Server 2012 Express (64-位版本) 。 建议另外运行最新的 service pack。
        
        我们支持对前端服务器和 Standard Edition 服务器上的 Microsoft SQL Server 进行修补和升级。 但是，当您在前端服务器上进行任何类型的升级或修补程序时，您必须考虑仲裁要求。 有关详细信息，请参阅在 lync server [2013 中升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md) [，以及在 lync server 2013 中的前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-bit edition) 由 Lync Server 2013 自动安装在每个 Standard Edition server 和每台前端服务器服务器上。

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 不支持32位版本的 SQL Server。 必须使用64位版本。</P>
> <LI>
> <P>SQL Server Web edition 和 SQL Server 工作组版不受支持。 不能将它们与 Lync Server 2013 一起使用。</P>
> <LI>
> <P>Lync Server 2013 支持本机数据库镜像。</P>
> <LI>
> <P>若要使用监视服务器角色，应安装 SQL Server Reporting Services。</P></LI></UL>



</div>

在前端池中，后端数据库可以是单个 SQL Server 计算机。

<div>


> [!IMPORTANT]  
> 如果您并置 Lync Server 数据库与其他数据库，我们强烈建议评估可能影响可用性和性能的所有因素，并确保如果一个节点发生故障，剩余的节点可以处理负载。 若要验证故障转移功能，建议您测试所有故障转移方案。



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>使用 SQL 镜像和 SQL 群集

Lync Server 2013 支持对每个 Lync Server 数据库使用 SQL 镜像或 SQL 群集。 您可以使用 Lync Server 2013 中的拓扑生成器工具轻松地设置 SQL 镜像。 对于 SQL 故障转移群集，必须使用 SQL Server 进行安装。

Lync Server 2013 支持对所有部署（包括 greenfield 部署和从以前版本的 Lync Server 升级的组织）使用 SQL 镜像和 SQL 群集拓扑。

SQL 群集支持适用于主动/被动配置。 出于性能原因，被动节点不应由任何其他 SQL 实例共享。

包括以下支持：

  - 针对以下各项的双节点故障转移群集：
    
      - Microsoft SQL Server 2012 Standard (64-位版本) 。 建议另外运行最新的 service pack。
    
      - Microsoft SQL Server 2008 R2 Standard (64-位版本) 。 建议另外运行最新的 service pack。

  - 针对以下各项的最高配置十六个节点的故障转移群集：
    
      - Microsoft SQL Server 2012 Enterprise (64-位版本) 。 建议另外运行最新的 service pack。
    
      - Microsoft SQL Server 2008 R2 企业版数据库软件 (64) 位版本。 建议另外运行最新的 service pack。

有关 SQL 镜像的详细信息，请参阅 [Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。 有关如何部署 SQL 群集的详细信息，请参阅 [CONFIGURE SQL Server 集群 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。

有关 SQL Server 2012 中故障转移群集的详细信息和最佳实践，请参阅 <https://technet.microsoft.com/library/hh231721.aspx> 。 有关 SQL Server 2008 中的故障转移群集，请参阅 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

