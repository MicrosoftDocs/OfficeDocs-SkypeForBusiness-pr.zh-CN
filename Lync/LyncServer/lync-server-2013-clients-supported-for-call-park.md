---
title: Lync Server 2013：支持呼叫寄存的客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74e9231c99754f0916d1ddf94ba36d1dce81fb1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499259"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="9de46-102">Lync Server 2013 中支持呼叫寄存的客户端</span><span class="sxs-lookup"><span data-stu-id="9de46-102">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9de46-103">_**上次修改的主题：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="9de46-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="9de46-104">本节介绍可用于寄存呼叫的客户端和可用于取回寄存呼叫的客户端。</span><span class="sxs-lookup"><span data-stu-id="9de46-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="9de46-105">支持寄存呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="9de46-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="9de46-106">可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9de46-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9de46-p101">只能寄存音频呼叫。不能寄存即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="9de46-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="9de46-109">以下客户端可以使用寄存呼叫的呼叫寄存：</span><span class="sxs-lookup"><span data-stu-id="9de46-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="9de46-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9de46-110">Lync 2013</span></span>

  - <span data-ttu-id="9de46-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="9de46-111">Lync 2010</span></span>

  - <span data-ttu-id="9de46-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="9de46-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="9de46-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9de46-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9de46-114">移动电话无法将呼叫寄存用于寄存呼叫。</span><span class="sxs-lookup"><span data-stu-id="9de46-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="9de46-115">支持取回呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="9de46-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="9de46-p102">将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9de46-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="9de46-118">联盟用户无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9de46-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="9de46-119">以下客户端可以检索寄存在呼叫寄存上的呼叫：</span><span class="sxs-lookup"><span data-stu-id="9de46-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="9de46-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9de46-120">Lync 2013</span></span>

  - <span data-ttu-id="9de46-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="9de46-121">Lync 2010</span></span>

  - <span data-ttu-id="9de46-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="9de46-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="9de46-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9de46-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="9de46-124">IP 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="9de46-124">IP common area phones</span></span>

  - <span data-ttu-id="9de46-125">连接到 Lync Server 2013 基础结构的非 IP 电话，包括公用区域电话和专用分支 exchange (PBX) 电话</span><span class="sxs-lookup"><span data-stu-id="9de46-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

