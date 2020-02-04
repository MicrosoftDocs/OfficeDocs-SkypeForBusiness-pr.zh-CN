---
title: Lync Server 2013： PSTN 连接组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63b5534b817477ea42dbefd5244c974fc70881f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 连接组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。 此外，用户在发起和接收呼叫时应不必了解底层技术。 从用户的角度来看，企业语音基础结构与 PSTN 之间的通话似乎就像是另一个 SIP 会话。

对于 PSTN 连接，既可以部署 SIP 中继，也可以部署 PSTN 网关（使用 PBX，也称为直接 SIP 链接；或不使用 PBX）。

<div>

## <a name="sip-trunking"></a>SIP 中继

作为使用 PSTN 网关的替代方法，你可以使用 SIP 中继将企业语音解决方案连接到 PSTN。 SIP 中继可以实现以下方案：

  - 企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。

  - 通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。

使用此部署解决方案需要 SIP 中继服务提供商。

</div>

<div>

## <a name="pstn-gateways"></a>PSTN 网关

PSTN 网关是在企业语音基础结构和 PSTN 或 PBX 之间转换信号和媒体的第三方设备。 PSTN 网关与中介服务器配合使用，向企业语音客户端提供 PSTN 或 PBX 呼叫。 中介服务器还将来自企业语音客户端的呼叫提供给 PSTN 网关，以便路由到 PSTN 或 PBX。 有关与 Microsoft 配合使用以提供与 Lync Server 配合使用的设备的合作伙伴的列表，请参阅 Microsoft 统一通信合作伙伴网站[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。

</div>

<div>

## <a name="private-branch-exchanges"></a>专用交换机

如果您有一个使用专用分支交换（PBX）的语音基础结构，则可以将 PBX 与 Lync Server 企业语音配合使用。

支持的企业语音 PBX 集成方案如下所示：

  - 使用中介服务器支持媒体旁路的 IP PBX。

  - 要求使用单独的 PSTN 网关的 IP-PBX。

  - 时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。

<div>


> [!NOTE]  
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>Lync Server at。



</div>

有关提供企业语音解决方案的合作伙伴的详细信息，请参阅 Microsoft 统一通信合作伙伴网站[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。

有关提供企业语音硬件解决方案（包括 PSTN 网关）的合作伙伴的详细信息，请参阅 Microsoft 统一[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)通信合作伙伴网站。

</div>

</div>

<span> </span>

</div>

</div>

</div>

