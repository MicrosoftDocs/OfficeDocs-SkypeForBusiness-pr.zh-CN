---
title: Lync Server 2013 拓扑更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 中的拓扑更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-02_

Lync Server 2013 的拓扑要求和注意事项与早期版本的拓扑要求和注意事项不同, 如本节中所述。

<div>

## <a name="new-front-end-pools-architecture"></a>新的前端池体系结构

在 Lync Server 2013 中, 企业版前端池的体系结构已更改为分布式系统体系结构。

使用此新体系结构, 后端数据库将不再是池中的实时数据存储。 有关特定用户的信息保存在池中的三个前端服务器上。 对于每个用户, 一台前端服务器充当该用户的信息的主服务器, 另外两个其他前端服务器充当副本。 如果前端服务器出现故障, 则作为副本提供的另一台前端服务器将自动提升为 master。

这会在后台发生, 管理员无需知道哪些前端服务器是哪些前端服务器是其用户。 此数据存储的分布提高了池中的性能和可伸缩性, 并消除了单个后端服务器的单点故障。

后端服务器充当用户和会议数据的备份存储, 也是其他数据库 (如响应组数据库) 的主存储。

这些改进还意味着你计划和维护池的方式有更改。 我们建议, 所有的企业版前端池至少包含三个前端服务器, 以提供前端池体系结构设计所需的完整的副本数。 此外, 在将服务器添加到前端池、从服务器中删除服务器或升级服务器时, 必须遵循某些过程。 有关详细信息, 请参阅[Lync Server 2013 中前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

<div>

## <a name="server-role-topology-changes"></a>服务器角色拓扑更改

以前在单独的服务器上运行的一些服务器角色现在合并到前端服务器角色中, 使你能够节省硬件成本

  - 在 Lync Server 2013 中, A/V 会议服务器始终与前端服务器 collocated。

  - 监视和存档的前端现在始终与前端服务器 collocated。 监视和存档每个设备仍需要单独的后端数据库, 该数据库可以在与前端池的后端数据库相同的服务器上 collocated, 也可以托管在单独的后端服务器上。

  - 持久聊天服务器现在是服务器角色。 在 Microsoft Lync Server 2010 中, 群组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任的应用程序。 在 Lync Server 2013 中, 持续聊天服务器功能是使用三个新的服务器角色实现的:
    
      - **PersistentChatService:** 作为前端角色实现的主持久聊天服务器服务
    
      - **PersistentChatStore:** 后端服务器角色
    
      - **PersistentChatComplianceStore:** 持久的聊天合规性的后端服务器角色

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

