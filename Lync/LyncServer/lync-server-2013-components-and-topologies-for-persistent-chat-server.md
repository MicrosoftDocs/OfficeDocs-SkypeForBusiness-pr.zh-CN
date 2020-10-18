---
title: Lync Server 2013：持久聊天服务器的组件和拓扑
description: Lync Server 2013：持久聊天服务器的组件和拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576808"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的组件和拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

持久聊天服务器支持单服务器配置和多服务器配置。 持久聊天服务器也可以在 Lync Server 2013 Standard Edition server 上运行。 这些配置包含以下持久聊天服务器组件和拓扑。

<div>

## <a name="persistent-chat-server-components"></a>持久聊天服务器组件

安装最新版本的持久聊天服务器需要以下组件：

  - 一个或多个运行持久聊天服务器并提供以下服务的计算机：
    
      - 持久聊天服务
    
      - 合规性服务，在启用合规性时打开
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 中，用于文件上载/下载的持久聊天 Web 服务现在并置使用 Lync Server 2013 &nbsp; 前端服务器。<BR>聊天室管理的持久聊天 Web 服务也与 Lync Server 2013 &nbsp; 前端服务器并置。

    
    </div>

  - 服务器 (s)  (多个服务器（如果使用镜像）) 承载用于承载聊天室内容、聊天室和类别的持久聊天内容数据库的 SQL Server 后端数据库。
    
    <div>
    

    > [!NOTE]  
    > 后端数据库存储聊天历史记录数据，其中包括有关所创建的类别和持久聊天室的信息。

    
    </div>

  - 如果启用了合规性，则在存储用于承载持久聊天合规性数据库的 SQL Server 后端数据库的) 中，服务器 (s)  (多台服务器，其中存储了合规性事件和用于实现合规性的聊天内容。

若要从单独的计算机管理持久聊天服务器 (如管理控制台) ，请使用计算机上的 Lync Server 控制面板。 此计算机必须部署在 Active Directory 域服务域中，林根中至少有一个全局编录服务器。

有关持久聊天服务器的硬件和软件要求的详细信息，请参阅可支持性文档中的 lync server [2013 中的 "持久聊天服务器" 的技术要求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、lync server [2013 支持的硬件](lync-server-2013-supported-hardware.md)以及 [Lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md) 。

</div>

<div>

## <a name="supported-collocation"></a>支持的并置

Lync Server 2013 支持各种并置方案，使您可以通过在一台服务器 (上运行多个组件来节省硬件成本) 如果您有一个小型组织或在不同的服务器上运行单个组件 (如果您有需要可伸缩性和性能) 的大型组织。 在决定是否并置组件之前，一定要考虑可伸缩性因素。

如果合规性已启用，则持久聊天合规性服务将与 Lync Server 2013 前端服务器并置。

可以在 Standard Edition server 上部署持久聊天服务器。 可以在本地 SQL Server Express 后端服务器上的 Standard Edition server 上并置持久聊天服务器后端服务器和持久聊天合规性数据库。 有关可在其中并置的组件的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md) 。

对于 Lync Server 2013 Enterprise Edition，不能在 Enterprise Edition Server 上并置持久聊天服务器。 持久聊天服务器的 SQL Server 数据库可与 Enterprise Edition 前端池的后端服务器数据库并置。 用于持久聊天合规性的 SQL Server 数据库也可以与 Enterprise Edition 池的后端服务器数据库并置。

<div>


> [!IMPORTANT]  
> 承载持久聊天数据库的服务器可以承载其他数据库。 但是，当您考虑并置将持久聊天数据库与其他数据库一起使用时，请注意，如果存储的邮件超过几个用户，则持久聊天数据库所需的磁盘空间可能会变得非常大。 因此，我们不建议并置持久聊天数据库与后端数据库。



</div>

如果使用后端数据库并置持久聊天数据库，则可以对任意或所有数据库使用单个 SQL Server 实例，也可以对每个数据库使用单独的 SQL Server 实例，但有以下限制：

  - 每个 SQL Server 实例只能包含一个后端数据库和一个持久聊天数据库。

有关所有服务器角色和数据库的并置的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md) 。

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>持久聊天服务器拓扑

持久聊天服务器支持下列拓扑：

  - Lync Server 2013 Enterprise Edition 单服务器持久聊天服务器前端服务器

  - Lync Server 2013 企业版多服务器持久聊天服务器前端服务器

  - 使用 SQL Server Express 的 Lync Server 2013 Standard Edition Server

  - 使用 Standard Edition server 作为下一个跃点服务器的独立服务器上的 Lync Server 2013 Standard Edition server 和持久聊天服务器。

您可以使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署中。 可以将单个服务器或多服务器持久聊天服务器池添加到拓扑中。

<div>


> [!IMPORTANT]  
> 使用拓扑生成器创建具有单个服务器的持久聊天服务器池之后，不能向该池添加其他服务器。



</div>

<div>

## <a name="single-server-topology"></a>单服务器拓扑

持久聊天服务器的最小配置和最简单部署是一个持久聊天服务器前端服务器拓扑。 此部署需要运行持久聊天服务器 (的单个服务器，如果符合性已启用，则可以选择运行合规性服务) 、承载 SQL Server 数据库的服务器以及是否需要合规性，以存储合规性数据的 SQL Server 数据库为依据。

<div>


> [!IMPORTANT]  
> 您不能向作为拓扑生成器中的单个服务器部署启动的持久聊天服务器池添加其他服务器。 即使您使用的是单个服务器，也建议您使用多服务器池拓扑以便稍后添加更多服务器（如有必要）。



</div>

下图显示了符合条件的单个持久聊天服务器前端服务器的拓扑的所有必需组件和可选组件。

**单个持久聊天服务器**

![单服务器拓扑与合规性服务](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "单服务器拓扑与合规性服务")

</div>

<div>

## <a name="multiple-server-topology"></a>多服务器拓扑

若要提供更大的容量和可靠性，可以部署多服务器拓扑，如在 [Lync server 2013 中规划持久聊天服务器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。 多服务器拓扑可以包含多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许8个，但只有四个活动可以处于活动状态，并且在待机) 的其余四个。 每个服务器最多可以支持多达20000个并发用户，共80000个并发用户连接到具有4台服务器的持久聊天服务器池。 多服务器拓扑与单服务器拓扑相同，不同之处在于多个服务器承载持久聊天服务器，并且可以扩展到更高级别。 运行持久聊天服务器的多台计算机应驻留在与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。

下图显示了多个服务器拓扑的所有组件，其中包含多个运行持久聊天服务器、可选合规性服务和独立合规性数据库的计算机。

**多个持久聊天服务器**

![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")

多服务器拓扑提供了服务器池功能。 在服务器池中，持久聊天服务会进行通信并共享数据。 例如，可以从系统中的任何持久聊天服务获取最初发布到一个持久聊天服务的聊天历史记录。 通过一个持久聊天服务上载的文件可由任何持久聊天服务访问。 用户可以连接到不同的持久聊天服务器前端服务器，并且可以相互聊天和相互通信。

TCP 8011 的默认端口将服务器连接到服务器池，持久聊天服务使用这些端口相互通信，或用于管理目的。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

