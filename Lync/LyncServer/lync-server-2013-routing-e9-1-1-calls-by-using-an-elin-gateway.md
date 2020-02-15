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
ms.openlocfilehash: befa9ad077780eb57d4690790673fc0a5452af60
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>在 Lync Server 2013 中使用 ELIN 网关路由 E9-1-1 呼叫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-05_

统一通信开放互操作性计划中的一些合作伙伴提供启用了合格的紧急位置识别号码 (ELIN) 的网关，可以充当到合格的 E9-1-1 服务提供商的 SIP 中继连接的替代之选。 ELIN 网关支持与基于公用电话交换网 (PSTN) 的 E9-1-1 服务的 ISDN 或集中式自动信息计算 (CAMA) 连接。 有关提供 ELIN 网关的合作伙伴以及其文档的链接的详细信息[http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)，请参阅。

与 E9-1-1 服务提供商的 SIP 中继连接一样，ELIN 网关还提供了将紧急呼叫路由到呼叫者最合适的公共安全应答点（PSAP）的方法，但这些网关使用 ELIN 作为位置标识符。 您可以为组织中的每个紧急响应位置（ERL）定义 Elin （有关详细信息，请参阅[在 Lync Server 2013 中管理 ELIN 网关的位置](lync-server-2013-managing-locations-for-elin-gateways.md)）。

当您使用 ELIN 网关进行紧急呼叫时，请使用与您将用于 SIP 中继连接的同一 Lync Server E9-1 基础结构。 也就是说，位置信息服务数据库提供了 Lync Server 客户端的位置，并且位置策略启用了该功能并定义了路由。 但是，使用 ELIN 网关时，您需要将 Elin 添加到位置信息服务数据库，并让 PSTN 运营商将其上载到自动位置标识（阿里）数据库。

当 Lync 客户端从 Location 信息服务获取其位置时，该位置包含 ELIN。 在紧急呼叫期间，ELIN 包括在发送到 ELIN 网关的位置中。 ELIN 网关将该呼叫识别为紧急呼叫并将呼叫方的号码交换为 ELIN。 然后 ELIN 网关使用 ELIN 作为呼叫号码将呼叫路由到 PSTN。 PSTN E9-1-1 提供商在 ALI 数据库中查找 ELIN，该数据库与主街道地址指南 (MSAG) 数据库是配套数据库。 然后 PSTN 根据 ALI 查询将呼叫发送到最适宜的 PSAP，随后 PSAP 根据 ALI 查询将首位响应者发送到呼叫者位置。 呼叫号码在 ELIN 网关上缓存预定义的一段时间以便回叫。 在回叫期间，PSAP 到达 ELIN 网关，后者将 ELIN 交换为呼叫者的直接拨入 (DID) 号码。

ELIN 网关仅支持来自组织网络的紧急呼叫。 它们不支持从您网络外部发出的紧急呼叫。

<div>


> [!NOTE]  
> 有关使用 SIP 中继连接进行紧急呼叫的详细信息，请参阅<A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">通过在 Lync Server 2013 中使用 sip 中继路由 E9-1-1 呼叫</A>。



</div>

下图显示了在使用 ELIN 网关时，紧急呼叫如何从 Lync Server 路由到 PSAP。

**使用 ELIN 网关路由 E9-1-1 呼叫**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回拨号码的 SIP INVITE 将路由到 Lync Server。

2.  Lync Server 匹配紧急号码，然后将呼叫路由到中介服务器，并**将其路由**到中介服务器，并从此处发送到 ELIN 网关。

3.  ELIN 网关通过 ISDN 或 CAMA 中继将呼叫路由到 PSTN。

4.  PSTN 将呼叫标识为紧急呼叫并将其路由到网路中的 E9-1-1 选择性路由器。E9-1-1 选择性路由器在 ALI 数据库中查找呼叫者的号码以获取地理位置。E9-1-1 选择性路由器根据从 ALI 数据库中检索到的位置信息将呼叫发送到最合适的 PSAP。

5.  如果为通知配置了位置策略，则会向一个或多个组织的安全主管发送特殊的 Lync 急诊通知即时消息。 此消息始终会在安全人员的屏幕上弹出，并且包含呼叫者的姓名、电话号码、时间和位置，这就让安全人员可以使用即时消息或语音快速响应紧急呼叫者。

6.  如果呼叫过早地中断，那么 PSAP 使用 ELIN 直接联系呼叫者。ELIN 网关将 ELIN 交换为呼叫者的 DID。

</div>

<span> </span>

</div>

</div>

</div>

