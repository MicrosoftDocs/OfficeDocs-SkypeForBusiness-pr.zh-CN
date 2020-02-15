---
title: Lync Server 2013：大型会议支持常见问题解答
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c8d834bbd38cbfeeccc74e90bad6f11e47cc805
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Lync Server 2013 的大型会议支持常见问题解答

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

以下各节提供有关创建和运行大型会议的常见问题的解答。

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>问：可以参与大型会议的用户数是多少？

Lync Server 用户模型指定在专用于大型会议的池中的共享池或1000用户中的250个用户的限制，但这些号码只代表我们测试的用户数，并且仅代表我们在测试中使用的特定硬件集。 根据我们的测试，建议将这些限制作为最大大小。 但是，通过配置一个或多个会议策略（使用 Lync Server 命令行管理程序中的 Windows PowerShell cmdlet 或使用 Lync Server 配置），可以控制组织中的会议允许的实际人数。控制面版）。 您在会议策略中指定的数字可以是 1 到 4,294,967,295 之间的任意 32 位整数，但建议大小为 2 到 250（包括 2 和 250）位参与者；默认值为 250。

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>问：可以在专用于大型会议的池中召开的会议数或运行的其他工作负载是多少？

为确保在多达 1000 位参与者的大型会议中获得最佳用户体验，建议您在专用于大型会议的池中一次仅召开一个会议。还建议在大型会议进行时不要允许其他任何工作负载在该池中运行。

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>问：大型会议的组织者是否应托管在专用池中？

不是。我们不建议托管除管理专用池中大型会议计划的专门人员以外的任何用户。这可防止其他实时通信流导致该池中托管的大型会议出现问题。您应使用大型会议计划人员的用户帐户安排专用池中的大型会议。您应将会议组织者（请求大型会议的用户）的用户帐户添加为大型会议的演示者。

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>问：在大型会议中可以使用哪些媒体形式？

多达 1000 位用户的大型会议可以包括音频、视频、PowerPoint 共享、白板以及状态轮询。

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>问：是否可以在大型会议中使用组即时消息 (IM)？

是。 但是，大量即时消息可能会因 IM 窗口中的快速文本滚动问题而影响用户体验，特别是在许多会议参与者发送即时消息时。 向多达 1000 位用户发送大量即时消息也可能会产生大量服务器负载，这可能会影响性能。 通常情况下，只有问题和解答（Q\&As）才需要 IM。

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>用户是否可以通过电话拨入加入大型会议？

是。 如果已正确部署 Lync Server 2013 池并为其启用电话拨入式会议，则用户将能够通过拨入来加入大型会议。 我们的测试表明在 10 分钟内 1000 位用户中将有多达 15% 的用户可以加入大型会议。

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>问：是否可以在虚拟拓扑中托管大型会议？

我们尚未在虚拟拓扑中测试大型会议，因此不支持使用虚拟机托管大型会议的专用池。

</div>

</div>

<span> </span>

</div>

</div>

</div>

