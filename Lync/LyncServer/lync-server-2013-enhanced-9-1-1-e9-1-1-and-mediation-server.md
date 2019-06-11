---
title: Lync Server 2013：增强型 9-1-1 (E9-1-1) 和中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d8ba329d55c916b089437d4c63804c592c0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="31c23-102">Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器</span><span class="sxs-lookup"><span data-stu-id="31c23-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31c23-103">_**主题上次修改时间:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="31c23-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="31c23-104">中介服务器具有扩展的功能, 以便可以与增强的 9-1-1 (E9-1) 服务提供程序正确交互。</span><span class="sxs-lookup"><span data-stu-id="31c23-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="31c23-105">中介服务器上不需要特殊配置;默认情况下, E9-1-1 交互所需的 SIP 扩展包括在中介服务器的 SIP 协议中, 用于与网关对等 (PSTN 网关、IP PBX 或 Internet 电话服务提供商的 SBC) 的交互, 包括 E9-1-1 服务商会</span><span class="sxs-lookup"><span data-stu-id="31c23-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="31c23-106">是否可以在现有中介服务器池上终止 E9 服务提供商的 SIP 主干, 或者是否需要独立中介服务器将取决于 E9 SBC 是否可以与中介服务器池进行交互。</span><span class="sxs-lookup"><span data-stu-id="31c23-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="31c23-107">有关详细信息, 请参阅[Lync Server 2013 中的 M:N 主干](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="31c23-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

