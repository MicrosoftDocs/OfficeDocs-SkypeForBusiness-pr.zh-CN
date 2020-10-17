---
title: Lync Server 2013：语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f457fc96981927ea2b6cb4d4177488dc3f5231
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535489"
---
# <a name="voice-routes-in-lync-server-2013"></a>Lync Server 2013 中的语音路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

呼叫路由指定 Lync Server 如何处理由企业语音用户发出的出站呼叫。 当用户拨打号码时，前端服务器会根据需要将拨号字符串规范化为 e.164 格式，并尝试将其与 SIP URI 进行匹配。 如果服务器无法进行匹配，它将基于该号码应用传出呼叫路由逻辑。 定义该逻辑的最后一步是为每个拨号计划中所列出的每组目标电话号码创建单独的命名呼叫路由。

在定义出站呼叫路由之前，应当完成以下步骤：

  - 部署一个或多个中继。

  - 根据需要为站点、个人和联系人对象创建拨号计划。

  - 创建公用电话交换网 (PSTN) 用法记录。

另外，为了启用出站呼叫路由，您必须创建并分配一个或多个语音策略。您既可以在定义出站呼叫路由之前，也可以在这之后执行此操作。

对于每个路由，必须指定：

  - 一个名称，用来方便地标识路由。

  - 可选说明，在名称本身不足以描述路由时使用。

  - 正则表达式匹配模式，可识别应用路由的目标电话号码，以及不应用匹配模式的例外情况。

  - 要分配给路由的一个或多个中继。

  - PSTN 用法记录，用户必须拥有该记录才能呼叫与目标电话号码正则表达式相匹配的号码。

可以在 "Lync Server 控制面板" 中指定呼叫路由。 这些呼叫路由将填充服务器路由表，Lync Server 使用它来路由发往 PSTN 的呼叫。

<div>

## <a name="mn-trunk-support"></a>M:N 中继支持

Lync Server 提供了如何将呼叫路由到 PSTN 的灵活性。 语音路由可指定一组指向可用于特定语音呼叫的 PSTN 的中继。 中继将中介服务器和端口号与 PSTN 网关和侦听端口号相关联。 通过此逻辑关联，中介服务器可以与多个网关关联，并且可以连接到同一网关的多个连接。 在定义呼叫路由时，请指定与该路由关联的中继，但不指定与该路由关联的中介服务器。 若要通过在中介服务器与 PSTN 网关、IP Pbx 和会话边界控制器之间定义关系来创建中继， (SBCs) ，请使用拓扑生成器。

</div>

<div>

## <a name="least-cost-routing"></a>最低成本路由

由于您可以指定各个号码所路由到的中继，因此可以确定哪些路由成本最低并相应地实现这些路由。在选择中继时，一般规则是选择具有距离目标号码所在位置最近的网关的中继，以便尽可能降低长途费用。例如，如果您在纽约呼叫罗马的号码，则应当通过 IP 网络将电话传送至网关位于您驻罗马办事处的中继，这样就只会产生本地电话的费用。

有关如何使用最低成本路由的示例，请考虑以下内容：Fabrkam 决定允许德国用户使用美国中继拨打美国号码。 Fabrikam 还需要配置系统，以便从美国 Lync Server 用户到德国的所有呼叫以及邻近国家/地区的所有呼叫都将在德国的网关在中继上终止。 这种路由可以省钱，因为举例来说，从德国发往澳大利亚的呼叫比从美国发往澳大利亚的呼叫便宜。

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>转换出站拨号串

Lync Server 2013 （如它的直属前置任务）要求将所有拨号字符串正常化为 e.164 格式，以执行反向号码查找 (RNL) 。 对于网关或专用交换机 (需要使用本地拨号格式转换号码的 Pbx) ，Lync Server 2013 使您能够创建一个或多个规则，以协助在将其路由到中继之前处理被叫号码 (例如，请求 URI) 。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的规则。

在 Lync Server 2013 中，可以创建一个或多个规则，在将呼叫号码路由到中继之前对其进行操作，以协助对其进行操作。

在规划与网关：端口对与中介服务器：端口对相关联的中继中，使用类似的本地拨号要求对中继进行分组可能很有用，从而减少所需的转换规则的数量和写入它们所需的时间。

</div>

<div>

## <a name="configuring-caller-id"></a>配置呼叫者 ID

Lync Server 提供了一种为出站呼叫操作呼叫者 ID 的方法。 例如，如果组织想要屏蔽员工的直接拨号分机并将其替换为通用公司或部门号码，则管理员可以通过使用 Lync Server 控制面板抑制呼叫者 ID 并将其替换为指定的备用呼叫者 ID 来执行此操作。 在规划路由逻辑时，请考虑您希望此选项面向哪些个人、组或站点—甚至也许面向所有员工。

<div>


> [!NOTE]  
> 对于通过 PSTN 重新路由的呼叫，将显示常规呼叫者 ID，而不是原始呼叫者 ID。这可能会导致呼叫绕过被叫方可能已配置的“请勿打扰”或隐私设置。



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>其他路由逻辑

在创建出站呼叫路由时，应当注意可能影响路由逻辑的以下因素：

  - 如果呼叫是通过联盟边界建立的，则 URI 的域部分会将该呼叫路由到负责应用出站路由逻辑的企业。

  - 如果请求 URI 的域部分不包含企业的支持域，则服务器上的出站路由组件不会处理呼叫。

  - 如果没有为用户启用企业语音，则服务器会根据需要应用其他路由逻辑。

  - 如果呼叫路由到已被完全占用的网关（即所有的中继线路都繁忙），则网关会拒绝该呼叫，并且出站路由逻辑会将该呼叫重定向到下一个成本最低的路由。请对此认真考虑，因为大小适合国外小型办事处（例如，苏黎世办事处）的网关可能会针对发往瑞士的国际呼叫实际传送大量非本地流量。如果网关没有针对这个额外的流量正确地调整大小，则发往瑞士的呼叫可能会通过德国的网关路由，这会增加长途电话费。

</div>

</div>

<span> </span>

</div>

</div>

</div>

