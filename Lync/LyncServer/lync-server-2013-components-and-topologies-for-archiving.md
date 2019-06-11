---
title: Lync Server 2013：用于存档的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434fd8216689b42e664b5b421101470ad984bf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中用于存档的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-09_

如果要将 Lync Server 2013 IM 和会议内容存档, 可以在 Lync Server 中实现存档。

<div>

## <a name="archiving-components"></a>存档组件

存档功能包括以下组件:

  - **存档代理**。 存档代理 (也称为统一数据收集代理) 在每个前端池和标准版服务器上自动安装和激活。 尽管自动激活了存档代理, 但在启用并正确配置存档之前, 不会实际捕获任何消息。

  - **存档数据存储**。 Lync Server 2013 的数据存储可以是以下两种情况之一:
    
      - Exchange 2013 存储。 如果启用 "Microsoft Exchange 集成" 选项, 则托管在 Exchange 2013 服务器上的用户邮箱将 Exchange 2013 存储用于存档的数据, 但仅当邮箱已放在原地保留时。
    
      - SQL Server 存储。 如果部署中的用户位于 Lync Server 2013 上托管, 则可以设置运行支持的 SQL Server 版本的存档数据库, 以便为这些用户启用存档。

存档还需要文件存储, 但存档使用与前端服务器或标准版服务器相同的文件存储。

有关存档的硬件和软件要求的列表, 请参阅支持文档中的 lync [server 2013 支持的硬件](lync-server-2013-supported-hardware.md)和[lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

在具有需要存档支持的用户的每个池中部署存档。 存档在企业版池的前端服务器和标准版服务器上运行。 存档数据存储可能如下所示:

  - 与 Exchange 2013 存储集成

  - 使用单独的 SQL Server 数据库进行部署

如果 Exchange 2013 部署不包括 Lync Server 部署中的所有用户, 则必须为其邮箱在 Exchange 2013 服务器上的主用户使用 Microsoft Exchange 集成, 并且必须为所有其他用户部署单独的 SQL Server 数据库。用于存档的 Lync 用户。

</div>

<div>

## <a name="supported-collocation"></a>支持的 Collocation

Lync Server 2013 支持各种 collocation 方案, 让你可以灵活地通过在一台服务器 (如果有一个小型组织) 上运行多个组件来节省硬件成本, 或在不同服务器上运行单个组件 (如果你有更大的需要可伸缩性和性能的组织)。 在决定是否 collocate 组件之前, 一定要考虑可伸缩性因素。

存档部署在池或标准版服务器的前端服务器上。 有关可在此处 collocated 的组件的详细信息, 请参阅支持文档中的[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md) 。

如果你将单独的 SQL Server 数据库用于存档, 而不是或除了将存储与 Exchange 2013 存储集成, 则可以使用以下任一项 collocate 存档数据库:

  - 监控数据库

  - 企业版前端池的后端数据库

<div>


> [!NOTE]  
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。



</div>

如果您 collocate 使用监视数据库、后端数据库或这两个数据库中的存档数据库, 则可以为任何或所有数据库使用单个 SQL 实例, 也可以为每个数据库使用单独的 SQL 实例, 如下所示责任

  - 每个 SQL 实例只能包含一个后端数据库、单个监视数据库和一个存档数据库。

有关所有服务器角色和数据库的 collocation 的详细信息, 请参阅支持文档中的[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

