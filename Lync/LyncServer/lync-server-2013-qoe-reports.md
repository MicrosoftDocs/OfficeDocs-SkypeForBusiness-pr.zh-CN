---
title: Lync Server 2013： QoE 报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 958c67b1b10b25e44805d2582ffe2e9fab575568
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>Lync Server 2013 中的 QoE 报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>QoE 摘要/趋势报告

QoE 摘要/趋势报告可用于查找一天的高峰使用时间，并在这些时间内检查媒体质量，以帮助确保组织的网络资源足够。 您的组织还可以使用报告中提供的多个筛选器来隔离特定位置、客户端和设备类型以及服务器的性能号码。

QoE 摘要/趋势报告包含以下内容：

  - UC 到 UC 摘要/趋势报告

  - PSTN 摘要/趋势报告

  - 会议摘要/趋势报告

</div>

<div>

## <a name="qoe-performance-reports"></a>QoE 性能报告

QoE 性能报告提供了有关三个报告的详细信息，这些报告集中在中介服务器、A/V 会议服务器和终结点位置的 QoE 性能上。

</div>

<div>

## <a name="mediation-server-performance-report"></a>中介服务器性能报告

中介服务器性能报告列出了在指定时间段内由一个或多个中介实现的指标。 统一通信（UC）到中介服务器腿的指标和每个呼叫的中介服务器到网关的线路分别报告。 使用此报告可比较组织的各种中介服务器的容量和性能。

对于每个中介服务器（和每个呼叫腿），报告将显示以下内容：

  - 呼叫数

  - 数据包丢失

  - 往返时间

  - 抖动

  - 会话平均意见得分（MOS）

  - 发送 MOS

  - 侦听 MOS

  - 网络 MOS

  - 网络 MOS 降级

  - 回显返回

  - 信号级别

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>A/V 会议服务器性能报告

A/V 会议服务器性能报告提供了在指定时间段内由一个或多个 A/V 会议服务器实现的指标的列表。 此报告可用于比较组织的各种 A/V 会议服务器的容量和性能。 您的组织还可以隔离报告以仅显示特定客户端类型（如 Lync 客户端或 PSTN 客户端）的体验。

对于每个 A/V 会议服务器，报告将显示以下内容：

  - 会议数

  - 数据包丢失

  - 往返时间

  - 抖动

  - 会话平均意见得分（MOS）

  - 发送 MOS

  - 侦听 MOS

  - 网络 MOS

  - 网络 MOS 降级

  - 回显返回

  - 信号级别

</div>

<div>

## <a name="location-based-performance-report"></a>基于位置的性能报告

基于位置的性能报告提供了网络位置的列表，每个位置都显示了每个预先确定的质量范围内的呼叫数。 此报告的目标是提供对各种位置的组织电话呼叫的媒体质量的深入了解，以便您能够识别出性能不佳的位置，并在组织中查看不同等级的媒体质量不同的位置。

显示报表时，将显示不同的指标表，即组织决定报告的每个指标的一个表。 您可以从此报告的以下指标中进行选择：

  - 会话平均意见得分（MOS）

  - 网络 MOS

  - 网络 MOS 降级

  - 发送 MOS

  - 侦听 MOS

  - 数据包丢失

  - 抖动

  - 延迟

</div>

</div>

<span> </span>

</div>

</div>

</div>

