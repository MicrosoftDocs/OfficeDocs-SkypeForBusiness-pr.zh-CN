---
title: Lync Server 2013 拓扑更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3979aa0725b632a1b5910c5f7e27b9a6a28245d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530389"
---
# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 中的拓扑更改

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

Lync Server 2013 的拓扑要求和注意事项与早期版本的拓扑要求和注意事项不同，如本节中所述。

<div>

## <a name="new-front-end-pools-architecture"></a>新的前端池体系结构

在 Lync Server 2013 中，企业版前端池的体系结构已更改为分布式系统体系结构。

有了此新的体系结构，后端数据库不再是池中的实时数据存储。有关特定用户的信息将保存在池中的三个前端服务器中。对于每个用户，一个前端服务器充当用户信息的主存储，而另外两个前端服务器充当副存储。如果一个前端服务器不可用，则充当副存储的其他前端服务器将自动提升为主存储。

这将在后台进行，管理员不必知道哪些前端服务器是哪些用户的主存储。 此数据存储的分布可提高池内的性能和可伸缩性，并消除单个后端服务器的单一故障点。

后端服务器充当用户和会议数据的备份存储，并且还是其他数据库（如响应组数据库）的主存储。

这些改进还意味着规划和维护池的方式有了变化。 我们建议您的所有 Enterprise Edition 前端池至少包含三台前端服务器，以提供前端池体系结构设计的完整数量的副本。 此外，在将服务器添加到前端池、从服务器中删除服务器或升级服务器时，必须遵循某些过程。 有关详细信息，请参阅 [Lync Server 2013 中的前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

<div>

## <a name="server-role-topology-changes"></a>服务器角色拓扑更改

之前在各台服务器上运行的部分服务器角色现已并置为前端服务器角色，使您节约了硬件成本

  - 在 Lync Server 2013 中，A/V 会议服务器始终与前端服务器并置。

  - 监控和存档的前端现已与前端服务器并置。监控和存档仍需要单独的后端数据库，该数据库可在与前端池的后端数据库相同的服务器上进行并置，也可以驻留在各台后端服务器上。

  - 持久聊天服务器现在是一个服务器角色。 在 Microsoft Lync Server 2010 中，组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任应用程序。 在 Lync Server 2013 中，持久聊天服务器功能是使用三个新的服务器角色实现的：
    
      - **PersistentChatService：** 作为前端角色实施的主持久聊天服务器服务
    
      - **PersistentChatStore：** 后端服务器角色
    
      - **PersistentChatComplianceStore：** 持久聊天合规性的后端服务器角色

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

