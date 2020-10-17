---
title: Lync Server 2013：执行 ABC 前端池故障转移
description: Lync Server 2013：执行 ABC 前端池故障转移。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c1aa7a18bc1f1126bcb942a0b3a21283637dcb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557218"
---
# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="39c5b-103">在 Lync Server 2013 中执行 ABC 前端池故障转移</span><span class="sxs-lookup"><span data-stu-id="39c5b-103">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c5b-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="39c5b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="39c5b-105">本节中的两个主题介绍在 Lync Server 2013 中执行 ABC 池故障转移的过程，其中有成对的 Lync Server 前端池 A 和 B，池 A 将不可恢复。</span><span class="sxs-lookup"><span data-stu-id="39c5b-105">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="39c5b-106">使用此过程，将使用新的完全限定域名 (FQDN) 创建新的前端池 C。</span><span class="sxs-lookup"><span data-stu-id="39c5b-106">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="39c5b-107">池 C 是从故障池 A 中的信息构造的。此过程还包括将池 B 和 C 配对在一起。</span><span class="sxs-lookup"><span data-stu-id="39c5b-107">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="39c5b-108">Lync Server 2013 中的 ABC 池故障转移的备份先决条件</span><span class="sxs-lookup"><span data-stu-id="39c5b-108">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="39c5b-109">Lync Server 2013 中的前端池 ABC 故障转移过程</span><span class="sxs-lookup"><span data-stu-id="39c5b-109">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

