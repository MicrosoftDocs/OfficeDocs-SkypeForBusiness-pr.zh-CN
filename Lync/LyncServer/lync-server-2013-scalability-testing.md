---
title: Lync Server 2013 可伸缩性测试
description: Lync Server 2013 可伸缩性测试。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73b4ab8726de7ea068ed60fedf104b01fe91ac1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574848"
---
# <a name="scalability-testing-in-lync-server-2013"></a>Lync Server 2013 中的可伸缩性测试

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

Lync Server 2013 为所有 Lync Server 实时通信（包括即时消息 (IM) 和状态、会议和企业语音）提供服务器基础结构。 这包括使用 Lync Server 2013 池的硬件资源的所有功能，因此会影响性能和规模。 所有组织并非均衡地使用所有功能。

例如，有些组织可能在会议中非常大量地使用视频，而其他组织的视频使用率可能很小或没有。 有些组织喜欢 PowerPoint 幻灯片共享而不喜欢应用程序共享，而其他组织的喜好则相反。 部署企业语音的组织可能会或不会频繁使用响应组应用程序。 大多数组织都部署监控服务器，但不是许多部署存档服务器。 此外，并非所有组织都具有相同的基础结构，包括硬件容量、网络容量，以及所部署的池数目和池的规模。 功能和基础结构的多样性为可伸缩性测试带来了挑战 – 无法模拟功能和基础结构的所有可能组合。

为确定 Lync Server 的可伸缩性支持，我们将根据平均使用率模型 (用户模型) ，以并发方式使用所有 Lync Server 功能进行测试。 为了确定适用于 Lync Server 工作负荷的用户模型，我们分析了许多数据点，包括客户调查、Microsoft 客户体验改善计划的反馈、Microsoft 内部 IT 部门的 Lync Server 使用情况数据，以及从 Live Meeting 服务中挖掘的数据。 在许多情况下，用户模型都偏向于更大的负载，以便为在组织中使用提供充裕的余量。

在我们的可伸缩性测试中，我们根据建议的硬件和软件规范（包括基础结构组件，如 Active Directory 域服务、硬件负载平衡器和防火墙）设置 Lync Server 2013 池。 我们将 Lync Server 环境尽可能与典型的实际环境紧密建立。 然后，使用 Lync Server 2013 压力和性能工具模拟 Lync Server 2013 加载 (基于我们的用户模型) 。 .

我们多次反复执行可伸缩性测试（包括多次为期三周的测试运行）。同时利用所有测试结果帮助进行性能调整并确认支持用户模型中的可伸缩数目。

</div>

<span> </span>

</div>

</div>

</div>

