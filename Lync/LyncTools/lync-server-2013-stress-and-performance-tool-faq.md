---
title: Lync Server 2013 压力和性能工具常见问题解答
description: Lync Server 2013 的压力和性能工具常见问题解答。
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
ms.openlocfilehash: 716325390bc33df209be3bdc67ed8b6cd7d1ec30
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573538"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 压力和性能工具常见问题解答

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>常见问题解答

以下是有关 Lync Server 2013 压力和性能工具的常见问题。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>我可以在生产中运行 LyncPerfTool.exe 吗？

我们不建议这样做。 此工具将影响服务器的性能、安全性和用户体验。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>我是首次登录我的用户。 为什么服务器在如此高的负载中运行？

用户首次登录时，会发生其他操作。 因此，Microsoft SQL Server 后端服务器上的性能将会降级。 我们建议您运行一个简短的测试，以在测量结果之前在所有用户上记录日志，然后重新启动客户端。 每秒仅支持12个以上的并发用户登录会话，但这取决于您的硬件配置。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的客户端内存不足。 该怎么办？

如果客户端内存不足，则需要减少每台计算机的用户数。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>目前，我的客户端是100% 的 CPU。 该怎么办？

如果在所有用户登录后，客户端运行的 CPU 非常高，则需要减少每台计算机的用户数。 高 CPU 峰值是可接受的，但是如果它是持续的，则需要减少负载。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>我是否可以在服务器上运行该工具？

不正确。 此方案不受支持，可能因二进制不匹配而失败。 此外，因为点是测量服务器上的资源消耗，所以运行该工具将导致度量无意义。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我是否可以在虚拟服务器或 Microsoft Hyper-v Server 2008/2012 上运行 LyncPerfTool.exe？

是。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 是什么意思？

MPOP 代表多点状态。 它旨在模拟用户从多台计算机登录到 Lync 2013 的情况。 请注意，在 LyncPerfTool.exe 中，每个终结点使用默认配置文件 (也就是说，配置文件不会在两个状态点) 进行拆分。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我 LyncPerfTool.exe 启动，但不会发生任何事情。 这是怎么回事？

检查客户端上的活动终结点总数计数器，以查看用户是否正在连接。 如果用户未连接，请验证 Lync Server 2013 配置。 出现此问题的原因通常是服务器名称、用户前缀或密码不正确。 请注意，外部客户端应将访问代理指定为 TargetServer 值。 验证配置文件中的端口。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>我如何知道发生了什么情况？

各种 LyncPerfTool 性能计数器指示用户是否正在连接和执行操作。 但是，要进行检查的一种简单方法是使用 Lync 2013 登录帐户之一并执行所需的操作。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>我安装了实时通信服务器 2007 R2 容量规划工具和/或 Lync Server 2010。 这是正常的吗？

不正确。 存在互操作性问题，您必须卸载此产品的所有早期版本。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>压力和性能工具是否会设置 CAA 呼叫信息服务器拓扑？

不正确。 工具只创建用户、联系人和通讯组列表，并模拟用户负载。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支持的最大用户数是多少？

我们总共创建了80000个用户并执行了使用这些工具总计30000个用户的测试。 我们建议最多为120000个用户，尽管技术限制允许更高的价值，具体取决于可用的客户端和服务器硬件。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

