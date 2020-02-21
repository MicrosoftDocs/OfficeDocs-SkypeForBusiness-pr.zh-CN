---
title: Lync Server 2013 server 并置 in Standard Edition Server 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1122605aabea32d86fbacd1f23675fcdef687539
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>适用于 Lync Server 2013 的 Standard Edition server 部署中的服务器并置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-20_

本节介绍了可以在 Lync Server 2013 Standard Edition server 部署中并置的服务器角色、数据库和文件共享。

<div>

## <a name="server-roles"></a>服务器角色

在 Lync Server 2013 中，A/V 会议服务、中介服务、监控和存档在 Standard Edition Server 上是并置，但需要进行其他配置才能启用它们。 您可以选择在单独的服务器上部署中介服务。

可以将受信任应用程序服务器与 Standard Edition 服务器并置。

必须在单独的计算机上部署以下服务器角色：

  - 控制器

  - 边缘服务器

  - 中介服务器（如果未与 Standard Edition 服务器并置）

  - Office Web Apps Server

</div>

<div>

## <a name="databases"></a>Databases

默认情况下，SQL Server Express 后端数据库并置在 Standard Edition 服务器上。 您不能将其移动到单独的计算机。 有一个例外，不能并置 Standard Edition server 上的其他数据库。 如果选择在 Standard Edition server 上部署持久聊天服务器，则可以在同一 Standard Edition 服务器上并置持久聊天数据库和持久聊天合规性数据库。

您还可以在一个单独的数据库服务器上并置以下每个数据库：

  - 监控数据库

  - 存档数据库

  - Enterprise Edition 前端池的后端数据库

您可以在单一的 SQL 实例中并置上述任意或所有数据库，或针对每个数据库使用一个单独的 SQL 实例，但有以下限制：

  - 每个 SQL 实例只能包含一个后端数据库（用于 Enterprise Edition 前端池）、一个监控数据库、一个存档数据库、一个持久聊天数据库以及一个持久聊天合规性数据库。

  - 数据库服务器无法支持多个 Enterprise Edition 前端池、一台运行存档的服务器、一台运行监控的服务器、单个持久聊天数据库和单个持久聊天合规性数据库，但它可以支持其中一种无论数据库是使用相同的 SQL Server 实例还是使用单独的 SQL Server 实例。

还可以将文件共享与数据库并置，如本节后面所述。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，可以选择将监控和存档存储与部署中的部分或所有用户的 Exchange 2013 存储集成。 您不能在与 Exchange 存储相同的服务器上部署任何运行 Lync Server 或组件的服务器。



</div>

<div>


> [!IMPORTANT]  
> 尽管支持并置数据库，但数据库的大小增长非常快。 例如，当您考虑将存档数据库与其他数据库并置时，您应了解，如果您要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。 因此，我们不建议并置多个数据库（尤其是存档数据库、持久聊天数据库和持久聊天合规性数据库）与企业版池的后端数据库一起使用。



</div>

</div>

<div>

## <a name="file-shares"></a>文件共享

文件共享可以配置为一台单独的服务器，也可以并置以下任意服务器或所有服务器上：

  - 数据库服务器，包括 Enterprise Edition 前端池的后端服务器

  - 存档数据库

  - 监控数据库

  - 持久聊天数据库

  - 持久聊天合规性数据库

单个文件共享可用于多个前端池、Standard Edition 服务器（均位于同一站点）。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，监视和存档将 Lync Server 文件共享用作 Standard Edition server。



</div>

</div>

<div>

## <a name="other-components"></a>其他组件

您不能并置不是 Lync Server 2013 组件的反向代理服务器，但如果您想要支持使用任何 Lync Server 2013 服务器角色的联合用户共享 web 内容，则您的部署中也是必需的。 不过，您可以通过在组织中对其他应用程序使用的现有反向代理服务器上配置支持，来实现对 Lync Server 2013 部署的反向代理支持。

您不能并置任何具有任何 Lync Server 2013 角色的 Exchange UM 组件或 SharePoint 组件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

