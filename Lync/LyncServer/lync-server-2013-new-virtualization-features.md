---
title: Lync Server 2013：新的虚拟化功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 687e1c77cec18dc9ad4372fd911db32c537c61c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="b869e-102">Lync Server 2013 中新的虚拟化功能</span><span class="sxs-lookup"><span data-stu-id="b869e-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b869e-103">_**主题上次修改时间：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b869e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b869e-104">Lync Server 2013 支持 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 上的虚拟化。</span><span class="sxs-lookup"><span data-stu-id="b869e-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="b869e-105">Windows Server 2012 和 Windows Server 2012 R2 上的支持包括对单个根 i/o 虚拟化（SR-IOV）功能的支持。</span><span class="sxs-lookup"><span data-stu-id="b869e-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="b869e-106">使用 SR-IOV，物理网络适配器的虚函数直接分配给虚拟机。</span><span class="sxs-lookup"><span data-stu-id="b869e-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="b869e-107">这会增加网络吞吐量并减少网络延迟，同时减少处理网络流量所需的主机 CPU 开销。</span><span class="sxs-lookup"><span data-stu-id="b869e-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="b869e-108">若要充分利用 SR-IOV，你必须使用具有支持 SR-IOV 的 BIOS 的主机服务器，以及使用支持 SR-IOV 的网络适配器。</span><span class="sxs-lookup"><span data-stu-id="b869e-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

