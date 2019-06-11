---
title: Lync Server 2013 可伸缩性测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Lync Server 2013 中的可伸缩性测试

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

Lync Server 2013 提供所有 Lync Server 实时通信的服务器基础结构, 包括即时消息 (IM) 和状态、会议和企业语音。 这包括使用 Lync Server 2013 池的硬件资源的所有功能, 因此会影响性能和规模。 所有组织都不会同等使用所有功能。

例如, 某些组织可能会非常频繁地在会议中使用视频, 而其他组织可能很少或无视频使用。 某些组织倾向于将 PowerPoint 幻灯片共享用于应用程序共享, 而其他组织更喜欢使用相反的幻灯片共享。 部署企业语音的组织可能会或不会大量使用响应组应用程序。 大多数组织部署监视服务器, 但不是其中许多部署存档服务器。 此外, 组织不具有相同的基础结构, 包括硬件容量、网络容量、已部署的池数和池的大小。 功能和基础结构的多样性对可伸缩性测试带来了挑战-不可能模拟所有可能的功能和基础结构组合。

为确定 Lync Server 的可伸缩性支持, 我们基于平均使用模式 (用户模型) 以并发方式使用所有 Lync Server 功能进行测试。 若要为 Lync Server 工作负荷确定合适的用户模型, 我们分析了许多数据点, 包括客户调查、Microsoft 客户体验改善计划的反馈、Microsoft 来自 Microsoft 的内部 IT 部门的 Lync 服务器使用数据、从 Live Meeting 服务中挖掘的数据。 在许多情况下, 用户模型具有较粗负载的偏差, 以便为组织内的使用提供舒适的边距。

在我们的可伸缩性测试中, 我们根据推荐的硬件和软件规范 (包括基础结构组件, 如 Active Directory 域服务、硬件负载平衡器和防火墙) 设置 Lync Server 2013 池。 我们尽可能与典型的实际环境紧密地建立 Lync 服务器环境。 然后, 我们使用 Lync Server 2013 应力和性能工具模拟 Lync Server 2013 加载 (基于我们的用户模型)。 .

我们执行多个可伸缩性测试的迭代 (包括多个三周测试运行)。 我们使用所有测试的结果来帮助优化性能, 并验证用户模型中的可伸缩性数字支持。

</div>

<span> </span>

</div>

</div>

</div>

