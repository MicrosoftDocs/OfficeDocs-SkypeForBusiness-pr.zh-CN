---
title: Lync Server 2013：SIP 中继概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 中继概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

部署 SIP 中继对于简化组织的电信和准备实时通信的最新增强功能来说可能是重要的一步。SIP 中继的主要优点之一是可以在中央站点中合并组织的公用电话交换网 (PSTN) 连接，与早期的时分多路复用 (TDM) 中继相反，后者通常要求在每个分支站点部署单独的中继。

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server 中的 SIP 中继

Lync Server 2013 SIP 中继功能支持以下功能:

  - 企业用户 (无论是在企业防火墙内部还是外部), 都可以通过在 PSTN 上终止的以164为单位的服务提供商的服务来指定本地呼叫或长途呼叫。

  - 任何 PSTN 订阅者都可以通过拨打与该企业用户相关联的直接向内拨号 (已完成) 号码, 与企业防火墙内部或外部的企业用户联系。

</div>

<div>

## <a name="cost-savings"></a>节省成本

可以大大节省与 SIP 中继有关的成本：

  - 通过 SIP 中继拨打长途电话通常可以大幅降低成本。

  - 可以节省可管理性成本并降低部署的复杂性。

  - 如果可以以极低的成本将 SIP 中继直接连接到 ITSP，则可以消除基本速率接口 (BRI) 和主速率接口 (PRI) 的费用。在 TDM 中继中，服务提供商按分钟对呼叫计费。SIP 中继的成本可能基于带宽使用，能够以更小、更经济的增量购买带宽。（实际成本取决于选择的 ITSP 的服务模型。）

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 中继与承载 PSTN 网关或 IP-PBX

由于 SIP 中继直接连接到服务提供商，因此可以消除 PSTN 网关及其管理成本和复杂性。使用 SIP 中继可以减少维护和管理工作，从而大幅节省成本。

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>扩展的 VoIP 服务

语音功能通常是部署 SIP 中继的主要动机，但是语音支持只是第一步。 使用 SIP 中继, 您可以扩展 VoIP 功能并启用 Lync Server 2013 以提供一组更丰富的服务。 例如：

  - 未运行 Lync Server 2013 的设备的增强状态检测可提供与移动电话的更好集成, 让你能够查看用户何时使用手机呼叫。

  - 通过使用 E9-1-1 紧急呼叫，应答 911 呼叫的机构可以通过电话号码确定呼叫者的位置。

<div>


> [!NOTE]  
> 与 ITSP 联系以获取他们支持并且可以为贵组织启用的服务列表。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

