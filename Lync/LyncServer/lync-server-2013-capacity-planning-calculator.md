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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>使用 Lync Server 2013 的容量计划计算器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-21_

可通过下载 Microsoft® Lync™ Server 2013 容量规划计算器<http://www.microsoft.com/en-us/download/details.aspx?id=36828>。 它旨在帮助你根据你的组织中启用的用户数和通信形式来确定服务器要求。 输入你的组织的配置文件，计算器将提供帮助你规划拓扑的建议。

计算器创建的建议仅供规划之用。 要确保已充分设置 Lync Server 2013，需要实际的负载模拟。 若要在模拟负载下执行压力测试，请使用[Lync Server 2013 应力和性能工具](http://go.microsoft.com/fwlink/?linkid=282724)。

确定要为用户启用的用户配置文件和形式后，可以使用计算器来计划所需的服务器、内存和带宽的数量。 此版本的计算器不针对磁盘 I/O 要求提供指导。

此计算器补充[Microsoft Lync server](http://go.microsoft.com/fwlink/?linkid=282725)和[microsoft lync server](lync-server-2013-planning.md)。 请在阅读指南并使用规划工具创建建议的拓扑之后使用计算器。

如果您拥有有关您的特定用户概况的准确、详细的信息，则可以充分享受计算器带来的好处。例如，启用语音的用户的百分比、每个用户每小时的平均呼叫、呼叫持续时间以及会议中的并发用户百分比可能会对服务器要求造成巨大差异。计算器创建的建议的准确性取决于您提供的信息的准确性。

<div>

## <a name="using-the-capacity-calculator"></a>使用容量计算器

计算器是 Microsoft Excel®电子表格。 橙色的单元格用于输入。 输入默认值（在一个池中有十二个前端服务器的80000用户），但您可以根据组织的需要更改这些值。

使用模型包含以下部分。 若要计算容量要求，请按如下所述输入数据：

**即时消息和状态**

  - 在 "用户数" 下，键入将同时登录的用户数。 此数目通常是已设置的用户总数的 80%。 在大多数情况下，将对所有并发用户启用 IM 和状态。 默认值为 80,000。

  - 联系人列表中的平均联系人数表示我们用于验证你的系统要求的联系人数。 此号码不可更改。

**企业语音**

  - 在 "已启用企业语音的用户" 中，键入已启用企业语音的用户的百分比。 默认值为 60%。

  - 在 "每个用户每小时平均通话次数（峰值）" 中，键入预计平均用户在高峰负载的时间内参与的每小时通话次数。 默认值为 4。

  - 在“使用媒体旁路的呼叫百分比”中，键入由你的用户拨打的、将绕过中介服务器的呼叫百分比。 默认值为65%。

  - 在“UC-PSTN 呼叫中涉及的语音用户百分比”中，键入你的组织的呼叫属于 UC-PSTN 电话呼叫的百分比。 默认值为60%

  - 在 UC-UC 通话中涉及的语音用户的百分比显示启用了企业语音的用户的百分比，仅适用于 UC-UC 呼叫。 此数目基于你对“启用 UC-PSTN 呼叫的语音用户百分比”输入的内容进行计算。

**会议**

  - 在 "并发会议中的用户百分比" 中，键入将同时参与会议的用户的百分比。 默认值为 5%。

  - 按仅限群组 IM （无语音）的会议的百分比，键入会议将仅涉及即时消息的会议百分比;也就是说，不包括音频组件。 默认值为 10%。

  - 在使用电话拨入式会议的用户百分比中，键入会议中将使用电话拨入式会议的并发参与者的百分比。 默认值为 15%。

  - 在使用语音的会议百分比中，键入将包含音频组件的会议的百分比。
    
      - 如果 20% 的语音会议也将包括普通视频，请选择“包括视频（无多视图）”复选框。
    
      - 如果 20% 的会议也将包括多视图视频，请选择“包括多视图”复选框。
    
      - 如果 50% 的语音会议也将包括应用程序共享，请选择“包括应用程序共享”复选框。
    
      - 如果您的语音会议的20% 包括数据上载（如 Microsoft PowerPoint®演示文稿），请选中 "包括 web 会议" 复选框。

**移动性**

  - 在 "为移动启用的用户百分比" 中，键入将启用其使用移动设备连接到 Lync Server 的用户的百分比。 默认值为 40%。

在你输入所有必要信息之后，容量计算器将估计你的要求。 黄色单元格根据 Lync Server 2013 性能实验室中执行的测试显示 CPU、内存和带宽要求的计算值。 这些数字仅供参考，并没有针对所有单个变体进行测试和验证。 将计算以下值：

  - 前端 CPU：如果整个负载由一台前端服务器处理，与 Microsoft 测试中使用的服务器相同，则为 CPU 使用率的百分比。

  - 网络 (Mbps)：对应工作负载的带宽要求 (Mbps)。

  - 内存 (GB)：对应工作负载所需的内存 (GB)。

绿色单元格显示为您输入的使用模型提供的建议。

  - 前端服务器总数：所需的物理服务器数基于运行 Lync Server 2013 的专用服务器（采用双处理器，十六进制），2260兆周期。

  - 请注意，建议启用超线程，它经过证明可改进支持音频/视频的服务器的性能。

  - 边缘服务器：所需的边缘服务器数目基于通过边缘服务器进行通信的所有并发用户的 30% 确定。 此百分比不可在计算器中更改。

  - 存档/呼叫详细记录/用户体验质量服务存储：存档或监视功能（如果你的组织已启用）所需的存储数。

  - 所需的后端数据库服务器（需要池）：支持所选工作负载所需的后端数据库服务器数目。

此外，在“前端服务器总数”旁边的行中，针对综合的所有计划工作负载提供了有关您的服务器和网络上的负载的更多信息。

  - 平均 CPU 负载：每个前端服务器的平均 CPU 使用。

  - 网络 (Mbps)：支持你输入的使用模型所需的带宽分配。

  - 内存 (GB)：每个前端服务器所需的内存 (GB)。

</div>

<div>

## <a name="adjusting-for-your-processors"></a>针对处理器进行调整

电子表格中的所有 CPU 使用数字都假设每台服务器具有双处理器、十六核 (2,260 GHz)、至少 32 GB 内存以及 8 个或以上 10,000-RPM 硬盘驱动器（至少 72 GB 的可用磁盘空间）。

如果您的服务器具有不同的处理器，您可以根据您的硬件调整数字。

</div>

</div>

<span> </span>

</div>

</div>

</div>

