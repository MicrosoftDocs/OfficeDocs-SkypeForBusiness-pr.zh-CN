---
title: Lync Server 2013 支持的池配对选项和最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>支持 Lync Server 2013 的池配对选项和最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2017-03-09_

对两个数据中心之间的距离没有限制, 包括彼此配对的前端池。 我们建议你在同一世界地区使用两个数据中心, 并在它们之间使用高速链接。 最好将两个数据中心分开, 以避免一次灾难碰到这两个数据中心。

可以在世界各地有两个数据中心, 但由于数据复制中的延迟, 可能会导致更高的数据丢失。

当您计划对池进行配对时，必须谨记仅支持以下配对法：

  - Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。 同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。

  - 物理池仅能与其他物理池配对。 同样，虚拟池仅能与其他虚拟池配对。

  - 配对的池必须运行相同的操作系统。

拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。但是，不支持进行这些类型的配对。

每个池中的每个池都应具有在发生灾难时为来自两个池的所有用户提供服务的容量。

如果你对企业版池进行了配对, 你也可以在后端服务器上实现高可用性, 但对于标准版池, 只有灾难恢复措施可用。

</div>

<span> </span>

</div>

</div>

</div>

