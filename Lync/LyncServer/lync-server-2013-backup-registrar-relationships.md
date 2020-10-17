---
title: Lync Server 2013 备份注册器关系
description: Lync Server 2013 备份注册器关系。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b0bfce6444ae78c2fb792a6d63dba4bf36b1791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552309"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="cbf2c-103">Lync Server 2013 中的备份注册器关系</span><span class="sxs-lookup"><span data-stu-id="cbf2c-103">Backup Registrar relationships in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf2c-104">_**上次修改的主题：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="cbf2c-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="cbf2c-105">除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-105">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="cbf2c-106">在 Lync Server 2013 中，前端池之间的备份注册器关系始终为1:1 和互惠。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-106">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="cbf2c-107">这意味着，如果 P1 是 P2 的备份，则 P2 必须为 P1 的备份，两者均不能成为任何其他前端池的备份。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-107">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="cbf2c-108">这是 Lync Server 2010 的更改，在这种情况下，前端池备份关系可能是多到一。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-108">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="cbf2c-109">尽管两个前端池之间的备份关系必须为1:1 和对称关系，但每个前端池仍可以是任意数量的 Survivable 分支设备的备份注册器，就像在 Lync Server 2010 中一样。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-109">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="cbf2c-110">请注意，Lync Server 2013 不会将灾难恢复支持扩展到驻留在 Survivable 分支设备上的用户。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-110">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="cbf2c-111">如果前端池用作 Survivable 分支设备的备份，则登录到 Survivable 分支设备的用户将进入恢复模式，即使在前端池上驻留的用户故障转移到备份前端池之后也是如此。</span><span class="sxs-lookup"><span data-stu-id="cbf2c-111">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

