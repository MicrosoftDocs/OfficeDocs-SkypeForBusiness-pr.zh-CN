---
title: Lync Server 2013：持久聊天服务器所需的资源
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c925a695fd856c4e9c2d272d39f18a7c3d1f78c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器所需的资源

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-02-05_

持久聊天服务器的高可用性和灾难恢复所需的资源超出了完整操作通常所需的其他资源。 在将持久聊天服务器配置为实现高可用性和灾难恢复之前，请确保除了标准持久聊天服务器操作所需的资源之外，还可以使用以下资源。 有关其他配置信息，请参阅[在 Lync server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。

  - 一个专用数据库实例位于持久聊天服务器服务的主前端所在的同一物理数据中心。 此数据库将充当主持久聊天数据库的 SQL Server 镜像。 （可选）如果希望自动故障转移到镜像数据库，则指定其他 SQL Server 作为镜像见证。

  - 一个位于其他物理数据中心的专用数据库实例。 此数据库将充当主数据中心中数据库的 SQL Server 日志传送辅助数据库。

  - 一个专用数据库实例，充当辅助数据库的 SQL Server 镜像。 （可选）指定另一个 SQL Server 作为镜像见证服务器。 它们都必须位于辅助数据库所在的同一物理数据中心。

  - 如果启用持久聊天服务器合规性，则需要额外的三个专用数据库实例。 它们的分布与前面介绍的持久聊天数据库的分布相同。 尽管合规性数据库可以与持久聊天数据库共享相同的 SQL Server 实例，但我们建议采用独立实例来实现高可用性和灾难恢复。

  - 必须为 SQL Server 日志传送事务日志创建和指定文件共享。 运行持久聊天数据库的两个数据中心中的所有 SQL 服务器都必须具有对此文件共享的读/写访问权限。 此共享不会定义为 FileStore 角色的一部分。

  - 辅助数据库服务器上的文件共享，用作从主服务器文件共享中复制的 SQL Server 事务日志的目标文件夹。

<div>


> [!NOTE]  
> 持久聊天服务器池中的活动持久聊天服务器必须与拓扑中定义的下一个跃点 Lync 池位于相同的时区。



</div>

下图提供了有关如何在两个不同的延伸池拓扑中配置整个持久聊天服务器池的示例：

  - 数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。

  - 数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。

下图显示了持续的持久聊天服务器池拓扑，其中数据中心具有高带宽/低延迟的地理位置。

**数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。**

![持久聊天服务器池 HBW 配置考试](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "持久聊天服务器池 HBW 配置考试")

下图显示了连续的持久聊天服务器池拓扑，其中数据中心的地理位置为低带宽/高延迟。

**数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。**

![持久聊天服务器池 LBW 配置考试](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "持久聊天服务器池 LBW 配置考试")

</div>

<span> </span>

</div>

</div>

</div>

