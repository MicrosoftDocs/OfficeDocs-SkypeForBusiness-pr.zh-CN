---
title: Lync Server 2013 支持的池配对选项和最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33bc5e9622728fb4ee9c2a6a566e6010466d577
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Lync Server 2013 的受支持的池配对选项和最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-03-09_

要包括互相配对的前端池的两个数据中心之间没有距离限制。建议使用位于相同世界区域的两个数据中心，因为它们之间存在高速链接。最好两个数据中心之间拥有足够距离，以避免一个灾难同时袭击两个数据中心。

跨世界区域分布两个数据中心也是可行的，但可能会因为数据复制延迟而导致丢失较多数据。

在规划要配对的池时，必须记住仅支持以下配对：

  - Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。

  - 物理池仅能与其他物理池配对。同样，虚拟池仅能与其他虚拟池配对。

  - 配对在一起的池必须运行相同的操作系统。

拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。 例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。 但是，不支持这些类型的配对。

配对中的每个池应能够在发生灾难时为两个池中的所有用户提供服务。

如果对 Enterprise Edition 进行配对，还可以在后端服务器上实现高可用性，但是对于 Standard Edition 池的配对，仅能采用灾难恢复措施。

</div>

<span> </span>

</div>

</div>

</div>

