---
title: Lync Server 2013：新的企业语音功能
description: Lync Server 2013：新的企业语音功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1fc0c0970fe22fb6a56eaf0d950f1d49d210826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578828"
---
# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="97ba8-103">Lync Server 2013 中新的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-103">New Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97ba8-104">_**上次修改的主题：** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="97ba8-104">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="97ba8-105">Lync Server 2013 引入了几个新的路由和呼叫管理功能，可增强企业语音。</span><span class="sxs-lookup"><span data-stu-id="97ba8-105">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="97ba8-106">Lync Server 2013 支持中介服务器和网关之间的多个中继。</span><span class="sxs-lookup"><span data-stu-id="97ba8-106">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="97ba8-107">*中继*是端口号和中介服务器与端口号和网关之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="97ba8-107">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="97ba8-108">这意味着中介服务器可以有多个中继到不同的网关，并且一个网关可以有多个中继到不同的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="97ba8-108">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="97ba8-109">中继间路由使 Lync Server 2013 能够将 IP-PBX 互连到公用电话交换网， (PSTN) 网关或互连多个 IP-PBX 系统。</span><span class="sxs-lookup"><span data-stu-id="97ba8-109">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="97ba8-110">Lync Server 2013 充当粘附 (也就是说，不同电话系统之间的互连) 。</span><span class="sxs-lookup"><span data-stu-id="97ba8-110">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="97ba8-111">Microsoft Lync Server 2013 改进了呼叫转接、同时响铃、语音邮件处理和呼叫者 ID 演示的各个方面。</span><span class="sxs-lookup"><span data-stu-id="97ba8-111">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="97ba8-112">这些功能丰富了企业语音呼叫体验。</span><span class="sxs-lookup"><span data-stu-id="97ba8-112">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="97ba8-113">Lync Server 2013 引入了以下新的企业语音增强功能：</span><span class="sxs-lookup"><span data-stu-id="97ba8-113">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="97ba8-114">Lync Server 2013 中的新呼叫功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-114">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="97ba8-115">Lync Server 2013 中的新呼叫者 ID 功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-115">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="97ba8-116">Lync Server 2013 中新的语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-116">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="97ba8-117">Lync Server 2013 中的新中继功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-117">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="97ba8-118">Lync Server 2013 中的新中继间功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-118">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="97ba8-119">Lync Server 2013 中的新呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="97ba8-119">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

