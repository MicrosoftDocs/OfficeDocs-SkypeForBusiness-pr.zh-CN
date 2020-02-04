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
ms.openlocfilehash: 31683641e50a3e3bc898841b0cf4b0911e046262
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 持久聊天服务器所需的资源

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-02-05_

持久聊天服务器的高可用性和灾难恢复需要更多资源，而不是完全操作所需的资源。 在为高可用性和灾难恢复配置持久聊天服务器之前，请确保除了标准持久聊天服务器操作所需的内容外，还可以使用以下资源。 有关其他配置信息，请参阅[在 Lync server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。

  - 一个专用数据库实例，位于永久聊天服务器服务的主前端所在的同一物理数据中心。 此数据库将用作主持久聊天数据库的 SQL Server 镜像。 （可选）如果希望自动故障转移到镜像数据库，请指定要用作镜像见证的其他 SQL Server。

  - 一个位于其他物理数据中心的专用数据库实例。 此数据库将用作主数据中心中数据库的 SQL Server 日志传送辅助数据库。

  - 一个专用数据库实例用作辅助数据库的 SQL Server 镜像。 （可选）将其他 SQL Server 指定为镜像见证服务器。 它们都必须位于辅助数据库所在的同一物理数据中心。

  - 如果启用了持久聊天服务器合规性，则需要另外三个专用数据库实例。 其分布与以前为持久聊天数据库所概括的一样。 虽然合规性数据库可能与持久聊天数据库共享相同的 SQL Server 实例，但我们建议将独立实例用于高可用性和灾难恢复。

  - 必须为 SQL Server 日志传送事务日志创建和指定文件共享。 运行持久聊天数据库的两个数据中心中的所有 SQL 服务器都必须具有对此文件共享的读/写访问权限。 此共享不会定义为 FileStore 角色的一部分。

  - 辅助数据库服务器上的文件共享，用作从主服务器文件共享复制的 SQL Server 事务日志的目标文件夹。

<div>


> [!NOTE]  
> 持久聊天服务器池中的活动持久聊天服务器必须与拓扑中定义的下一个跃点 Lync 池驻留在同一个时区中。



</div>

下图提供了有关如何在两个不同的延伸池拓扑中配置整个持久聊天服务器池的示例：

  - 延长的持久聊天服务器池当数据中心位于具有高带宽/低延迟的地域时。

  - 延长的持久聊天服务器池，在数据中心位于具有低带宽/高延迟的地域时。

下图显示了一种持续的持久聊天服务器池拓扑，其中数据中心具有高带宽/低延迟的地理位置。

**延长的持久聊天服务器池当数据中心位于具有高带宽/低延迟的地域时。**

![持久聊天服务器池 HBW 配置测试](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "持久聊天服务器池 HBW 配置测试")

下图显示了永久的持久聊天服务器池拓扑，其中数据中心具有低带宽/高延迟的地理位置。

**延长的持久聊天服务器池，在数据中心位于具有低带宽/高延迟的地域时。**

![持久聊天服务器池 LBW 配置测试](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "持久聊天服务器池 LBW 配置测试")

</div>

<span> </span>

</div>

</div>

</div>

