---
title: 'Lync Server 2013: 大型会议支持常见问题'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>适用于 Lync Server 2013 的大型会议支持常见问题

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

以下部分提供了有关创建和运行大型会议的常见问题的答案。

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>问: 有多少用户可以参与大型会议？

Lync Server 用户模型指定在专用于大型会议的池中的共享池或1000用户中的250用户的限制, 但这些数字仅表示我们测试的用户数, 并且仅表示我们在测试中使用的特定硬件集。 根据我们的测试, 我们建议对最大大小的限制。 但是, 你可以通过配置一个或多个会议策略来控制你组织中的会议所允许的实际参与者数 (使用 Lync Server Management Shell 中的 Windows PowerShell cmdlet 或使用 Lync 服务器配置)"控制面板")。 在会议策略中指定的数字可以是1和4294967295之间的任何32位整数, 但建议的大小介于2和250参与者之间, 包括;默认值为250。

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>问: 我可以在一个专用于大型会议的池中拥有多少个会议或其他工作负荷？

为确保在最多1000参与者的大型会议中获得最佳用户体验, 我们建议在专用于大型会议的池上一次仅托管一个大型会议。 我们还建议当大型会议正在进行时, 不允许任何其他工作负荷在该池中运行。

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>问: 大型会议的组织者是否应该托管在专用池？

不能。 我们建议不要在专门的人员 (这些员工) 之外的其他任何用户 (在专用的池中管理大型会议的计划) 进行托管。 这可防止其他实时通信流量导致在池中托管的大型会议出现问题。 你应该使用大型会议计划员工的用户帐户, 在专用池上安排大型会议。 应将会议组织者的用户帐户 (请求大型会议的用户) 添加为大型会议的演示者。

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>问: 我可以在大型会议中使用哪些媒体形式？

最多1000个用户的大型会议可以包括音频、视频、PowerPoint 共享、白板和状态轮询。

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>问: 是否可以在大型会议中使用群组即时消息 (IM)？

是。 但是, 大量即时消息 (尤其是当由大量的会议参与者发送时) 可能会因在即时消息窗口中快速文本滚动问题而影响用户体验。 向多达1000用户提供大量即时消息也可能会引入大量的服务器负载, 这可能会影响性能。 通常, 只有问题和解答 (Q\&As) 才需要 IM。

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>通过从电话拨入, 用户能否加入大型会议？

是。 如果 Lync Server 2013 池已正确部署, 并且已启用电话拨入式会议, 则用户可以通过拨入来加入大型会议。 我们的测试显示, 最多 15% 的1000用户可以在10分钟时间内加入大型会议。

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>问: 我是否可以在虚拟拓扑中托管大型会议？

我们尚未在虚拟拓扑中测试大型会议, 因此我们不支持使用虚拟机来托管大型会议的专用池。

</div>

</div>

<span> </span>

</div>

</div>

</div>

