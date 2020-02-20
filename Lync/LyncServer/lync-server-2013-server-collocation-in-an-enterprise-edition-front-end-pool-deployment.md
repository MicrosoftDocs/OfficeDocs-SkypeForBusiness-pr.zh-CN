---
title: Lync Server 2013 Server 并置 in Enterprise Edition 前端池部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44b6c298d6c0d2116be92d5e267ef9b7418ea480
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>适用于 Lync Server 2013 的 Enterprise Edition 前端池部署中的服务器并置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-11_

本节介绍可以在 Lync Server 2013 前端池部署中并置的服务器角色、数据库和文件共享。

<div>

## <a name="server-roles"></a>服务器角色

在 Lync Server 2013 中，A/V 会议服务、中介服务、监控和存档在前端服务器上是并置，但需要进行其他配置才能启用它们。 如果您不想将中介服务器与前端服务器并置，则可以在单独的计算机上将其作为独立中介服务器进行部署。

您可以使用前端服务器并置受信任的应用程序服务器。

必须在单独的计算机上部署以下服务器角色：

  - 控制器

  - 边缘服务器

  - 中介服务器（如果未与前端服务器并置）

  - Office Web Apps Server

您不能并置持久聊天服务器角色与前端服务器。

</div>

<div>

## <a name="databases"></a>Databases

您可以在同一个数据库服务器上并置以下每个数据库：

  - 后端数据库

  - 监控数据库

  - 存档数据库

  - 持久聊天数据库

  - 持久聊天合规性数据库

可以在一个 SQL Server 实例中并置任何或全部或所有这些数据库，也可以为每个数据库使用单独的 SQL Server 实例，但具有以下限制：

  - 每个 SQL Server 实例只能包含一个后端数据库、一个监视数据库、一个存档数据库、一个持久聊天数据库和一个持久聊天合规性数据库。

  - 数据库服务器无法支持多个前端池、一个存档部署和一个监视部署，但它可以支持其中一个，而不管数据库是使用相同的 SQL Server 实例还是使用单独的 SQL Server 实例。

还可以将文件共享与数据库并置，如本节后面所述。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，可以选择将存档存储与部署中的部分或所有用户的 Exchange 2013 存储集成。 您不能在与 Exchange 存储相同的服务器上部署任何运行 Lync Server 或组件的服务器。



</div>

<div>


> [!IMPORTANT]  
> 尽管支持并置数据库，但数据库的大小增长非常快。 例如，当您考虑将存档数据库与其他数据库并置时，您应了解，如果您要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。 因此，我们不建议并置多个数据库（尤其是存档数据库、持久聊天数据库或与后端数据库的持久聊天合规性数据库）。



</div>

</div>

<div>

## <a name="file-share"></a>文件共享

文件共享可以配置为一台单独的服务器，也可以并置以下任意服务器或所有服务器上：

  - 数据库服务器，包括 Enterprise Edition 前端池的后端服务器

  - 存档数据库

  - 监控数据库

  - 持久聊天数据库

  - 持久聊天合规性数据库

单个文件共享可用于多个前端池、Standard Edition 服务器（均位于同一站点）。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，监视和存档将 Lync Server 文件共享用作前端服务器。



</div>

</div>

<div>

## <a name="other-components"></a>其他组件

您不能并置不是 Lync Server 2013 组件的反向代理服务器，但如果您想要支持使用任何 Lync Server 2013 服务器角色的联合用户共享 web 内容，则您的部署中也是必需的。 不过，您可以通过在组织中对其他应用程序使用的现有反向代理服务器上配置支持，来实现对 Lync Server 2013 部署的反向代理支持。

您不能并置任何 Exchange 统一消息（UM）组件或 SharePoint 组件与任何 SharePoint Server 角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

