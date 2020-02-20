---
title: Lync Server 2013：规划 PSTN 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65474919bdd189f35431700f834402c5815d959c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="46993-102">在 Lync Server 2013 中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="46993-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46993-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="46993-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="46993-104">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="46993-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="46993-105">发出和接收呼叫的用户不应了解基础技术：从用户的角度来看，企业语音基础结构与 PSTN 之间的呼叫似乎只是另一个电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="46993-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="46993-106">Lync Server 2013 通过使用以下选项提供可靠、可扩展的 PSTN 连接：</span><span class="sxs-lookup"><span data-stu-id="46993-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="46993-107">到 Internet 电话服务提供商 (ITSP) 的 **SIP 中继**</span><span class="sxs-lookup"><span data-stu-id="46993-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="46993-108">到 PSTN 网关的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="46993-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="46993-109">到 PBX 的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="46993-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="46993-110">根据企业大小、地理范围和现有语音基础结构，企业可能会在不同位置使用一个、两个甚至所有三个选项。</span><span class="sxs-lookup"><span data-stu-id="46993-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="46993-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="46993-111">In This Section</span></span>

  - [<span data-ttu-id="46993-112">Lync Server 2013 中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="46993-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="46993-113">Lync Server 2013 中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="46993-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="46993-114">Lync Server 2013 中的 M:N 中继</span><span class="sxs-lookup"><span data-stu-id="46993-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="46993-115">Lync Server 2013 中的转换规则</span><span class="sxs-lookup"><span data-stu-id="46993-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="46993-116">在 Lync Server 2013 中规划出站语音路由</span><span class="sxs-lookup"><span data-stu-id="46993-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

