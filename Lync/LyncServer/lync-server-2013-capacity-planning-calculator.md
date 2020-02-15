---
title: Lync Server 2013 容量规划计算器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5ece90e8db4240eaef00f39a827e6779663dcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>使用 Lync Server 2013 的容量规划计算器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-21_

Microsoft® Lync™ Server 2013 容量规划计算器可从<http://www.microsoft.com/download/details.aspx?id=36828>下载。 它旨在帮助您根据组织中启用的用户数和通信形式来确定服务器要求。 输入您的组织的配置文件，计算器将提供可帮助您规划拓扑的建议。

计算器创建的建议仅用于规划目的。 若要确保已正确设置 Lync Server 2013，需要实际的负载模拟。 若要在模拟负载下执行压力测试，请使用[Lync Server 2013 压力和性能工具](http://go.microsoft.com/fwlink/?linkid=282724)。

在确定您要为用户启用的用户配置文件和形式之后，可以使用计算器来规划所需的服务器、内存和带宽的数量。 此版本的计算器不会提供磁盘 i/o 要求指南。

此计算器是对[Microsoft Lync server](http://go.microsoft.com/fwlink/?linkid=282725)和[microsoft lync server](lync-server-2013-planning.md)的补充。 在您查看指南并使用规划工具创建推荐的拓扑之后，使用计算器。

如果您具有有关特定用户配置文件的准确、详细信息，则可以从计算器中获益最多。 例如，启用了语音的用户的百分比、每个用户每小时平均呼叫数、呼叫持续时间以及会议中并发用户的百分比可能会对服务器的要求产生巨大的影响。 计算器所创建的建议的准确性取决于您提供的信息的准确性。

<div>

## <a name="using-the-capacity-calculator"></a>使用容量计算器

计算器是 Microsoft Excel®电子表格。 橙色的单元格供您输入。 输入的默认值为（80000个用户在一个池中的12台前端服务器上），但您可以根据组织的需要更改这些值。

使用模型包含以下部分。 若要计算您的容量需求，请按如下所述输入数据：

**即时消息和状态**

  - 在 "用户数" 下，键入将并发登录的用户数。 此数字通常为已设置的用户总数的80%。 在大多数情况下，将对100% 的并发用户启用 IM 和状态。 默认值为80000。

  - 联系人列表中的平均联系人数表示用于验证您的系统要求的联系人数量。 此数字不可更改。

**企业语音**

  - 在 "启用企业语音的用户" 中，键入启用了企业语音的用户的百分比。 默认值为60%。

  - 在 "每个用户每小时的平均呼叫数（峰值）" 中，键入预计在高峰负载期间平均用户参与的每小时的呼叫数。 默认值为 4。

  - 在 "使用媒体旁路的呼叫百分比" 中，键入用户发出的将绕过中介服务器的呼叫百分比。 默认值为65%。

  - 在与 UC-PSTN 呼叫相关的语音用户的百分比中，键入组织的呼叫的百分比，即 UC-PSTN 电话呼叫。 默认值为60%

  - 在 UC-UC 呼叫中涉及的语音用户的百分比显示为企业语音启用的、仅对 UC UC 呼叫启用的用户的百分比。 根据为 UC-PSTN 呼叫启用的语音用户百分比输入的内容计算此数字。

**会议**

  - 在 "并发会议的用户百分比" 中，键入将并发参与会议的用户的百分比。 默认值为5%。

  - 在 "仅限组 IM （无语音）的会议百分比" 中，键入会议将仅涉及即时消息的会议所占的百分比;也就是说，不包含音频组件。 默认值为10%

  - 在使用电话拨入式会议的用户百分比中，键入将使用电话拨入式会议的会议中的并发参与者的百分比。 默认值为15%。

  - 在 "使用语音的会议百分比" 中，键入将包含音频组件的会议所占的百分比。
    
      - 如果20% 的语音会议也将包含常规视频，请选中 "包含视频（无多视图）" 复选框。
    
      - 如果20% 的会议也将包含多视图视频，请选中 "包含多个视图" 复选框。
    
      - 如果50% 的语音会议也将包含应用程序共享，请选中 "包括应用程序共享" 复选框。
    
      - 如果20% 的语音会议包括数据上载（如 Microsoft PowerPoint®演示文稿），请选中 "包括 web 会议" 复选框。

**移动性**

  - 在 "已启用移动性的用户百分比" 中，键入将启用使用移动设备连接到 Lync Server 的用户的百分比。 默认值为40%。

输入所有必要的信息后，容量计算器估计您的要求。 黄色单元格显示基于 Lync Server 2013 性能实验室中执行的测试的 CPU、内存和带宽要求的计算值。 这些数字作为指南提供，并不是每个单独的变体都经过测试和验证。 将计算以下值：

  - 前端 CPU：如果整个负载与 Microsoft 测试中使用的服务器具有相同规范的一台前端服务器的处理，则为 CPU 使用率的百分比。

  - 网络（以 Mbps 为单位）：带宽要求对应工作负载的带宽要求为每秒兆位（Mbps）。

  - 内存（GB）：针对相应工作负荷的内存，以千兆字节（GB）为单位。

绿色单元格显示有关您输入的使用情况模型的建议。

  - 前端服务器总数：所需的物理服务器数取决于运行 Lync Server 2013 的专用服务器和双处理器，hex-core，含2260兆周期。

  - 请注意，建议启用超线程，并已证明可提高支持音频/视频的服务器的性能。

  - 边缘服务器：根据所有并发用户通过边缘服务器通信时所需的边缘服务器的数量。 计算器中不能更改此百分比。

  - 存档/呼叫详细记录/高级服务存储：存档或监控功能所需的存储数量（如果在组织中已启用）。

  - 必需的后端数据库服务器（需要池）：支持所选工作负荷所需的后端数据库服务器的数量。

此外，在前端服务器总数的第一行中，提供了有关服务器和网络上的负载的更多信息，用于组合所有计划的工作负载。

  - 平均 CPU 负载：每个前端服务器的平均 CPU 使用率。

  - 网络（以 Mbps 为单位）：支持所需的带宽分配以支持您输入的使用模式。

  - 内存（GB）：每个前端服务器所需的内存（以 gb 为单位）。

</div>

<div>

## <a name="adjusting-for-your-processors"></a>针对处理器进行调整

电子表格中的所有 CPU 使用情况图都假定每台服务器都有双处理器、hex-core、2.26 GHz、至少 32 GB 的内存以及8个或更多个具有至少 72 GB 可用磁盘空间的 10000 RPM 硬盘。

如果你的服务器具有不同的处理器，则可以调整这些数字以匹配你的硬件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

