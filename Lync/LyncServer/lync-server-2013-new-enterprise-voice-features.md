---
title: Lync Server 2013：新的企业语音功能
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
ms.openlocfilehash: 92c1c264b9ffa5459962b2b6e915ea0fef2cf775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="5044d-102">Lync Server 2013 中新的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="5044d-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5044d-103">_**主题上次修改时间：** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="5044d-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="5044d-104">Lync Server 2013 引入了一些新的路由和通话管理功能，可增强企业语音。</span><span class="sxs-lookup"><span data-stu-id="5044d-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="5044d-105">Lync Server 2013 支持中介服务器和网关之间的多个中继。</span><span class="sxs-lookup"><span data-stu-id="5044d-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="5044d-106">*主干*是端口号和中介服务器与端口号和网关之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="5044d-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="5044d-107">这意味着中介服务器可以有多个中继用于不同的网关，并且网关可以为不同的中介服务器提供多个中继。</span><span class="sxs-lookup"><span data-stu-id="5044d-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="5044d-108">Intertrunk 路由使 Lync Server 2013 能够将 IP PBX 互连到公共交换式电话网络（PSTN）网关或互连多个 IP PBX 系统。</span><span class="sxs-lookup"><span data-stu-id="5044d-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="5044d-109">Lync Server 2013 充当不同电话系统之间的粘附（即互连）。</span><span class="sxs-lookup"><span data-stu-id="5044d-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="5044d-110">Microsoft Lync Server 2013 改进了呼叫转接、同时拨打、语音邮件处理和来电显示的演示文稿方面的改进。</span><span class="sxs-lookup"><span data-stu-id="5044d-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="5044d-111">这些功能丰富了企业语音呼叫体验。</span><span class="sxs-lookup"><span data-stu-id="5044d-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="5044d-112">Lync Server 2013 引入了以下新的企业语音增强功能：</span><span class="sxs-lookup"><span data-stu-id="5044d-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="5044d-113">Lync Server 2013 中新的呼叫功能</span><span class="sxs-lookup"><span data-stu-id="5044d-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="5044d-114">Lync Server 2013 中新的来电显示功能</span><span class="sxs-lookup"><span data-stu-id="5044d-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="5044d-115">Lync Server 2013 中新的语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="5044d-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="5044d-116">Lync Server 2013 中新的中继功能</span><span class="sxs-lookup"><span data-stu-id="5044d-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="5044d-117">Lync Server 2013 中新的中继间功能</span><span class="sxs-lookup"><span data-stu-id="5044d-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="5044d-118">Lync Server 2013 中的新呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="5044d-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

