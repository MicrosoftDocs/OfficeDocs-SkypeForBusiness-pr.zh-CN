---
title: 'Lync Server 2013: QoE 报表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04960c43dc8e29c6e5af44a1d3109e40dd578479
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Lync Server 2013 中的 QoE 报表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>QoE 摘要/趋势报告

QoE 摘要/趋势报表可用于查找每天的高峰使用时间和在这些时间内检查媒体质量, 以帮助确保你的组织的网络资源足够有效。 你的组织还可以使用报表中提供的许多筛选器来隔离特定位置、客户端和设备类型以及服务器的性能数字。

QoE 摘要/趋势报告包括:

  - UC 到 UC 摘要/趋势报告

  - PSTN 摘要/趋势报告

  - 会议摘要/趋势报告

</div>

<div>

## <a name="qoe-performance-reports"></a>QoE 性能报告

QoE 性能报告提供了有关三个报表的详细信息, 这些报表专注于中介服务器、A/V 会议服务器和终结点位置的 QoE 性能。

</div>

<div>

## <a name="mediation-server-performance-report"></a>中介服务器性能报告

中介服务器性能报告列出了在指定时间段内由一个或多个中介实现的指标。 统一通信 (UC) 到中介服务器腿的指标和每个通话的中介服务器到网关腿分别报告。 使用此报告比较组织的各种中介服务器的数量和性能。

对于每个中介服务器 (和每个呼叫腿), 报告将显示以下内容:

  - 通话的数量

  - 丢包

  - 往返行程时间

  - 抖动

  - 按会话平均观点 (MOS)

  - 发送 MOS

  - 侦听 MOS

  - 网络 MOS

  - 网络 MOS 性能下降

  - 回音返回

  - 信号级别

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>A/V 会议服务器性能报告

A/V 会议服务器性能报告提供指定时间段内由一个或多个 A/V 会议服务器实现的指标的列表。 此报告可用于比较组织的各种 A/V 会议服务器的数量和性能。 你的组织还可以隔离报表以仅显示特定客户端类型 (如 Lync 客户端或 PSTN 客户端) 的体验。

对于每个 A/V 会议服务器, 报表显示以下内容:

  - 会议数

  - 丢包

  - 往返行程时间

  - 抖动

  - 按会话平均观点 (MOS)

  - 发送 MOS

  - 侦听 MOS

  - 网络 MOS

  - 网络 MOS 性能下降

  - 回音返回

  - 信号级别

</div>

<div>

## <a name="location-based-performance-report"></a>基于位置的性能报告

基于位置的性能报告提供网络位置列表, 每个位置都显示了每个预定的质量范围内的通话次数。 此报告的目标是提供对不同位置的组织电话通话的媒体质量的深入了解, 以便您能够识别出较差的位置, 并在您的组织中查看不同等级的媒体质量不同的位置。

显示报表时, 将显示不同的度量表, 即组织决定报告的每个指标的一个表。 你可以从此报表的以下指标中进行选择:

  - 按会话平均观点 (MOS)

  - 网络 MOS

  - 网络 MOS 性能下降

  - 发送 MOS

  - 侦听 MOS

  - 丢包

  - 抖动

  - 滞后

</div>

</div>

<span> </span>

</div>

</div>

</div>

