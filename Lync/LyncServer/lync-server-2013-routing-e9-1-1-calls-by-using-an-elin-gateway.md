---
title: Lync Server 2013：使用 ELIN 网关路由 E9-1-1 呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-05_

统一通信开放互操作性计划中的某些合作伙伴提供了合格的支持紧急位置标识号 (ELIN) 的网关，该网关可充当合格 E9-1-1 服务提供商的 SIP 中继连接的备选项。 ELIN 网关支持 ISDN 或与基于公用电话交换网 (PSTN) 的 E9-1-1 服务的集中式自动通话记帐 (CAMA) 连接。 有关提供 ELIN 网关的合作伙伴以及其文档的链接的详细信息[http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)，请参阅。

与 E9-1-1 服务提供商的 SIP 中继连接相似，ELIN 网关还提供了将紧急呼叫路由到呼叫者的最合适的公共安全应答点 (PSAP) 的方法，但这些网关将 ELIN 用作位置标识符。 为你的组织中的每个紧急响应位置（ERL）定义 ELINs （有关详细信息，请参阅[在 Lync Server 2013 中管理 ELIN 网关的位置](lync-server-2013-managing-locations-for-elin-gateways.md)）。

将 ELIN 网关用于紧急呼叫时，你使用的是用于 SIP 中继连接的同一 Lync Server E9-1 基础结构。 也就是说，位置信息服务数据库提供 Lync Server 客户端的位置，并且位置策略启用该功能并定义路由。 但是，使用 ELIN 网关时，你需要将 ELINs 添加到位置信息服务数据库，并让 PSTN 运营商将其上传到自动位置识别（阿里）数据库。

当 Lync 客户从位置信息服务获取其位置时，位置包含 ELIN。 在紧急呼叫期间，ELIN 将包含在发送到 ELIN 网关的位置中。 ELIN 网关会将此呼叫标识为紧急呼叫并将呼叫者的号码与 ELIN 交换。 ELIN 网关随后会将呼叫路由到带有作为主叫号码的 ELIN 的 PSTN。 PSTN E9-1-1 提供商将在 ALI 数据库中查找 ELIN，该数据库是主街道地址指南 (MSAG) 数据库的附带数据库。 PSTN 随后会根据 ALI 查找将呼叫发送到最合适的 PSAP，而 PSAP 会根据 ALI 查找将第一个响应者发送到呼叫者的位置。 主叫号码将在 ELIN 网关上缓存一段预定时间以供回拨。 在回拨期间，PSAP 将到达 ELIN 网关，后者会将 ELIN 与呼叫者的直拨分机 (DID) 号码交换。

ELIN 网关仅支持来自您组织的网络中的紧急呼叫。 它们不支持从您的网络外发出的紧急呼叫。

<div>


> [!NOTE]  
> 有关使用 SIP 中继连接进行紧急呼叫的详细信息，请参阅<A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">在 Lync Server 2013 中使用 sip 主干进行路由 E9 呼叫</A>。



</div>

下图显示了使用 ELIN 网关时，如何将紧急呼叫从 Lync Server 路由到 PSAP。

**使用 ELIN 网关路由 E9-1-1 呼叫**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回呼号码的 SIP 邀请将路由到 Lync 服务器。

2.  Lync Server 匹配紧急号码，然后将呼叫路由（基于在适用位置策略中定义的**PSTN 使用**值）到中介服务器，以及从此处到 ELIN 网关。

3.  ELIN 网关通过 ISDN 或 CAMA 中继将呼叫路由到 PSTN。

4.  PSTN 将呼叫标识为紧急呼叫并将其路由到网路中的 E9-1-1 选择性路由器。E9-1-1 选择性路由器在 ALI 数据库中查找呼叫者的号码以获取地理位置。E9-1-1 选择性路由器根据从 ALI 数据库中检索到的位置信息将呼叫发送到最合适的 PSAP。 

5.  如果为通知配置了位置策略，则会向一个或多个组织的安全专员发送特殊的 Lync 紧急通知即时消息。 此消息始终会在安全主管的屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员可以使用即时消息或语音快速应答紧急呼叫者。

6.  如果呼叫被永久性中断，PSAP 将使用 ELIN 直接联系呼叫者。ELIN 网关会将 ELIN 与呼叫者的 DID 交换。

</div>

<span> </span>

</div>

</div>

</div>

