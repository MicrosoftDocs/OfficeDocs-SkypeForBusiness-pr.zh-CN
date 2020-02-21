---
title: Lync Server 2013：增强的9-1-1 （E9-1-1）和中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a84b9eb5579a1f0931f3363e2e4071ea7c8ac5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="05d18-102">Lync Server 2013 中的增强型9-1-1 （E9-1-1）和中介服务器</span><span class="sxs-lookup"><span data-stu-id="05d18-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05d18-103">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="05d18-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="05d18-104">中介服务器扩展了某些功能，从而可以正确地与增强型 9-1-1 (E9-1-1) 服务提供商进行交互。</span><span class="sxs-lookup"><span data-stu-id="05d18-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="05d18-105">中介服务器上不需要特殊配置;默认情况下，E9-1-1 交互所需的 SIP 扩展包括在中介服务器的 SIP 协议中，以用于与网关对等方（PSTN 网关、ip-pbx 或 Internet 电话服务提供商的 SBC，包括 E9-1-1 服务）的交互。商会</span><span class="sxs-lookup"><span data-stu-id="05d18-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="05d18-106">到 E9-1-1 服务提供商的 SIP 中继是可以在现有中介服务器池上终止，还是需要独立的中介服务器将取决于 E9-1-1 SBC 能否与中介服务器池进行交互。</span><span class="sxs-lookup"><span data-stu-id="05d18-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="05d18-107">有关详细信息，请参阅[Lync Server 2013 中的 M:N 中继](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="05d18-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

