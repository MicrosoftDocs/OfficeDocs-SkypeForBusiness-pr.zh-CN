---
title: Lync Server 2013：海报： Lync 呼叫质量方法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3647de7f803a8ec90d50236c5cf14c1a1cf8e0da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513389"
---
# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Lync Server 2013 中的 lync 呼叫质量方法

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-06-24_

本文是 [Lync 呼叫质量方法](https://go.microsoft.com/fwlink/?linkid=391841) 海报的附带，可以从下载中心下载。

![描述 CQM 过程的海报](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "描述 CQM 过程的海报")

您可以使用此海报了解 CQM、Lync 2013 和2010的呼叫质量方法，可帮助您查找并消除影响包含企业语音功能的 Lync 实现的呼叫质量和用户体验的问题。 呼叫质量方法是一种新的故障排除和服务管理框架，可以更好地集中精力改进 Lync 中的企业语音服务。 在本文中，您可以详细了解 CQM、所监视的服务器和解决方案的种类，以及如何处理所收集的遥测数据。

如果您对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。

海报对以下方面进行了说明：

  - 什么是 Lync CQM？

  - 优先顺序：运行趋势查询

  - PCD

  - 托管/非托管

  - 服务器植物道路

  - 最后一英里路

  - 终结点道路

  - 服务管理

  - 董事会游戏规则

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>什么是 Lync CQM？

呼叫质量方法是一种新的故障排除和服务管理框架，可以更好地集中精力改进 Lync 中的企业语音服务。 当您使用 CQM 时，需要付出的精力更少，以确保呼叫质量和用户对企业语音服务的满意度。 在 [通话质量方法](https://go.microsoft.com/fwlink/p/?linkid=615208)中，CQM 更全面地说明。 本文和海报是这些内容的摘要。

CQM 将系统故障排除分解为三个路径或 "道路"。 这些是：服务器植物道路，它看起来是服务器和它们之间的链接、结束点线，它看起来是用户设备和用于拨打呼叫的媒体，最后是一次英里路，可解决传统交换电话网络呼叫的集成。

每个道路分成多个与特定区域或主题相关的段，并在每个段定义的内容是可接受质量级别的情况下，执行操作以实现该质量级别，并就地实施服务管理计划，以在移动到下一主题之前维护该质量级别。

海报将 Lync CQM 作为一局游戏提供给三个玩家，每个玩家都会经历一条道路。 下载中附带的卡片用于模拟必须克服的呼叫质量障碍。 有关目标和如何实现它们的提示和建议包括在三个路径中，同时还针对在游戏中 (的实际应用程序中首先推荐的道路的优先级准则，这三个道路以并行) 的形式进行寻址。

CQM 在早期版本的 Lync 中如何工作？ CQM 是 Lync 2013 的新版，但其中的大部分可适应与 Lync 2010 一起使用。 CQM 可能会对 Microsoft Office Communicator 有一定程度的作用，但此操作未经测试且不受支持。

如果您对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>优先顺序：运行趋势查询

CQM 中的第一步是运行两周的每个趋势查询，然后分析结果。 按最大的流参与者（最高差的流比率和受管理的区域 (您控制) 的受管理区域）确定纠正措施的优先级。如果音频/视频多点控制单位 (AV MCU) 或中介查询显示较差的结果，则从红色或服务器植物路上开始。如果有线或无线查询显示较差的结果，则从蓝色或最后一英里路上开始。如果 VPN 或外部查询显示较差的结果，则从绿色或终结点路上开始。

选择开始使用的道路之后，为每个区域定义一个目标 (Assert) ，努力满足该目标 (实现) ，然后实施过程以保持在目标 (维护) 。 您还可以将此海报用作游戏，以了解 CQM 背后的原则。

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

PreCall 诊断工具 (PCD) 将帮助您识别和诊断外围网络中的问题 (QoE 数据库不会收集边缘或外围网络) 上的信息，还可以对最后一英里的连接进行故障排除。 该工具可作为 Windows 8 新式应用或 Windows 桌面应用程序 https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88 。

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>托管/非托管

Lync Server 部署和网络基础结构通常可分为托管和非托管空间。 管理空间包括您的整个内部有线网络和服务器基础结构。 非托管空间是无线基础结构和外部网络基础结构。

进行这种区分会提高数据的清晰度，并帮助您的组织专注于将对用户的语音和视频质量产生实实在在影响的工作负荷。 如果将呼叫放在您所拥有的基础结构上，则用户具有不同的质量预期，这是对某些其他实体 (非托管) 的控制的部分 (托管) 和基础结构。 这并不意味着无线用户会离开自己的设备，以获得出色的 Lync Server 体验。

在非托管空间中提高语音质量要求在管理空间中具有高质量。 无线 (Wi-fi) 是否被视为托管或非托管空间由您的组织决定。 实现正常运行环境的方法在两个空间中不同，这是解决方案。

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>服务器植物道路

服务器植物公路的第1部分解决了 Lync 实施中的实际服务器。 收集有关服务器本身及其在实施中的角色的 KHI 数据，并分析结果。 如果操作是保证的，请更正发现的任何问题。 有关此主题的更多详细信息，请参阅 KHI 海报随附的 [Lync Server 2013 中的关键运行状况指示器](lync-server-2013-poster-key-health-indicators.md) 一文。

下一段用于解决 AV MCU 服务器和中介服务器之间的媒体流。 首先，确定数据流阈值较差的目标。 较差的流通常为 PacketLossRate \> .01 或 PacketLossRateMax \> 。 另一个理想目标是 PoorStreamsRatio \< 2%。 接下来，使用详细的查询来查找 AVMCU 和中介服务器对，使用较差的流，调查不良流的原因、查看较差流路径中的网络设备、修正较差的流，并定义网络设备的最佳或 "黄金" 配置。 若要维护您的成就，请实施流程和工具来管理配置偏移并报告新的问题区域。

接下来，检查中介服务器和公用电话交换网（ (PSTN) 网关之间的媒体流。 首先，确定数据流阈值较差的目标。 较差的流通常为 PacketLossRate \> .01 或 PacketLossRateMax \> 。 另一个理想目标是 PoorStreamsRatio \< 2%。 接下来，使用详细查询查找具有较差流的中介服务器和网关对，调查不良流的原因、查看较差流路径中的网络设备、修正较差的流以及定义网络设备的最佳或 "黄金" 配置。 若要维护您的成就，请实施流程和工具来管理配置偏移并报告新的问题区域。

最后，检查 PSTN 网关的运行状况指标。 确定显示运行状况的统计信息并为其定义目标。 此处不提供任何特定指导，因为可以使用多个可能的网关。 建立目标后，根据需要进行补救以实现目标;在此过程中，您可能会定义网关的 "黄金" 或最佳配置。 若要维护您的成就，请实施流程和工具来管理配置偏移并报告新的问题区域。 请注意，固件和软件更新可能会改变您的配置，或让您更改 "黄金" 配置的定义，因此需要谨慎使用这些活动。

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>最后一英里路

在客户端连接到网络的两种方式中，有线预期能够提供最高的质量，并且相应的问题必须是最后一个英里问题的初始焦点。 使用 CQM 有线查询 (LastMile \_ 0 \_ 有线) 和它所提供的不良流比率数据。 建议您将目标 PoorStreamsRatio \< 5% for sites with \> 300 流定义) 。 若要实现目标，请将从最差订购的子网修正为最佳，并实施 QoS。

优化有线连接的质量后，提高无线质量会变得更加轻松，因为无线基础结构在每个位置驻留在有线内核顶部。 具有较好的有线质量的站点中的无线流较差必须具有特定的无线组件。 CQM 无线查询 (LastMile \_ 1 \_ 无线) 在日期范围内运行，并将从 Lync 客户端向或从会议服务器或中介服务器返回环境中的所有内部无线流。 建议您将目标 PoorStreamsRatio \< 5% for sites with \> 300 流定义) 。 若要实现目标，请将从最差订购的子网修正为最佳，并实施 QoS。

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>终结点道路

在与 Lync 配合使用时，可以通过耳机和已知生成可接受质量的其他设备来开始查询终结点道路。 我们建议将目标 AvgSendListen MOS \> 3.6 用于包含100个以上流的实现。 ) 通过识别有问题的设备并修复或替换它们来实现目标。

接下来，检查设备或电脑处理音频的最终用户呼叫。 建议的目标质量指标是 AudioMicGlitchRate \< = 1。 在确定用户系统的最佳系统配置时，请定义包括驱动程序版本的 "黄金" PC 配置。

现在，检查音频流从 Lync 终结点系统获取的网络路径，这可能会导致音频质量不佳。 如果音频通过 VPN 连接，您可能会看到延迟问题。 如果内部 Lync 客户端无法为两方或对等呼叫的其他内部 Lync 客户端建立直接媒体流，它将回退到通过 Lync Edge 服务器中继的路径，这将导致延迟问题，并增加丢失和抖动的可能性。 我们建议你在 VPN 上定义质量指标0% 的媒体。 在您进行修正以实现您设置的目标时，请确定问题子网并调查防火墙规则、数据包 shapers 和其他相关的网络设备配置。

IP 数据包可以使用传输控制协议 (TCP) 或用户数据报协议 (UDP) 。 TCP 对于数据流而言是最佳的。 UDP 是无连接的，更有效的媒体，因为 TCP 恢复机制无法及时解决实时媒体丢失的情况。 Lync 始终首选 UDP，但如果无法建立 UDP 会话，则将还原为 TCP。 通过 TCP 的媒体会话将表现出比通过 UDP 更差的质量。 我们建议通过 TCP 的高质量定义连接0%。 在您进行修正以实现您设置的目标时，请确定问题子网并调查防火墙规则、数据包 shapers 和其他相关的网络设备配置。

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>服务管理

服务管理是 CQM 的结束状态和所有三个道路的目标。 若要维护高级别的呼叫质量，请监视以下方面：

1.  **用户** -补救活动应显示用户满意度的实实在在增长。 您可以通过问题票证或其他反馈机制对此进行衡量。 您还可以发布质量指标。

2.  **Process** -定义 operationalize CQM 的每日、每周和每月进程。 监视节奏会在更高的频率下启动，同时您对 (日常) 进行补救， (每月) 按您稳定的频率移动到较低频率。

3.  **Tools** -确定用于衡量和修正的工具。 您可能会发现，自动运行 CQM 查询以支持您的过程非常有用。 修正可能需要其他工具，例如，在网络元素上强制实施标准化配置或在不良流中排除丢失问题。

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>董事会游戏规则

您可以使用此海报作为对 CQM 实现的引用或作为一种练习这些概念的游戏。 若要播放，你将需要 1 6 侧骰子和所提供的卡。 可在标准 Avery 5871 名片上进行打印的卡片的可下载版本。

游戏适用于3个玩家。 播放机可使用三种路径达到所需质量并达到中心服务管理状态：服务器工厂、终结点和最后英里。 每个路径在断言质量目标、实现目标和维护系统方面都有停止的方式。 将卡片放在上面的指示区域中，然后绘制5张卡片。 查看已绘制的卡片并将其放在相关的板段上。 每个玩家逐步在卡片上移动，断言质量目标，实现这些目标，并维护服务级别。 当所有玩家都达到中心服务管理状态时，就完成了游戏。 游戏卡下载中提供了更详细的规则。

若要 **断言** 质量目标，请查看适用于该目标的参数，并将所需的内容弄清楚并不能选择接受。 我们建议的起始点，但您必须进行最后的调用。 例外情况是 KHI 数据，应使用 Microsoft 建立的标准。 请参阅随附的 KHI 海报。

若要在游戏中 **实现** ，请使用提供的卡片代替 KHI 数据和系统查询。 如果游戏开始时未与给定的方位一起绘制卡片，可以继续执行此操作。 如果有相关卡片，请滚动骰子。 如果您在卡片上显示的数字下滚动，说明您已成功。 如果您在指定的数字上滚动，则必须从卡片组中绘制另一个卡片。 如果该卡片指示两个或更多玩家需要滚动，则必须全部成功滚动。

若要在游戏中 **维护** ，请将有关 Lync 环境的服务管理计划更高的状态反馈。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 网络指南](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[关键运行状况指示器：用于维护正常运行的 Lync 服务器的基础](https://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 呼叫质量方法](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

