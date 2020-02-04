---
title: Lync Server 2013 应力和性能工具常见问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9138a23ee1fa45f3da827832b568852952b0ae4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 应力和性能工具常见问题

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>常见问题

下面是一些有关 Lync Server 2013 应力和性能工具的常见问题。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>是否可以在生产中运行 LyncPerfTool？

我们不建议这样做。 此工具将影响服务器性能、安全性和用户体验。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>我是第一次登录用户。 为什么服务器在如此高的负载中运行？

用户首次登录时，将发生其他操作。 因此，Microsoft SQL Server 后端服务器上的性能将降级。 我们建议你运行一个简短测试，该测试将在你测量结果之前登录所有用户，然后重新启动客户端。 我们不支持每秒超过12个并发用户登录会话，但这取决于你的硬件配置。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的客户端内存不足。 我该怎么办？

如果客户端内存不足，则需要减少每台计算机的用户数。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>我的客户始终处于100% 的 CPU。 我该怎么办？

如果您的客户在所有用户登录后都使用非常高的 CPU 运行，则您需要减少每台计算机的用户数。 高 CPU 峰值可接受，但如果持续，则需要减少负载。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>是否可以在服务器上运行该工具？

不能。 此方案不受支持，并且可能会由于二进制不匹配而失败。 此外，由于点用于测量服务器上的资源占用，因此运行工具会使度量变得毫无意义。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我是否可以在虚拟服务器或 Microsoft Hyper-v Server 2008/2012 上运行 LyncPerfTool？

是。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 的含义是什么？

MPOP 代表多点状态。 它旨在模拟用户从多台计算机登录到 Lync 2013 的情形。 请注意，在 LyncPerfTool 中，每个终结点使用默认配置文件（即，配置文件未在两个状态点之间拆分）。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我启动了 LyncPerfTool，但没有发生任何事情。 这是怎么回事？

检查客户端上的 "活动终结点总数" 计数器以查看用户是否连接。 如果用户未连接，请验证您的 Lync Server 2013 配置。 出现此问题的原因通常是服务器名称、用户前缀或密码不正确。 请注意，外部客户端应将访问代理服务器指定为 TargetServer 值。 验证配置文件中的端口。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>如何知道发生了什么情况？

各种 LyncPerfTool 性能计数器指示用户是否在连接和执行操作。 但是，要检查的一种简单方法是使用 Lync 2013 登录到其中一个帐户，并执行所需的操作。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>我已安装实时通信服务器 2007 R2 容量规划工具和/或 Lync Server 2010。 是否确定？

不能。 存在互操作性问题，必须卸载本产品的所有早期版本。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>压力和性能工具是否会设置 CAA 呼叫信息服务器拓扑？

不能。 这些工具仅创建用户、联系人和通讯组列表，并模拟用户负载。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支持的最大用户数是多少？

我们最多可创建80000个用户和执行的测试，这些测试共30000个用户，使用这些工具。 我们建议最多120000用户，尽管技术限制允许使用较高的值，具体取决于可用的客户端和服务器硬件。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

