---
title: 'Lync Server 2013: 持久聊天服务器的组件和拓扑'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

持久聊天服务器支持单服务器配置和多服务器配置。 持久聊天服务器也可以在 Lync Server 2013 标准版服务器上运行。 这些配置包含以下持久聊天服务器组件和拓扑。

<div>

## <a name="persistent-chat-server-components"></a>持久聊天服务器组件

安装持久聊天服务器的最新版本需要以下组件:

  - 运行持久聊天服务器并提供以下服务的一个或多个计算机:
    
      - 持久聊天服务
    
      - 合规性服务，在启用合规性时打开
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 中, 用于文件上传/下载的持久聊天 Web 服务现在与 Lync Server 2013&nbsp;前端服务器 collocated。<BR>适用于聊天室管理的持久聊天 Web 服务也与 Lync Server 2013&nbsp;前端服务器 collocated。

    
    </div>

  - 服务器 (如果使用了镜像, 则会有多个服务器) 托管 SQL Server 后端数据库, 用于托管持久聊天内容数据库, 其中存储了聊天室内容、会议室和类别。
    
    <div>
    

    > [!NOTE]  
    > 后端数据库存储聊天历史记录数据, 包括有关已创建的类别和持续聊天室的信息。

    
    </div>

  - 如果启用了合规性, 则为托管持久聊天合规性数据库的 SQL Server 后端数据库托管 SQL Server 后端数据库的服务器 (多个服务器) (将存储合规性事件和聊天内容)。

若要从单独的计算机 (如管理控制台) 管理持久聊天服务器, 请使用计算机上的 Lync Server "控制面板"。 然后, 此计算机必须部署在 Active Directory 域服务域中, 并且林根中至少有一个全局编录服务器。

有关持久聊天服务器的硬件和软件要求的详细信息, 请参阅[Lync server 2013 中持久聊天服务器的技术要求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、 [lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md)以及[服务器软件和基础结构可支持文档中的 Lync Server 2013 支持](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-collocation"></a>支持的 Collocation

Lync Server 2013 支持各种 collocation 方案, 让你可以通过在一台服务器 (如果有一个小型组织) 上运行多个组件来灵活地保存硬件成本, 或在不同的服务器上运行单个组件 (如果你有需要可伸缩性和性能的较大组织。 在决定是否 collocate 组件之前, 一定要考虑可伸缩性因素。

如果合规性已启用, 则持久聊天合规性服务将与 Lync Server 2013 前端服务器 collocated。

可在标准版服务器上部署持久聊天服务器。 永久性聊天服务器后端服务器和持久聊天合规性数据库可在本地 SQL Server Express 后端服务器上的标准版服务器上 collocated。 有关可在此处 collocated 的组件的详细信息, 请参阅支持文档中的[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md) 。

对于 Lync Server 2013 企业版, 不能在企业版服务器上 collocated 持久聊天服务器。 持久聊天服务器的 SQL Server 数据库可与企业版前端池的后端服务器数据库 collocated。 适用于持久聊天合规性的 SQL Server 数据库也可与企业版池的后端服务器数据库 collocated。

<div>


> [!IMPORTANT]  
> 托管持久聊天数据库的服务器可以托管其他数据库。 但是, 当你考虑将持久聊天数据库与其他数据库一起使用时, 请注意, 如果你存储的消息超过了几个用户, 则持久聊天数据库所需的磁盘空间会变得非常大。 因此, 我们不建议将持久聊天数据库与后端数据库 collocating。



</div>

如果您使用后端数据库 collocate 持久聊天数据库, 则可以对任何或所有数据库使用一个 SQL Server 实例, 也可以为每个数据库使用单独的 SQL Server 实例, 但有以下限制:

  - 每个 SQL Server 实例只能包含一个后端数据库和一个持久聊天数据库。

有关所有服务器角色和数据库的 collocation 的详细信息, 请参阅支持文档中的[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md) 。

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>持久聊天服务器拓扑

持久聊天服务器支持下列拓扑:

  - Lync Server 2013 企业版单服务器持久聊天服务器前端服务器

  - Lync Server 2013 企业版多服务器持久聊天服务器前端服务器

  - 使用 SQL Server Express 的 Lync Server 2013 标准版服务器

  - 使用标准版服务器作为下一个跃点服务器的单独服务器上的 Lync Server 2013 标准版服务器和持久聊天服务器。

你可以使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署。 你可以将单个服务器或多台服务器持久聊天服务器池添加到你的拓扑。

<div>


> [!IMPORTANT]  
> 使用拓扑生成器创建单个服务器的持久聊天服务器池后, 不能将其他服务器添加到池中。



</div>

<div>

## <a name="single-server-topology"></a>单服务器拓扑

持久聊天服务器的最低配置和最简单的部署是单个持久聊天服务器前端服务器拓扑。 此部署需要运行持久聊天服务器的单个服务器 (可选择运行合规性服务)、托管 SQL Server 数据库的服务器以及是否需要合规性、SQL Server 数据库 (用于存储合规性数据。

<div>


> [!IMPORTANT]  
> 不能将其他服务器添加到在拓扑生成器中作为单服务器部署启动的持久聊天服务器池。 我们建议你使用多服务器池拓扑, 即使你使用的是单个服务器, 也可以稍后添加更多服务器 (如果需要)。



</div>

下图显示了具有合规性的单个持久聊天服务器前端服务器的拓扑的所有必需和可选组件。

**单个持久聊天服务器**

![具有合规性服务的单服务器拓扑](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有合规性服务的单服务器拓扑")

</div>

<div>

## <a name="multiple-server-topology"></a>多服务器拓扑

为了提供更大的容量和可靠性, 你可以部署多服务器拓扑, 如在[Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)中所述。 多服务器拓扑可以包括多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许八个, 但只有四个可以激活, 并且其余四个处于待机状态)。 每台服务器可支持多达20000并行用户, 总共可支持连接到具有4台服务器的持久聊天服务器池的80000个并发用户。 多服务器拓扑与单服务器拓扑相同, 不同之处在于多台服务器托管持久聊天服务器, 并且可以更高的比例。 运行持久聊天服务器的多台计算机应位于与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。

下图显示多服务器拓扑的所有组件, 其中包含运行持久聊天服务器的多台计算机、可选合规性服务和单独的合规性数据库。

**多个持久聊天服务器**

![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")

多服务器拓扑提供了服务器池功能。 在服务器池中, 持久聊天服务与数据进行通信和共享。 例如, 您可以从系统中的任何持续聊天服务获取最初发布到一个持久聊天服务的聊天历史记录。 通过一个持久聊天服务上载的文件可由任何永久聊天服务访问。 用户可以连接到不同的持久聊天服务器前端服务器, 并且可以互相聊天和通信。

TCP 8011 的默认端口将服务器连接到服务器池, 并由永久聊天服务用于自身通信, 或用于管理用途。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

