---
title: Lync Server 2013：新的虚拟化功能
description: Lync Server 2013：新的虚拟化功能。
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
ms.openlocfilehash: ac15b8592d158d84807ff9e665dd6da50b699059
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579218"
---
# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="a31da-103">Lync Server 2013 中的新的虚拟化功能</span><span class="sxs-lookup"><span data-stu-id="a31da-103">New virtualization features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a31da-104">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="a31da-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="a31da-105">Lync Server 2013 支持在 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 上实现虚拟化。</span><span class="sxs-lookup"><span data-stu-id="a31da-105">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="a31da-106">对 Windows Server 2012 和 Windows Server 2012 R2 的支持包括对单个根 i/o 虚拟化 (SR-IOV) 功能的支持。</span><span class="sxs-lookup"><span data-stu-id="a31da-106">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="a31da-107">借助 SR-IOV，可直接将物理网络适配器的虚拟功能分配到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a31da-107">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="a31da-108">这增加了网络吞吐量并减少的网络延迟，同时还减少了处理网络流量所需的主机 CPU 开销。</span><span class="sxs-lookup"><span data-stu-id="a31da-108">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="a31da-109">要充分利用 SR-IOV，必须使用主机服务器，该服务器具有支持 SR-IOV 的 BIOS，并使用支持 SR-IOV 的网络适配器。</span><span class="sxs-lookup"><span data-stu-id="a31da-109">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

