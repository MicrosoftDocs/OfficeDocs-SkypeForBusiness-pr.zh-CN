---
title: Lync Server 2013：用于存档的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea07370fc0ccaebb5e89cfea958067b3d6373bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中用于存档的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

如果要存档 Lync Server 2013 IM 和会议内容，可以在 Lync Server 中实施存档。

<div>

## <a name="archiving-components"></a>存档组件

存档功能包括以下组件：

  - **存档代理**。将在每个前端池和 Standard Edition 服务器上自动安装和激活存档代理（也称为“统一数据收集代理”）。尽管会自动激活存档代理，但实际上并不捕获任何消息，除非启用存档并正确配置存档。

  - **存档数据存储**。 Lync Server 2013 的数据存储可以是以下两种情况之一：
    
      - Exchange 2013 存储。 如果启用了 Microsoft Exchange 集成选项，则驻留在 Exchange 2013 服务器上的用户邮箱将 Exchange 2013 存储用于存档的数据，但前提是这些邮箱已置于就地保留状态。
    
      - SQL Server 存储。 如果您的部署中有用户托管在 Lync Server 2013 上，则可以设置存档数据库，以运行受支持的 SQL Server 版本，以便为这些用户启用存档。

存档还需要文件存储，但是存档使用与前端服务器或 Standard Edition 服务器相同的文件存储。

有关存档的硬件和软件要求的列表，请参阅可支持性文档中的 lync server [2013 支持的硬件](lync-server-2013-supported-hardware.md)和[lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

您在每个具有需要存档支持的池中部署存档。 存档在企业版池的前端服务器和 Standard Edition 服务器上运行。 存档数据存储可以：

  - 与 Exchange 2013 存储集成

  - 使用单独的 SQL Server 数据库部署

如果您的 Exchange 2013 部署不包括 Lync Server 部署中的所有用户，则您必须为其邮箱位于 Exchange 2013 服务器上的用户使用 Microsoft Exchange 集成，并且您必须为所有其他服务器部署单独的 SQL Server 数据库。用于存档的 Lync 用户。

</div>

<div>

## <a name="supported-collocation"></a>支持的并置

Lync Server 2013 支持各种并置方案，从而可以灵活地通过在一台服务器（如果有小型组织）上运行多个组件来节省硬件成本，或在不同的服务器上运行单个组件（如果有更大的需要可伸缩性和性能的组织）。 在决定是否并置组件之前，一定要考虑可伸缩性因素。

存档部署在池或 Standard Edition 服务器的前端服务器上。 有关可在其中并置的组件的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

如果将单独的 SQL Server 数据库用于存档，而不是或除了将存储与 Exchange 2013 存储集成，则可以使用以下任一项对存档数据库进行并置：

  - 监控数据库

  - 企业版前端池的后端数据库

<div>


> [!NOTE]  
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。



</div>

如果将存档数据库与监控数据库、后端数据库或这两个数据库并置，则可以对任一或所有数据库使用单个 SQL 实例，也可以对每个数据库使用一个单独的 SQL 实例，但有以下限制：

  - 每个 SQL 实例只能包含一个后端数据库，一个监控数据库和一个存档数据库。

有关所有服务器角色和数据库的并置的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

