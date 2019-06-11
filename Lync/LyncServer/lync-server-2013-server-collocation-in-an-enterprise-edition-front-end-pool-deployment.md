---
title: Enterprise Edition 前端池部署中的 Lync Server 2013 服务器并置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Lync Server 2013 的 Enterprise Edition 前端池部署中的服务器并置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-11_

本部分介绍了可在 Lync Server 2013 前端池部署中 collocate 的服务器角色、数据库和文件共享。

<div>

## <a name="server-roles"></a>服务器角色

在 Lync Server 2013 中, A/V 会议服务、中介服务、监视和存档都在前端服务器上 collocated, 但需要进行其他配置才能启用它们。 如果您不想 collocate 前端服务器的中介服务器, 则可以在单独的计算机上将其作为独立中介服务器进行部署。

你可以使用前端服务器 collocate 受信任的应用服务器。

以下服务器角色必须分别部署在单独的计算机上:

  - 控制器

  - 边缘服务器

  - 中介服务器 (如果未与前端服务器 collocated)

  - Office Web Apps Server

您不能与前端服务器 collocate 持久聊天服务器角色。

</div>

<div>

## <a name="databases"></a>数据库

你可以在同一个数据库服务器上 collocate 以下每个数据库:

  - 后端数据库

  - 监控数据库

  - 存档数据库

  - 持久聊天数据库

  - 持久聊天合规性数据库

你可以在 SQL Server 的单个实例中 collocate 任何或所有或所有这些数据库, 或者对每个实例使用单独的 SQL Server 实例, 但具有以下限制:

  - SQL Server 的每个实例只能包含单个后端数据库、单个监视数据库、单个存档数据库、单个持久聊天数据库和单个持久聊天合规性数据库。

  - 数据库服务器无法支持多个前端池、一个存档部署和一个监视部署, 但它可以支持其中一个, 而不管数据库使用的是相同的 SQL Server 实例还是 SQL Server 的单独实例。

你可以将文件共享与数据库 collocate, 如本节后面部分所述。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中, 你可以选择将存档存储与部署中的部分或所有用户的 Exchange 2013 存储进行集成。 不能在 Exchange 存储所在的服务器上部署任何运行 Lync Server 或组件的服务器。



</div>

<div>


> [!IMPORTANT]  
> 尽管支持 collocation 数据库, 但数据库的大小可以快速增长。 例如, 当你考虑将存档数据库与其他数据库 collocating 时, 请注意, 如果你要对超过几个用户的邮件进行存档, 则存档数据库所需的磁盘空间可能会变得非常大。 出于此原因, 我们不建议 collocating 多个数据库, 尤其是存档数据库、持久聊天数据库或与后端数据库的持久聊天合规性数据库。



</div>

</div>

<div>

## <a name="file-share"></a>文件共享

文件共享可以是单独的服务器, 也可以在同一台服务器上 collocated, 如下所示:

  - 数据库服务器, 包括企业版前端池的后端服务器

  - 存档数据库

  - 监控数据库

  - 持久聊天数据库

  - 持久聊天合规性数据库

单个文件共享可用于多个前端池, 标准版服务器 (所有位于同一网站中)。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中, 监视和存档将 Lync Server 文件共享用作前端服务器。



</div>

</div>

<div>

## <a name="other-components"></a>其他组件

不能 collocate 不是 Lync Server 2013 组件的反向代理服务器, 但如果你希望支持使用任何 Lync Server 2013 服务器角色的联盟用户共享 web 内容, 则你的部署中需要使用该服务器。 但是, 你可以通过在你的组织中针对其他应用程序使用的现有反向代理服务器上配置支持, 从而实现 Lync Server 2013 部署的反向代理支持。

不能 collocate 任何 Exchange 统一消息 (UM) 组件或具有任何 SharePoint Server 角色的 SharePoint 组件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

